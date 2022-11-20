# transparency-and-interpretability
Using SHAP to generate locally interpretable explanations of classification decisions on a text corpus, using local explanations for feature selection, ultimately improving classification accuracy on a text corpus
## Objectives
Understand how to use SHAP to generate locally interpretable explanations of
classification decisions on a text corpus. <br>
Learn how to use local explanations for feature selection, ultimately improving
classification accuracy on a text corpus. <br>
Understand the relationship between transparency and data protection, by reasoning
about the benefits and the risks of automated decision making to different stakeholders. <br>
### Online job ads
Consider a hypothetical job search website that uses a machine learning system to determine
which job openings to show to which users. The system uses historical employment data, and
also collects interaction data from its own users: which users were shown which job openings,
and which users clicked. The service also receives data from employers, detailing which users
were invited to job interviews, and which were hired. <br>
1. Give three distinct reasons why gender disparities might arise in the
operations of such a system. <br>
2.  Suppose that the job search service decides to increase the number of times
it presents job openings in STEM to women. To do so, the service observes that STEM
job experience (in years) is positively associated with the likelihood that a user clicks
on an advertised STEM job opening: the more years of experience, the more likely a
user is to click. Consider the following intervention: <br>
<i> Pre-process the training dataset, replacing the value of the “job experience” feature
for women with the best (highest) possible value for the feature in the dataset </i><br>
a.  Under what conditions will this intervention increase the number of times job
openings in STEM are shown to women? <br>
b. Under what conditions will this intervention fail to increase the number of times job
openings in STEM are shown to women? <br>
### AI Ethics: Global Perspectives
In this part of the assignment, you will watch a lecture from the AI Ethics: Global
Perspectives course and write a memo (500 words maximum) reflecting on issues raised in
the lecture. <br>
### Generating Explanations with SHAP
For the programming portion of this assignment, we will use a subset of the text corpus from the
20 newsgroups dataset. This is the dataset used in the LIME paper to generate the
Christianity/Atheism classifier, and to illustrate the concepts. However, rather than explaining
predictions of a classifier with LIME, we will use this dataset to explain predictions with SHAP. <br>
1. Use the provided Colab template notebook to import the 20 newsgroups
dataset from sklearn.datasets, importing the same two-class subset as was used in the
LIME paper: Atheism and Christianity. Use the provided code to fetch the data and split it
into training and test sets. Then, fit a TF-IDF vectorizer to the data, and train a
SGDClassifier classifier.
2. Generate a confusion matrix (hint: use sklearn.metrics.confusion_matrix) to
evaluate the accuracy of the classifier. The confusion matrix should contain a count of
correct Christian, correct Atheist, incorrect Christian, and incorrect Atheist predictions
from your SGDClassifier. Use SHAP’s explainer to generate visual explanations for any
5 documents in the test set. The documents you select should include some correctly
classified and some misclassified documents.
3. Use SHAP’s explainer to study mis-classified documents, and the features
(words) that contributed to their misclassification, by taking the following steps: <br>
a. Report the accuracy of the classifier, as well as the number of misclassified
documents. <br>
b. For a document doc_i let us denote by conf_i the difference between the
probabilities of the two predicted classes for that document. Generate a plot that
shows conf_i for all misclassified documents (which, for misclassified
documents, represents the magnitude of the error). Use any chart type you find
appropriate to give a good sense of the distribution of errors. <br>
c. Identify all words that contributed to the misclassification of documents.
(Naturally, some words will be implicated for multiple documents.) For each word
(call it word_j), compute (a) the number of documents it helped misclassify (call
is count_j) and (b) the total weight of that word in all documents it helped
misclassify (weight_j) (sum of absolute values of weight_j for each misclassified
document). The reason to use absolute values is that SHAP assigns a positive or
a negative sign to weight_j depending on the class to which word_j is
contributing. Plot the distribution of count_j and weight_j, and discuss your
observations in the report. <br>
