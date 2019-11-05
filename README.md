## About
This repository represents a sample merchant server for a merchant integrating with `BraintreePayPalValidator`. This repository uses sample PayPal merchant staging credentials to create PayPal orderIDs and universal access tokens, and to capture orders.

**Note:** The `BraintreePayPalValidator` module is still in development and not meant for public consumption.

## Build and run locally
To build and run locally, use the command: `./mvnw spring-boot:run -Dspring-boot.run.profiles=local`. Running this command will install Maven and all necessary dependencies.

If everything worked, you should be able to hit `http://localhost:5000/uat?countryCode=US`.

## Switching Merchant Account/ Authentication

To change the merchant account used on this server, update the credentials in `application-local.properties`.

After making this change, execute both the build and run steps in the *Build and run locally* section above.

## Troubleshooting

### PayPal v2/orders Request Limitations
The PP merchant account we are using to generate an `orderID` has a high account balance which results in limitations on our ability to use this endpoint. Follow these steps to temporarily lift restrictions on the current merchant account.

1. Log into admin.msmaster.qa.paypal.com with the username `concordia_admin` and password `1111111`.
2. Search on the email `rtimoschuk-us-bus-onb-ppcp-approve-seller15@paypal.com`. It will take a while.
3. On the red banner where it says "Limited - High", click "View Limitations" and wait a bit.
4. Find and click the "Edit Limitations" button.
5. In the banner that says "Current Limitations", click the link in the white text that says "Remove Limitations".
6. Check all of the checkboxes. You must enter a memo.
