# API Documentation

## Authentication APIs

{% api-method method="post" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/authentication/login/" %}
{% api-method-summary %}
Login User
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows user to login and get JWT tokens from Node server.  
Before making this request, firebase authentication must be made from client app and Firebase JWT token is send in body for verification purpose.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="firebase\_token" type="string" required=true %}
Firebase JWT token obtainer after successful authentication.
{% endapi-method-parameter %}

{% api-method-parameter name="phoneNo" type="string" required=true %}
Phone number the user.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
On Successful login, receive any of these response based on use case.
{% endapi-method-response-example-description %}

```
// If First time login
{
    "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwaG9uZU5vIjoiOTEwNjY1OTc3MCIsImlkIjozMywiaXNLeWNDb21wbGV0ZWQiOmZhbHNlLCJpc1Byb2ZpbGVDb21wbGV0ZWQiOmZhbHNlLCJpYXQiOjE2MDczMTY4MDAsImV4cCI6MTYwNzQwMzIwMCwiYXVkIjoibWFya2V0LW1mdW5kLXVzZXJzIiwiaXNzIjoiZ2Vla3lhbnRzIn0.gItGLLnrTGebazmj8L_9r4UOCg7s9ukM2BZ5otprMr-tksA6sC-pNmUsQKgcCKfUXkd3bZZCLCWzcAuOPaomno7x4oRO2eKoPcBGbAfRyCQbUDTPoa_CpCb4xNlGn9TFKZ0uUom1v-V5NwQvAgAsLl0tHOKeI9kqvEUrwCiXrfFqdgf4RPLAGCXp1APrzfG-3tRSk7HVZrgIveE71fKftIEjO1Q4K3hnVa9TjuWbW9eFSe_KqepxqWCXvmOp1QRQRIBEqFh6dKtAG0pbQ4qrCLXyjXLXLx3wKrN0l3yIZWK-2rpSe-8wSenIOs8yGO1GIyMfNDYYOaUkIdbC7vbgwqOjPjZpc-dpWSdNkiu_S7tewKuyL43vRiWZImFnzikPnByAo9ZcUlGfRATUDbxwJ8kzLjybZLkyCA0u9r68ldL_KQG_UTXLuBAzq92P8Md2e9o8yN01NE-cIvoFyq-JzEKh8MnYlKFIJkGkDAIieNyxMGl1QnLwVwJV4i6e-RPTOhSEk0UrSTIG5OPLf-s0QBMs2AAI2I7PFPZ4Ejm3tSwMou9RI17cztO45Ob5gcXSS0bR4L_jUJz8zWW50cAhSmVIHnb0b3gS1byaFQTa6TNp__ivUD3lBrnqto13f-pTjqf6xa6VSWoJgSforBn9cm4-2a2vNAYZxATOVcBV5_I",
    "refresh_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwaG9uZU5vIjoiOTEwNjY1OTc3MCIsImlkIjozMywiaXNLeWNDb21wbGV0ZWQiOmZhbHNlLCJpc1Byb2ZpbGVDb21wbGV0ZWQiOmZhbHNlLCJpc1JlZnJlc2hUb2tlbiI6dHJ1ZSwiaWF0IjoxNjA3MzE2ODAwLCJleHAiOjE2MDc5MjE2MDAsImF1ZCI6Im1hcmtldC1tZnVuZC11c2VycyIsImlzcyI6ImdlZWt5YW50cyJ9.EcPh5RGKXAyfYRk7FJluOVThjY80aIPGmsGImVQB-xERAY0fafJDbmz7ulsz9M3wZvrpn-dcfcRAgH-Vw6FMlq2Hfx62fBhzZlxw_zvaGDHJ9-v2Zj37QYEchLfY9u7ZkZqCxV65lrd72-aU22AqSdCxOT7hOKwAugQoNtcVd91U2LPHtC_YLidNouxiBBxPaEnfXDcACCg7DZ0O0MA9EKkWZVh-iGW-s639lhExO9pIb9PdTJR9Wx2nfFzosoGWHICmU-2YKTSbMzWQsgCPVmlEutucFTQ2xqqEaiwWMke_nvwboeF4FqdT1h1VWyx63M1kHPusPvk9GZlA1QaWV76di1OaWFPIeNXdE51H-y-rPEN_qPD5kwlAHPn5eqHh454UqnS-jbbhneJlwW2tV5RJeWCGfkquzjpncu5S0BqkXKM-H_GjaXNb0TAFoG16OYb0PvkBhJwASQx3oMgb9Dl87-xqxtafIvfGFufS_aaYPjh5SV2miNhjSb3Dw13HZWsqROYazsFcsCKS31yf5O30EPpSufd5yEM0qVD1u5DdCMSH-TP8eRjuLjCVYxLL2-lM4d_AdmznShQeqz7GX7PVlaknolGLHJJGcPBhIgdKPOdcj7Oozv8qYMF22kdtiHPpGcSs2MPOhqsAsXBXTv21WCu9X8RcDITMpfHnOoE",
    "userId": 33
}
// else if 
{
    "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwaG9uZU5vIjoiOTgyNDI4MDc1MiIsImlkIjozMCwiaXNLeWNDb21wbGV0ZWQiOmZhbHNlLCJpc1Byb2ZpbGVDb21wbGV0ZWQiOnRydWUsImlhdCI6MTYwNzMxNjg4NiwiZXhwIjoxNjA3NDAzMjg2LCJhdWQiOiJtYXJrZXQtbWZ1bmQtdXNlcnMiLCJpc3MiOiJnZWVreWFudHMifQ.WR2Ku0dB3uj3CGHbWA_scVAEYNdPZ8ovE0uWkwDgQpsRNOFHc4z8lk7acZmubxHpq0G3pAFNW3n009KLOPPs16uX2ovkjkjXZHholi4RxRwZSQNFfb4d4MsUmxL43y02M3BNO0WRKXkEibCBH3KWmk7JgnClNz9Obl1KMLAqDpkyc5Sm0m3z4ZUhabfzLJgq0x7e4TALY8rkWpOZfq6PXWrpmcI5zugAbleP9ozmkkmeKmkMAAeXHOA12decs-WXfnWEOD-ViTHUBl-004txjETTCX2Cvypa47txGt8HGyGSQzISdc1PV4uM5mxDtM-TbUs42t05dO_LI8ORYSSvONnt4aWcDFwbKbSp3dsOiXCsNXgWxyYNCBsNiXhsChKq_ANuRrtwJIXOK5vVy940fsMcMkTRC8eLWlFKWl2peHvqrYgdD-GW44hIsPWLKlTkxWcSGgyT4N0OnQyoTrqgKUO_A78dHTm-eFYMsu-Z-SLzK1Ggbirca8gHUHZC4QJSsCi6uqTjOkW-GFfQuxeRHar86psuQ2Xeqfhqj0DIPQwmL0r74ZSRn74oZBDcoYX8icPdkcsj3tFhyC_f7pA_YQA-9x6l9hQV5aEgN0gQPpDHtF9HvtGfawysDCmdR5KKeqARUQAAlYPGj1DlFNhc96-JbvWP8pkbxNhy-tjFRNc",
    "refresh_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwaG9uZU5vIjoiOTgyNDI4MDc1MiIsImlkIjozMCwiaXNLeWNDb21wbGV0ZWQiOmZhbHNlLCJpc1Byb2ZpbGVDb21wbGV0ZWQiOnRydWUsImlzUmVmcmVzaFRva2VuIjp0cnVlLCJpYXQiOjE2MDczMTY4ODYsImV4cCI6MTYwNzkyMTY4NiwiYXVkIjoibWFya2V0LW1mdW5kLXVzZXJzIiwiaXNzIjoiZ2Vla3lhbnRzIn0.QnRXqAwgonP-xQso-9IR3Zm3ivsBatOqMxiJC9YcBcPCEeOvwtnwUvdnTT4ATSZL1apW-BI9pjJbz04Wooqs3zfa4Mvo0D6t00tHKZ1c1DKqYnQB84AnGY5mmwwneXwAJMm8I-Op1c9HpuuVaHCIdXQEh8OvkML_WEwkWSpi72Z_0tjQ2BHDtjpmeLAy38bX-Sj37OTeWo2GhcHCjBwy01bU394sY4ez6HYvKxsdcpadENKVdNob733QX4xEPPVGKAvAnkCGfARnlCd4mOLubRKy3oeyMtjHA1c0pJhsidVG4nrxhSYmg8g65va3Mq77x_-py8n7-19MctcbP4L1MzNyxMSMGNIl8AoydwgRvd4GYBD6mw_SQu7a6WwOrFKijom3gJbw8MAdrNpEbXZ-NsMSQi6WBy0J7icH3KElO-6ExP2PXj-D03xjap8wHcmG7UIvYZHkzrCsluXkYC0ykS7Yt3h1zTwaTDf2oBU3JlTb7zcPn0v2hO79f5WzdcUxxm-NZwviYlwD4iaYY1kvAvIx5VYP-RE-5xZD8HgrIuuYD6HyVT598rVLeEw9b_RXQOGYW67eLAuPYVYdwBBsEWeXe6Dare6OUWoGrv6WziRJgsh5zCOygzCfwDQoJYT25obYIdJlqCgFKlbTuMFo4O46_ImE-Ge89PFuXfbEAPI",
    "id": 30,
    "fullName": "Viral Sangani",
    "phoneNo": "9824280752",
    "dob": "20000401",
    "gender": "Male",
    "panNo": null,
    "nomineeName": "Tes",
    "relation": "Brother",
    "isKycCompleted": false,
    "isProfileCompleted": true,
    "imageId": null,
    "profileImageId": null
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://market-mfund-development.herokuapp.com/" path="api/mfund/authentication/complete\_profile/" %}
{% api-method-summary %}
Complete Profile
{% endapi-method-summary %}

{% api-method-description %}
When user Login for first time, then these information are asked to complete the Signup process.  
These API require JWT access token which is retrieved from Login API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Bearer eyJhbGciOiJS....
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="fullName" type="string" required=true %}
Full name of new user.
{% endapi-method-parameter %}

{% api-method-parameter name="dob" type="string" required=true %}
Date of birth should be in "YYYY/MM/DD" format.
{% endapi-method-parameter %}

{% api-method-parameter name="gender" type="string" required=true %}
Gender value can only be "Male" or "Female".
{% endapi-method-parameter %}

{% api-method-parameter name="nomineeName" type="string" required=true %}
Nominee name for new account.
{% endapi-method-parameter %}

{% api-method-parameter name="relation" type="string" required=true %}
Relation with the nominee.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Upon successful response, we get new access token with updated payload.
{% endapi-method-response-example-description %}

```
{
    "dob": "2000/01/23",
    "fullName": "Viral Sangani",
    "gender": "Male",
    "nomineeName": "XYZ",
    "relation": "Father",
    "success": "true",
    "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwaG9uZU5vIjoiOTEwNjY1OTc3MCIsImlkIjozMywiaXNLeWNDb21wbGV0ZWQiOmZhbHNlLCJpc1Byb2ZpbGVDb21wbGV0ZWQiOnRydWUsImlhdCI6MTYwNzMxNzM4OCwiZXhwIjoxNjA3NDAzNzg4LCJhdWQiOiJtYXJrZXQtbWZ1bmQtdXNlcnMiLCJpc3MiOiJnZWVreWFudHMifQ.Ffqil6AbwrTqYfFzuzXVzJWYSzFAZMsBhr1qzPwc3D7NiYmYP5tylnXY7fuHqmdJ6avUxZCtWXIOttaNlF19BPJemxwy5gTuD2IMXrs93Y8wBbLXn38PLSOhObZPH-yaflycDR_J66pcRzY0OB6Ww9o5FqRL9Mzofx4-b4kHXsieyQ29Nh-o6eXC-RlM-W-RgsyZAMhtxINu1vabbCQrTjA7rj-LyRIq1g55fbKNorgS4blidve2_tDQLVUtVd06E4YlloQ6mEn-R_xSrT5hEWskcdeDm2i855lJ-Lg53WN4e61Wj1A9Mk9Fi-wTVqLn0DhXJUVFXaCAcTmYPIig8WOi7J4NQFvTxU6V6R-YdnWKgdqbQ-wVT-_XI0pIBaBveChKcRMQ_FqnINHTwOXz6Ti0wYoAuZlgWBa8uqnBQGZVWfMjjPA4YXbHwRdDrizw0MbZtJZY08rRY-pEmvJqlyD42Josn3vjyNwcL23MDj5wehIPGlx8ziltNqehWLTYr40E75UE_f35AVe3NdDUWfw_Iq5fQL74TxnMcSoc2EAULor6LCHFrSZKhDR9v4jmbLnudMpMQQ7WksxLp93sYKSp8BfsGD1O1ZGouh4vspUIvxNScjcB1AYdNTjdZqttdT9-s2uhb7dB_6q9ViTUsuPds8yPOIlg69KChQrGVFA"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://market-mfund-development.herokuapp.com/" path="api/mfund/authentication/logout/" %}
{% api-method-summary %}
Logout User
{% endapi-method-summary %}

{% api-method-description %}
This API required Firebase JWT token, so that firebase refresh token can be revoked.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token with Bearer.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="firebaseToken" type="string" required=true %}
Firebase JWT Token of logged in user.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Refresh token of user is revoked.
{% endapi-method-response-example-description %}

