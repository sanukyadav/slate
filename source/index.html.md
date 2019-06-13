---
title: API Reference Goibibo Flights

language_tabs: # must be one of https://git.io/vQNgJ
  - json
  - xml

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

## Flight Search 

The search API enables you to search for operational flights based on specified parameters i.e. route details departure and arrival dates, cabin type and passenger details. Leave dateofarrival blank if looking for only one way flights(onward flights). 


### HTTP Request Example
 
`GET ENV/api/search/?format=json&dateofdeparture=20190701&dateofarrival=&source=DEL&destination=DXB&seatingclass=E&adults=1&children=0&infants=0&counter=100`

> The above command returns response like this:

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

```xml
<response>
    <data>
        <returnflights/>
        <onwardflights>
            <resource>
                <origin>DEL</origin>
                <rating>0</rating>
                <DepartureTime/>
                <flightcode>23</flightcode>
                <Group/>
                <farebasis>SISALE</farebasis>
                <depterminal>3</depterminal>
                <holdflag/>
                <CINFO>air-DEL-DXB-20190701--1-0-0-E-100--</CINFO>
                <deptime>07:20</deptime>
                <codeshare/>
                <ibibopartner>indigonew</ibibopartner>
                <duration>3h 50m</duration>
                <platingcarrier/>
                <qtype/>
                <arrterminal>1</arrterminal>
                <flightno>23</flightno>
                <destination>DXB</destination>
                <FlHash>o6E-23</FlHash>
                <stops>0</stops>
                <seatsavailable>27</seatsavailable>
                <carrierid>6E</carrierid>
                <airline>IndiGo</airline>
                <provider/>
                <PromotionId/>
                <fare>
                    <grossamount>7800</grossamount>
                    <totalbasefare>7055</totalbasefare>
                    <adultbasefare>7055</adultbasefare>
                    <totalfare>7800</totalfare>
                    <totalsurcharge>0</totalsurcharge>
                    <adulttotalfare>7800</adulttotalfare>
                    <totalcommission/>
                </fare>
                <CabinClass/>
                <warnings>Non-Refundable</warnings>
                <BookabilityValue>0.6904707</BookabilityValue>
                <ArrivalTime/>
                <onwardflights/>
                <aircraftType>320</aircraftType>
                <seatingclass>E</seatingclass>
                <operatingcarrier/>
                <src/>
                <internationalsearch>true</internationalsearch>
                <splitduration>3h 50m</splitduration>
                <searchKey>0:0:0:0:0:7055:0:7800:0:0:0:0:0:0:0:0:7800:7055:7800:0:0:0:0:0:0</searchKey>
                <bookingclass>S</bookingclass>
                <SetTime>2019-06-12 12:44:28</SetTime>
                <DataSource>indigonew</DataSource>
                <multicitysearch/>
                <depdate>2019-07-01t0720</depdate>
                <arrtime>09:40</arrtime>
                <arrdate>2019-07-01t0940</arrdate>
                <CacheKey>DELDXB20190701E6E</CacheKey>
                <TravelTime/>
            </resource>
        </onwardflights>
    </data>
</response>
```

### Query Parameters

Parameter | Example-Value | Description 
--------- | ------- | ----------- |
format | xml/json | Response format
ENV | pp.goibibobusiness.com & www.goibibobusiness.com | pp: test environment and www: production 
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

> interantional roundtrip response looks like this:

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

```xml
<response>
    <data>
        <returnflights/>
        <onwardflights>
            <resource>
                <origin>DEL</origin>
                <rating>0</rating>
                <DepartureTime/>
                <flightcode>11</flightcode>
                <Group/>
                <farebasis>ARTSAVER</farebasis>
                <depterminal>3</depterminal>
                <holdflag/>
                <CINFO>air-DEL-DXB-20190701-20190702-1-0-0-E-100--</CINFO>
                <deptime>07:50</deptime>
                <codeshare/>
                <ibibopartner>spicejetnew</ibibopartner>
                <duration>3h 50m</duration>
                <platingcarrier/>
                <qtype/>
                <arrterminal>1</arrterminal>
                <flightno>11</flightno>
                <destination>DXB</destination>
                <FlHash>oSG-11oSG-12</FlHash>
                <stops>0</stops>
                <seatsavailable>1</seatsavailable>
                <carrierid>SG</carrierid>
                <airline>Spicejet</airline>
                <provider/>
                <PromotionId/>
                <fare>
                    <grossamount>24114</grossamount>
                    <totalbasefare>20941</totalbasefare>
                    <adultbasefare>20941</adultbasefare>
                    <totalfare>24114</totalfare>
                    <totalsurcharge>0</totalsurcharge>
                    <adulttotalfare>24114</adulttotalfare>
                    <totalcommission/>
                </fare>
                <CabinClass/>
                <returnfl>
                    <resource>
                        <origin>DXB</origin>
                        <rating>0</rating>
                        <DepartureTime/>
                        <flightcode/>
                        <Group/>
                        <farebasis>KRTSAVER</farebasis>
                        <depterminal>1</depterminal>
                        <holdflag/>
                        <CINFO>air-DEL-DXB-20190701-20190702-1-0-0-E-100--</CINFO>
                        <deptime>22:45</deptime>
                        <codeshare/>
                        <ibibopartner>spicejetnew</ibibopartner>
                        <duration>3h 20m</duration>
                        <platingcarrier/>
                        <qtype/>
                        <arrterminal>3</arrterminal>
                        <flightno>12</flightno>
                        <destination>DEL</destination>
                        <FlHash>SG-12</FlHash>
                        <stops>0</stops>
                        <seatsavailable>1</seatsavailable>
                        <carrierid>SG</carrierid>
                        <airline>Spicejet</airline>
                        <provider/>
                        <PromotionId/>
                        <fare>
                            <totalsurcharge>0</totalsurcharge>
                            <totalfare>0</totalfare>
                            <totalbasefare>0</totalbasefare>
                            <totalcommission>0</totalcommission>
                        </fare>
                        <CabinClass/>
                        <warnings>Refundable</warnings>
                        <BookabilityValue>4.8372793</BookabilityValue>
                        <ArrivalTime/>
                        <onwardflights/>
                        <aircraftType>737</aircraftType>
                        <operatingcarrier/>
                        <src/>
                        <internationalsearch>true</internationalsearch>
                        <aircraftTypecode>189</aircraftTypecode>
                        <splitduration>3h 20m</splitduration>
                        <searchKey>0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0:0</searchKey>
                        <bookingclass>K</bookingclass>
                        <SetTime>2019-06-12 11:32:59</SetTime>
                        <DataSource>spicejetnew</DataSource>
                        <multicitysearch/>
                        <depdate>2019-07-02t2245</depdate>
                        <arrtime>03:35</arrtime>
                        <arrdate>2019-07-03t0335</arrdate>
                        <CacheKey>DXBDEL20190702ESGR</CacheKey>
                        <TravelTime/>
                    </resource>
                </returnfl>
                <warnings>Refundable</warnings>
                <BookabilityValue>0.7310451</BookabilityValue>
                <ArrivalTime/>
                <onwardflights/>
                <aircraftType>737</aircraftType>
                <seatingclass>E</seatingclass>
                <operatingcarrier/>
                <src/>
                <internationalsearch>true</internationalsearch>
                <aircraftTypecode>189</aircraftTypecode>
                <splitduration>3h 50m</splitduration>
                <searchKey>0:0:0:0:0:20941:0:24114:0:0:0:0:0:0:0:0:24114:20941:24114:0:0:0:0:0:0</searchKey>
                <bookingclass>A</bookingclass>
                <SetTime>2019-06-12 11:38:59</SetTime>
                <DataSource>spicejetnew</DataSource>
                <multicitysearch/>
                <depdate>2019-07-01t0750</depdate>
                <arrtime>10:10</arrtime>
                <arrdate>2019-07-01t1010</arrdate>
                <CacheKey>DELDXB20190701ESGO</CacheKey>
                <TravelTime/>
            </resource>
        </onwardflights>
    </data>
</response>
```

let's explore the additional changes available in the international roundtrip response.

Key | Description
--------- | -----------
returnflights | always empty list in case of international roundtrip
fare | Fare details about the roundtrip will be available inside this key. The details about the all keys are as given above column.
internationalsearch | true or false possible values
returnfl | as mentioned earlier this key consists of return flight details values.The length of this dict will remain one. If return flight is non direct flight onwardflight dict will present inside the `returnfl` key. `fare` dict and `searchkey`  values inside returnfl will be empty, consider the fare key inside parent `onwardflights`.


## Flights Reprice

Repricing of flight data is essential prior to booking, the fare dictionary for any flight is returned upon calling this API. It makes use of tentative booking data and is called upon automatically before any tentative booking is made.

Same API can be used to reschedule a booking. Additional three parameters (bookingId, psg_onward, psg_return) should be added for rescheduling. It will return reschedule_breakup in response which shows total reschedule charges, total amount paid and total refund amount. 
If there is some error in calculating airline charges, reschedule_breakup will return following message in response:
"There was some error in calculating reschdelule charges and refund amount. You can not perform online rescheduling for this booking."
Parameter psg_onward ensures onward resheduling, psg_return ensures return rescheduling and both parameters reschedules both the segments for the passengers you have mentioned in these parameters.
A discounted roundtrip booking will be considered as one segment and this booking is not eligible for segment rescheduling.
Your ticket is not eligible for online rescheduling if it expires in 24 hours. 
A family fare booking is not eligible for pax rescheduling (you have to reschedule all the passengers at a time). 

