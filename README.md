​🚀 AWS Lambda Bulk Invoker (Cloud Automation Tool)
​👨‍💻 Developed by Ismail
​Role: Cloud Systems & Automation Engineer
Target: O-1 Visa Extraordinary Ability Portfolio
​📌 Project Overview
​This professional Python tool automates the process of invoking AWS Lambda functions in bulk using data from CSV files. It is designed for cloud-native environments where multiple datasets (collections) need to be processed sequentially with error handling and local logging.
​🛠 Features
​Bulk Processing: Automatically reads short_name, version, and tolerance from a CSV and triggers Lambda events.
​Sequential Execution: Implements a stable invocation flow with a 0.5s delay to prevent API throttling.
​Automatic Logging: Every Lambda response is saved as a JSON file in a timestamped directory for audit trails.
​Robust Error Handling: Detects and reports both network-level and application-level errors (statusCode check).
​Custom Payloads: Dynamically builds POST request bodies compatible with REST API standards.
​📂 Project Structure
​lambda_bulk_invoker.py: Core logic for CSV parsing and AWS SDK (boto3) integration.
​collections.csv: Input file containing the target data.
​responses_YYYYMMDD_HHMMSS/: Output directory where all execution logs are stored.
​🚀 How to Use
​1. Requirements
​Ensure you have the AWS SDK installed:pip install boto3
2. Execution
​Run the tool from the terminal by providing the Lambda function name and your CSV file:python lambda_bulk_invoker.py <your-lambda-function-name> collections.csv
3. CSV Format
​The tool expects a CSV without headers (or skips the first row) in the following format:
| short_name | version | tolerance (optional) |
| :--- | :--- | :--- |
| MERRA2 | 5.12.4 | 10 |
| MODIS | 6.1 | |
