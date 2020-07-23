# BERT_MachineLearning
BERT vectors for text classification
PROCEDURES FOLLOWED
1. Cloned the BERT repository from the maintainers into a local directory on my computer and referred it as BERT_BASE_DIR by running the bash command,
$ git clone https://github.com/google-research/bert.git
export BERT_BASE_DIR=/mnt/c/Users/bert
2. Downloaded a pre-trained BERT-Base, Uncased model and uncompressed it into a location and referred it as BERT_DATA_DIR
export BERT_DATA_DIR=/mnt/c/uncased_L-12_H-768_A-12
3. Took the datafiles(lang_id_eval.csv, lang_id_test.csv, lang_id_train.csv) and re-formatted then by running the python file DataCleanup.ipynb
4. The python code generated 3 .txt files(eval.txt, test.txt, train.txt) which are placed inside the folder bert_input_data; each input file contains all the texts from their corresponding .csv file on a single line, with no other information
5. Updated and ran the run_bert_fv.sh script based on my system requirements and generated the feature vectors inside the folder bert_output_data as .jsonlines files (eval.jsonlines, test.jsonlines, train.jsonlines) representing each of the document
6. Tensorflow 1.14.0 was used in python environment 3.6.9 ton run upon the BERT repository
7. Trained a text categorization ie., logistic regression model using the features derived from BERT in order to predict the native_language attribute of the formatted data
8. Used the trained model to make predictions on the test data (lang_id_test.csv), produced appropriate evaluation metrics for each class and identified the misclassification rate by running ModelTrainingwithBERT.ipynb