### HTTP Request Example

`POST ENV/api/reprice/`

* bookingdata : `[{"Search data dictionary"}]`
* querydata : `{"origin": "DEL", "adults": "1", "destination": "BLR", "infants": "0", "depdate": "2019-07-29", "children": "0"}`
* fare : `2798`
* searchKey_onward : `0:0:0:0:0:2267:0:2798:0:0:0:0:0:0:0:0:2798:2267:2798:0:0:0:0:0:0`

<aside class="notice">
Reprice API require a POST HTTP Call. To hit this API user has to provide <code>bookingdata</code> <code>querydata</code> <code>fare</code> <code>searchKey_onward</code> in HTTP request Body.
</aside>

> The above POST request will give response like this:

```json
    {
    "data": {
        "onwardflights": [
            {
                "origin": "DEL",
                "fare": {
                    "totalsbct": 0,
                    "adultothers": 165,
                    "totalsurcharge": 0,
                    "adulttotalfare": 2798,
                    "totalcommission": 0,
                    "adultbasefare": 2267,
                    "spicejetnewgrossamount": 2798,
                    "totalpassengerhandlingfee": 0,
                    "totalsvct": 0,
                    "adultpassengerservicefee": 244,
                    "totalpassengerservicefee": 244,
                    "totalothers": 165,
                    "childtotalfare": 0,
                    "totalkkc": 0,
                    "totalbasefare": 2267,
                    "adultcgst": 61,
                    "totalfare": 2798,
                    "discount": 0,
                    "totaludf": 0,
                    "adultsgst": 61,
                    "totalservicetax": 0,
                    "totaljn": 0,
                    "totalchandlingfee": 0,
                    "transactionfee": 0
                },
                "flightcode": "191",
                "farebasis": "P1",
                "spicestatus": "Normal",
                "carrier_id": "SG",
                "deptime": "06:10",
                "duration": "2h 50m",
                "ibibopartner": "spicejetnew",
                "productclass": "SS",
                "carriercode": "SG",
                "ruleno": "1111",
                "qtype": "fbs",
                "tickettype": "e",
                "flightno": "191",
                "servicetype": "",
                "fareclass": "P1",
                "faresequence": "18",
                "destination": "BLR",
                "depterminal": "1D",
                "isallotmentmarketfare": "false",
                "stops": "0",
                "seatsavailable": "1",
                "carrierid": "SG",
                "arrterminal": "-",
                "EticketFlag": "false",
                "journeysellkey": "SG~ 191~ ~~DEL~07/29/2019 06:10~BLR~07/29/2019 09:00~~",
                "fareapptype": "Route",
                "state": "New",
                "company": "",
                "warnings": "Refundable",
                "onwardflights": [],
                "aircraftType": "737",
                "seatingclass": "E",
                "promotionText": "",
                "faresellkey": "0~P1~ ~SG~P1~1111~~0~18~~X",
                "std": "2019-07-29t0610",
                "aircraftTypecode": "",
                "dotentative": "true",
                "sta": "2019-07-29t0900",
                "ssrcode_baggage": [
                    {
                        "fare": 300,
                        "code": "PRCP",
                        "weight": 0,
                        "desc": "Priority Check-In"
                    },
                    {
                        "fare": 750,
                        "code": "LNGS",
                        "weight": 0,
                        "desc": "Lounge Access"
                    },
                    {
                        "fare": 250,
                        "code": "EXCB",
                        "weight": 0,
                        "desc": "Carry More On Board"
                    },
                    {
                        "fare": 11400,
                        "code": "EB30",
                        "weight": 30,
                        "desc": "Excess Baggage 30 Kgs"
                    },
                    {
                        "fare": 7600,
                        "code": "EB20",
                        "weight": 20,
                        "desc": "Excess Baggage 20 Kgs"
                    },
                    {
                        "fare": 5700,
                        "code": "EB15",
                        "weight": 15,
                        "desc": "Excess Baggage 15 Kgs"
                    },
                    {
                        "fare": 3800,
                        "code": "EB10",
                        "weight": 10,
                        "desc": "Excess Baggage 10 Kgs"
                    },
                    {
                        "fare": 1900,
                        "code": "EB05",
                        "weight": 5,
                        "desc": "Excess Baggage 5 Kgs"
                    },
                    {
                        "fare": 300,
                        "code": "BOF3",
                        "weight": 0,
                        "desc": "Priority Baggage Out 3 Bag"
                    },
                    {
                        "fare": 200,
                        "code": "BOF2",
                        "weight": 0,
                        "desc": "Priority Baggage Out 2 Bag"
                    },
                    {
                        "fare": 100,
                        "code": "BOF1",
                        "weight": 0,
                        "desc": "Priority Baggage Out 1 Bag"
                    }
                ],
                "splitduration": "2h 50m",
                "farerule": "",
                "searchKey": "0:0:0:0:0:2267.0:244.0:2798.0:0:0:0:0:0:0:0:0.0:2798.0:2267.0:2798.0:0:0.0:0:0:0.0:0:",
                "ssrcode_meal": [
                    {
                        "fare": 144,
                        "code": "VGSW2",
                        "desc": "Spinach, Corn And Cheese Sandwich In Marble Bread"
                    },
                    {
                        "fare": 220,
                        "code": "VGMLS2",
                        "desc": "Chilli Paneer With Vegetable Fried Rice"
                    },
                    {
                        "fare": 240,
                        "code": "VCC2",
                        "desc": "Vegetable In Red Thai Curry With Steamed Rice"
                    },
                    {
                        "fare": 144,
                        "code": "NVSW2",
                        "desc": "Malai Chicken Tikka  Sandwich In Marble Bread"
                    },
                    {
                        "fare": 220,
                        "code": "NVMLS2",
                        "desc": "Chilli Chicken With Vegetable Fried Rice"
                    },
                    {
                        "fare": 240,
                        "code": "NCC5",
                        "desc": "Tawa Fish Masala On Bed Of Steamed Rice With Tadka Masoor Dal"
                    },
                    {
                        "fare": 240,
                        "code": "NCC4",
                        "desc": "Tandoori Chicken Tangri With Chicken Haryali Tikka & Vegetable Shami Kebab"
                    },
                    {
                        "fare": 240,
                        "code": "NCC1",
                        "desc": "Grilled Chicken Breast With Mushroom Sauce, Yellow Rice, Sauteed Carrots & Beans Baton"
                    },
                    {
                        "fare": 250,
                        "code": "LCVS",
                        "desc": "Low Cal Salad Vegetarian"
                    },
                    {
                        "fare": 250,
                        "code": "LCNS",
                        "desc": "Low Cal Salad Non-Vegetarian"
                    },
                    {
                        "fare": 144,
                        "code": "JNSW",
                        "desc": "Jain Cold Sandwich (Current Cucumber And Tomato Sandwich)"
                    },
                    {
                        "fare": 280,
                        "code": "JNML",
                        "desc": "Jain Hot Meal"
                    },
                    {
                        "fare": 280,
                        "code": "GFVG",
                        "desc": "Vegetarian Gluten-Free Cold Meal (Dhokla)"
                    },
                    {
                        "fare": 280,
                        "code": "GFNV",
                        "desc": "Non-Vegetarian Gluten-Free Hot Meal"
                    },
                    {
                        "fare": 280,
                        "code": "GFCM",
                        "desc": "Vegetarian Gluten-Free Cold Meal (Dhokla)"
                    },
                    {
                        "fare": 280,
                        "code": "FPML",
                        "desc": "Fruit Platter"
                    },
                    {
                        "fare": 280,
                        "code": "DNVL",
                        "desc": "Non-Vegetarian Diabetic Hot Meal"
                    },
                    {
                        "fare": 280,
                        "code": "DBML",
                        "desc": "Vegetarian Diabetic Hot Meal"
                    },
                    {
                        "fare": 280,
                        "code": "CHML",
                        "desc": "Kid'S Meal"
                    }
                ],
                "airline": "spicejet",
                "classofservice": "P1",
                "rowbody": " ",
                "depdate": "2019-07-29t0610",
                "arrtime": "09:00",
                "arrdate": "2019-07-29t0900"
            }
        ],
        "faredict": {
            "kbb": "Y9Rz8g==",
            "totalsurcharge": 0,
            "passengercount": "1",
            "netpayable": 2798,
            "repriceloss": 0,
            "tokenec": "5874c91f89a1e03ec45a8736334e0782",
            "lead_message": "",
            "isfamilyfare": false,
            "promocode": "",
            "totalbasefare": 2267,
            "kb": "temp",
            "totalfare": 2798,
            "goibibofee": 0,
            "credits": "False",
            "transactionfee": 0,
            "leaddiscount": 0,
            "premiermiles": 0,
            "fuelsurcharge": 0,
            "leadcode": "",
            "discount": 0,
            "dob": false,
            "k": "temp",
            "promo_message": "",
            "promodiscount": 0,
            "leadlist": []
        },
        "active_offers": [],
        "review_screen_text": []
    },
    "data_length": 4
}
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<response>
    <data>
        <onwardflights>
            <resource>
                <origin>DEL</origin>
                <fare>
                    <totalsbct>0.0</totalsbct>
                    <adultothers>165.0</adultothers>
                    <totalsurcharge>0.0</totalsurcharge>
                    <adulttotalfare>2798.0</adulttotalfare>
                    <totalcommission>0.0</totalcommission>
                    <adultbasefare>2267.0</adultbasefare>
                    <spicejetnewgrossamount>2798.0</spicejetnewgrossamount>
                    <totalpassengerhandlingfee>0.0</totalpassengerhandlingfee>
                    <totalsvct>0.0</totalsvct>
                    <adultpassengerservicefee>244.0</adultpassengerservicefee>
                    <totalpassengerservicefee>244.0</totalpassengerservicefee>
                    <totalothers>165.0</totalothers>
                    <childtotalfare>0.0</childtotalfare>
                    <totalkkc>0.0</totalkkc>
                    <totalbasefare>2267.0</totalbasefare>
                    <adultcgst>61.0</adultcgst>
                    <totalfare>2798.0</totalfare>
                    <discount>0</discount>
                    <totaludf>0.0</totaludf>
                    <adultsgst>61.0</adultsgst>
                    <totalservicetax>0</totalservicetax>
                    <totaljn>0.0</totaljn>
                    <totalchandlingfee>0.0</totalchandlingfee>
                    <transactionfee>0</transactionfee>
                </fare>
                <flightcode>191</flightcode>
                <farebasis>P1</farebasis>
                <spicestatus>Normal</spicestatus>
                <carrier_id>SG</carrier_id>
                <deptime>06:10</deptime>
                <duration>2h 50m</duration>
                <ibibopartner>spicejetnew</ibibopartner>
                <productclass>SS</productclass>
                <carriercode>SG</carriercode>
                <ruleno>1111</ruleno>
                <qtype>fbs</qtype>
                <tickettype>e</tickettype>
                <flightno>191</flightno>
                <servicetype></servicetype>
                <fareclass>P1</fareclass>
                <faresequence>18</faresequence>
                <destination>BLR</destination>
                <depterminal>1D</depterminal>
                <isallotmentmarketfare>false</isallotmentmarketfare>
                <stops>0</stops>
                <seatsavailable>1</seatsavailable>
                <carrierid>SG</carrierid>
                <arrterminal>-</arrterminal>
                <EticketFlag>false</EticketFlag>
                <journeysellkey>SG~ 191~ ~~DEL~07/29/2019 06:10~BLR~07/29/2019 09:00~~</journeysellkey>
                <fareapptype>Route</fareapptype>
                <state>New</state>
                <company></company>
                <warnings>Refundable</warnings>
                <onwardflights></onwardflights>
                <aircraftType>737</aircraftType>
                <seatingclass>E</seatingclass>
                <promotionText></promotionText>
                <faresellkey>0~P1~ ~SG~P1~1111~~0~18~~X</faresellkey>
                <std>2019-07-29t0610</std>
                <aircraftTypecode></aircraftTypecode>
                <dotentative>true</dotentative>
                <sta>2019-07-29t0900</sta>
                <ssrcode_baggage>
                    <resource>
                        <fare>300.0</fare>
                        <code>PRCP</code>
                        <weight>0</weight>
                        <desc>Priority Check-In</desc>
                    </resource>
                    <resource>
                        <fare>750.0</fare>
                        <code>LNGS</code>
                        <weight>0</weight>
                        <desc>Lounge Access</desc>
                    </resource>
                    <resource>
                        <fare>250.0</fare>
                        <code>EXCB</code>
                        <weight>0</weight>
                        <desc>Carry More On Board</desc>
                    </resource>
                    <resource>
                        <fare>11400.0</fare>
                        <code>EB30</code>
                        <weight>30</weight>
                        <desc>Excess Baggage 30 Kgs</desc>
                    </resource>
                    <resource>
                        <fare>7600.0</fare>
                        <code>EB20</code>
                        <weight>20</weight>
                        <desc>Excess Baggage 20 Kgs</desc>
                    </resource>
                    <resource>
                        <fare>5700.0</fare>
                        <code>EB15</code>
                        <weight>15</weight>
                        <desc>Excess Baggage 15 Kgs</desc>
                    </resource>
                    <resource>
                        <fare>3800.0</fare>
                        <code>EB10</code>
                        <weight>10</weight>
                        <desc>Excess Baggage 10 Kgs</desc>
                    </resource>
                    <resource>
                        <fare>1900.0</fare>
                        <code>EB05</code>
                        <weight>5</weight>
                        <desc>Excess Baggage 5 Kgs</desc>
                    </resource>
                    <resource>
                        <fare>300.0</fare>
                        <code>BOF3</code>
                        <weight>0</weight>
                        <desc>Priority Baggage Out 3 Bag</desc>
                    </resource>
                    <resource>
                        <fare>200.0</fare>
                        <code>BOF2</code>
                        <weight>0</weight>
                        <desc>Priority Baggage Out 2 Bag</desc>
                    </resource>
                    <resource>
                        <fare>100.0</fare>
                        <code>BOF1</code>
                        <weight>0</weight>
                        <desc>Priority Baggage Out 1 Bag</desc>
                    </resource>
                </ssrcode_baggage>
                <splitduration>2h 50m</splitduration>
                <farerule></farerule>
                <searchKey>0:0:0:0:0:2267.0:244.0:2798.0:0:0:0:0:0:0:0:0.0:2798.0:2267.0:2798.0:0:0.0:0:0:0.0:0:</searchKey>
                <ssrcode_meal>
                    <resource>
                        <fare>144.0</fare>
                        <code>VGSW2</code>
                        <desc>Spinach, Corn And Cheese Sandwich In Marble Bread</desc>
                    </resource>
                    <resource>
                        <fare>220.0</fare>
                        <code>VGMLS2</code>
                        <desc>Chilli Paneer With Vegetable Fried Rice</desc>
                    </resource>
                    <resource>
                        <fare>240.0</fare>
                        <code>VCC2</code>
                        <desc>Vegetable In Red Thai Curry With Steamed Rice</desc>
                    </resource>
                    <resource>
                        <fare>144.0</fare>
                        <code>NVSW2</code>
                        <desc>Malai Chicken Tikka  Sandwich In Marble Bread</desc>
                    </resource>
                    <resource>
                        <fare>220.0</fare>
                        <code>NVMLS2</code>
                        <desc>Chilli Chicken With Vegetable Fried Rice</desc>
                    </resource>
                    <resource>
                        <fare>240.0</fare>
                        <code>NCC5</code>
                        <desc>Tawa Fish Masala On Bed Of Steamed Rice With Tadka Masoor Dal</desc>
                    </resource>
                    <resource>
                        <fare>240.0</fare>
                        <code>NCC4</code>
                        <desc>Tandoori Chicken Tangri With Chicken Haryali Tikka &amp; Vegetable Shami Kebab</desc>
                    </resource>
                    <resource>
                        <fare>240.0</fare>
                        <code>NCC1</code>
                        <desc>Grilled Chicken Breast With Mushroom Sauce, Yellow Rice, Sauteed Carrots &amp; Beans Baton</desc>
                    </resource>
                    <resource>
                        <fare>250.0</fare>
                        <code>LCVS</code>
                        <desc>Low Cal Salad Vegetarian</desc>
                    </resource>
                    <resource>
                        <fare>250.0</fare>
                        <code>LCNS</code>
                        <desc>Low Cal Salad Non-Vegetarian</desc>
                    </resource>
                    <resource>
                        <fare>144.0</fare>
                        <code>JNSW</code>
                        <desc>Jain Cold Sandwich (Current Cucumber And Tomato Sandwich)</desc>
                    </resource>
                    <resource>
                        <fare>280.0</fare>
                        <code>JNML</code>
                        <desc>Jain Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>280.0</fare>
                        <code>GFVG</code>
                        <desc>Vegetarian Gluten-Free Cold Meal (Dhokla)</desc>
                    </resource>
                    <resource>
                        <fare>280.0</fare>
                        <code>GFNV</code>
                        <desc>Non-Vegetarian Gluten-Free Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>280.0</fare>
                        <code>GFCM</code>
                        <desc>Vegetarian Gluten-Free Cold Meal (Dhokla)</desc>
                    </resource>
                    <resource>
                        <fare>280.0</fare>
                        <code>FPML</code>
                        <desc>Fruit Platter</desc>
                    </resource>
                    <resource>
                        <fare>280.0</fare>
                        <code>DNVL</code>
                        <desc>Non-Vegetarian Diabetic Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>280.0</fare>
                        <code>DBML</code>
                        <desc>Vegetarian Diabetic Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>280.0</fare>
                        <code>CHML</code>
                        <desc>Kid'S Meal</desc>
                    </resource>
                </ssrcode_meal>
                <airline>spicejet</airline>
                <classofservice>P1</classofservice>
                <rowbody> </rowbody>
                <depdate>2019-07-29t0610</depdate>
                <arrtime>09:00</arrtime>
                <arrdate>2019-07-29t0900</arrdate>
            </resource>
        </onwardflights>
        <faredict>
            <kbb>Y9Rz8g==</kbb>
            <totalsurcharge>0</totalsurcharge>
            <passengercount>1</passengercount>
            <netpayable>2798</netpayable>
            <repriceloss>0</repriceloss>
            <tokenec>5874c91f89a1e03ec45a8736334e0782</tokenec>
            <lead_message></lead_message>
            <isfamilyfare>False</isfamilyfare>
            <promocode></promocode>
            <totalbasefare>2267</totalbasefare>
            <kb>temp</kb>
            <totalfare>2798</totalfare>
            <goibibofee>0</goibibofee>
            <credits>False</credits>
            <transactionfee>0</transactionfee>
            <leaddiscount>0</leaddiscount>
            <premiermiles>0</premiermiles>
            <fuelsurcharge>0</fuelsurcharge>
            <leadcode></leadcode>
            <discount>0</discount>
            <dob>False</dob>
            <k>temp</k>
            <promo_message></promo_message>
            <promodiscount>0</promodiscount>
            <leadlist></leadlist>
        </faredict>
        <active_offers></active_offers>
        <review_screen_text></review_screen_text>
    </data>
    <data_length>4</data_length>
</response>
```
> For internatinal Round trip refer this response

