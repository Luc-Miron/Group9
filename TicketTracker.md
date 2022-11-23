# Ticket Tracker

## API Description
We would like to design a simple API that returns the number of tickets issued by red light and speed cameras in Winnipeg at a given intersection in the last week.   

This API could be used by motorists, navigation systems and anyone who is interested in tracking the current trends in photo radar ticketing in the city of Winnipeg.

The caller can send two street names for a given intersection to one of two endpoints and our API will return either the number of speeding tickets issued at that intersection or the number of red light tickets issued at that intersection depending on the endpoint accessed.

## List of Endpoints with Parameters
We have two endpoints. Which each having two parameters.
  - Endpoints
    - red(Red Light Camera): Return the numbers of tickets issued by the red light camera at specific location.
    - speed(Speed Camera): Return the numbers of tickets issued by the speed camera at specific location.
  - Parameters
    - street1(street name 1): The first street name all in lower case. Required.
    - street2(street name 2): The second street name all in lower case. Required.

## Description of Resources


## Sample request with sample response

#### Get red light ticket count  

Returns a red light ticket count from the last 7 days for a cross road in Winnipeg as a JSON object.

##### Path parameters  
| Parameter   | Description |
| ----------- | ----------- |
| street1     | The name of a street       |
| street2     | The name of a crossing street        |  

**GET**  
```
https://www.ticket-track.com/tickets/redlight?street1=test1&street2=test2
```
Response  
`200`  
```
{
    "data": {
        "type": "red light"
        "date": "2022-11-22"
        "street1": "test1",
        "street2": "test2",
        "ticketsCount": 15
    }
}
```  

#### Get speeding ticket count 

Returns a speeding ticket count from the last 7 days for a cross road in Winnipeg as a JSON object.

##### Path parameters 

| Parameter   | Description |
| ----------- | ----------- |
| street1     | The name of a street|
| street2     | The name of a crossing street|  

**GET** 

```
https://www.ticket-track.com/tickets/speed?street1=test1&street2=test2  
```
Response  
`200`  
```
{
    "data": {
        "type": "speed"
        "date": "2022-11-22"
        "street1": "test1",
        "street2": "test2",
        "ticketsCount": 25
    }
}
```
