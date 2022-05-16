# Mepal - Measurement protocol
For Datatricks and Google ads Enhanced Conversions

## Background
In order to match more profiles in Datatrics AND to implement Enhanced Ecommerce, we need to add personal information to the dataLayer. In this case the extra information will be the email address. The email address should be available in the dataLayer at the moment of a log-in AND the moment of a purchase.

## Specific dataLayer components
This chapter contains all of the dataLayer components that must be implemented in order to implement enhanced conversions.

### Variable
| Data Field | Type | dataLayer Variable | Description
| -------- | ------------- | ------------- | -------------|
| Email address | string | email | User email

### How to measure email

| On | Whenever a website visiter Logs in |
| -------- | ------------- |
| Whereby | The user succesfully logs in and the event 'accountLogin' is fired into the dataLayer. The dataLayer object should contain the values presented in code example 1 below.

**Code Example 1: For login event (This dataLayer push and event already exisits, only email adress should be added**
```
<!-- dataLayer -->
<script>
dataLayer.push({
  event: "accountLogin", // ALREADY EXISTS
  userId: 175381, // ALREADY EXISTS
  email : 'test@test.nl', // NEW filled in e-mail address of a user
  eventCallback: "Function", // ALREADY EXISTS
  eventTimeout: 2000, // ALREADY EXISTS 
  gtm.uniqueEventId: 1173 // ALREADY EXISTS is unique for every event       
});
</script>
<!-- end dataLayer -->
```

| On | Whenever a website visitor purchases something|
| -------- | ------------- |
| Whereby | The user receives a notification of a successful submission on the page: /nl/winkelwagen/bevestiging After this submission the Google dataLayer (dataLayer) has to be filled. The dataLayer object should contain the values presented in code example 2 below.

The email address is filled in, in the first step of the checkout.

**Code Example 2: For purchases, this dataLayer push and event are new**
```
<!-- dataLayer -->
<script>
dataLayer.push({
    'email' : 'test@test.nl', // filled in e-mail address of a user
    'event' : 'fireEnhancedConversionTag'          
});
</script>
<!-- end dataLayer -->
```

