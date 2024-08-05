Statistical Key Figure Posting API
This API endpoint allows users to post statistical key figures in SAP S4HANA Cloud.

Endpoint
POST /api/statistical-key-figures

Authentication
This API uses Bearer Token authentication. Ensure the token is included in the Authorization header.

Headers
Authorization: Bearer your_bearer_token
Content-Type: application/json
Payload Structure
Below is the structure of the payload with masked sensitive values:

json
Copy code
{
    "StatisticalKeyFigure": "*****",
    "ControllingArea": "****",
    "FiscalYear": "****",
    "PostingDate": "****-**-**",
    "DocumentHeaderText": "*****",
    "LineItems": [
        {
            "StatisticalKeyFigure": "*****",
            "CostCenter": "******",
            "KeyFigureValue": "****",
            "DocumentLineText": "*****"
        },
        {
            "StatisticalKeyFigure": "*****",
            "CostCenter": "******",
            "KeyFigureValue": "****",
            "DocumentLineText": "*****"
        }
    ]
}
Example Payload
json
Copy code
{
    "StatisticalKeyFigure": "SKG001",
    "ControllingArea": "A000",
    "FiscalYear": "2023",
    "PostingDate": "2023-08-17",
    "DocumentHeaderText": "Monthly Posting",
    "LineItems": [
        {
            "StatisticalKeyFigure": "SKG001",
            "CostCenter": "1000201",
            "KeyFigureValue": 500.0,
            "DocumentLineText": "Administrative Costs"
        },
        {
            "StatisticalKeyFigure": "SKG001",
            "CostCenter": "1000202",
            "KeyFigureValue": 300.0,
            "DocumentLineText": "Operational Costs"
        }
    ]
}
Response
Upon successful posting, the API will return a confirmation with the posted data and a status indicating success.

Error Handling
In case of errors, the API will return appropriate HTTP status codes and error messages. The response will include details on the nature of the error and possible actions to resolve it.

Notes
Ensure all required fields are provided and follow the correct data format.
Mask sensitive information as required by your organization's data privacy policies.
