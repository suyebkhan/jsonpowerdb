<h1 align="center"><img src="https://www.powerlink.co.il/images/powerlink-logo.svg"></h1>

# Powerlink RestAPI

This is an up to date wrapper for the Powerlink.co.il REST API. 
we initially found working with the API to be a bit frustrating and hopefully this wrapper will make everything easy for you.

More information about the Powerlink REST API can be found at

https://support.powerlink.co.il/support/kb/%D7%94%D7%AA%D7%9E%D7%9E%D7%A9%D7%A7%D7%95%D7%99%D7%95%D7%AA/Rest_API

Please email support@powerlink.co.il if you find any bugs.

## index

+ <a href="#create">Create</a>
+ <a href="#update">Update</a>
+ <a href="#delete">Delete</a>
+ <a href="#query">Query</a>


## Authentication
To make a REST API call, you must include request headers including the Authorization header ==>
Find your <a href="https://api.powerlink.co.il/workpad/admin/leadform.aspx">TOKENID<a/>

## Create

URL: 
```
https://api.powerlink.co.il/api/record/{ObjectType}
```
Method: 
```
POST
```
Json exemple:
```javascript
{
 "accountname" : "משה",
 "telephone1" : "036339060",
 "idnumber" : "1234",
 "billingcity" : "תל אביב"
}
```
More exemple in <a href="https://github.com/powerlink/Rest-API/blob/master/Create/create-readme.md#php">PHP</a> | <a href="https://github.com/powerlink/Rest-API/blob/master/Create/create-readme.md#python">python</a> | <a href="https://github.com/powerlink/Rest-API/blob/master/Create/create-readme.md#aspnet">ASP.NET</a> |


## Update

URL: 
```
https://api.powerlink.co.il/api/record/{ObjectType}/{id}
```
Method: 
```
PUT
```
Json exemple:
```javascript
{
 "accountname" : "משה",
 "telephone1" : "00000000",
 "idnumber" : "56670",
 "billingcity" : "ירושלים"
}
```
More exemple in <a href="https://github.com/powerlink/Rest-API/blob/master/Update/update-readme.md#php">PHP</a> | <a href="https://github.com/powerlink/Rest-API/blob/master/Update/update-readme.md#python">python</a> | <a href="https://github.com/powerlink/Rest-API/blob/master/Update/update-readme.md#aspnet">ASP.NET</a> |


## Delete

URL: 
```
https://api.powerlink.co.il/api/record/{ObjectType}/{id}
```
Method: 
```
DELETE
```
More exemple in <a href="https://github.com/powerlink/Rest-API/blob/master/Delete/delete-readme.md#php">PHP</a> | <a href="https://github.com/powerlink/Rest-API/blob/master/Delete/delete-readme.md#python">python</a> | <a href="https://github.com/powerlink/Rest-API/blob/master/Delete/delete-readme.md#aspnet">ASP.NET</a> |


## Query

URL: 
```
https://api.powerlink.co.il/api/query
```
Method: 
```
POST
```

Json exemple:
```javascript
{
"objecttype": 1,
"page_size": 50,
"page_number": 1,
"fields": "accountname,idnumber,telephone1",
"query": "(idnumber  = 12345678) AND (telephone1 = 036339060)",
"sort_by": "accountname",
"sort_type": "desc"
} 
```
More exemple in <a href="https://github.com/powerlink/Rest-API/blob/master/Query/query-readme.md#php">PHP</a> | <a href="https://github.com/powerlink/Rest-API/blob/master/Query/query-readme.md#python">python</a> | <a href="https://github.com/powerlink/Rest-API/blob/master/Query/query-readme.md#aspnet">ASP.NET</a> |


Field | Description | exemple
------|------------ | --------------------
objecttype | the number of object | Account=1,	Contact=2,Cases=5 (<a href="https://api.powerlink.co.il/_common/viewrecordsystemsettings.aspx?oid=58">See more..</a>)
page_size | the number of result per page | Min:1 Max:500
page_number | the page of result | start at: 1
fields | which fields to show on result | for all field: *
query | the query you want search | ((idnumber  = 1234) AND (idnumber  = 5678))
sort_by | Select field to sort by | accountname/idnumber/telephone1
sort_type | Select type to sort | desc/asc

Type of query:

Operator | Description | exemple
------|------------ | --------------------
**=** | find result equal | "query": "(idnumber  **=** 1234)"
**!=** | find result not equal | "query": "(idnumber  **!=** 1234)"
**>** | Greater than | "query": "(age1  **>** age2)"
**<** | Less than | "query": "(age1  **<** age2)"
**<=** | Greater than or equal to | "query": "(age1  **<=** age2)"
**>=** | Less than or equal to | "query": "(age1  **>=** age2)"
**OR** | performs a logical-OR of its bool operands | "query": "((idnumber  = 1234) **OR** (idnumber  = 456789))"
**AND** | performs a logical-AND of its bool | "query": "((idnumber  = 1234) **AND** (accountname  = 'משה'))"
**is-null** | look for NULL values | "query": "(idnumber **is-null** 1234567)"
**is-not-null** | look for not NULL values | "query": "(idnumber **is-not-null** 1234567)"
**start-with** | find if the string start with the string |  "query": "(idnumber **start-with** 1234567)"
**end-with** | find if the string end with the string | "query": "(idnumber **end-with** 1234567)"
**not-start-with** | find if the string not start with the string | "query": "(idnumber **not-start-with** 1234567)"
**not-end-with** | find if the string not end with the string | "query": "(idnumber **not-end-with** 1234567)"

You can combining the AND and OR Conditions

**Note**

+ AND & OR conditions allow you to test multiple conditions.
+ Don't forget the order of operation parentheses!

 Go to your <a href="http://powerlink.co.il">Powerlink account</a> and let's start!
