# google-sheets-gpt

### Overview

This repo is part of a tutorial on how to use OpenAI Assistants API v2 in Google Sheets. 

Watch the full tutorial here: https://youtu.be/QJDj0UUcoDM?si=j3UNtVISXFZZnHGn

### Additional Code Needed

Install this code into the Google Apps Script:

```
function GPT(inputString, cellRange) {
  const url = 'URL'; // Replace with your API endpoint

  // cellRange is already an array of values
  const rangeValues = cellRange;
  
  // Flatten the range values into a single array if needed
  const flattenedValues = rangeValues.flat();

  const payload = {
    'yourDataField1': inputString, // Adjust according to your API requirements
    'yourDataField2': flattenedValues // Adjust according to your API requirements
  };

  const options = {
    'method': 'post',
    'contentType': 'application/json',
    'payload': JSON.stringify(payload)
  };

  try {
    const response = UrlFetchApp.fetch(url, options);
    const json = response.getContentText();
    const data = JSON.parse(json);

    // Assuming the API response has a field named 'result'
    return data.result;
  } catch (error) {
    return 'Error: ' + error.message;
  }
}
```

### Support Me

If this tutorial/ code saved you time, consider buying me a coffee:

→ [Buy Me a Coffee](https://ko-fi.com/bartybart)
