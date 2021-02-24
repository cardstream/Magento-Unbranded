# README

# Contents

- Introduction
- Prerequisites
- Rebranding
- Installing and configuring the module
- License

# Introduction

This Magento module provides an easy method to integrate with the payment gateway.
 - Supports versions: **2.3**

# Prerequisites

- The module requires the following prerequisites to be met in order to function correctly:

> Please note that we can only offer support for the module itself. While every effort has been made to ensure the payment module is complete and bug free, we cannot guarantee normal functionality if unsupported changes are made.

# Rebranding

In order to successfully rebrand this module, please complete the following updates:

In `httpdocs/app/code/P3/PaymentGateway/Model/Gateway.php` change the following to match what you've been provided:

```
	const DIRECT_URL = 'https://gateway.example.com/direct/';
	const HOSTED_URL = 'https://gateway.example.com/hosted/';
```

and

```
	/**
		* Gateway Hosted API Endpoint
		*/
	const API_ENDPOINT_HOSTED = 'https://gateway.example.com/hosted/';

	/**
		* Gateway Hosted API Endpoint
		*/
	const API_ENDPOINT_HOSTED_MODAL = 'https://gateway.example.com/hosted/modal/';

	/**
		* Gateway Direct API Endpoint
		*/
	const API_ENDPOINT_DIRECT = 'https://gateway.example.com/direct/';
```

When downloading as a zip file, you can right-click and rename to remove the `Unbranded` text from the filename.

# Installing and configuring the module

1. If you are upgrading this module, please make sure to disable the module first with `bin/magento module:disable P3_PaymentGateway`. Afterwards, make sure to delete the `app/code/Pixel` or `app/code/P3` directories that may interfere with the new version. Make sure to delete the `P3_PaymentGateway` row from the `setup_module` table in the database so that any database tables required can be created
2. Copy the contents of httpdocs to your Magento root directory. If you are asked if you want to replace any existing files, click 'Yes'
3. Enable the new module using the command `bin/magento module:enable P3_PaymentGateway`
4. Upgrade and re-compile Magento so that the system will install the module and create all necessary arrangements for the module. This command can be particulary helpful... ```
bin/magento setup:upgrade && bin/magento setup:db-schema:upgrade && bin/magento setup:di:compile && chmod 775 -R ./var```
5. Navigate to Stores -> Configuration -> Payment methods
6. Enter your MerchantID / Secretkey and update the customer/country code
7. Select what type of integration you would like to use
8. Set what status you would like to update an order to once paid
9. Set the Enabled option to true
10. Click 'Save Changes'

License
----
MIT