```json
    {
    "data": {
        "returnflights": [
            {
                "origin": "DXB",
                "fare": {
                    "totalsbct": 0,
                    "adultothers": 857,
                    "totalsurcharge": 0,
                    "adulttotalfare": 9561,
                    "totalcommission": 0,
                    "adultbasefare": 7191,
                    "spicejetnewgrossamount": 9561,
                    "totalpassengerhandlingfee": 0,
                    "adultudf": 95,
                    "totalsvct": 0,
                    "adultpassengerservicefee": 1418,
                    "totalpassengerservicefee": 1418,
                    "totalothers": 857,
                    "childtotalfare": 0,
                    "totalkkc": 0,
                    "totalbasefare": 7191,
                    "totalfare": 9561,
                    "discount": 0,
                    "totaludf": 95,
                    "transactionfee": 0,
                    "totalservicetax": 0,
                    "totaljn": 0,
                    "totalchandlingfee": 0
                },
                "flightcode": "12",
                "farebasis": "CRTSAVER",
                "spicestatus": "Normal",
                "carrier_id": "SG",
                "deptime": "22:45",
                "duration": "3h 20m",
                "ibibopartner": "spicejetnew",
                "discountedreturnfaresearch": "Y",
                "productclass": "XA",
                "carriercode": "SG",
                "ruleno": "3002",
                "qtype": "fbs",
                "tickettype": "e",
                "flightno": "12",
                "servicetype": "",
                "fareclass": "C",
                "faresequence": "8",
                "destination": "DEL",
                "depterminal": "1",
                "isallotmentmarketfare": "false",
                "stops": "0",
                "seatsavailable": "1",
                "carrierid": "SG",
                "arrterminal": "3",
                "EticketFlag": "false",
                "journeysellkey": "SG~  12~ ~~DXB~07/30/2019 22:45~DEL~07/31/2019 03:35~~",
                "fareapptype": "Route",
                "state": "New",
                "warnings": "Refundable",
                "onwardflights": [],
                "aircraftType": "737",
                "seatingclass": "E",
                "promotionText": "",
                "faresellkey": "0~C~ ~SG~CRTSAVER~3002~~0~8~~X",
                "std": "2019-07-30t2245",
                "aircraftTypecode": "",
                "internationalsearch": "true",
                "dotentative": "true",
                "sta": "2019-07-31t0335",
                "ssrcode_baggage": [
                    {
                        "fare": 400,
                        "code": "PRCP",
                        "weight": 0,
                        "desc": "Priority Check-In"
                    },
                    {
                        "fare": 450,
                        "code": "EXCB",
                        "weight": 0,
                        "desc": "Carry More On Board"
                    },
                    {
                        "fare": 4950,
                        "code": "EB10",
                        "weight": 10,
                        "desc": "Excess Baggage 10 Kgs"
                    },
                    {
                        "fare": 2475,
                        "code": "EB05",
                        "weight": 5,
                        "desc": "Excess Baggage 5 Kgs"
                    }
                ],
                "splitduration": "3h 20m",
                "farerule": "",
                "searchKey": "0:0:95.0:0:0:7191.0:1418.0:9561.0:0:0:0:0:0:0:0:0.0:9561.0:7191.0:9561.0:0:0.0:0:0:0.0:0",
                "ssrcode_meal": [
                    {
                        "fare": 196,
                        "code": "VGSW3",
                        "desc": "Vegetable Junglee Sandwich In White Bread"
                    },
                    {
                        "fare": 316,
                        "code": "VGMLS3",
                        "desc": "Kadai Paneer Khurchan With Masala Kulcha"
                    },
                    {
                        "fare": 360,
                        "code": "VCC2",
                        "desc": "Vegetable In Red Thai Curry With Steamed Rice"
                    },
                    {
                        "fare": 196,
                        "code": "NVSW3",
                        "desc": "Roast Chicken, Sundried Tomato And Basil Sandwich In Marble Bread"
                    },
                    {
                        "fare": 316,
                        "code": "NVMLS3",
                        "desc": "Chicken Khurchan With Aloo Parantha With Vegetable Kebab"
                    },
                    {
                        "fare": 360,
                        "code": "NCC5",
                        "desc": "Tawa Fish Masala On Bed Of Steamed Rice With Tadka Masoor Dal"
                    },
                    {
                        "fare": 360,
                        "code": "NCC4",
                        "desc": "Tandoori Chicken Tangri With Chicken Haryali Tikka & Vegetable Shami Kebab"
                    },
                    {
                        "fare": 360,
                        "code": "NCC1",
                        "desc": "Grilled Chicken Breast With Mushroom Sauce, Yellow Rice, Sauteed Carrots & Beans Baton"
                    },
                    {
                        "fare": 300,
                        "code": "LCVS",
                        "desc": "Low Cal Salad Vegetarian"
                    },
                    {
                        "fare": 300,
                        "code": "LCNS",
                        "desc": "Low Cal Salad Non-Vegetarian"
                    },
                    {
                        "fare": 196,
                        "code": "JNSW",
                        "desc": "Jain Cold Sandwich (Current Cucumber And Tomato Sandwich)"
                    },
                    {
                        "fare": 320,
                        "code": "JNML",
                        "desc": "Jain Hot Meal"
                    },
                    {
                        "fare": 320,
                        "code": "GFVG",
                        "desc": "Vegetarian Gluten-Free Cold Meal (Dhokla)"
                    },
                    {
                        "fare": 320,
                        "code": "GFNV",
                        "desc": "Non-Vegetarian Gluten-Free Hot Meal"
                    },
                    {
                        "fare": 320,
                        "code": "GFCM",
                        "desc": "Vegetarian Gluten-Free Cold Meal (Dhokla)"
                    },
                    {
                        "fare": 320,
                        "code": "FPML",
                        "desc": "Fruit Platter"
                    },
                    {
                        "fare": 320,
                        "code": "DNVL",
                        "desc": "Non-Vegetarian Diabetic Hot Meal"
                    },
                    {
                        "fare": 320,
                        "code": "DBML",
                        "desc": "Vegetarian Diabetic Hot Meal"
                    },
                    {
                        "fare": 320,
                        "code": "CHML",
                        "desc": "Kid'S Meal"
                    }
                ],
                "airline": "spicejet",
                "classofservice": "C",
                "rowbody": " ",
                "depdate": "2019-07-30t2245",
                "arrtime": "03:35",
                "arrdate": "2019-07-31t0335"
            }
        ],
        "onwardflights": [
            {
                "origin": "DEL",
                "fare": {
                    "totalsbct": 0,
                    "adultothers": 195,
                    "totalsurcharge": 0,
                    "adulttotalfare": 7427,
                    "totalcommission": 0,
                    "adultbasefare": 6650,
                    "spicejetnewgrossamount": 7427,
                    "totalpassengerhandlingfee": 0,
                    "totalsvct": 0,
                    "adultpassengerservicefee": 244,
                    "totalpassengerservicefee": 244,
                    "totalothers": 195,
                    "childtotalfare": 0,
                    "totalkkc": 0,
                    "totalbasefare": 6650,
                    "adultcgst": 169,
                    "totalfare": 7427,
                    "discount": 0,
                    "totaludf": 0,
                    "adultsgst": 169,
                    "totalservicetax": 0,
                    "totaljn": 0,
                    "totalchandlingfee": 0,
                    "transactionfee": 0
                },
                "flightcode": "11",
                "farebasis": "VRTSAVER",
                "spicestatus": "Normal",
                "carrier_id": "SG",
                "deptime": "07:50",
                "duration": "3h 50m",
                "ibibopartner": "spicejetnew",
                "discountedreturnfaresearch": "Y",
                "productclass": "XA",
                "carriercode": "SG",
                "ruleno": "3002",
                "qtype": "fbs",
                "tickettype": "e",
                "flightno": "11",
                "servicetype": "",
                "fareclass": "V",
                "faresequence": "8",
                "destination": "DXB",
                "depterminal": "3",
                "isallotmentmarketfare": "false",
                "stops": "0",
                "seatsavailable": "1",
                "carrierid": "SG",
                "arrterminal": "1",
                "EticketFlag": "false",
                "journeysellkey": "SG~  11~ ~~DEL~07/29/2019 07:50~DXB~07/29/2019 10:10~~",
                "fareapptype": "Route",
                "state": "New",
                "company": "",
                "warnings": "Refundable",
                "onwardflights": [],
                "aircraftType": "737",
                "seatingclass": "E",
                "promotionText": "",
                "faresellkey": "0~V~ ~SG~VRTSAVER~3002~~0~8~~X",
                "std": "2019-07-29t0750",
                "aircraftTypecode": "",
                "internationalsearch": "true",
                "dotentative": "true",
                "sta": "2019-07-29t1010",
                "ssrcode_baggage": [
                    {
                        "fare": 400,
                        "code": "PRCP",
                        "weight": 0,
                        "desc": "Priority Check-In"
                    },
                    {
                        "fare": 1400,
                        "code": "LNGS",
                        "weight": 0,
                        "desc": "Lounge Access"
                    },
                    {
                        "fare": 450,
                        "code": "EXCB",
                        "weight": 0,
                        "desc": "Carry More On Board"
                    },
                    {
                        "fare": 4950,
                        "code": "EB10",
                        "weight": 10,
                        "desc": "Excess Baggage 10 Kgs"
                    },
                    {
                        "fare": 2475,
                        "code": "EB05",
                        "weight": 5,
                        "desc": "Excess Baggage 5 Kgs"
                    }
                ],
                "splitduration": "3h 50m",
                "farerule": "",
                "searchKey": "0:0:0:0:0:6650.0:244.0:7427.0:0:0:0:0:0:0:0:0.0:7427.0:6650.0:7427.0:0:0.0:0:0:0.0:0:",
                "ssrcode_meal": [
                    {
                        "fare": 196,
                        "code": "VGSW3",
                        "desc": "Vegetable Junglee Sandwich In White Bread"
                    },
                    {
                        "fare": 316,
                        "code": "VGMLS3",
                        "desc": "Kadai Paneer Khurchan With Masala Kulcha"
                    },
                    {
                        "fare": 360,
                        "code": "VCC2",
                        "desc": "Vegetable In Red Thai Curry With Steamed Rice"
                    },
                    {
                        "fare": 196,
                        "code": "NVSW3",
                        "desc": "Roast Chicken, Sundried Tomato And Basil Sandwich In Marble Bread"
                    },
                    {
                        "fare": 316,
                        "code": "NVMLS3",
                        "desc": "Chicken Khurchan With Aloo Parantha With Vegetable Kebab"
                    },
                    {
                        "fare": 360,
                        "code": "NCC5",
                        "desc": "Tawa Fish Masala On Bed Of Steamed Rice With Tadka Masoor Dal"
                    },
                    {
                        "fare": 360,
                        "code": "NCC4",
                        "desc": "Tandoori Chicken Tangri With Chicken Haryali Tikka & Vegetable Shami Kebab"
                    },
                    {
                        "fare": 360,
                        "code": "NCC1",
                        "desc": "Grilled Chicken Breast With Mushroom Sauce, Yellow Rice, Sauteed Carrots & Beans Baton"
                    },
                    {
                        "fare": 300,
                        "code": "LCVS",
                        "desc": "Low Cal Salad Vegetarian"
                    },
                    {
                        "fare": 300,
                        "code": "LCNS",
                        "desc": "Low Cal Salad Non-Vegetarian"
                    },
                    {
                        "fare": 196,
                        "code": "JNSW",
                        "desc": "Jain Cold Sandwich (Current Cucumber And Tomato Sandwich)"
                    },
                    {
                        "fare": 320,
                        "code": "JNML",
                        "desc": "Jain Hot Meal"
                    },
                    {
                        "fare": 320,
                        "code": "GFVG",
                        "desc": "Vegetarian Gluten-Free Cold Meal (Dhokla)"
                    },
                    {
                        "fare": 320,
                        "code": "GFNV",
                        "desc": "Non-Vegetarian Gluten-Free Hot Meal"
                    },
                    {
                        "fare": 320,
                        "code": "GFCM",
                        "desc": "Vegetarian Gluten-Free Cold Meal (Dhokla)"
                    },
                    {
                        "fare": 320,
                        "code": "FPML",
                        "desc": "Fruit Platter"
                    },
                    {
                        "fare": 320,
                        "code": "DNVL",
                        "desc": "Non-Vegetarian Diabetic Hot Meal"
                    },
                    {
                        "fare": 320,
                        "code": "DBML",
                        "desc": "Vegetarian Diabetic Hot Meal"
                    },
                    {
                        "fare": 320,
                        "code": "CHML",
                        "desc": "Kid'S Meal"
                    }
                ],
                "airline": "spicejet",
                "classofservice": "V",
                "rowbody": " ",
                "depdate": "2019-07-29t0750",
                "arrtime": "10:10",
                "arrdate": "2019-07-29t1010"
            }
        ],
        "faredict": {
            "kbb": "Z9hy6w==",
            "totalsurcharge": 0,
            "passengercount": "1",
            "netpayable": 16988,
            "tokenec": "985cb6698e365ff02bb60b03316d4c81",
            "passport": false,
            "international": "true",
            "lead_message": "",
            "fare_diff": -526,
            "isfamilyfare": false,
            "promocode": "",
            "totalbasefare": 6650,
            "kb": "temp",
            "totalfare": 16988,
            "goibibofee": 0,
            "credits": "False",
            "transactionfee": 0,
            "leaddiscount": 0,
            "premiermiles": 0,
            "fuelsurcharge": 0,
            "leadcode": "",
            "discount": 0,
            "dob": false,
            "k": "temp",
            "promo_message": "",
            "promodiscount": 0,
            "leadlist": []
        },
        "active_offers": [],
        "review_screen_text": []
    },
    "data_length": 5
}

```
```xml
<?xml version="1.0" encoding="utf-8"?>
<response>
    <data>
        <returnflights>
            <resource>
                <origin>DXB</origin>
                <fare>
                    <totalsbct>0.0</totalsbct>
                    <adultothers>857.0</adultothers>
                    <totalsurcharge>0.0</totalsurcharge>
                    <adulttotalfare>9561.0</adulttotalfare>
                    <totalcommission>0.0</totalcommission>
                    <adultbasefare>7191.0</adultbasefare>
                    <spicejetnewgrossamount>9561.0</spicejetnewgrossamount>
                    <totalpassengerhandlingfee>0.0</totalpassengerhandlingfee>
                    <adultudf>95.0</adultudf>
                    <totalsvct>0.0</totalsvct>
                    <adultpassengerservicefee>1418.0</adultpassengerservicefee>
                    <totalpassengerservicefee>1418.0</totalpassengerservicefee>
                    <totalothers>857.0</totalothers>
                    <childtotalfare>0.0</childtotalfare>
                    <totalkkc>0.0</totalkkc>
                    <totalbasefare>7191.0</totalbasefare>
                    <totalfare>9561.0</totalfare>
                    <discount>0</discount>
                    <totaludf>95.0</totaludf>
                    <transactionfee>0</transactionfee>
                    <totalservicetax>0</totalservicetax>
                    <totaljn>0.0</totaljn>
                    <totalchandlingfee>0.0</totalchandlingfee>
                </fare>
                <flightcode>12</flightcode>
                <farebasis>CRTSAVER</farebasis>
                <spicestatus>Normal</spicestatus>
                <carrier_id>SG</carrier_id>
                <deptime>22:45</deptime>
                <duration>3h 20m</duration>
                <ibibopartner>spicejetnew</ibibopartner>
                <discountedreturnfaresearch>Y</discountedreturnfaresearch>
                <productclass>XA</productclass>
                <carriercode>SG</carriercode>
                <ruleno>3002</ruleno>
                <qtype>fbs</qtype>
                <tickettype>e</tickettype>
                <flightno>12</flightno>
                <servicetype></servicetype>
                <fareclass>C</fareclass>
                <faresequence>8</faresequence>
                <destination>DEL</destination>
                <depterminal>1</depterminal>
                <isallotmentmarketfare>false</isallotmentmarketfare>
                <stops>0</stops>
                <seatsavailable>1</seatsavailable>
                <carrierid>SG</carrierid>
                <arrterminal>3</arrterminal>
                <EticketFlag>false</EticketFlag>
                <journeysellkey>SG~  12~ ~~DXB~07/30/2019 22:45~DEL~07/31/2019 03:35~~</journeysellkey>
                <fareapptype>Route</fareapptype>
                <state>New</state>
                <warnings>Refundable</warnings>
                <onwardflights></onwardflights>
                <aircraftType>737</aircraftType>
                <seatingclass>E</seatingclass>
                <promotionText></promotionText>
                <faresellkey>0~C~ ~SG~CRTSAVER~3002~~0~8~~X</faresellkey>
                <std>2019-07-30t2245</std>
                <aircraftTypecode></aircraftTypecode>
                <internationalsearch>true</internationalsearch>
                <dotentative>true</dotentative>
                <sta>2019-07-31t0335</sta>
                <ssrcode_baggage>
                    <resource>
                        <fare>400.0</fare>
                        <code>PRCP</code>
                        <weight>0</weight>
                        <desc>Priority Check-In</desc>
                    </resource>
                    <resource>
                        <fare>450.0</fare>
                        <code>EXCB</code>
                        <weight>0</weight>
                        <desc>Carry More On Board</desc>
                    </resource>
                    <resource>
                        <fare>4950.0</fare>
                        <code>EB10</code>
                        <weight>10</weight>
                        <desc>Excess Baggage 10 Kgs</desc>
                    </resource>
                    <resource>
                        <fare>2475.0</fare>
                        <code>EB05</code>
                        <weight>5</weight>
                        <desc>Excess Baggage 5 Kgs</desc>
                    </resource>
                </ssrcode_baggage>
                <splitduration>3h 20m</splitduration>
                <farerule></farerule>
                <searchKey>0:0:95.0:0:0:7191.0:1418.0:9561.0:0:0:0:0:0:0:0:0.0:9561.0:7191.0:9561.0:0:0.0:0:0:0.0:0</searchKey>
                <ssrcode_meal>
                    <resource>
                        <fare>196.0</fare>
                        <code>VGSW3</code>
                        <desc>Vegetable Junglee Sandwich In White Bread</desc>
                    </resource>
                    <resource>
                        <fare>316.0</fare>
                        <code>VGMLS3</code>
                        <desc>Kadai Paneer Khurchan With Masala Kulcha</desc>
                    </resource>
                    <resource>
                        <fare>360.0</fare>
                        <code>VCC2</code>
                        <desc>Vegetable In Red Thai Curry With Steamed Rice</desc>
                    </resource>
                    <resource>
                        <fare>196.0</fare>
                        <code>NVSW3</code>
                        <desc>Roast Chicken, Sundried Tomato And Basil Sandwich In Marble Bread</desc>
                    </resource>
                    <resource>
                        <fare>316.0</fare>
                        <code>NVMLS3</code>
                        <desc>Chicken Khurchan With Aloo Parantha With Vegetable Kebab</desc>
                    </resource>
                    <resource>
                        <fare>360.0</fare>
                        <code>NCC5</code>
                        <desc>Tawa Fish Masala On Bed Of Steamed Rice With Tadka Masoor Dal</desc>
                    </resource>
                    <resource>
                        <fare>360.0</fare>
                        <code>NCC4</code>
                        <desc>Tandoori Chicken Tangri With Chicken Haryali Tikka &amp; Vegetable Shami Kebab</desc>
                    </resource>
                    <resource>
                        <fare>360.0</fare>
                        <code>NCC1</code>
                        <desc>Grilled Chicken Breast With Mushroom Sauce, Yellow Rice, Sauteed Carrots &amp; Beans Baton</desc>
                    </resource>
                    <resource>
                        <fare>300.0</fare>
                        <code>LCVS</code>
                        <desc>Low Cal Salad Vegetarian</desc>
                    </resource>
                    <resource>
                        <fare>300.0</fare>
                        <code>LCNS</code>
                        <desc>Low Cal Salad Non-Vegetarian</desc>
                    </resource>
                    <resource>
                        <fare>196.0</fare>
                        <code>JNSW</code>
                        <desc>Jain Cold Sandwich (Current Cucumber And Tomato Sandwich)</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>JNML</code>
                        <desc>Jain Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>GFVG</code>
                        <desc>Vegetarian Gluten-Free Cold Meal (Dhokla)</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>GFNV</code>
                        <desc>Non-Vegetarian Gluten-Free Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>GFCM</code>
                        <desc>Vegetarian Gluten-Free Cold Meal (Dhokla)</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>FPML</code>
                        <desc>Fruit Platter</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>DNVL</code>
                        <desc>Non-Vegetarian Diabetic Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>DBML</code>
                        <desc>Vegetarian Diabetic Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>CHML</code>
                        <desc>Kid'S Meal</desc>
                    </resource>
                </ssrcode_meal>
                <airline>spicejet</airline>
                <classofservice>C</classofservice>
                <rowbody> </rowbody>
                <depdate>2019-07-30t2245</depdate>
                <arrtime>03:35</arrtime>
                <arrdate>2019-07-31t0335</arrdate>
            </resource>
        </returnflights>
        <onwardflights>
            <resource>
                <origin>DEL</origin>
                <fare>
                    <totalsbct>0.0</totalsbct>
                    <adultothers>195.0</adultothers>
                    <totalsurcharge>0.0</totalsurcharge>
                    <adulttotalfare>7427.0</adulttotalfare>
                    <totalcommission>0.0</totalcommission>
                    <adultbasefare>6650.0</adultbasefare>
                    <spicejetnewgrossamount>7427.0</spicejetnewgrossamount>
                    <totalpassengerhandlingfee>0.0</totalpassengerhandlingfee>
                    <totalsvct>0.0</totalsvct>
                    <adultpassengerservicefee>244.0</adultpassengerservicefee>
                    <totalpassengerservicefee>244.0</totalpassengerservicefee>
                    <totalothers>195.0</totalothers>
                    <childtotalfare>0.0</childtotalfare>
                    <totalkkc>0.0</totalkkc>
                    <totalbasefare>6650.0</totalbasefare>
                    <adultcgst>169.0</adultcgst>
                    <totalfare>7427.0</totalfare>
                    <discount>0</discount>
                    <totaludf>0.0</totaludf>
                    <adultsgst>169.0</adultsgst>
                    <totalservicetax>0</totalservicetax>
                    <totaljn>0.0</totaljn>
                    <totalchandlingfee>0.0</totalchandlingfee>
                    <transactionfee>0</transactionfee>
                </fare>
                <flightcode>11</flightcode>
                <farebasis>VRTSAVER</farebasis>
                <spicestatus>Normal</spicestatus>
                <carrier_id>SG</carrier_id>
                <deptime>07:50</deptime>
                <duration>3h 50m</duration>
                <ibibopartner>spicejetnew</ibibopartner>
                <discountedreturnfaresearch>Y</discountedreturnfaresearch>
                <productclass>XA</productclass>
                <carriercode>SG</carriercode>
                <ruleno>3002</ruleno>
                <qtype>fbs</qtype>
                <tickettype>e</tickettype>
                <flightno>11</flightno>
                <servicetype></servicetype>
                <fareclass>V</fareclass>
                <faresequence>8</faresequence>
                <destination>DXB</destination>
                <depterminal>3</depterminal>
                <isallotmentmarketfare>false</isallotmentmarketfare>
                <stops>0</stops>
                <seatsavailable>1</seatsavailable>
                <carrierid>SG</carrierid>
                <arrterminal>1</arrterminal>
                <EticketFlag>false</EticketFlag>
                <journeysellkey>SG~  11~ ~~DEL~07/29/2019 07:50~DXB~07/29/2019 10:10~~</journeysellkey>
                <fareapptype>Route</fareapptype>
                <state>New</state>
                <company></company>
                <warnings>Refundable</warnings>
                <onwardflights></onwardflights>
                <aircraftType>737</aircraftType>
                <seatingclass>E</seatingclass>
                <promotionText></promotionText>
                <faresellkey>0~V~ ~SG~VRTSAVER~3002~~0~8~~X</faresellkey>
                <std>2019-07-29t0750</std>
                <aircraftTypecode></aircraftTypecode>
                <internationalsearch>true</internationalsearch>
                <dotentative>true</dotentative>
                <sta>2019-07-29t1010</sta>
                <ssrcode_baggage>
                    <resource>
                        <fare>400.0</fare>
                        <code>PRCP</code>
                        <weight>0</weight>
                        <desc>Priority Check-In</desc>
                    </resource>
                    <resource>
                        <fare>1400.0</fare>
                        <code>LNGS</code>
                        <weight>0</weight>
                        <desc>Lounge Access</desc>
                    </resource>
                    <resource>
                        <fare>450.0</fare>
                        <code>EXCB</code>
                        <weight>0</weight>
                        <desc>Carry More On Board</desc>
                    </resource>
                    <resource>
                        <fare>4950.0</fare>
                        <code>EB10</code>
                        <weight>10</weight>
                        <desc>Excess Baggage 10 Kgs</desc>
                    </resource>
                    <resource>
                        <fare>2475.0</fare>
                        <code>EB05</code>
                        <weight>5</weight>
                        <desc>Excess Baggage 5 Kgs</desc>
                    </resource>
                </ssrcode_baggage>
                <splitduration>3h 50m</splitduration>
                <farerule></farerule>
                <searchKey>0:0:0:0:0:6650.0:244.0:7427.0:0:0:0:0:0:0:0:0.0:7427.0:6650.0:7427.0:0:0.0:0:0:0.0:0:</searchKey>
                <ssrcode_meal>
                    <resource>
                        <fare>196.0</fare>
                        <code>VGSW3</code>
                        <desc>Vegetable Junglee Sandwich In White Bread</desc>
                    </resource>
                    <resource>
                        <fare>316.0</fare>
                        <code>VGMLS3</code>
                        <desc>Kadai Paneer Khurchan With Masala Kulcha</desc>
                    </resource>
                    <resource>
                        <fare>360.0</fare>
                        <code>VCC2</code>
                        <desc>Vegetable In Red Thai Curry With Steamed Rice</desc>
                    </resource>
                    <resource>
                        <fare>196.0</fare>
                        <code>NVSW3</code>
                        <desc>Roast Chicken, Sundried Tomato And Basil Sandwich In Marble Bread</desc>
                    </resource>
                    <resource>
                        <fare>316.0</fare>
                        <code>NVMLS3</code>
                        <desc>Chicken Khurchan With Aloo Parantha With Vegetable Kebab</desc>
                    </resource>
                    <resource>
                        <fare>360.0</fare>
                        <code>NCC5</code>
                        <desc>Tawa Fish Masala On Bed Of Steamed Rice With Tadka Masoor Dal</desc>
                    </resource>
                    <resource>
                        <fare>360.0</fare>
                        <code>NCC4</code>
                        <desc>Tandoori Chicken Tangri With Chicken Haryali Tikka &amp; Vegetable Shami Kebab</desc>
                    </resource>
                    <resource>
                        <fare>360.0</fare>
                        <code>NCC1</code>
                        <desc>Grilled Chicken Breast With Mushroom Sauce, Yellow Rice, Sauteed Carrots &amp; Beans Baton</desc>
                    </resource>
                    <resource>
                        <fare>300.0</fare>
                        <code>LCVS</code>
                        <desc>Low Cal Salad Vegetarian</desc>
                    </resource>
                    <resource>
                        <fare>300.0</fare>
                        <code>LCNS</code>
                        <desc>Low Cal Salad Non-Vegetarian</desc>
                    </resource>
                    <resource>
                        <fare>196.0</fare>
                        <code>JNSW</code>
                        <desc>Jain Cold Sandwich (Current Cucumber And Tomato Sandwich)</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>JNML</code>
                        <desc>Jain Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>GFVG</code>
                        <desc>Vegetarian Gluten-Free Cold Meal (Dhokla)</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>GFNV</code>
                        <desc>Non-Vegetarian Gluten-Free Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>GFCM</code>
                        <desc>Vegetarian Gluten-Free Cold Meal (Dhokla)</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>FPML</code>
                        <desc>Fruit Platter</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>DNVL</code>
                        <desc>Non-Vegetarian Diabetic Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>DBML</code>
                        <desc>Vegetarian Diabetic Hot Meal</desc>
                    </resource>
                    <resource>
                        <fare>320.0</fare>
                        <code>CHML</code>
                        <desc>Kid'S Meal</desc>
                    </resource>
                </ssrcode_meal>
                <airline>spicejet</airline>
                <classofservice>V</classofservice>
                <rowbody> </rowbody>
                <depdate>2019-07-29t0750</depdate>
                <arrtime>10:10</arrtime>
                <arrdate>2019-07-29t1010</arrdate>
            </resource>
        </onwardflights>
        <faredict>
            <kbb>Z9hy6w==</kbb>
            <totalsurcharge>0</totalsurcharge>
            <passengercount>1</passengercount>
            <netpayable>16988</netpayable>
            <tokenec>985cb6698e365ff02bb60b03316d4c81</tokenec>
            <passport>False</passport>
            <international>true</international>
            <lead_message></lead_message>
            <fare_diff>-526</fare_diff>
            <isfamilyfare>False</isfamilyfare>
            <promocode></promocode>
            <totalbasefare>6650</totalbasefare>
            <kb>temp</kb>
            <totalfare>16988</totalfare>
            <goibibofee>0</goibibofee>
            <credits>False</credits>
            <transactionfee>0</transactionfee>
            <leaddiscount>0</leaddiscount>
            <premiermiles>0</premiermiles>
            <fuelsurcharge>0</fuelsurcharge>
            <leadcode></leadcode>
            <discount>0</discount>
            <dob>False</dob>
            <k>temp</k>
            <promo_message></promo_message>
            <promodiscount>0</promodiscount>
            <leadlist></leadlist>
        </faredict>
        <active_offers></active_offers>
        <review_screen_text></review_screen_text>
    </data>
    <data_length>5</data_length>
</response>
```


