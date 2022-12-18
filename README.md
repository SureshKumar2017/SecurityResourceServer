# SecurityResourceServer
Resource Server:
Resource Server controls the client authentication & authorization
Authorization Server generates access token(JWT token) using client ID and Client Secret for the registerd user. 
Step 1 - When first time user login , the user name ,password,client id & client secret will be passed from resource server to the authorisation server to get the access token. 
In authorization server the crediatial will get validated and generate the access token and send as response along with validlity & refresh token
Step 2 - On further api call request the client will send the access token through the header as bearer token for validation from resource server. 
From 2nd request onwards client won't send the username and password to auth server, only send access token.
Step 3 - The validity of the access token is set in access token. If the validity expires the refresh token has to pass to generate the access token to the auth server. 
The auth server will generate a new JWT token based on the refresh token information details.

=============================

http://localhost:9081/hello POST call
Authorisation - Bearer
Token - eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE2NzEzNjA4MTAsInVzZXJfbmFtZSI6InN1cmVzaCIsImp0aSI6ImZiMjk4NWNhLWQ4OGUtNDFmZS1hM2UyLThiMjI1NjMzMzllYiIsImNsaWVudF9pZCI6InRlc3QiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXX0.9DwQcAMPraJOsEJz9TyF9uSs9AqKTlqmIUFHxxGsbtE

Request body:
{
    "name":"test"
}

Response:
Hello {
    "name": "test"
}
