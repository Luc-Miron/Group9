# Ticket Tracker
























































































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