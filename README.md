### Instructions for Matching Old URLs with New URLs Based on Similarity

Follow these steps to run the URL redirect matching script using Google Colab:

1. **Library:**
   - The script uses `rapidfuzz` for calculating similarity. You need to install this library if it’s not already installed. This will be done automatically with the command:
     ```python
     !pip install rapidfuzz
     ```
   This command is already included in the script, so you just need to run it.

2. **Upload Your Files:**
   - Prepare two Excel files:
     1. `Old.xlsx`: Contains the old URLs and their corresponding H1 tags.
     2. `New.xlsx`: Contains the new URLs and their corresponding H1 tags.
   
   Both files should have two columns: `URL` and `H1`.

   **Steps to upload the files in Colab:**
   - Click the folder icon on the left sidebar of Google Colab.
   - Click the upload icon (a paper with an arrow) and select the Excel files from your computer.

3. **Data Loaded:**
   - The script reads both Excel files into `pandas` dataframes:
     - `Old.xlsx` contains old URLs and H1 tags.
     - `New.xlsx` contains new URLs and H1 tags.
   The script processes these files automatically when you run it.

4. **How Matching Works:**
   - The script compares the "slugs" (the last part of the URLs after the last "/") and the H1 tags between the old and new URLs.
   - It uses the `rapidfuzz` library to calculate how similar the old and new URLs and H1 tags are.
   - The similarity score combines both the URL slug and H1 comparison (50% each) to find the best match for each old URL.

5. **Save and View the Results:**
   - After matching the old URLs with the best possible new URLs, the script saves the results to an Excel file: `output.xlsx`.
   - This file will include:
     - `Old_URL`: The original URL.
     - `Best_Match_New_URL`: The best-matching new URL.
     - `Similarity_Score`: A score that indicates how closely the old and new URLs/H1 tags match.
   
   **To download the result:**
   - After running the script, go to the folder icon on the left sidebar.
   - Right-click on `output.xlsx` and select "Download" to save it to your local computer.

6. **Viewing the Results in Colab:**
   - The script also shows the first few rows of the results directly in the Colab notebook, so you can check the output immediately after running the script.
