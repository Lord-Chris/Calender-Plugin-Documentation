<!-- 


PLS READ!!
Paste your documentation in the section created for you


 -->







# Zuri Calende Plugins (Calender Endpoints) (1.0.0)

Download OPenApi specification: [Download](auth.4cf62435.yaml)

Connect With Us: `developer@zuri.chat` <br>
Zuri Chat is an open source slack clone. However, it offers a lot more functionality via a plugin system where each room can be provided by a different plugin provider.


# Calender
The Calender Plugin API 0enables you to manage all events and reminders on Zuri App. It offers endpoints so users can Create events and reminders, update the and more.


## **BearerAuth**
The authorization token for this account. It's gives access to the bearer. This token should be kept a secret, so no sharing. Its expires in 24hours.

|  |  |
| ----------- | ----------- |
| Security Scheme Type | HTTP |
| HTTP Authorization Scheme | bearer|
|  |  |
## **CookieAuth**
It authorizes clients request and maintains session information. Its expires in 24hours.

|  |  |
| ----------- | ----------- |
| Security Scheme Type | API KEY |
| Cookie parameter name: | JSESSIONID|
|  |  |



## **Errors**
When an error occurs, you will receive an error object. Most of these error objects contain an error code and an error description so that your applications can more efficiently identify the problem.

If you get a 4xx response code, then you can assume that there is a bad request from your end. In this case, 
check the [Standard Error Responses](#standard-error-responses) for more context.

5xx errors suggest a problem on server's end.



## EndPoint Under Zuri Calender Plugin are

- GET: Fetch List Of Events
- GET: Fetch List Of Reminders
- GET: Search Reminders
- GET: Event Details
- GET: Reminder Details
- POST: Create Event
- POST: Create Reminder
- PATCH: Update Event
- PATCH: Update Reminder
- DEL: Delete Event
- DEL: Delete Reminder



# FETCH LIST OF EVENTS
## Description:
This endpoint fetches a list of all events.

```sh
PATH PARAMETERS: null
```
Request Body schema: application/json

## How it works
It works when there is a (get request) made to the events Endpoint, it then gets the list of events.

## How to set up Endpoint 
These ways to set up the end point to function properly:
- With the help of python set up django framework
- Create all necessary files like ( url.py  ,serializer.py, views.py)
- Import all needed modules
- It is important you set your database in set up ur database with models.py
- Copy the URL for the fetch list of events request
-   ‘GET'\https://calender.zuri.chat/api/v1/event-list
- Paste it where it is needed in the code which is  the url.py
That is a summary of how the end point is being set up.

## Endpoint
<details>
  <summary> GET/event-list </summary>
Zuri Calender Plugin

https://calender.zuri.chat/api/v1/event-list
 </details>

## RESPONSES;
### **200** Events Fetched Successfully <br>
```sh
{
  "status": 200,
  "message": "string",
  "data": [
      {...}
  ]
}
```
### **404** The event is not found on the database <br>

**Content type** <br>
application/json

```sh
{
  "status": 404,
  "message": "string",
  "data": null
}
```
### Response Sample
**Content type** <br>
application/json

````
{
"code": 200,
"message": "string",
"data": [
  {...}
]
}
````




# FETCH LIST OF REMINDERS

# SEARCH REMINDERS

# EVENT DETAILS
## Description: 
This endpoint fetches the details of an event. The event id must be present in the request

```sh
PATH PARAMETERS: event_id(required)
```

## How it works
It works when there is a request(GET) made to a particular event_id to get the event linked to the event_id.

## HOW TO SET UP THE END POINT
These ways to set up the end point to function properly:
- With the help of python set up django framework
- Create all necessary files like ( url.py  ,serializer.py, views.py)
- Import all needed modules
- It is important you set your database in set up ur database with models.py
- Copy the URL for the fetch event request
-   ‘GET'\https://calender.zuri.chat/api/v1/event-detail/{id}
- Paste it where it is needed in the code which is  the url.py
That is a summary of how the end point is being set up.

## Endpoint
<details>
  <summary> GET/event-detail/{id} </summary>
Zuri Calender Plugin

https://calender.zuri.chat/api/v1/event-detail/{id}
 </details>

## RESPONSES;
### **200** Event Fetched Successfully <br>
```sh
{
  "status": 200,
  "message": "string",
  "data": {...}
}
```
### **404** The event is not found on the database <br>
```sh
{
  "status": 404,
  "message": "string",
  "data": null
} (edited) 
```

### Response Sample
**Content type** <br>
application/json

````
{
"code": 200,
"message": "string",
"data": {...}
}
````



# REMINDER DETAILS

# CREATE EVENTS
## Description:
This Endpoint creates a new event given a request body of required key-value pairs. Returns ID of a created event.

Request Body schema: application/json

## Parameters
|   Name                |   Data type
---------------------------------------
 	Event title         |   string
 	Start and end date  |   string
 	Start  and end time |   string
 	Time zone           |   string
 	Description         |   string
 	All day             |   Boolean
    Event tag           |   string
 	Event color         |   string
 	Reminder            |   string


## Endpoint
<details>
  <summary> GET/delete_reminder/{reminder_id} </summary>
Zuri Calender Plugin

https://calender.zuri.chat/api/v1/delete_reminder/{reminder_id}
 </details>


## Response
```sh
201
```
- The resource is successfully created.


## how to create an event
- Click on Add Event
- Enter event title
- Enter start date
- Enter end date
- Enter start time
- Enter end time
- Select time zone
- All day, True or False
- Enter event tag
- Select event color
- Set reminder date and time

## The endpoint is setup using django REST framework


# CREATE REMINDER

# UPDATE EVENT

# UPDATE REMINDER

# DELETE EVENT

# DELETE REMINDER



# Standard Error Responses 
The Authentication API may return the following HTTP Status Codes:

---

### **400**  An icorrect client request <br>

```
RESPONSE SCHEMA: application/json

code required      integer <int32> 
message required   string

 ```



### **401** Is the error that shows up because the request is unauthorized <br>

```
 RESPONSE SCHEMA:   application/json

code required        integer <int32>
message required     string


```

 ### **422** Server unable to process contained information e.g API behavior <br>

```
RESPONSE SCHEMA: application/json

code required      integer <int32> 
message required   string 

```

### **500** Comes up when internal server error occured during operation

```

RESPONSE SCHEMA:     application/json

code required         integer <int32>
message required      string

```

