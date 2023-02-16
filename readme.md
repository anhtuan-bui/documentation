# Paxform Business API documentation

## Introduction

**Uri** of the API is: https://{account_username}.dev.paxform.net/api/ - change {account_username} to your organisation account username.
For example: https://example.dev.paxform.net/api/document

Endpoint URL = {URI}/{function_name}

All examples are in the following PostMan collection: [Postman Collection]("https://elements.getpostman.com/redirect?entityId=24471378-f56d173b-dc6d-4b18-b804-6ab28bd9f931&entityType=collection")

## Signature

* SIGNED endpoints require an additional parameter, signature, to be sent in the request body.
* Endpoints use **HMAC SHA256** signatures. The HMAC SHA256 signature is a keyed HMAC SHA256 operation. Use your secretKey as the key and totalParams as the value for the HMAC operation.
* The signature is **not case sensitive**.
* totalParams is defined as the query string concatenated with the request body.

### How to get the signature

Use hash tool such as [HMAC-SHA256 Online Generator Tool]("https://www.devglan.com/online-tools/hmac-sha256-online") to generate the signature using env=test and your secret key. 

Enter the following field to the tool. Currently, **env** should be **test**. It allow the api to decrypt the return value.

| Field                      | Value               |
| -------------------------- | ------------------- |
| Plain Text to Compute Hash | {env}               |
| Secret Key                 | Your Api Secret Key |

## Function names

### Form
<!-- 
1. POST form - Create a form

To create a form from the API use: {URI}/form
For example: https://example.dev.paxform.net/api/document/form

**headers**: 
| Key     | Value            |
| ------- | ---------------- |
| Accept  | application/json |
| api-key | Your Api Key     |

**params:**
| Key       | Value                                                          |
| --------- | -------------------------------------------------------------- |
| env       | test                                                           |
| signature | The signature hash generated as mentioned in signature section |

**body**