### Query Parameters

Parameter | Example-Value | Description 
--------- | ------- | ----------- |
ENV | pp.goibibobusiness.com or www.goibibobusiness.com | pp: testing & www: Production
bookingdata | Give all keys of flight details for a particular flight chosen from response of Search API, if it contains onward or return flights, that need to be included too. These dictionaries should be provided as a List of dictionaries.
querydata | `{ "origin": "del", "destination": "blr", "depdate": "2016-01-14", "adults": "1", "infants": "0", "children": "0" }` | origin,destination,departuredate,number of adults,children and infants should be provided in the form of dictionary as show in default value. Provide one more key "arrdate" if you want return flights as well.Provide source, destination and passenger details as same as the booking you want to reschedule in case of rescheduling.
fare | 4567 | totalfare should be provided.In case of return flights, sum of both fares ( onward and return) should be entered.
searchKey_onward | `0:0:408.0:0:0:9950.0:147.0:11307.0:0:0:0:0:0:0:0:0:11307.0:9950.0:11307.0:0:0.0:0:0:0.0:0:0` | searchKey of onward flights should be entered
searchKey_return | `0:0:408.0:0:0:9950.0:147.0:11307.0:0:0:0:0:0:0:0:0:11307.0:9950.0:11307.0:0:0.0:0:0:0.0:0:0` | searchKey for return flights should be entered if booking is to be done for return flights
leadcodes | ["2","7"] | List of travel insurance IDs. E.g. ["2","7"] you want to apply. These IDs must be obtained from defaultLeads in the response of getAllLeads API.
bookingId | GOFLDAPIfe6911439890114 | Value of bookingrequestid from the response of Confirm API. This parameter should be added only in case of reschedule a booking
psg_onward | ["A-Mr-Tester-Test", "C-Master-Testerc-Test", "I-Miss-Testeri-Test"] | The list of passengers for onward flights you want to reschedule (This information will be obtained from reschedule_info api).
psg_return | ["A-Mr-Tester-Test", "C-Master-Testerc-Test", "I-Miss-Testeri-Test"] | The list of passengers for return flights you want to reschedule (This information will be obtained from reschedule_info api).




