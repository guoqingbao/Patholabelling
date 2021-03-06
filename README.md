# Patholabelling
An open-source website for marking histopathology images. It is a part of our PathoFusion framework, a researech project for analysis in histopathology: https://github.com/guoqingbao/Pathofusion 

#### Upgrade for the labelling website: support overlay of IHC/fusion heatmaps and labelling for extremely large pathology images (over 60,000x60,000; cutting), please refer the new demo videos for the website: https://cloudstor.aarnet.edu.au/plus/s/EdC2kydCJsQuhm6 https://cloudstor.aarnet.edu.au/plus/s/IMwKJmdPHX4Uzsj

#### Important for using the labelling website: Edge legacy is required (other web browers, including the new Edge have problem when dealing with large images)
To use Edge legacy: 1) rename the new Edge folder to any other names you want; 2) download "EdgeLaunch.exe" to launch legacy Edge (or Win+run: shell:Appsfolder\Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge)

![](/others/login.png)
![](/others/markings.jpg)
![](/others/overlays.jpg)


# Citation
Bao G, Wang X, Xu R, Loh C, Adeyinka OD, Pieris DA, Cherepanoff S, Gracie G, Lee M, McDonald KL, Nowak AK, Banati R, Buckland ME, Graeber MB. PathoFusion: An Open-Source AI Framework for Recognition of Pathomorphological Features and Mapping of Immunohistochemical Data. Cancers. 2021; 13(4):617. https://doi.org/10.3390/cancers13040617

# Video demonstration:

Image Labelling: https://cloudstor.aarnet.edu.au/plus/s/JSASsezqvrB9sgA

# Who may use?
1) You are a researcher who is dealing with pathology images and wants to build your own deep learning model to analysis those images or struggling to find an effective method for pathology image analysis.
2) You are a doctor or clinical staff who specialized in pathology and want to pass your knowledge to machines.
3) You are seeking a technique that may facilitate your company to build an AI-powered product which can automate the disease diagnosis based on analysing pathology images.

# How it works?
The labelling website provided here is part of a framework solution for pathology image analysis. It works as following:
1) You obtained whole-slide pathology images (H&E, IHC images)
2) You define which types of diagnostic features important to your research/product for disease diagnosis, for example, microvascular proliferation is a key diagnostic feature for glioma multiforme (GBM), which can be observed from whole-slide images of GBM patients.
3) You deploy this labelling website, upload the pathology images to your website (you may compress them first, for example, jpg), add records in your website backend system, and define the types as well as corresponding marking colours.
4) You invite consultant pathologists to mark the region of interests (ROI) using the website for different types of features with different colours.
5) You visit https://github.com/guoqingbao/Pathofusion and download the pathology analysis project and train a model using the given code.
6) You validate and improve the model, and finally deploy the trained model to your customers. 

You may repeat 1) - 6) for many times until you find a optimal model you think that can be used in clinical environments.

# How to use?
1) Install Python 3.6+ (https://www.python.org/)
2) Install django through pip (https://pypi.org/project/Django/)
3) Install mysql 5.6+ and mysqlclient (https://docs.djangoproject.com/en/2.2/ref/databases/#mysql-notes)
4) You may setup your mysql server and configure the host and password of the mysql database in WebLabelling/settings.py; you may also use the default database name "WebLabelling" and user as "root";
5) Perform database migration (set up your database with different tables) by running command "python manage.py migrate";
6) After migration succeed, you can run the website with command "python manage.py run server xx.xx.xx.xx:port" (replace xx.xx.xx.xx with your server IP and port as your prefered server port)
7) Access your labelling website through xx.xx.xx.xx:port. 
8) There is no records in your database by default, you can access xx.xx.xx.xx:port/admin to add records.


# Need to know

1) We provided a sample case (case 11 with H&E and IHC images) under labelling/static/labelling/
2) The images need to compressed as jpg format for marking.
3) Recommend image size is: under 200 MB
#### 4) Must use Microsoft Edge for labelling, you may experiment stuck if you using other web browsers.
5) Make sure you have enough memory for labelling (8GB +)
6) Process your labelling using PathoFusion: https://github.com/guoqingbao/Pathofusion
7) Enable local cache by first check "LocalServer" in the admin portal (see below). To use local cache, you need to install XAMPP (https://www.apachefriends.org/index.html); start the apache server; navigate to "htdocs" folder by clicking "Explorer" in XAMPP control panel; create a "labelling" folder; copy images and corresponding thumb images into that folder. 

# How to add records?

1) Goto admin portal of your website and add a user with ImageGroup permission (permitted to marking)

![](/others/user_and_permission.png)

2) Click the ImageList and add a record as follow:

![](/others/add_records.png)

Please make sure the file (you added in the list) is under your website static folder (labelling/static/labelling/)

3) Define categories of your study and assign to the expert user (who mark the images) 

![](/others/categories_marking_config.png)

Please make sure the user have ImageGroup permission.

4) Go to you website main page and enjoy your marking