```
{
	"id": "",
	"form_name": "Testing ",
	"qr_code": "/public/assets/images/qrcode.png",
	"instructions": "",
	"form_data": [
		 {
			  "section_id": 0,
			  "section_title": "",
			  "section_type": "",
			  "section_description": "",
			  "section_addon_count": 5,
			  "section_hide_description": true,
			  "section_disable_for_users": true,
			  "section_instructions": "",
			  "section_groups": [
					{
						 "type": "group",
						 "id": "Group 1",
						 "name": "Group Name 1",
						 "group_title": " Group Title 1",
						 "group_description": "",
						 "group_instructions": "",
						 "is_title": true,
						 "is_description": true,
						 "is_instructions": true,
						 "group_fields": [
							  {
									"id": 2,
									"tool_id": "6071393F0842E",
									"key": "TextInput",
									"name": "First name",
									"required": false,
									"use_as_title": false,
									"searchbar": false,
									"show_count": false,
									"max_file_allow": 0,
									"icon": "fas fa-font",
									"label": "First name",
									"content": "",
									"static": false,
									"options": "",
									"href": "",
									"blod": false,
									"italic": false,
									"inline": true,
									"step": "",
									"default_value": "",
									"min_value": "",
									"max_value": "",
									"min_label": "",
									"max_label": "",
									"src": "",
									"status": 1,
									"field_id": "PRF_1001_01_C",
									"dependent_id": "",
									"dataset_id": "",
									"dependent": "",
									"prefix": "PRF",
									"option_type": "",
									"alternative_label": [
										 "Given Name",
										 " Forname"
									],
									"description": "Your first name",
									"note": "The first name of the user",
									"field_size": "50",
									"created_at": "2022-12-22T11:47:24.000000Z",
									"example": "Joseph",
									"placeholder": "",
									"field_identifier": "",
									"chosen": false,
									"selected": false,
									"identity": "Primary"
							  },
							  {
									"id": 4,
									"tool_id": "6071393F09BF0",
									"key": "TextInput",
									"name": "Last name",
									"required": false,
									"use_as_title": false,
									"searchbar": false,
									"show_count": false,
									"max_file_allow": 0,
									"icon": "fas fa-font",
									"label": "Last name",
									"content": "",
									"static": false,
									"options": "",
									"href": "",
									"blod": false,
									"italic": false,
									"inline": true,
									"step": "",
									"default_value": "",
									"min_value": "",
									"max_value": "",
									"min_label": "",
									"max_label": "",
									"src": "",
									"status": 1,
									"field_id": "PRF_1001_03_C",
									"dependent_id": "",
									"dataset_id": "",
									"dependent": "",
									"prefix": "PRF",
									"option_type": "",
									"alternative_label": [
										 "Family name",
										 " Surname",
										 " Byname"
									],
									"description": "Your last name",
									"note": "User specifies the last name while account creation.",
									"field_size": "0",
									"created_at": "2022-12-22T11:47:24.000000Z",
									"example": "Makur",
									"placeholder": "",
									"field_identifier": "",
									"chosen": false,
									"selected": false,
									"identity": "Primary"
							  },
							  {
									"id": 9,
									"tool_id": "6071393F0D1C1",
									"key": "PhoneNumberInput",
									"name": "Mobile number",
									"required": false,
									"use_as_title": false,
									"searchbar": false,
									"show_count": false,
									"max_file_allow": 0,
									"icon": "fas fa-font",
									"label": "Mobile number",
									"content": "",
									"static": false,
									"options": "",
									"href": "",
									"blod": false,
									"italic": false,
									"inline": true,
									"step": "",
									"default_value": "",
									"min_value": "",
									"max_value": "",
									"min_label": "",
									"max_label": "",
									"src": "",
									"status": 1,
									"field_id": "PRF_1006_01_C",
									"dependent_id": "",
									"dataset_id": "",
									"dependent": "",
									"prefix": "PRF",
									"option_type": "",
									"alternative_label": [
										 "Mobile phone number",
										 " Cell phone number"
									],
									"description": "Your phone number",
									"note": "Set a default flag",
									"field_size": "25",
									"created_at": "2022-12-22T11:47:25.000000Z",
									"example": "0421 456 585",
									"placeholder": "",
									"field_identifier": "",
									"chosen": false,
									"selected": false,
									"identity": "Primary"
							  }
						 ],
						 "chosen": false,
						 "selected": false
					}
			  ]
		 }
	],
	"description": "<p>Description</p>",
	"form_title": "Testing ",
	"form_type": 1,
	"status": 0,
	"form_instructions": "<p>Description</p>",
	"identity": [
		 {
			  "id": 1,
			  "description": "",
			  "identity_instructions": "",
			  "label": "Primary",
			  "placeholdername": "Primary",
			  "value": "Primary",
			  "is_lable": true,
			  "is_value": true,
			  "is_instructions": true,
			  "is_description": true,
			  "signatory_identity": true,
			  "chosen": false,
			  "selected": false
		 }
	],
	"form_origin_id_version": "1.0.0",
	"form_organisation_id": "4435648379483O36",
	"form_origin_id_date_created": "2023-01-30T06:01:09.841Z",
	"form_internal_note": "Please keep this short (max 255 characters)",
	"form_short_description": "Please keep this short (max 255 characters)",
	"privacy_policy_link": "https://https://www.google.com",
	"terms_condition_link": "https://https://www.google.com",
	"signature": "will be in this sequence "form_title:form_type"
}
``` -->

1. GET get-form - Get a list of all forms in the account

To get a list of forms from the API use: {URI}/get-form
Example uri: https://example.dev.paxform.net/api/document/get-form

**headers**: 
| Key     | Value            |
| ------- | ---------------- |
| Accept  | application/json |
| api-key | Your Api Key     |

**params:**
| Key       | Value                                                          |
| --------- | -------------------------------------------------------------- |
| env       | test                                                           |
| signature | The signature hash generated as mentioned in signature section |

Example request: https://example.dev.paxform.net/api/document/get-form?env=test&signature=this_should_be_a_signature_as_mentioned_above

<!-- 2. POST get-form - Get a form with its id sending in the header -->