### Reprice Response Parameters And Structure

Oneway trip responses can have fare details of onward flights inside `onwardflights` list. If it is round trip then along with onwardflights key `returnflights` key will be present in which return flight fare details will be available.

Key | Description
--------- | -----------
onwardflights | dictionary contains reprice details of onward flight.
returnflights | if the journey is domestic/international round trip then response will contains reprice details inside retunflights keys accordingly.
origin | Indicates IATA code of source airport
flightcode | indicates flight code
farebasis | vendor specific farebase
carrier_id | Indicates carier ID
deptime | departure time based on local GMT
duration | duration of flight
ibibopartner | indicates ibibo partner name / vendorname
carriercode | carrier code indicates
flightno | indicates flight number
destination | indicates IATA code of destination airport
stops | indicates stops number
seatsavailable | indicates available seats in the inventory
onwardflights | If there is any connection flights which will be available inside this key.
aircraftType | type of aircrafts eg:airbus 320, boying 737,etc
warnings | indicates warnings line Refundable or non refundable
dotentative | can have true/false values
ssrcode_baggage | this key contains list of dicts which details about baggage.`fare:` excess baggage fare,`code:` short code for this baggage plan,`weight:` weight limit under the baggage plan,`desc:` description about the baggage plan.
splitduration | indicates splituation duration. If no connecting flight total travel time will present inside this key.
searchKey | the key string formed by concatenating fare,adultbase fare,tax,etc. this key can be find in search response as well.
ssrcode_meal | this is a list of meal plans dictionaries available in flights.`fare:` fare of meal, `code:` meals plan code, `desc:` description about meals plan.
airline | airline name
depdate | departure date time 
arrtime | arrival time in 24 hours format local GMT
arrdate | arrival date time
fare | dictionary contains fare brakup from airline API.If it is multi flight, fare details will be available here.
adultothers | other charge for adult
adulttotalfare | total fare for adult can be calculated by bse fare and number of adults.
adultbasefare | base fare for an adult
totalpassengerhandlingfee | passenger handling fee
adultpassengerservicefee | base passenger service fee for an adult.
totalpassengerservicefee | can be calculated by multiplaying number of passengers to base fare.
adultcgst | adult CGST(central goods service tax,domestic)
totalbasefare | total base fare
goairnewgrossamount | amount to be pay to vendor
adultsgst | State good service tax(domestic)
adultfuelsurcharge | fuel surcharge charge per adult
faredict | this dictionary contains fare details. If there is some multi airline total fare will be calculated and can be find here.
netpayable | totall amount to be paid.
tokenec | trace key for debugging purpose
totalfare | total fare same as netpayable
promodiscount | if promo apllied, discounted amount available here
isfamilyfare | flag can have true or false familyfare plan.


