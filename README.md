# Rest API Basics

![API logo](/API-logo.png)

### Who is this for?

This guide is meant for absolute beginners. As a Sales Engineer, I often have to demonstrate API capabilties of my products. After receiveing help from colleagues I have decided to make a guide in an attempt to make understanding this topic easy. 

The end goal is for you to learn about the very basics of working with APIs, specifically REST API, and make a few API calls using a tool such as Postman or from your terminal. 

### What is an API?

To start making API calls, we first start with learning about an API. 

API stands for Application Programmable Interface. In simple terms, it is a way for two different (or multiple) computer programs or software to communicate with each other. 

Let's understand with an example. Say, you have two different programs, one is a CRM which hosts all your customer interactions and data, and the other is an accounting system, where you do billing and payments. Assume both are different SaaS products or web applications, meaning that their hosted on the web, and accessed through a browser such as Chrome, Edge or Firefox. 

Now, whenever a new customer is acquired, you already have some data residing in the CRM. At this point, you'd need to share the data into your accounting software for billing and payment processing. What would you do? The easiest option would be to simply copy over the data every time you acquire a new customer. 

But what if you are maybe acquiring 50 customers per day? You'd say okay, creating the record manually would be a pain, and you'd say maybe you can export the data from the CRM in a spreadsheet (Excel, CSV) and upload it back into the Accounting software. Great! But now you have the overhead of matching the columns correctly, also you'd do this maybe once or twice a day at best.

If we now increase the scope to acquiring a few hundred customers a day, even the spreadsheet method becomes tasking. This is where APIs will come in handy. 

![Rest API](/Rest-API.png)
<p style="text-align:center"><i>credits_ :https://www.seobility.net/en/wiki/REST_API_</i></p>

The Accounting application will have a set of APIs that the CRM can use to share the customer data. This will remove the manual intervention discussed in the first couple of data sharing options. And since this is a more automated way, it can run on a far better scale than copying data one by one, or uploading a part of it at a time using spreadsheets!

APIs are used more widely than just inter-application communication. They can be used to communicate between different services of the same application as well. Say you're using a banking application from your computer. The application has a set of APIs that allow it to connect to the backend and database. Likewise, when you switch to the mobile application, the mobile app uses a set of APIs to communicate with the backend of the banking system. 

Now, that we have a basic understanding of what an API is and can do, let's get to know different kinds of data available. 

**NOTE:** In this document, I'll be focusing on REST APIs and referring to web applications specifically.  

#### REST API

REST API stands for RESTful API. Not very helpful at first glance I understand, but hang on a second. 

REST is an architecture on top which one can build their API service. Most web applications use REST APIs as a way to allow communcation with external applications or service. 

When a client request is made via a RESTful API, it transfers a representation of the state of the resource to the requester or endpoint[1]. The data or information can be transferred over HTTP in various formats of which JSON is the most popular. 

##### CRUD

CRUD stands for Create, Read, Update, and Delete. Rest APIs calls are generally CRUD operations. 

Whenever an API call is done, it is restricted to one of the above data operations. 

| **Operation** | **Description**               |
|---------------|-------------------------------|
| CREATE        | Adding new record(s)          |
| READ          | Retrieving/Pulling existing record(s) |
| UPDATE        | Modifying existing record(s)  |
| DELETE        | Delete record(s)              |

##### What is JSON?

JSON stands for JavaScript Object Notation and is an open format file format used for exchanging data over the internet. While initially this grew out of Javascript, a popular programming language but is now object independent as other languages have gained the ability to parse it. 

Let's take an example of transferring the details of a contact. The details are as follows:

1. Name: Michael Scott
2. Company: Dunder Mifflin
3. Phone Number: (212) 555-6733
4. Designation: Regional Manager
5. Branch: Scranton
6. Address: 1725 Slough Ave. Scranton, PA 18501. 

Now, if I have to send this detail from one application to another in JSON, the structure would look as follows:

```JSON
{
    "contactName": "Michael Scott",
    "age": 40,
    "address": {
        "streetAddress": "1725 Slough Avenue",
        "city": "Scranton",
        "state": "PA",
        "postalCode": "18501"
  },
  "phoneNumbers": [
    {
      "type": "office",
      "number": "212-555-6733"
    }
  ],
  "designation": "Branch Manager",
  "branch": "Scranton"
}
```

The contact data will be shared in the above format between the two applications and will be a part of the API call that will be made.

#### Webhooks vs API

Another term you ought to hear very often while discussing REST APIs is Webhook. It is nothing but a subset of APIs. 

APIs are reactive whereas Webhooks are proactive. An API works when a request is made to it by an external system. Based on the data received, it will provide a response. An API also has to support all CRUD operations. 

A webhook on the other hand is event driven. A webhook will send data out to an external based on a specific event.
Eg: You purchased something from a E-commerce website and immediately get an SMS. That action is driven by a webhook. The webhook will send your order details to the SMS portal which will trigger the SMS to you. 

![Webhook vs Rest API](/webhook_v_api.png)

To summarise:

| **REST API**                                                                                | **Webhook**                                                                             |
|---------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| Architectural style to allow communication between different web applications               | Subset of API                                                                           |
| Needs an incoming request from an external system and will share response based on the same | Event driven. It will push data to an external system based on a specific event trigger |
| API needs to support CRUD operations from single resource                                   | Purpose specific. Will only do data push to a resource                                  |
| Use Cases: CRUD - data pull, push, modification, deletion                                   | Use Cases: push data to external system                                                 |                            |

### Tools to help us


### cURL

### Request Types

GET
POST


### Making an API Call



### References

1. What is a REST API? - Redhat - https://www.redhat.com/en/topics/api/what-is-a-rest-api
2. WEbhook vs API - Zapier - https://zapier.com/blog/webhook-vs-api/
