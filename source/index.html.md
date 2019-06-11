---
title: API Reference Goibibo Flights

language_tabs: # must be one of https://git.io/vQNgJ
  - json

toc_footers:
  - <a href='http://goibibo.github.io/goibibobusinessapi/#!/flights'>Sign Up for a Developer Key Goibibo API</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Goibibo Flight API You can use our API to access Goibibo Flight API endpoints. Forget about the tedious task to make smart intelligent flight booking flow by making use of our API.

Our API ensures the fastest responses to the millions of queries per second. Best in practice deployment strategies helped us to boost the performance of our API. We have designed our API to access the unique needs of your travel business It's light reliable and quick to integrate with your business.

Below are the Goibibo Flight API from search to book a flight of your choice, step by step. This documentation is for only B2BRate Flow


# Flights API

## Flight Search Oneway and Round Trip

The search API enables you to search for operational flights based on specified parameters i.e. route details departure and arrival dates, cabin type and passenger details. Leave dateofarrival blank if looking for only one way flights(onward flights). 


### HTTP Request Example
 
`GET ENV/api/search/?format=json&dateofdeparture=20190701&dateofarrival=&source=DEL&destination=DXB&seatingclass=E&adults=1&children=0&infants=0&counter=100`

> The above command returns JSON structured like this:

```json
{
    "data": {
        "onwardflights": [
            {
                "ArrivalTime": "",
                "BookabilityValue": 0.77734697,
                "CINFO": "air-DEL-DXB-20190701--1-0-0-E-100--",
                "CabinClass": "",
                "CacheKey": "DELDXB20190701ESG",
                "DataSource": "spicejetnew",
                "DepartureTime": "",
                "FilteringValue": 0.011396011000000001,
                "FlHash": "oSG-11",
                "Group": "",
                "PromotionId": "",
                "SetTime": "2019-06-11 03:43:06",
                "TravelTime": "",
                "aircraftType": "737",
                "aircraftTypecode": "189",
                "airline": "Spicejet",
                "arrdate": "2019-07-01t1010",
                "arrterminal": "1",
                "arrtime": "10:10",
                "bookingclass": "A",
                "carrierid": "SG",
                "codeshare": "",
                "depdate": "2019-07-01t0750",
                "depterminal": "3",
                "deptime": "07:50",
                "destination": "DXB",
                "duration": "3h 50m",
                "fare": {
                    "adultbasefare": 7300,
                    "adulttotalfare": 8111,
                    "grossamount": 8111,
                    "totalbasefare": 7300,
                    "totalcommission": "",
                    "totalfare": 8111,
                    "totalsurcharge": 0
                },
                "farebasis": "ASAVER",
                "flightcode": "11",
                "flightno": "11",
                "holdflag": "",
                "ibibopartner": "spicejetnew",
                "internationalsearch": "true",
                "multicitysearch": "",
                "onwardflights": [],
                "operatingcarrier": "",
                "origin": "DEL",
                "platingcarrier": "",
                "provider": "",
                "qtype": "",
                "rating": 0,
                "searchKey": "0:0:0:0:0:7300:0:8111:0:0:0:0:0:0:0:0:8111:7300:8111:0:0:0:0:0:0",
                "seatingclass": "E",
                "seatsavailable": "1",
                "splitduration": "3h 50m",
                "src": "",
                "stops": "0",
                "warnings": "Refundable"
            }
        ],
        "returnflights": []
    },
    "data_length": 2
}
```



### Query Parameters

