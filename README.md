# Question-Answering
A model that will help the purchasing department extract
the required piece of text from the document in order to create an application form. Exactly which piece of text needs to be extracted depends on the questionnaire item corresponding to the document.

Some observations lack a fragment of text to extract


# Data

### train.json 
The training data in json format has the following fields:
- `id`: int - document ID
-  `text`: str - document text, where a fragment corresponding to the questionnaire item from the `label` field may be present
- `label`: str - the title of the questionnaire item. It can take one of two values: `contract performance assurance` or `guarantee obligations assurance`
- `extracted_part`: dict with the following format:
    ```
    {
        'text': [fragment of text from the `text` field corresponding to the questionnaire item], 
        'answer_start': [index of the starting character of the text fragment in the document text],
        'answer_end': [index of the ending character of the text fragment in the document text]
    }
   ```
