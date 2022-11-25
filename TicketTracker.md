# Ticket Tracker

## API Description
We would like to design a simple API that returns the number of speeding or red light tickets issued by a given fixed photo radar camera in Winnipeg, Manitoba at in the last week.   

This API could be used by motorists, navigation systems and anyone who is interested in tracking the current trends in photo radar ticketing in the city of Winnipeg.

The caller can send two street names as parameters representing a given intersection to one of two endpoints and our API will return either the number of speeding tickets issued at that intersection or the number of red light tickets issued at that intersection depending on the endpoint being accessed.

## List of Endpoints with Parameters
We have two endpoints. Which each have two parameters.
  - **Endpoints**
    - `/redlight`(Red Light Camera): Return the numbers of tickets issued by the photo radar camera at specific location.
    - `/speed`(Speed Camera): Return the numbers of tickets issued by the photo radar camera at specific location.
  - **Parameters**
    - `street1`(street name 1): The first street name all in lower case. **Required**.
    - `street2`(street name 2): The second street name all in lower case. **Required**.

## Description of Resources

Both endpoints return a JSON with the following information:  
1. **type**: `/redlight` or `/speed` depending on the endpoint.
2. **date**: The date of the query.
    > Note the API returns the total number of tickets for the last 7 days.
3. **street1**: The name of the first cross-street entered.
4. **street2**: The name of the second cross-street entered.
5. **ticketCount**: The number of tickets issued in the last 7 days.

## Sample Request with Sample Response

#### Get red light ticket count  

Returns a red light ticket count from the last 7 days for an intersection in Winnipeg as a JSON object.

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
        "ticketCount": 15
    }
}
```  

#### Get speeding ticket count 

Returns a speeding ticket count from the last 7 days for an intersection in Winnipeg as a JSON object.

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
        "ticketCount": 25
    }
}
```
