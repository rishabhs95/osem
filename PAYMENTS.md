# Configure payment gateway of your choice into Open Source Event Manager
All the information that you need to configure payment gateway of your choice into OSEM. If you have any problems with installing don't hesitate to [contact us](https://github.com/openSUSE/osem#contact)

We use Active Merchant to provide you flexibility in using payment gateway of your choice for recieving ticket payments for conferences.

You can use any of the Active Merchant's [supported gateways](https://github.com/activemerchant/active_merchant#supported-payment-gateways).

## Default Configuration
Open Source Event Manager comes configured with *Stripe* payment gateway by default.

You just need to set your live and test secret API keys as `OSEM_GATEWAY_LIVE_SECRET_KEY` and `OSEM_GATEWAY_TEST_SECRET_KEY` into your environment and you can start recieving your payments.

## Configure
There are a couple of environment variables you can set to configure OSEM.

