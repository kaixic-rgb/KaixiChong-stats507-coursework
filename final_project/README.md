# Amazon Review Sentiment and Rating

This repo has the code and figures for my final project  
I use Amazon review text to predict

- 1 to 5 star rating  
- three kinds of sentiment: negative neutral positive  

I compare three models

- TF IDF plus logistic regression  
- a small MLP using TF IDF features  
- a BERT model from Hugging Face  
  LiYuan/amazon-review-sentiment-analysis  

Note: fine tuning the BERT model needs time  
On my RTX 3080 Ti one task is about 20 minutes  
On CPU it is much slower  
Running the full notebook will also create about 35 GB of data  
(mainly model and dataset cache files on disk)

## Files

- Kaixi Chong_final_project_code.ipynb   main notebook  
- fig_length_vs_star.png                 review length by star  
- fig_model_comparison_rating5.png       model accuracy for 5 class rating  
- fig_model_comparison_sentiment3.png    model accuracy for 3 class sentiment  
- fig_review_length_distribution.png     histogram of review lengths  
- fig_star_distribution.png              star rating distribution  

All figures in the report come from this notebook

## Data

I use the Hugging Face dataset

- SetFit/amazon_reviews_multi_en  

The notebook uses the datasets library to download it  
You do not need to download anything yourself  

Ratings

- labels 0 to 4 become stars 1 to 5  
- 1 to 2 stars negative  
- 3 stars neutral  
- 4 to 5 stars positive  

## Environment

Main Python packages

- scikit-learn  
- torch  
- transformers  
- datasets  
- numpy  
- pandas  
- matplotlib  

Install example

    pip install scikit-learn torch transformers datasets numpy pandas matplotlib

GPU is helpful for the BERT model  
CPU can run it but will be much slower

## How to run

1. Clone this repo and enter the folder

       git clone https://github.com/<your-username>/<your-repo-name>.git
       cd <your-repo-name>

2. Install the Python packages

3. Open Kaixi Chong_final_project_code.ipynb in Jupyter or JupyterLab  
   Run all cells from top to bottom  

The notebook will

- load and clean the data  
- train the three models  
- evaluate them on the test set  
- save the figures that appear in the report  
- write about 35 GB of cache and model files to disk  
