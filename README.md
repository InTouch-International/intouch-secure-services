# InTouch Secure Services
InTouch Secure Services is a collection of API endpoints encapsulated in a Postman collection, designed to interact with various individual data enrichment and identity verification services.

## Table of Contents
- [Authorisation](#authorisation)
- [API Endpoints](#api-endpoints)
- [Setup](#setup)
- [Usage](#usage)
- [Environment Configuration](#environment-configuration)
- [Testing](#testing)

## Authorisation
Each call within the InTouch Secure Services requires authorisation using a bearer token. The authorisation is achieved by making a call to the `Get Authorisation Token` endpoint with the client ID and secret, which in turn returns a unique bearer token that is saved at the Environment level for subsequent requests.

## API Endpoints
### Pre-Run File Upload
#### Upload Single File
Upload an image file to retrieve a reusable path to the file. Use the new path in `Identity Document Capture and Extract`, `Compare Images (Facial Match)`, `Selfie Liveness Verification`.
#### Upload Files
Upload image files to retrieve reusable paths to the file. Use the new paths in `Identity Document Capture and Extract`, `Compare Images (Facial Match)`, `Selfie Liveness Verification`.

### Secure Data Services
- South African Department of Home Affairs Verification + Identity Photo
- Identity Verification via South African Credit Bureaus
- Best Address -  provides current highest scoring addresses
- Contact-ability (Provides current highest scoring Cell phone and Telephone Numbers)
- eKYC Individual – submit identity and existing Address for Verification
- South African Bank Account Verification
- Combined AML Check (Sanctions Screening/PEPS/Crimelists/Watchlists/Adverse Media Verification)
- Company KYC (CIPC Company Check and Director Information)
- Eagle Eye (Pre-Assessment Credit Check Enquiry)

### Secure Biometric and Identity Document Services
- Identity Document Capture and Extract
- Compare Images (Facial Match)
- Selfie Liveness Verification

## Setup
1. Clone the repository to your local machine.
2. Import the Postman collection into your Postman application.
3. Setup your environment variables for `{{base_url}}`, `{{auth_url}}`, `{{client_id}}`, and `{{client_secret}}`.

## Usage
1. Make a POST request to the `Get Authorisation Token` endpoint to retrieve the bearer token.
2. Use the bearer token to authorise the other endpoints within the collection.

## Environment Configuration
The repository includes an environment configuration file named `isl-prod.postman_environment.json`. This file contains predefined environment variables to facilitate testing and development in different stages. Here's how you can use it:
### Importing Environment Configuration
1. Download the `isl-prod.postman_environment.json` file from the repository.
2. Open Postman, click on the gear icon in the top right corner to manage environments.
3. Click the Import button and select the `isl-prod.postman_environment.json` file to import the environment configuration.

### Utilising Environment Variables
The `isl-prod.postman_environment.json` file defines the following environment variables:
- `base_url`: The base URL for the API endpoints.
- `auth_url`: The URL for authorisation requests.
- `token`: The bearer token for authorisation. This will be populated after making a successful authorisation request.
- `client_id`: Your client ID for the authorisation request.
- `client_secret`: Your client secret for the authorisation request.

These variables allow for easier configuration and usage of the Postman collection. Make sure to populate the `client_id` and `client_secret` variables with your credentials before making authorisation requests.

### Example Usage
Here's an example of how you'd use an environment variable in a request:
- URL: `{{base_url}}?id=2ca14077-9213-4043-a4dc-315d95e6b09b`

The `{{base_url}}` placeholder will be replaced with the actual value defined in the `isl-prod.postman_environment.json` file, making the request URL: `https://api.intouch.io/library/api/v3?id=2ca14077-9213-4043-a4dc-315d95e6b09b`.

## Testing
Use the Postman's built-in runner to execute the collection and observe the responses.