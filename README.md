# Fuel API
An API for retrieving Indian petrol, diesel, and LPG pricing. I couldn't find a better API, so I made one. It **scrapes from different sources** and consolidates and persist in a Database. It may scale up and down as needed. I used AWS Lambda, which can handle millions(or more than that) of requests in a month in a fraction of cost. It may also scale down if traffic is low which further reduces the cost of the deployment.


# Technical Details
**Environment**: Flask, Postgre SQL <br>
**Deployment**: EC2 (Postgre SQL), AWS Lambda (for public Access)

# Features
- By State : Sends out a Json response for all the cities in the state
    - Petrol
    - Diesel
    - LPG
# REST API Documentation

`Note: You should always check for 200 Response. If it is 404, then please refer to the error message. This 404 response is because either you have given wrong state code or not enough parameters.`

### Request

`GET /api/v2/fuel?state=<state-code>&fuel=<fuel-name>`

     curl -i -H 'Accept: application/json' "https://<host>/api/v2/fuel?state=TN&fuel=petrol"

### Response - 200 OK

  ```
  {
  "cities": [
    {
      "city": "Ariyalur", 
      "currency": "INR", 
      "fuel": "PETROL", 
      "rate": "103.56"
    }, 
    {
      "city": "Chennai", 
      "currency": "INR", 
      "fuel": "PETROL", 
      "rate": "102.62"
    },
    
    .
    .
    
    
    {
      "city": "Thoothukudi", 
      "currency": "INR", 
      "fuel": "PETROL", 
      "rate": "102.95"
    }
  ], 
  "state_code": "TN", 
  "state_name": "Tamil Nadu"
}
```


### Error Response  - Parameter not given properly

```
{
 
 "error": "Bad Error. Please double check the parameters. Refer available_states and available_fuel.",
 
  "available_fuel": [
    "petrol", 
    "diesel", 
    "lpg"
  ], 
  
  "available_states": {
    "AD": {
      "state_code": "AD", 
      "state_name": "Andhra Pradesh"
    }, 
    "AN": {
      "state_code": "AN", 
      "state_name": "Andaman and Nicobar Island"
    }, 
    "AR": {
      "state_code": "AR", 
      "state_name": "Arunachal Pradesh"
    }, 
    
    .
    .
    
    "UP": {
      "state_code": "UP", 
      "state_name": "Uttar Pradesh"
    }, 
    "WB": {
      "state_code": "WB", 
      "state_name": "West Bengal"
    }
  }
}

```
### Error Response 2 - State_code or fuel_name is missing in GET

```
{
  "error": "Please provide enough GET parameters. Refer available_states and available_fuel.",
  
  "available_fuel": [
    "petrol", 
    "diesel", 
    "lpg"
  ], 
  
  "available_states": {
    "AD": {
      "state_code": "AD", 
      "state_name": "Andhra Pradesh"
    }, 
    "AN": {
      "state_code": "AN", 
      "state_name": "Andaman and Nicobar Island"
    }, 
    "AR": {
      "state_code": "AR", 
      "state_name": "Arunachal Pradesh"
    }, 
    
    .
    .
    
    "UP": {
      "state_code": "UP", 
      "state_name": "Uttar Pradesh"
    }, 
    "WB": {
      "state_code": "WB", 
      "state_name": "West Bengal"
    }
  }
}

```
 

# Details
Project is in the final stage, will bring up the link shortly!
