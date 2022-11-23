# Ticket Tracker


## API Description
We would like to design a simple API that returns the number of tickets issued by red light and speed cameras in Winnipeg at a given intersection in the last week.   

This API could be used by motorists, navigation systems and anyone who is interested in tracking the current trends in photo radar ticketing in the city of Winnipeg.

The caller can send two street names to one of two endpoints and our API will return either the number of speeding tickets issued at that intersection or the number of red light tickets issued at that intersection depending on the endpoint accessed.


## List of Endpoints with Parameters
## Description of Resources

## Sample request with sample response
#### Get red light tickets count  
Get red light tickets counts for a cross road  
##### Path parameters  
| Parameter   | Description |
| ----------- | ----------- |
| street1      | The name of a street       |
| street2   | The name of a crossing street        |  

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

#### Get speed tickets  
Get speed tickets counts for a cross road  
##### Path parameters  
| Parameter   | Description |
| ----------- | ----------- |
| street1      | The name of a street       |
| street2   | The name of a crossing street        |  

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


