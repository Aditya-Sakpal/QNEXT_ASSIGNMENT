# QNext Assignment
## Introduction 

This repository contains a backend Flask server developed for processing transcripts and extracting details using Gemini-1.5 Flash. The project is part of a candidate selection assignment by QNext AI.

## API Implementation Overview
**Endpoint:** earnings_transcript_summary – This endpoint accepts a request body containing two keys: company_name and transcript_text. A schema has been implemented using the Marshmallow package to validate and structure the input.

**Processing and Response Generation:** Once the input data is validated through the schema, it is passed to a model to generate a structured JSON response with the desired information.

**Security Measures:** Various security layers have been incorporated to prevent the leakage of sensitive information and to filter out any inappropriate or offensive content.

**Logging:** Detailed logs capture the API’s performance and resource usage. Logs are stored with timestamps and track memory consumption, execution time, and other performance metrics on a daily basis

## Workflow 
![image](https://github.com/user-attachments/assets/72a9b6d7-d952-4d42-8829-c7a3b09de366)

## Installation

### Prerequisites
- **Python 3.8+**: Make sure Python is installed on your system. You can download it from [python.org](https://www.python.org/downloads/).
- **Git**: Ensure Git is installed to clone the repository. You can download it from [git-scm.com](https://git-scm.com/).

##### Clone the repository
```bash
git clone https://github.com/GIGA-CODER/SR_Learning_assesment.git
```
##### Setting Up the Virtual Environment 

*Option 1: Using venv (Recommended for simplicity)*

Create a Virtual Environment (macOS/Linux/Windows)
```bash
python3 -m venv venv 
```
Activate the Virtual Environment

macOS/Linux:

```bash
source venv/bin/activate
```

Windows:
```bash
venv\Scripts\activate
```

*Option 2: Using Conda*

If you prefer Conda, follow these steps:

Create a Conda Environment
```bash
conda create --name [env_name] python=[python_version]
```
Activate the Conda Environment
```bash
conda activate [env_name]
```

##### Install Dependencies

Once the environment is activated, install the required dependencies from requirements.txt:
```bash
pip install -r requirements.txt
```

##### Add Constants
Create constants.py file in the root directory and take the reference from constants.py.example file and fill up the values

##### Run the flask server
To start the Flask server, use:
```bash
python app.py 
```






## Usage

After the server is up and running, you can use API clients like **Postman** or **curl** to interact with the endpoints provided for processing transcripts.

### Example Request

#### Using `curl`

```bash
curl -X POST http://127.0.0.1:5000/earnings_transcript_summary \
-H "Content-Type: application/json" \
-d '{
    "company_name": "",
    "transcript_text": ""
}'
```

#### Using Postman
- Open Postman and select POST as the HTTP method.

- In the URL field, enter http://127.0.0.1:5000/earnings_transcript_summary.

- Go to the Body tab, select raw, and choose JSON from the dropdown menu.

- Enter the following JSON in the request body:

```
{
    "company_name": "",
    "transcript_text": ""
}
```
- Click Send to send the request.

Both of these requests will send a POST request to the /earnings_transcript_summary endpoint with a JSON body containing the company name and transcript text.

### Excepted Response 

```
{
"company_name": "COMPANY NAME",
"financial_performance": "SHORT SUMMARY OF FINANCIAL PERFORMANCE
HERE",
"market_dynamics": "SHORT SUMMARY OF MARKET DYNAMICS HERE",
"expansion_plans": "SHORT SUMMARY OF EXPANSION PLANS HERE",
"environmental_risks": "SHORT SUMMARY OF ENVIRONMENTAL RISKS
HERE",
"regulatory_or_policy_changes": "SHORT SUMMARY OF REGULATORY OR
POLICY CHANGES HERE"
}
```
## Deployed version 
https://qnextassignment.vercel.app/