```
{
    "status": "success",
    "message": "User Logged out successfuly"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://market-mfund-development.herokuapp.com/" path="api/mfund/authentication/get\_token/" %}
{% api-method-summary %}
Get Access Token
{% endapi-method-summary %}

{% api-method-description %}
Once access token is expired, user need new access token. This API expects Refresh token in header and generate new access token after verifying refresh token.  
Firebase JWT is required in this API because if refresh token is also expired then user's refresh token for firebase is revoked and logout message is send in the response.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Refresh Token with Bearer
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="firebaseToken" type="string" required=true %}
Firebase JWT of logged in user.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Receive new access token in response.
{% endapi-method-response-example-description %}

```
{
    "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwaG9uZU5vIjoiOTEwNjY1OTc3MCIsImlkIjozMywiaXNLeWNDb21wbGV0ZWQiOmZhbHNlLCJpc1Byb2ZpbGVDb21wbGV0ZWQiOnRydWUsImlhdCI6MTYwNzMxODI4NiwiZXhwIjoxNjA3NDA0Njg2LCJhdWQiOiJtYXJrZXQtbWZ1bmQtdXNlcnMiLCJpc3MiOiJnZWVreWFudHMifQ.UBn0VZa1ssezS9wPwtZJKzkUZVR6NaTlhJKQh5bIkp81VVMiieCFfrJcKCsXe3K4EwPzp8lajEHNKRcvouusMaYFdDKDA-OxmexOVyEFZT83mVVF3oSjZnXey6PGzflyARiiNkvQAx_wBXv1M52QeMqCSTmfUFMkNvwyS9FpSN1GWV0DLYGAj75gDmtSPTJWZOjWZWIeAFHDOcHX7Tmb1THBgh-Qo9T5suuCLFJSU04ZW8D49-lRKoba1uZjGecP3XRJLLHpinbRq-qHJoQkrrtCa19qLF96rpGHKXfV4eNBnf_5ACA2p6QMJ4Z64sLGLKmrwN-BIhWYBzUzjMUmrO_zxITZk7MMwFp4nkqZNjgB9EE_RUL18zeDiHVLDxb9Qt67-cE_4dEePipKUe9o_XrTwYcAFsVv1Lm0W4vKUUi17lPOyDXEy6wvpIBSlHS6uFxgKs8GtVhTzF4P70H3IULtS7g8QUMcbF5XVV-RUqoImxU9l3PovJvcnLrlT-mSEXDPLk2iX90fNJpAPwtdyisM5rW8wobocHqdFMFWhzY5oGDQ_zv_6jjIbaKQ0V-ToWw-P3l8zpeyWDFKqkw4e4jU-2tJistJGlZ136O7CSxr98jetC4rqh_7CfwRKd1_31ES-jsVKP1RNFVLVkyj-EqqUBXYy0fqPt9tiPgQMMg"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## KYC APIs

{% api-method method="post" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/kyc" %}
{% api-method-summary %}
KYC APIs
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="ifscCode" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="bankName" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="accountNo" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="cardHolder" type="string" required=true %}
Card holder name.
{% endapi-method-parameter %}

{% api-method-parameter name="licenseNo" type="string" required=true %}
Driving license number.
{% endapi-method-parameter %}

{% api-method-parameter name="dateOfIssue" type="string" required=true %}
DL Issue date in "YYYY/MM/DD".
{% endapi-method-parameter %}

{% api-method-parameter name="validityOfLicense" type="string" required=true %}
DL validity date in "YYYY/MM/DD".
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="pincode" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="state" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="country" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="licenseImage" type="string" required=true %}
DL image link. Images are uploaded in firebase storage.
{% endapi-method-parameter %}