## Flight Book Tentative

Tentative booking is done through this API and requires a user to pass booking parameters using search data to the specified URL. Tentative Booking parameters include flight details, search details, passenger details, contact details, total fare, and a search key (Except paxinfo and contactinfo(which should be given by user, others are obtained from Reprice API response).

Same API can be used to reschedule a booking. Additional two parameters (reschedule_breakup, faredict) should be added in case of rescheduling only if you get reschedule_breakup in the response of reprice API.

### FAQs :
1. I am getting status:Pending => Check whether you are sending email in correct format. If yes, then it might be coming from Airline's end. Try another airline.
2. I am getting error : unicode has no object "get" => Possible Cause: you need to pass list of dictionaries for bookingdata while you are passing simply dictionaries.
3. I am getting error: Flights not connected => Possible Cause: You forgot to append some onward flights inside the onward or return flights dictionary in case of indirect flights (i.e. flights with stop overs) 
4. I am getting error as : 'NoneType' object has no attribute 'get' => Possbile Cause: You might be searching for one way and giving data for two ways or vice versa.
5. I am getting "Error": "coercing to Unicode: need string or buffer, int found" => Possible Cause: You are passing integer value where string is expected.E.g. "adults":1 instead of "adults":"1" gives this error 
6. Will any value of payment is applicable for production as well => Yes.You can give any value for payment in contact info.
7. How much delay or time gap should be there between hitting tentative booking(book api) and confirm booking api => *None. You can hit confirm api immediately after you get response from book(this one) api.*
8. What are leadcodes and how do I know its possible values? => *Leadcodes are insurances you wish to choose. getAllLeads API gives you all available insurances for selected vertical. Now from response of getAllLeads API you can select Ids for the insurance you wish to select for your journey. And give that id surrounded by double quotes as a list (e.g. ["1"] or ["1","2"]) for the value of leadcodes parameter and then you will get total fare inclusive of insurance amount.*



### HTTP Request Example

`POST ENV/api/book/`

HTTP request Body mandatory fields:

* bookingdata : `[{"List of dict from search/reprice response"}]`
* querydata : `{"origin": "DEL", "adults": "1", "destination": "BLR", "infants": "0", "depdate": "2019-07-29", "arrdate": "", "children": "0"}`
* paxinfo : `[{"FirstName": "Test1", "eticketnumber": "", "LastName": "User", "Title": "1", "DateOfBirth": "", "Type": "A"}]`
* contactinfo: `{"pincode": "110110",     "state": "delhi",    "firstname": "test",     "lastname": "User",     "email": "test.user@test.com",     "landline": "12345678",     "mobile": "",     "payment": "AXIS",    "address": "test","city": "Bangalore" }`
* fare: `5862`
* searchKey_return: `0:0:0:0:0:6399:0:7378:0:0:0:0:0:0:0:0:0:6399:7378:0:0:0:0:0:0`

<aside class="notice">
Tentative Book API require a POST HTTP Call. To hit this API user has to provide <code>bookingdata</code> <code>querydata</code> <code>fare</code> <code>searchKey_onward</code><code>paxinfo</code><code>contactinfo</code><code>searchKey_return ( If roundtrip)</code> in HTTP request Body.
</aside>


> Example response of Book API

```json
    {
    "data": {
        "sku": {
            "parent_sku": "default",
            "child_sku": "default"
        },
        "hash": "a7eebe9816e45eccb871239b6ff169aebf36f19aa544e0a66ee677657fc9a1d6e0cb24ed98c3c42db8a3594e37ad88c313e5930b611b3ac9925047178266bec3",
        "guest": "false",
        "go_pg": "payu",
        "txnid": "GOFLDAPI2d1d80425645",
        "amount": "2798",
        "customReference": "GOFLDAPI2d1d80425645",
        "currency": "INR",
        "productinfo": "travel-DEL-BLR-20190729-0610",
        "payu_si": false,
        "native_payu": 0,
        "pay_at_hotel": false
    },
    "data_length": 12
}
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<response>
    <data>
        <sku>
            <parent_sku>default</parent_sku>
            <child_sku>default</child_sku>
        </sku>
        <hash>c01c07d096f57aa57d276ca1830d4655da7448a6c65827acc7f8c6b537ba7a9d320624658ad842ce07e9de4e6d85b9da8447236fa53de19bd2ba48a06af605fc</hash>
        <guest>false</guest>
        <go_pg>payu</go_pg>
        <txnid>GOFLDAPIeb9160426079</txnid>
        <amount>2798</amount>
        <customReference>GOFLDAPIeb9160426079</customReference>
        <currency>INR</currency>
        <productinfo>travel-DEL-BLR-20190729-0610</productinfo>
        <payu_si>False</payu_si>
        <native_payu>0</native_payu>
        <pay_at_hotel>False</pay_at_hotel>
    </data>
    <data_length>12</data_length>
</response>
```


### Query Parameters

Parameter | Example-Value | Description |
--------- | --------------| ----------- |
ENV | pp.goibibobusiness.com / www.goibibobusiness.com | pp: test www: production
bookingdata |             |Give all keys of flight details for a particular flight chosen from response of Search API, if it contains onward or return flights, that need to be included too. These dictionaries should be provided as a List of dictionaries.One more key carriers is added to bookingdata having value same as carrier-id.
querydata | {"origin": "del","destination": "blr","depdate": "2016-01-14","adults": "1","infants": "0","children": "0" } | origin,destination,departuredate,number of adults,children and infants should be provided in the form of dictionary as show in default value. Provide one more key "arrdate" if booking is being done for return flights as well.Provide source, destination and passenger details as same as the booking you want to reschedule in case of rescheduling.
fare | 4567 | totalfare should be provided.In case of return flights, sum of both fares ( onward and return) should be entered.
searchKey_onward | 0:0:408.0:0:0:9950.0:147.0:11307.0:0:0:0:0:0:0:0:0:11307.0:9950.0:11307.0:0:0.0:0:0:0.0:0:0 | searchKey of onward flights should be entered
searchKey_return | 0:0:408.0:0:0:9950.0:147.0:11307.0:0:0:0:0:0:0:0:0:11307.0:9950.0:11307.0:0:0.0:0:0:0.0:0:0 | searchKey of return flights should be entered
paxinfo | [{"FirstName": "test","eticketnumber": "","LastName": "Pandey""Title": "1","DateOfBirth": "","Type":}] | Passenger Info to be passed of each passengers in the form a dictionary having details FirstName,LastName,eticketnumber,Title,DateOfBirth,Type. If more than one passenger is booked, details of each passenger should be provided in a different dictionary and list of dictonaries should be passed as input for paxinfo.Use 1 for MR, 2 for MRS, 3 for MS and 4 for MSTR for title. Provide passanger details as same as the booking you want to reschedule in case of rescheduling.
contactinfo | {"pincode":"110110","state":"delhi","firstname":"test","lastname":"Pandey","email":"test@test.com","landline":"12345678","mobile":"","payment":"AXIS","address":"new_address123","city":"Bangalore"} | Contact details for passenger booking flight should be passed including details such as pincode,state,firstname, lastname,email,landline,mobile,payment,address,city in a dictonary. This passenger will be notified in case of any issues.
reschedule_breakup   |  | This information must be obtained from the response of reprice API. This parameter should be added only in case of reschedule a booking
faredict |  | This information must be obtained from the response of reprice API. This parameter should be added only in case of reschedule a booking


### BOOK API Response Parameters And Structure

As mentioned before BOOK flight Api Call is to make tenatative booking. This tenatative booking will have life of 15 minutes. Within this time duration payment has to complete to make this booking complete.


**Hash Is formed by concatenating following strings**

* payment_key: `PG secret key`
* paymentId: `PaymentId or GoFl ID`
* Amount: `ticket amount`
* productinfo: `string consists of source,destination,deptime,arrtime,etc`
* firstname: `passengers firstname`
* email: `email of passenger` 
* paymentSalt: `payment secret`

<aside class="success">
Attention— Consider the description given above about creating Hash for book. While sending client details from your end make sure that all mandatory details are matching the logic of hash formation.
</aside>


Key | Description
--------- | -----------
hash | Unique hash id formed by concatenating multiple strings related to the booking.
go_pg | indicates payment gateway used
txnid | Transaction id of this booking.
currency | currency always will be in `INR` irrespective of international or domestic flights.



## Flight Confirm

For booking confirmation of tentatively booked data, the user is required to pass certain parameters from tentatively booked data to the specified URL. Booking confirmation request parameters include a booking ID and hash key. 

**FAQs**

1. I am getting status:Pending => Check whether you are sending email in correct format. If yes, then it might be coming from Airline's end. Try another airline.

### HTTP Request Example

`POST ENV/api/confirm/`


### Query Parameters

Parameter | Example-Value | Description |
--------- | --------------| ----------- |
BookingId | `GOFLDAPIfe6911439890114` | The value of customReference from response of Book API
secret | `041aa022fc447581df851b8a16335bb586f6258b1e1a460e0ff2e9db012bc3d361c95fb9d5308366600a52a61c56be7a796faa02b7504febc9ec83dcd4c2595b` | hash_key to be passed is calculated as follows: 1) we calculate md5str using formula, md5str = pSalt + bookingId + '|'+ str(amount) + '|' + productinfo.lower()+ '|' + firstname.lower() + '|' + email.lower() + '|' + amountCrypt + '|' + "true" + '|' +"travelibibo" Example: "test123GOFLDAPI7b78c1439275195|6937|travel-del-blr-20160106-|amit|amit.prakash@ibibogroup.com|temp|true|travelibibo" here test123 is password used. where psalt is password used and use "temp" for amountCrypt. Rest of details can be found in response of Book api. 2) hash_key= sha512(md5str).hexdigest().Use this hash_key as secret."



