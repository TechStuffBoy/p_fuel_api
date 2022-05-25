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

# Details
Project is in the final stage, will bring up the link shortly!
