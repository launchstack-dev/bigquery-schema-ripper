# 📘 BigQuery Schema Ripper - Enhanced Version

## 🚀 Overview

This script extracts schema metadata from all datasets or a specified dataset in a Google BigQuery project, then exports it in either CSV or JSON format. Users can choose to download the file directly or save it to Google Drive.

**Note:** This script is **read-only** for enhanced security — it does not modify or delete any data in your project.

---

## 🔧 Features

- ✅ **Authentication** with Google Cloud via Colab
- ✅ **Optional dataset filtering** (scan one dataset or all datasets)
- ✅ **Choose export format**: CSV or JSON
- ✅ **Export destination options**:
  - Save to **Google Drive** (if available)
  - **Download** directly to local machine
- ✅ Prints schema in a readable format to console

---

## 💠 Setup & Authentication

```python
from google.colab import auth
auth.authenticate_user()
```

---

## 📦 Required Libraries

- `google.cloud.bigquery`
- `google.auth`
- `pandas`
- `json`
- `os`
- `google.colab` (for Drive and file download support)

Install any missing libraries using pip:

```python
!pip install --upgrade google-cloud-bigquery
```

---

## 🧠 Script Behavior

1. Prompts for **Dataset ID** (you can leave it blank to scan all datasets)
2. Prompts for **Export Format**: either `csv` or `json`
3. Scans the project for datasets and their table schemas
4. Outputs schema data to a file: `bigquery_schema.csv` or `bigquery_schema.json`
5. Prompts for export **destination**:
   - Type `yes` to mount Google Drive and save the file there
   - Type `no` to immediately trigger a download to your local machine

---

## 📄 Steps to Run

1. Open the script in Google Colab.
2. **Update the **``** placeholder** in the script with your actual GCP project ID:
   ```python
   PROJECT_ID = 'INSERT_BIGQUERY_PROJECT_ID_HERE'
   ```
3. Run all cells (step-by-step or Runtime > Run All).
4. When prompted:
   - Enter a dataset ID (or press Enter for all)
   - Enter export format (`csv` or `json`)
   - Choose whether to export to Drive or download directly
5. The script prints progress and generates a downloadable/exported file.

---

## 📄 Export Options

- **Google Drive** (mounted automatically using `drive.mount()`)
- **Direct Download** using `files.download()`

---

## 📁 Example Schema Output (CSV)

| project\_id | dataset\_id | table\_id | field\_name | field\_type | field\_mode |
| ----------- | ----------- | --------- | ----------- | ----------- | ----------- |
| my-project  | sales\_data | orders    | order\_id   | STRING      | REQUIRED    |

---

## 🔄 Future Improvements (Optional)

- Support for nested RECORD flattening
- Add field descriptions and labels
- Include table metadata (e.g. description, row counts)
- Optional export to Google Cloud Storage (GCS)

---

## ✅ Usage Notes

- Run in **Google Colab** with proper project permissions.
- Make sure the Google Cloud project is accessible to your authenticated account.
- The script uses **read-only** access for safety.

---

## 📬 Contact

For suggestions or issues, reach out to the script author.

---

Happy ripping schemas! 🎉

