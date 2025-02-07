In this report I have mentioned the steps taken for Named Entity Recognition (NER) manually
and using Spacy library and how I assessed the models below.
Step 1: Loading Data
➢ First, I have installed and downloaded spacy and the en_core_web_lg model. Then
loaded a JSON file named (NER_Tweets_300.json) containing manually labeled NER
data which I have generated using the NER tool. Later also loaded a CSV file with
tweets for analysis.
Step 2: Extracting Named Entities with spacy
➢ In this step applied the spacy model to extract named entities from the tweet dataset.
Then filtered entities to include only important 7 categories such as PERSON, ORG,
NORP, GPE, LOC, DATE, and MONEY. Stored the results in a structured format which
is given by spacy.
Step 3: Converting Entity Format
➢ As we can see from the cell outputs that the manually labelled dataset used a different
format, storing entity positions (start, end, and label) whereas spacy stored entity string
value and label. So wrote a function “retrieve_entity_positions” to retrieve the position
and “format_conversion_from_spacy_to_manual” to convert the spacy output into this
format for comparison.
Step 4: Accuracy Assessment
➢ Finally in this step compared spacy entities with manual annotations. Calculated True
Positives (TP) which are presented in both manual and spacy sets, False Positives (FP)
which are only present in spacy set, and False Negatives (FN) which are only present
in manual set for each entity type. Using these values, computed Precision, Recall, and
F1-score for each category. Also stored all false positives and false negatives each in
one set.
Assessment of spacy's Accuracy
➢ spacy performed well on some entity types like GPE (F1 = 0.69) and NORP (F1 = 0.72).
➢ Performance was average for PERSON (F1 = 0.43) and ORG (F1 = 0.29).
➢ It struggled with LOC (F1 = 0.21) and MONEY (F1 = 0.13), showing poor detection.
The accuracy differences could be due to training data limitations or complexity in recognizing
certain entities. Improvements could be made by fine-tuning the model with more labelled
examples, especially for weak categories.
