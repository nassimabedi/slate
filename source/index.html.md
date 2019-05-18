---
title: Manam API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Manam API! You can use our API to access Manam API endpoints, which is a IDaaS and can register, login, conform, recover, Google Login oauth2.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.


# Manam

## Register


```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
$.ajax({
    url: "/auth/register",
    dataType: "json",
    type : "POST",
    data: {name:"myname", email:"myemail@mail.com", password:"password", confirm_password:"password", "customer_token":"cus_token"}
    success : function(r) {
      console.log(r);
    }
  });
```

> The above command returns JSON structured like this:

```json
{
"location": "/",
"message": "Please verify your account, an e-mail has been sent to you.",
"status": "success"
}
```

This endpoint register user in Manam.

### HTTP Request

`POST https://manam.ir/auth/register`

### Query Parameters
None.


### Data Params

Parameter | Type 
--------- | ------- 
name | string
email | [string] 
password | [string]
confirm_password | string
customer_token | string



## Confirm

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
$.ajax({
    url: "/auth/confirm?cnf=FFL5QDOYTXJZcO3SdcDgd8Kv-_euyLqVwm-eFagHZG_KCBLgtyhUkjFAeeDXvMFVVame3vXKyiWbnpNAVxQI8A==&customer_token=cus_token",
    dataType: "json",
    type : "GET",
    success : function(r) {
      console.log(r);
    }
  });
```

> The above command returns JSON structured like this:

```json
{
"location": "/",
"message": "You have successfully confirmed your account.",
"status": "success"
}
```

This endpoint confirm users on Manam.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://manam.ir/auth/confirm/<cnf>/<customer_token>`

### URL Parameters

Parameter | Description
--------- | -----------
cnf | The string that confirm registartion
customer_token | The token that specific for each customer

## Login


```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
 $.ajax({
    url: "/auth/login",
    dataType: "json",
    type : "POST",
    data: { email:"myemail@mail.com", password:"password", "customer_token":"cus_token"}
    success : function(r) {
      console.log(r);
    }
  });
```

> The above command returns JSON structured like this:

```json
{
"location": "/",
"status": "success"
}
```

This endpoint login user on Manam.

### HTTP Request

`POST https://manam.ir/auth/login`

### URL Parameters

None.


### Data Parameters

Parameter | Description
--------- | -----------
email | The email that register 
password | The password to login
customer_token | The token is specific for customer



## Recover

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
$.ajax({
    url: "/auth/recover",
    dataType: "json",
    type : "POST",
    data: { email:"myemail@mail.com", "customer_token":"cus_token"}
    success : function(r) {
      console.log(r);
    }
  });
  ```

> The above command returns JSON structured like this:

```json
{
"location": "/",
"message": "An email has been sent to you with further instructions on how to reset your password.",
"status": "success"
}
```

This endpoint recover user on Manam.

### HTTP Request

`POST https://manam.ir/auth/recover`

### URL Parameters

None.

### Data Parameters

Parameter | Description
--------- | -----------
email | The email that register 
customer_token | The token is specific for customer


## Google Login (oauth2)
use this link `<a href="/googlelogin/[customer-token]">Google Log In</a>`

Contact to admin for give customer-token


