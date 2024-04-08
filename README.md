# sms_spam_detector
## The purpose of this challenge is to train a ML model to distinguish between spam and not spam (ham) text messages
- The project folder contains to Jupyter Notebook files: sms_text_classification_solution and gradio_sms_text_classification, both do the same but in two different ways
### The tools/Libraries used where :
- [Pandas](https://pandas.pydata.org/)
- *From scikit-learn:*
  - [train_test_split](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html)
  - [Pipeline](https://scikit-learn.org/stable/modules/compose.html#build-a-pipeline)
  - [TFIDFVectorizer](https://scikit-learn.org/stable/auto_examples/text/plot_hashing_vs_dict_vectorizer.html#tfidfvectorizer)
  - [LinearSVC](https://scikit-learn.org/stable/modules/generated/sklearn.svm.LinearSVC.html#sklearn.svm.LinearSVC)
- *from gradio:*
  -   [Interface](https://www.gradio.app/docs/interface)
- Edx provided csv file

### Process of sms_text_classification_solution
1. Import Libraries
2. Load csv file
3. Review the data ( data types and values )
4. Create dataframes for target data (y) and for non-target data (X)
5. Split the data in train and test datasets
6. Create the Pipeline with:
    - TfidfVecotirzer
    - LinearSVC
7. Train/Fit the Pipeline
8. Review Pipeline Train and Test Accuracy results
9. Test the model with the test 4 "text messages"

### Results
The Accuracy results returned as 
- Train Accuracy : 1.000
- Test Accuracy : 0.989
After Testing it with 4 "text messages" it returned 50/50 Ham/Spam ...


### Process of gradio_sms_text_classification
1. Import Libraries
2. define *sms_classification* function as follows
    1. Receive a DataFrame as parameter
    2. From the received DataFrame create dataframes for target data (y) and for non-target data (X)
    3. Split the data in train and test datasets
    4. Create the Pipeline with:
        - TfidfVecotirzer
        - LinearSVC
    5. Train/Fit the Pipeline
    6. return Pipeline
4. Load csv file into a DataFrame (sms_text_df)
5. Assign to **text_clf** the result of *sms_classification* sending sms_text_df as parameter
6. define *sms_prediction* function as follows
    1. Receive an array of strings as Parameter
    2. Convert the parameter to an array if it is not already one
    3. run **text_clf** with the array as parameter and assign the result to prediction_result
    4. Evaluate the result and return the corresponding string
7. Initialize the gradio interface and launch it
8. Test the model with the test 4 "text messages"

### Results
After Testing it with 4 "text messages" it returned 50/50 Ham/Spam ...
Same results as far as distinguishing. The file using gradio offers a more user friendly presentation as well as the option to try other strings without changing the code