Parameter | Example-Value | Description 
--------- | ------- | ----------- |
format | xml/json | Response format
dateofdeparture | 20190701 | Departure Date in ISO format i.e. YYYYMMDD. It must be before Arrival Date.
dateofarrival | 20190702 | Arrival Date(provided in case of return flights) in ISO format i.e. YYYYMMDD
source | DEL | Origin Airport Code (A valid IATA code). Source should not be same as destination
destination | BLR | Destination Airport Code ( A valid IATA code)
seatingclass | E(Default) | Travel Class/Cabin Type e.g. E(Economy), B(Business)
adults | 1 (Default) | No of Adults(0-9). Number of passengers cannot exceed 9. Minimum of 1 adult is required for booking.
children | 0 (Default) | No of Children(0-9).
infants | 0 (Default) | No of Infants(Can't exceed No of Adults)
counter | 100 (Default) | Choice of carriers ({ '0' : ["ALL","SG","6E", "NSG"], '1' : ["9W","S2","IT","AI"], '2' : ["6E","N6E"], '3' : ["G8","PG8","RG8"], '4' : ["9W", "S2"], '5' : ["IT"], '6' : ["AI"], '7' : ["SG", "PSG", "NSG"], '11' : ["6E","NSG","MG8","9W","S2","IT","AI","SG"], # 11 is for mobile special G8 fare; if any changes to be done to '100', do it here as well. '100' : ["6E","NSG","G8","9W","S2","IT","AI","SG","IX","SG","N6E","AK","LB"], '101' : ["9W","S2","6E","SG", "NSG","AI","IT"], '200' : ["ALL"], # Internatinal Multicity. '201' : ["6E","SG","G8","9W","S2","IT","AI", "NSG"] # Domestic Multicity. })
discountedflights  | Y/N | optional parameter, if Y, gives discounted flights


This endpoint returns search results according to the query parameter.


### Search Response Parameters And Structure

The typical flight search response format will be in the format as shown above. Response data will have two keys `onwardflights` and `returnflights`. If the search query is a Domestic oneway trip, then the `returnflight` key values will be **Empty** and `onwardflights` values will be present as shown in example response.

let's explore the keys available in response.


Key | Description
--------- | -----------
returnflights | This keys will have data if the user query is Domestic Roundtrip.If the return flight is multi stop flight `onwardflight` key will be nested inside `returnflights`.
onwardflights | This key will have data related to the onward flight details and if it has one or more stops it will be available inside onwarflights key nested inside `onwardflights`
arrtime | This key indicates the arrival time. Time is added reference to the destination airport/countries time. 
CabinClass | Values: Economy,Business , Premium Economy and Firstclass
DepartureTime | Denotes departure time in departure countries standard timezone.
TravelTime | Total travel time
aircraftType | denotes aircraft type eg: boying 737,787,etc
airline | Indicates the carrier name
arrdate | denotes arriving date at the destination.
carrierid | indicates IATA based airline id.
depdate | Departure date in yyyy-mm-ddtHHMM format
destination | destination Airport IATA code
duration | duration of flight
fare | fare is a dict inside the onwardflight or returnflight values. This will consist of adultbasefare,adulttotalfare,grossamount,totalbasefare,totalcommission,totalfare,totalsurcharge.
adultbasefare | Base fare of an adult.
adulttotalfare | This is calculated by multiplaying num.of adults * adultbasefare + taxes. tax breakup will not show in search details.
grossamount | amount without any discount
totalbasefare | total fare of passengers without tax addition
totalfare | toatal amount to be paid
farebasis | vendor specific farebasis code
flightcode/flightno | flight number
ibibopartner | vendor name
internationalsearch | it can have two values true/false
multicitysearch | can be true or false 
onwardflights | it can have values if the flight is multi stop flight.
origin | denotes origin airport IATA code.
searchKey | multi string concatenated values to easily identify fare details.
seatingclass | Possible keys for class are E,B,W,A
seatsavailable | The key Denote availability of seats. If the airline API couldnt provide the value by default it will set to `999`
splitduration | key to denote total duration in case of one or more stop flights. In case of Direct flight that duration will added as value.
warnings | indicates warrning like refundable or non-refundable,etc 


**In case of Domestic Round Trip** returnflights keys values will be populated with the flight details accordingly. The structure of this json response will be the same as that of onwardflight.


**International flight search response behaviour**

For international roundrip, flight search response will have some changes as compared to domestic response.
* For international roundtrip  `returnflights`list will remain empty. Round trip flight details and connection flights details will be populated inside the key `returnfl` which is available inside `onwardflights`.
* 

> interantional roundtrip JSON structure looks like this:

```json
{
  "data": {
    "returnflights": [
      
    ],
    "onwardflights": [
      {
        "origin": "DEL",
        "rating": 0,
        "DepartureTime": "",
        "flightcode": "11",
        "Group": "",
        "farebasis": "ARTSAVER",
        "depterminal": "3",
        "holdflag": "",
        "CINFO": "air-DEL-DXB-20190701-20190702-1-0-0-E-100--",
        "deptime": "07:50",
        "codeshare": "",
        "ibibopartner": "spicejetnew",
        "duration": "3h 50m",
        "platingcarrier": "",
        "qtype": "",
        "arrterminal": "1",
        "flightno": "11",
        "destination": "DXB",
        "FlHash": "oSG-11oSG-12",
        "stops": "0",
        "seatsavailable": "1",
        "carrierid": "SG",
        "airline": "Spicejet",
        "provider": "",
        "PromotionId": "",
        "fare": {
          "grossamount": 24114,
          "totalbasefare": 20941,
          "adultbasefare": 20941,
          "totalfare": 24114,
          "totalsurcharge": 0,
          "adulttotalfare": 24114,
          "totalcommission": ""
        },
        "CabinClass": "",
        "returnfl": [
          {
            "origin": "DXB",
            "rating": 0,
            "DepartureTime": "",
            "flightcode": "",
            "Group": "",
            "farebasis": "KRTSAVER",
            "depterminal": "1",
            "holdflag": "",
            "CINFO": "air-DEL-DXB-20190701-20190702-1-0-0-E-100--",
            "deptime": "22:45",
            "codeshare": "",
            "ibibopartner": "spicejetnew",
            "duration": "3h 20m",
            "platingcarrier": "",
            "qtype": "",
            "arrterminal": "3",
            "flightno": "12",
            "destination": "DEL",
            "FlHash": "SG-12",
            "stops": "0",
            "seatsavailable": "1",
            "carrierid": "SG",
            "airline": "Spicejet",
            "provider": "",
            "PromotionId": "",
            "fare": {
              "totalsurcharge": 0,
              "totalfare": 0,
              "totalbasefare": 0,
              "totalcommission": 0
            },
            "CabinClass": "",
            "warnings": "Refundable",
            "BookabilityValue": 4.588426,
            "ArrivalTime": "",
            "onwardflights": [
              
            ],
            "aircraftType": "737",
            "operatingcarrier": "",
            "src": "",
            "internationalsearch": "true",
            "aircraftTypecode": "189",
            "splitduration": "3h 20m",
            "searchKey": "0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0",
            "bookingclass": "K",
            "SetTime": "2019-06-11 11:34:13",
            "DataSource": "spicejetnew",
            "multicitysearch": "",
            "depdate": "2019-07-02t2245",
            "arrtime": "03:35",
            "arrdate": "2019-07-03t0335",
            "CacheKey": "DXBDEL20190702ESGR",
            "TravelTime": ""
          }
        ],
        "warnings": "Refundable",
        "BookabilityValue": 0.7344035999999999,
        "ArrivalTime": "",
        "onwardflights": [
          
        ],
        "aircraftType": "737",
        "seatingclass": "E",
        "operatingcarrier": "",
        "src": "",
        "internationalsearch": "true",
        "aircraftTypecode": "189",
        "splitduration": "3h 50m",
        "searchKey": "0:0:0:0:0:20941:0:24114:0:0:0:0:0:0:0:0:24114:20941:24114:0:0:0:0:0:0",
        "bookingclass": "A",
        "SetTime": "2019-06-11 13:54:21",
        "DataSource": "spicejetnew",
        "multicitysearch": "",
        "depdate": "2019-07-01t0750",
        "arrtime": "10:10",
        "arrdate": "2019-07-01t1010",
        "CacheKey": "DELDXB20190701ESGO",
        "TravelTime": ""
      }
    ]
  }
}
```

let's explore the additional changes available in the international roundtrip response.

Key | Description
--------- | -----------
returnflights | always empty list in case of international roundtrip
fare | Fare details about the roundtrip will be available inside this key. The details about the all keys are as given above column.
internationalsearch | true or false possible values
returnfl | as mentioned earlier this key consists of return flight details values.The length of this dict will remain one. If return flight is non direct flight onwardflight dict will present inside the `returnfl` key. `fare` dict and `searchkey`  values inside returnfl will be empty, consider the fare key inside parent `onwardflights`.


