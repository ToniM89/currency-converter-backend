# Currency Converter Backend

## Whats in it

The backend of the currency converter contains of the following components

- data-updated-lambda
- data-provider-lambda
- s3-bucket
- api-gateway

## data-updated-lambda

This lambda will run multiple times a day to get the current rates. This rates will then be stored as json object to an s3-bucket

## s3-bucket

This bucket contains the data with the loaded rates as a json object

## data-provider-lambda and api-gateway

The data-provider-lambda is behind an api gateway and provide the user with the data needed for example when requesting the rate for 1€ in US$ then the,
needed data from the s3-bucket will be provided.

Hint: Since I get only the rates for one base it migth makes sense to send the whole json file (aprox. 74kb) then the client can handle the rest.
