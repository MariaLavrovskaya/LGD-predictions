# Prediction Loss Given Default using Gradient Boosting Machine

This particular research project explores the potential of using ensembles classifiers such as Gradient Boosting Machines (GBM) to deliver reliable forecast on Loss Given Default (LGD) prior to borrower's default. This project is done in collaboration with Santander UK. 

## Getting started 
This project is based on the random sample of mortgage loans data. We first investigate the data itself, then build a number of GBM regressors and finally provide interpretabilty results based on Shapley values.
This project is built around Catboost, an open-source gradient boosting on decision trees library developed by Yandex. The full set of results can be provided upon request. 

By analysing different configurations, we conclude that GBM greatly enhances the generalisation performance of LGD modelling. The project findings highlight the importance of the preprocessing scheme, the chosen boosting principle and incorporated domain knowledge to the final quality of the model. The best performing GBM configuration shows a generalisation accuracy on the testing set nearly twice as high as that obtained with Ordinary Least Squares regression, which was used as baseline method. This project also demonstrates that Tree SHAP algorithm is a suitable method for interpretability of GBM models as in most cases it provides intuitive explanations.

Symmetric tree growing policy with enforced monotonic constraints is shown to be the best model for our use case as it achieves the shortest distance in evaluation metrics between training and testing sets.

## Requirements 
Python (we use 3.9.7)  
catboost==0.26.1  
pandas==1.3.2  
matplotlib==3.4.3  
matplotlib-inline==0.1.2  
scikit-learn==0.24.2  
sklearn==0.0  
numpy==1.20.0  
seaborn==0.11.2  
shap==0.39.0  
(dependencies for each library are not listed here)

## Structure
1. **LGD_Data_pass.xlsx** - initial data set obtained from Santander UK. The description can be found in here http://www.freddiemac.com/fmac-resources/research/pdf/user_guide.pdf
2. **data.xlsx** - cleaned data set that is directly used for LGD modelling. 
3. **eda.ipynb** - provides exploratory data analysis of the data set under consideration. 
4. **models.ipynb** - lists a number of different congifurations of GBM regressors with various quantization techniques and three different three structures. Grid search is also used. 
5. **json file** - provides the best performing model in json format that can easily be reused.

### Note 
All the models were trained on CPU due to the small data set. However, one can consider using GPU to accelarate the learning process. The default parameters should be then changed accordingly. 




<img width="697" alt="Screenshot 2021-09-24 at 15 42 34" src="https://user-images.githubusercontent.com/51481457/134693861-73ec6533-6046-4971-9bb7-760e7f4d05a4.png">
