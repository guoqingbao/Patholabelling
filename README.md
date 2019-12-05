# Patholabelling
An open-source website for marking histopathology images. It is a part of our research project: https://github.com/guoqingbao/Pathofusion 

This repository is made public for our research paper:

![](/others/paper-title.png) 

## Please cite our work if you found it is useful for your research or clinical practice.

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
