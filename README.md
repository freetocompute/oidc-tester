# oidc-tester

Simple Test Application for verifiying OIDC is correctly configured

# License

The sample code used was part of go-oidc which is itself Apache License 2.0. SO this repo will use
that license.

## OIDC Provider

I used Keycloak and this guide as a basis:

https://docs.xebialabs.com/v.10.1/release/concept/release-oidc-with-keycloak/#set-up-digitalai-release

Some of the details of the UI are slightly off now but it was good enough.

## cURL test

Set these environment variables used below (or substitue).

PROVIDER_URL
REALM
CLIENT_ID
PASSWORD
CLIENT_SECRET
SCOPE
USERNAME
PASSWORD

curl -L -X POST "${PROVIDER_URL}/auth/realms/${REALM}/protocol/openid-connect/token' \
-H 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode "client_id=$CLIENT_ID" \
--data-urlencode "grant_type=$PASSWORD" \
--data-urlencode "client_secret=$CLIENT_SECRET' \
--data-urlencode "scope=$SCOPE' \
--data-urlencode "username=$USERNAME' \
--data-urlencode "password=$PASSWORD'

## Troubleshooting

I had to include the "openid" scope to get the id_token included in the response.

# Acknowledgements

This code comes from:

https://github.com/coreos/go-oidc/blob/v3/example/idtoken/app.go