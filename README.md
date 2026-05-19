# Forecasting And Detection Of Paroxysmal Atria Fibrillation From Electrocardiograms Using Transparent Convolutional Neural Networks

This GitHub repository is associated with the following thesis: 📄 will be uploaded soon...

## Description of the repository

This GitHub repository presents the **_code_1D_final.ipynb_** file which contains the code used to develop, train, validate, and test various transparent 1D and 2D Convolutional Neural Networks (CNNs) that were used to forecast and detect Paroxysmal Atrial Fibrillation (AF/AFib). Additionaly, the code was used for the following processes:
- Accessing the ECG data and annotation data, respectively, from the ECG waveform data files (H5 format) and their associated annotation file (CSV format) in the IRIDIA-AF database.  
- Pre-processing and generation of 10 and 30 seconds 1D ECG signal windows, as well as 2D spectrograms derived from lead I and lead II, based on the data from the ECG waveform data files (H5 format) and their asscoiated annotation file (CSV format) in the IRIDIA-AF database, which served as input data for the developed 1D and 2D CNN models.
- Application of various Explainable AI (XAI) techniques, such as Grad-CAM, Guided Grad-CAM (low resolution maps), Guided Grad-CAM (high resolution maps), and LRP, to interpret and assess the decision-making process of the various developed 1D and 2D CNN models.

Because GitHub enforces strict file size limits, essential folders such as **_iridia-af-records-v1.0.1_**, **_2D_data_forecasting_**, **_2D_data_detection_** and **_results_** needs to be retrived from other sources. The **_iridia-af-records-v1.0.1_** folder can be downloaded and unzipped following the link provided in the **_Database_** section. The **_2D_data_forecasting_**, **_2D_data_detection_** and **_results_** folders can be downloaded and unzipped from the following link: https://www.kaggle.com/datasets/cafeeee/forecasting-and-detection-of-afafib

After downloading and unzipping these folders, ensure to have the following structure: <br>
<img width="226" height="200" alt="image" src="https://github.com/user-attachments/assets/753de221-4ca4-4290-b33b-aa8e11242ce0"/>


The purpose of the folders are explained below:
- **_iridia-af-records-v1.0.1_**: this folder continas the Holter records of the different involved patients. Each Holter record contians one or more ECG waveform data files (H5 format) and one associated annotations file (CSV format), from which data was utilized in the **_code_1D_final_ipynb_** file to generate the input data for the various developed 1D and 2D CNN models.
- **_2D_data_forecasting_**: this folder contains 10 seconds lead I, 10 seconds lead II, 30 seconds lead I, and 30 seconds lead II spectrograms that were utilized, respectively, as input data for the developed 2D CNN models to forecast AF in the **_code_1D_final.ipynb_** file.
- **_2D_data_detection_**: this folder contains 10 seconds lead I, 10 seconds lead II, 30 seconds lead I, and 30 seconds lead II spectrograms that were utilized, respectively, as input data for the developed 2D CNN models to detect AF in the **_code_1D_final.ipynb_** file.
- **_results_**: this folder contains the trained, validated, and tested 1D and 2D CNN models which can be loaded in the the **_code_1D_final.ipynb_** file to forecast and detect AF. Additionaly, for the 1D models, the **_results_** folder contains the data split that was utilized to train and test various 1D CNN models, which can be loaded in the the **_code_1D_final.ipynb_** file. For each developed 1D and 2D model, its confusion matrix and ROC-AUC score obtained from the testing process is also presented. For some models, whose decision-making process was investigated in detial, also the XAI results are presented, however, everything necessary regarding the XAI results is presented in the thesis, it is not necessary to check the XAI results from the **_results_** folder.

Considering the paths presented below related, respectively, to the **_iridia-af-records-v1.0.1_**, **_2D_data_forecasting_**, **_2D_data_detection_** folders, it is very important to check and ensure that the order of the ---specify--- placeholder is in ascending order, otherwise the code will not work. This should be automatically fixed, but when these folders are zipped, the zipping process may affect the order, so be aware:
```
2D_data_forecasting/..._sec_lead_.../pre_AF/Patient_---specify---
2D_data_detection/..._sec_lead_..._data/Normal/Patient_---specify---
iridia-af-records-v1.0.1/record_---specify---
```
For example, considering **_2D_data_detection_** folder and the following path:
- 2D_data_detection/10_sec_lead_0_data/Normal/Patient_---specify---

Ensure that the patient folders are defined in ascending order:
```
Patient_0, Patient_1, Patient_2, Patient_3 etc.
```
## Database
The IRIDIA-AF database can be accessed through the following link: https://zenodo.org/records/8405941

## Necessary installations

Before running the code in the **_code_1D_final_ipynb_** file, the following pip installations are essential:

```
pip install pandas h5py scipy matplotlib opencv-python scikit-learn tensorflow
```
The pip installations should be run in a Python virtual environment. Follow the instructions in the following short video tutorial to set up a Python virtual environment for Jupyter Notebook: https://www.youtube.com/watch?v=9LIWqWSABHc
