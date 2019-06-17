# Errors

<aside class="notice">
	Consider error codes given below if you recieve some undesirable results.
	</aside>

###The Goibibo Flight Search API uses the following error codes:


Error Code | Meaning
---------- | -------
100	| Invalid IATA Code for Source/Destination
101	| Source and Destination are same
102	| Departure Date is after Arrival Date
103	| Invalid Counter value
108	| No. of passengers cannot exceed 9
113	| Minimum of 1 adult required for booking
118	| No of infants cannot exceed no. of adults
123	| You dont have enough amount in your account to book this flight
125	| Number of passangers can not be zero
130	| Schedule unavailable, try again after some time

###The Goibibo Flight Reprice API uses the following error codes:

Error Code | Meaning
---------- | -------
100	| Invalid IATA Code for Source/Destination
101	| Source and Destination are same
102	| Departure Date is after Arrival Date
104	| Flights not connected
105	| Repricing failed with airlines or flight full, please try again after some time or choose another flight
107	| Invalid Carrier ID
113	| Minimum of 1 adult required for booking
116	| Booking not found
118	| No of infants cannot exceed no. of adults
125	| Number of passangers can not be zero
126	| Repricing failed, please try again
129	| Cannot get fare at this time. Please try again
134	| Unable to calculate lead amount
140	| Invalid passenger details
150	| Error in reschedule
151	| Minimum of 1 adult required for rescheduling
152	| Invalid Source and Destination
153	| This is discounted trip. Can't perform partial rescheduling. Provide same passsenger list for both the segments
155	| Not able to calculate reschedule charges and refund
156	| This is family fare booking. Can't perform partial rescheduling. Select all passengers
157	| Minimum of 1 adult should be present in old booking
159	| You are trying to reschedule one way trip. Provide details for one way trip


###The Goibibo Flight Book API uses the following error codes:

Error-Code | Meaning
---------- | -------
100	| Invalid IATA Code for Source/Destination
101	| Source and Destination are same
102	| Departure Date is after Arrival Date
104	| Flights not connected
106	| Fare does not match, please do a reprice
107	| Invalid Carrier ID
108	| No. of passengers cannot exceed 9
109	| Children should be between 2 and 12 years of age
110	| Infants should be below 2 years of age
111	| Adults should be above 12 years of age
112	| Invalid passenger title (1,2,3,4 allowed)
113	| Minimum of 1 adult required for booking
114	| Inconsistency with passenger data and bookings for each passenger type
115	| Date of Birth mandatory for Child and Infant Passengers
118	| No of infants cannot exceed no. of adults
123	| You dont have enough amount in your account to book this flight
125	| Number of passangers can not be zero
130	| Schedule unavailable, try again after some time
131	| Cannot make this booking
134	| Unable to calculate lead amount
140	| Invalid passenger details
150	| Error in reschedule
151	| Minimum of 1 adult required for rescheduling
152	| Invalid Source and Destination
153	| This is discounted trip. Can't perform partial rescheduling. Provide same passsenger list for both the segments
155	| Not able to calculate reschedule charges and refund
156	| This is family fare booking. Can't perform partial rescheduling. Select all passengers
157	| Minimum of 1 adult should be present in old booking
159	| You are trying to reschedule one way trip. Provide details for one way trip


###The Goibibo Confirm  API uses the following error codes:

Error Code | Meaning
---------- | -------
116	| Booking not found
117	| Invalid hash key
123	| You dont have enough amount in your account to book this flight
127	| Unable to confirm booking, please try again after some time
130	| Schedule unavailable, try again after some time
131	| Cannot make this booking


###The Goibibo get_status  API uses the following error codes:

Error Code | Meaning
---------- | -------
116	| Booking not found
128	| Unable to retrieve booking status


###The Goibibo reschedule_info  API uses the following error codes:

Error Code | Meaning
---------- | -------
116	| Booking not found
150	| Error in reschedule
155	| Not able to calculate reschedule charges and refund



###The Goibibo cancel_info  API uses the following error codes:

Error Code | Meaning
---------- | -------
147	| Unable to fetch cancellation information
149	| Not Elligible for cancellation








