# POS Multiple E-Wallet
 Company Hitachi is developing a Payment Integration Platform that allows merchants to
connect Point-of-Sale (POS) systems with multiple e-wallet providers (GoPay, OVO,
Dana, ShopeePay). Merchants will use the API to:  
1. Authenticate securely.
2. Retrieve available e-wallet channels.
3. Create a payment request.
4. Check transaction status.
5. Handle refund requests 
The API uses Bearer Token authentication and returns responses in JSON format. 
**End Point** 
---
Domain: https://hitmeapi.com

Port: 8080

Authentication: Bearer Token

Format: JSON

1. Authentication – Get Access Token

Request

POST : https://hitmeapi.com/auth/token

Headers
```
Content-Type: application/json
```
Request Body
| Field        | Type   | Required | Description         |
| ------------ | ------ | -------- | ------------------- |
| `api_key`    | string | Yes      | API key merchant    |
| `api_secret` | string | Yes      | Secret key merchant |

Example Request
```
json
{
  "api_key": "your_api_key",
  "api_secret": "your_api_secret"
}
```
Response – Success
```
json
{
"access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI...",
"expires_in": 3600
} 
```
Respone - Failed
```
json
{
"errorCode": "200",
"errorType": "invalid_credentials",
"errorMessage": "API key or secret is incorrect."
}
```
Non-Technical Description (Merchant View)

Endpoint ini digunakan merchant untuk masuk ke sistem. Hasilnya adalah kunci akses (token) yang dipakai setiap kali memanggil API lain.