{% api-method-parameter name="signatureImage" type="string" required=true %}
Signature image link. Images are uploaded in firebase storage.
{% endapi-method-parameter %}

{% api-method-parameter name="panNo" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "access_token": "eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJwaG9uZU5vIjoiOTEwNjY1OTc3MCIsImlkIjozMywiaXNLeWNDb21wbGV0ZWQiOnRydWUsImlzUHJvZmlsZUNvbXBsZXRlZCI6dHJ1ZSwiaWF0IjoxNjA3MzE4NDE3LCJleHAiOjE2MDc0MDQ4MTcsImF1ZCI6Im1hcmtldC1tZnVuZC11c2VycyIsImlzcyI6ImdlZWt5YW50cyJ9.F__7X6jd8LURouuw-MaCPfMDFxPhf5tlKzIW5BR-a8WC-ICrnSda83ApczsR-C3ulVjgBVBEBtvPy6LuIGqHGm6-dwRHVHR0jfZvSocjn8yDR5ioJNG_daNb4DcLRn31h_5YsAvdUjKneC_n-uk5OnrHouiHePY31Zp8WkPqPfj7ILp572dwPE4-m2CMuofeqw9KrljTK-nsT-2Gca3A5OV138h41SznXU_5b7jmlCRl6G1K_28gUBkSG_chMCLAYSSxf28ps-0k5Th0qpiOWV_KoTd7qxENPKoZ48dsp3DvgBhHn-LQFWJr0lIgZUeJ202pYrwLbizzS8C3Lsi1rxdtv2xiHVzW4hf9Whc4t5dggEkYEP7wUsKXSGeRIICrzkB6p35p6Fcs6KAX3ovd8licY-yEi9OFyKRJ0QxJH6EMglGSqgyY5l3u2QFrKiqFuPKWasmgke6K9NWjqqj4XH6VbaBgHXqvEqvw6DZOjGBB5UzPqJ8jwajDoB1iY6hWDF3hfb9k_-xyXeIPanThfrZ0Iy3ghOfU2jNi96Z9APnNbddPvMb3jd48tJRuFbM4lcDAY85UHhkKElZafuojjwMZuAFaSPUy4odomH7hcFRbxUfYzDKAnvXAHWflWdSIQPCBXrqgvfx7q2XcJyLnpLtxBmm_-sFk1OSrc3J3x_Q",
    "success": "true"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Organisation / Firms APIs

{% api-method method="get" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/organisations" %}
{% api-method-summary %}
Get All Firms
{% endapi-method-summary %}

{% api-method-description %}
Get list of all the firms/organisation list.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="offset" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
This is not the full response. In response chart data has all the information required to create the chart of history of that firm.
{% endapi-method-response-example-description %}

```
{
    "status": "success",
    "data": [
        {
            "id": 1,
            "logoImageId": 101,
            "cap": "LARGE",
            "rating": 3.5,
            "threeYearRate": 9.12,
            "name": "Axis Bluechip Fund Direct Plan Growth",
            "chartData": [
                {
                    "timeDuration": 1,
                    "avgRate": [
                        {
                            "date": "2019-01-01",
                            "nav": 29.1234
                        },
                        {
                            "date": "2019-01-08",
                            "nav": 29.2233
                        },
                    ]
                },
                {
                    "timeDuration": 3,
                    "avgRate": [
                        {
                            "date": "2019-01-01",
                            "nav": 29.1234
                        },
                        {
                            "date": "2019-01-01",
                            "nav": 28.878
                        },
                    ]
                },
                {
                    "timeDuration": 5,
                    "avgRate": [
                        {
                            "date": "2019-01-01",
                            "nav": 29.1234
                        },
                        {
                            "date": "2019-01-01",
                            "nav": 29.909
                        },
                    ]
                }
            ],
            "image": {
                "id": 101,
                "imageUrl": "https://firebasestorage.googleapis.com/v0/b/market-mfund-development.appspot.com/o/Organization-logo-image%2FAxis.png?alt=media&token=70443f42-43aa-463b-9762-a33aa25eb8aa",
                "createdAt": "2020-11-23T05:07:47.849Z",
                "updatedAt": "2020-11-23T05:07:47.849Z"
            }
        }
    ],
    "count": 3,
    "pages": 1
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/organisations/1" %}
{% api-method-summary %}
Get One Firm
{% endapi-method-summary %}

{% api-method-description %}
Get full information of the firm/organisation whose id is provided in endpoint.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access token.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Get all the required information for that one organisation.
{% endapi-method-response-example-description %}

```
{
    "status": "success",
    "data": [
        {
            "id": 2,
            "oneYearRate": 1.53,
            "threeYearRate": 8.42,
            "fiveYearRate": 6.55,
            "oneYearCategoryAverage": 0.25,
            "threeYearCategoryAverage": 8.11,
            "fiveYearCategoryAverage": 9.22,
            "oneYearRankInCategory": 2,
            "threeYearRankInCategory": 1,
            "fiveYearRankInCategory": 2,
            "prosCons": "Hey there how are you . This is a very cool FLutter Project we are building which can calculate you the lorem ipsum odor lorem ipsum odor lorem ipsum odor lorem ipsum odor",
            "about": "Hey there i am all about the about So hello Once again",
            "currentNav": 758,
            "oneDayRate": 0.77,
            "avgNav": 300,
            "name": "Reliance Small Cap Fund Direct Growth",
            "chartData": [
                {
                    "timeDuration": 1,
                    "avgRate": [
                        {
                            "date": "2019-01-01",
                            "nav": 29.1234
                        },
                        {
                            "date": "2019-01-08",
                            "nav": 29.2233
                        },
                    ]
                },
                {
                    "timeDuration": 3,
                    "avgRate": [
                        {
                            "date": "2019-01-01",
                            "nav": 29.1234
                        },
                        {
                            "date": "2019-01-01",
                            "nav": 28.878
                        },
                    ]
                },
                {
                    "timeDuration": 5,
                    "avgRate": [
                        {
                            "date": "2019-01-01",
                            "nav": 29.1234
                        },
                        {
                            "date": "2019-01-01",
                            "nav": 29.909
                        },
                    ]
                }
            ],
            "image": {
                "id": 102,
                "imageUrl": "https://firebasestorage.googleapis.com/v0/b/market-mfund-development.appspot.com/o/Organization-logo-image%2FReliance.png?alt=media&token=432ad8b7-6825-42c4-affc-9943e813a7ef",
                "createdAt": "2020-11-23T05:07:47.849Z",
                "updatedAt": "2020-11-23T05:07:47.849Z"
            }
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Investment APIs

{% api-method method="post" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/investment/transaction/" %}
{% api-method-summary %}
Add Investment
{% endapi-method-summary %}

{% api-method-description %}
When user make investment monthly or one time then this api is called.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="investmentPeriod" type="integer" required=true %}
This value can be 1, 3, 5 for transaction period in years.
{% endapi-method-parameter %}

{% api-method-parameter name="organisationId" type="integer" required=true %}
Organisation ID making investment in.
{% endapi-method-parameter %}

{% api-method-parameter name="isMonthlySip" type="boolean" required=false %}
If monthly SIP then only add this parameter.
{% endapi-method-parameter %}

{% api-method-parameter name="isOntTimeSip" type="boolean" required=false %}
If One Time SIP then only add this parameter.
{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="number" required=true %}
Investment amount.
{% endapi-method-parameter %}

{% api-method-parameter name="payment\_mode" type="string" required=true %}
This can be "card" or "net\_banking".
{% endapi-method-parameter %}

{% api-method-parameter name="billingDate" type="string" required=true %}
In YYYY-MM-DD format.
{% endapi-method-parameter %}

{% api-method-parameter name="cardNo" type="string" required=false %}
Add this only if payment\_mode is card.
{% endapi-method-parameter %}

{% api-method-parameter name="bankName" type="string" required=false %}
Add this only if payment\_mode is net\_banking.
{% endapi-method-parameter %}

{% api-method-parameter name="cardName" type="string" required=false %}
Add this only if payment\_mode is Card.
{% endapi-method-parameter %}

{% api-method-parameter name="cardType" type="string" required=false %}
Add this only if payment\_mode is Card.
{% endapi-method-parameter %}

{% api-method-parameter name="expiryDate" type="string" required=false %}
In "MM/YY" format.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Upon successful transaction receive success status.
{% endapi-method-response-example-description %}

```
{
    "status": "success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/investment/transaction" %}
{% api-method-summary %}
Get All Investments
{% endapi-method-summary %}

{% api-method-description %}
Get all the investment made by logged in user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": "success",
    "data": [
        {
            "id": 52,
            "folio_no": "2ZVY927OJ7oo",
            "amount": 5000,
            "billingDate": "2020-01-02",
            "paymentMode": "Debit card",
            "transactionId": "pLguhg4QnsY3nU2448cN",
            "transactionTime": "5:42:54 AM",
            "totalUnit": 125,
            "organisationName": "Axis Bluechip Fund Direct Plan Growth",
            "currentNav": 489,
            "avgNav": 200,
            "currentValue": 5050,
            "return": 50,
            "status": true,
            "investmentPeriod": 3,
            "purchaseDate": "Dec 07, 2020"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Cards APIs

{% api-method method="get" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/cards/" %}
{% api-method-summary %}
Get Cards
{% endapi-method-summary %}

{% api-method-description %}
Get all the cards added by logged in user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": "success",
    "data": [
        {
            "id": 14,
            "name": "Viral Sangani",
            "cardNo": "4234123412341234",
            "cardType": "CardType.Visa",
            "expiryDate": "12/33"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Notification APIs.

{% api-method method="get" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/notification/" %}
{% api-method-summary %}
Get Notifications
{% endapi-method-summary %}

{% api-method-description %}
Get all the notification for logged in user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": "success",
    "data": [
        {
            "id": 1,
            "title": "Test Notification",
            "description": "Lorem Ipsum Lorem Ipsum Lorem Ipsum Lorem Ipsum Lorem Ipsum",
            "createdAt": "2020-12-07T05:52:17.703Z",
            "updatedAt": "2020-12-07T05:52:17.703Z",
            "userId": 30
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="delete" host="https://market-mfund-development.herokuapp.com" path="/api/mfund/notification/" %}
{% api-method-summary %}
Delete all Notifications
{% endapi-method-summary %}

{% api-method-description %}
Delete all the notification of logged in user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
Access Token.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "status": "success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

