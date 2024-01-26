## **Flask Application Design**

### **HTML Files**

1. `index.html`:
   - Serves as the home page of the application.
   - Contains necessary elements for user interaction, such as a form to gather the Google Collections URL from the user.
   - Includes a container where the extracted items and the graph will be displayed.

2. `result.html`:
   - Displays the result of the data processing.
   - Comprises the extracted items from the Google Collection URL, along with the graph that visually represents the semantic connections between them.
   - Utilizes JavaScript to generate and manipulate the graph based on the extracted data.

### **Routes**

1. `/`:
   - Home Route:
     - Renders the `index.html` file.
     - Displays the form for user input and the container where the results will be shown.

2. `/extract_items`:
   - Data Extraction Route:
     - Accepts the Google Collections URL from the user via POST request.
     - Scrapes the specified URL using web scraping techniques to extract the items along with their titles and note fields.
     - Utilizes the large language model (LLM) to determine semantic connections between the extracted items.
     - Saves the extracted items and the connections in a suitable data format (e.g., JSON) for further processing.
     - Redirects to the `/result` route.

3. `/result`:
   - Result Display Route:
     - Reads the extracted items and connections from the data file generated in the `/extract_items` route.
     - Renders the `result.html` file.
     - Passes the extracted items and semantic connections to the JavaScript in the `result.html` to generate and display the graph.