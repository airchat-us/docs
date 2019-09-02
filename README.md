# Airchat SDK

## Overview

1. Who can help me to add Airchat to my website?
1. [Airchat SDK](https://github.com/airchat-us/docs#sdk)
1. Airchat API (coming soon)

### Who can help me?
If you have questions, you can always [email](mailto:alex@airchat.us) or skype us(gamanuk_alexander)! If you found a bug feel free to [create an issue](https://github.com/airchat-us/docs/). 

### Getting Started
This is a simplified walkthrough to see the platform in action. Register at [airchat.us](https://airchat.us) to learn more.

1. Register on [airchat.us](https://airchat.us/) using your Google account.
2. Add a JavaScript snippet to your website. Copy the snippet here [https://airchat.us/settings/install-pixel](https://airchat.us/settings/install-pixel). ![Airchat Pixel](https://archt.blob.core.windows.net/static/img/docs/airchat-pixel.png)


### Airchat SDK
The Airchat SDK allows you to pass some information about users to Airchat. Add the following JavaScript code before the body tag closing.

```
    <script type='text/javascript' src="https://widget.airchat.us/scripts/sdk.js"></script>
    <script>
        setTimeout(function () { 
            airchatSdk.identify('5938104868471', { //EXTERNAL USER ID
                customFields: {
                    'first-name': 'Alexander' //USER FIRST NAME
                },
                appFields: {
                    subscription: {
                        stripe: {
                            customerId: 'cus_DoI173JzBQyefN' //STRIPE CUSTOMER ID 
                        }
                    }
                }
            }); 
        }, 2000);
    </script>
```

#### 1. Load sdk.js

Add the https://widget.airchat.us/scripts/sdk.js as to the header.
```
 <script type='text/javascript' src="https://widget.airchat.us/scripts/sdk.js"></script>
```

#### 2. Initialize Airchat SDK
Call `airchatSdk.identify` and pass the external user id from your database as the first parameter.

Example: ![airchatSDK.identify](https://archt.blob.core.windows.net/static/img/docs/airchat-sdk-identify-id.png)

#### 3. Add customFields
You can pass any extra information about the uses by adding the `customFields` field. Usually it's used to add users first name, last name, email, current plan, etc.
Example: ![airchatSDK.identify custom fields](https://archt.blob.core.windows.net/static/img/docs/airchat-sdk-identify-custom-fields.png)

#### 4. Add Stripe Customer id 
If you're using Stripe API inside your Airchat bots you're required to pass the `Stripe Customer ID`. To do that you need to add the `appFields` object to the `airchatSdk.identify` call.
```
           appFields: {
                    subscription: {
                        stripe: {
                            customerId: 'cus_DoI173JzBQyefN' //STRIPE CUSTOMER ID 
                        }
                    }
                }
```
Example: ![airchatSDK.identify stripe customer id](https://archt.blob.core.windows.net/static/img/docs/airchat-sdk-identify-stripe-customer-id.png)

See the complete example [here](https://github.com/airchat-us/docs/blob/master/README.md#airchat-sdk-1).
