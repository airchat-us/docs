# Airchat SDK

## Overview

1. Who can help me to integration Airchat with my website?
1. [Airchat SDK](https://github.com/airchat-us/docs#sdk)
1. Airchat API (coming soon)

### Who can help me?
If you have questions, you can always [email](mailto:alex@airchat.us) or skype us(gamanuk_alexander)! If you found a bug feel free to [create an issue](https://github.com/airchat-us/docs/). 

## Getting Started
This is a simplified walkthrough to see the platform in action. Register at [airchat.us](https://airchat.us) to learn more.

1. Register on [airchat.us](https://airchat.us/) using your Google account.
2. Add a JavaScript snippet to [your website. Copy the snippet here [https://airchat.us/settings/install-pixel](https://airchat.us/settings/install-pixel).
3. Add the following JavaScript code before the body tag closing:

```
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

