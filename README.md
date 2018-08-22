# hello-world
Welcome punny humans!
I will be doing my task here hopefully.
FORMAT: 1A
HOST: https://promocodes.kiwi.com

# Kiwi.com promocodes API

Kiwi.com promocodes API is accessible only via https for authorized users under given set of IP addresses. This API is connected directly to our backend and it is the recommended  way how to operate with promocodes.

# Group Poromocodes

# /promocodes

Resource for retrieving information about promocodes and creating new ones.

## GET

Returns list of all promocodes in our system with some additional information.

**Parameters of every promocode in body response:**
- Code: string, unique alphanumeric code
- BID: integer, booking ID of connected booking, why promocode was created (some problem with previous booking or on which booking it was used), can be null
- Used: boolean, true if promocode was used
- Amount: integer, the amount the promocode can cover, always in EUR
- Email: string, email of connected user account the promocode was created for or used by, can be null

+ Response 200 (json application)
    + Body

            {
              "promocodes":[
                {
                  "code":"AAAAQ",
                  "bid":null,
                  "used":false,
                  "amount":10.0,
                  "email":"some@mail.com"
                },
                {
                  "code":"AAAAR",
                  "bid":123456,
                  "used":true,
                  "amount":10.0,
                  "email": null
                }
              ]
            }

+ Response 401 (text/plain)

        You are not authorized for this operation.

## PUT

ToDo: Write documentation for creating one promocode. A user should provide the API with the same details that are returned for each promocode in the GET method above.
In the response, the API returns created promocode with all its details. New promocodes are not used. Parameters that can be null, might not be passed to the API.

+ Request (json application)
    + Body

            {}

+ Response 200 (json application)
    + Body

            {}