## Flight getstatus

The booking status API gives confirmed ticket search results using booking ID/PNR number. It responds with complete booking details of all the passengers, flight details, contact, and booking ID.

### HTTP Request Example

`POST ENV/api/getstatus/`

### Query Parameters

Parameter | Example-Value | Description |
--------- | --------------| ----------- |
ENV | `pp.goibibobusiness.com / www.goibibobusiness.com` | pp: test www: production
bookingId | `GOFLDAPIfe6911439890114` | Value of bookingrequestid from response of Confirm API.







## Flight cancel_update

This api cancels your ticket and allows segment cancellation (onward/return or both) and pax cancellation (you can select passengers you want to cancel).
Parameter passengerlist_onward ensures that you want to cancel onward segment for the passengers you have mentioned in this paramenter.
Parameter passengerlist_return ensures that you want to cancel return segment for the passengers you have mentioned in this paramenter.
If you pass both the parameters passengerlist_onward and passengerlist_return, it cancels both the segments for the passengers you have mentioned in these parameters. 
A discounted roundtrip booking will be considered as one segment and this booking is not eligible for segment cancellation.
A family fare booking is not eligible for pax cancellation. You have to cancel all the passengers at a time.
Your ticket is not eligible for online cancellation if it expires in 4 hours. 
If there is some error in calculating airline chagres or flight is cancelled (when reasonBox_onward/reasonBox_return = Flight Cancelled), it submits cancellation request and CRM will take care of it. 
You can cancel a booking only when it is in confirmed status.

### HTTP Request Example

`POST ENV/api/v2/cancel_update/`

### Query Parameters

Parameter | Example-Value | Description |
--------- | --------------| ----------- |
ENV | `pp.goibibobusiness.com / www.goibibobusiness.com` | pp: test www: production
bookingId | `GOFLDAPIfe6911439890114` | Value of bookingrequestid from response of Confirm API.
passengerlist_onward | `["A-Mr-Test-BD","C-Mr-User-BC"]` | The list of passengers for onward flights you want to cancel (This information will be obtained from cancel_info api).
passengerlist_return | `["A-Mr-Test-BD","C-Mr-User-BC"]` | The list of passengers for return flights you want to cancel (This information will be obtained from cancel_info api).
reasonBox_onward | Normal Cancellation/Flight Cancelled | Reason for cancellation.
reasonBox_return | Normal Cancellation/Flight Cancelled | Reason for cancellation 











