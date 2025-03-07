PagerDuty to ServiceNow Incident Mapper
A Python script to extract PagerDuty incidents with ServiceNow metadata and generate a CSV mapping file.
Description
This script sends a GET request to the incidents endpoint to retrieve incident data, filters for incidents containing ServiceNow metadata, and then generates a CSV file mapping the PagerDuty incidents to their corresponding ServiceNow incidents:

PagerDuty Incident Number
Title
Description
Created At
Updated At
Status
PagerDuty Incident URL
ServiceNow Incident ID
ServiceNow Incident URL

Requirements

Python 3.6+
PagerDuty API Access Token

Installation

1.Clone this repository
Copygitclone https://github.com/shirleyilenechan/External-References.git
2.Install required dependencies:
Copypip install -r requirements.txt

Usage
1.Create a .env file in the same directory where you cloned this repository.
2.Update the .env file with your PagerDuty API key:
CopyPAGERDUTY_REST_API_KEY=your_api_key_here
3.Define  your request parameters in the request_parameters.py file.
4.Run the script from the command line, from the same directory where you cloned this repository:
Copypython3 external_references.py

How the Script Works

The external_references.py script will:

Send a GET request to the incidents endpoint to retrieve incident data
Filter incidents to include only those with ServiceNow references
Generate a CSV file named pagerduty_incidents_mapped_to_servicenow.csv in the same directory where you cloned this repository.

Error Handling
The script will exit with an error message in the following cases:

If the PagerDuty API request fails
If no incidents with ServiceNow metadata are found

Security Notes

1.Never commit your .env file
2.User Token Rest API Keys are restricted in accordance with the user's access and permissions, so the GET request to the incidents endpoint will only retrieve incidents that the user has access to. General Access Rest API Keys do not have such restrictions. 


Resources
1.List incidents endpoint documentation: https://developer.pagerduty.com/api-reference/9d0b4b12e36f9-list-incidents
2.Pagination documentation: https://developer.pagerduty.com/docs/pagination
3.API Access Keys documentation: https://support.pagerduty.com/main/docs/api-access-keys
