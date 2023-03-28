
# Project Title
## Problem Description
A description of the problem that you are modeling describing it in sufficient detail that makes sense in the context of your data model.

## Group Name and Members

Group 21482_ 6

-Aaron Fritchley
 
-Mason Layfield

-Alexandra Shalikashvili

-Simran Simran

-Ashley Skaggs
## Data Model
![7ab846dadefd44b6b43f2a3b6b4a9f21](https://user-images.githubusercontent.com/128408107/228365560-0e42d841-0b02-4c29-a8db-56a5eaabb5d6.jpeg)

## Data Dictionary

Table: AIRCRAFT
| Column Name     | Description                                        | Data Type | Size | Format | Key? |
| --------------- | -------------------------------------------------- | --------- | ---- | ------ | ---- |
| aircraftID      | Unique sequential number identifying each aircraft | INT       |      |        | PK   |
| aircraftType    | Type of aircraft                                   | Text      | 45   |        |      |
| seatingCapacity | Indicates the number of seats in the aircraft      | Text      | 45   |        |      |

Table: AIRLINE
| Column Name | Description                           | Data Type | Size | Format | Key? |
| ----------- | ------------------------------------- | --------- | ---- | ------ | ---- |
| airlineID   | Unique number identifying the airline | INT       |      |        | PK   |
| airlineName | The airline’s name                    | Text      | 45   |        |      |
| websiteURL  | The airline’s website                 | Text      | 45   |        |      |
| logo        | The airline’s logo                    | Text      | 45   |        |      |

Table: AIRPORT
| Column Name | Description                                 | Data Type | Size | Format | Key? |
| ----------- | ------------------------------------------- | --------- | ---- | ------ | ---- |
| airportID   | Unique number identifying the airport       | INT       |      |        | PK   |
| airportName | The airport’s name                          | Text      | 45   |        |      |
| city        | The city in which the airport is located    | Text      | 45   |        |      |
| state       | The state in which the airport is located   | Text      | 45   |        |      |
| country     | The country is which the airport is located | Text      | 45   |        |      |

Table: CREW
| Column Name       | Description                                           | Data Type | Size | Format | Key?          |
| ----------------- | ----------------------------------------------------- | --------- | ---- | ------ | ------------- |
| crewMemberID      | Unique sequential number identifying each crew member | INT       |      |        | PK            |
| crewType          | The crew member’s role/position                       | Text      | 45   |        |               |
| crewFullName      | The crew member’s name                                | Text      | 45   |        |               |
| crewPhoneNumber   | The crew member’s phone number                        | Text      | 45   |        |               |
| crewHomeCountry   | The crew member’s home country                        | Text      | 45   |        |               |
| Crew_crewMemberID | Indicates                                             | INT      |      |        | FK(ref. CREW) |

Table: FLIGHT
| Column Name             | Description                                      | Data Type | Size | Format | Key?             |
| ----------------------- | ------------------------------------------------ | --------- | ---- | ------ | ---------------- |
| flightID                | Unique sequential number identifying each flight | INT       |      |        | PK               |
| duration                | The duration of the flight                       | Text      | 45   |        |                  |
| Airline_airlineID       |                                                  | INT       |      |        | FK(ref. AIRLINE) |
| Airport_airportIDdepart |                                                  | INT       |      |        | FK(ref. AIRPORT) |
| Airport_airportIDarrive |                                                  | INT       |      |        | FK(ref.AIRPORT)  |

Table: LUGGAGE
| Column Name           | Description                                   | Data Type | Size | Format | Key?              |
| --------------------- | --------------------------------------------- | --------- | ---- | ------ | ----------------- |
| luggageID             | Unique sequential number identifying each bag | INT       |      |        | PK                |
| luggageWeight         | The weight of each bag                        | Text      | 45   |        |                   |
| luggageDesc           |                                               | Text      | 45   |        |                   |
| Trip_tripID           |                                               | INT       |      |        | FK(ref.TRIP)      |
| Passenger_passengerID |                                               | INT       |      |        | FK(ref.PASSENGER) |

Table: Passenger
| Column Name  | Description                                         | Data Type | Size | Format | Key?          |
| ------------ | --------------------------------------------------- | --------- | ---- | ------ | ------------- |
| passengerID  | Unique sequential number identifying each passenger | INT       |      |        | PK            |
| firstName    | The passenger’s first name                          | Text      | 45   |        |               |
| lastName     | The passenger’s last name                           | Text      | 45   |        |               |
| emailAddress | The passenger’s email address                       | Text      | 45   |        |               |
| phoneNumber  | The passenger’s phone number                        | Text      | 45   |        |               |
| city         | The city in which the passenger resides             | Text      | 45   |        |               |
| state        | The state in which the passenger resides            | Text      | 45   |        |               |
| country      | The country in which the passenger resides          | Text      | 45   |        |               |
| Trip_tripID  | Indicates the trip the passenger is taking          | INT       |      |        | FK(ref. TRIP) |

Table: SEAT 
| Column Name | Description                        | Data Type | Size | Format | Key?          |
| ----------- | ---------------------------------- | --------- | ---- | ------ | ------------- |
| seatNumber  | Unique number identifying the seat | INT       |      |        | PK            |
| Trip_tripID |                                    | INT       |      |        | FK(ref. TRIP) |

Table: SEAT_HAS_PASSENGER
| Column Name           | Description | Data Type | Size | Format | Key?              |
| --------------------- | ----------- | --------- | ---- | ------ | ----------------- |
| Seat_seatNumber       |             | INT       |      |        | FK(ref.SEAT)      |
| Passenger_passengerID |             | INT       |      |        | FK(ref.PASSENGER) |

Table: TRIP 
| Column Name         | Description                                   | Data Type | Size | Format     | Key?              |
| ------------------- | --------------------------------------------- | --------- | ---- | ---------- | ----------------- |
| tripID              | Unique sequential number identifying the trip | INT       |      |            | PK                |
| tripDate            | The date of the trip                          | Text      | 45   | YYYY-MM-DD |                   |
| tripDepartTime      | The departure time for the trip               | Text      | 45   |            |                   |
| tripArriveTime      | The arrival time for the trip                 | Text      | 45   |            |                   |
| Flight_flightID     |                                               | INT       |      |            | FK(ref. FLIGHT)   |
| Aircraft_aircraftID |                                               | INT       |      |            | FK(ref. AIRCRAFT) |

Table: TRIP_HAS_CREW
| Column Name       | Description | Data Type | Size | Format | Key?          |
| ----------------- | ----------- | --------- | ---- | ------ | ------------- |
| Trip_tripID       |             | INT       |      |        | FK(ref.TRIP)  |
| Crew_crewMemberID |             | INT       |      |        | FK(ref. CREW) |

## Queries

## Query Matrix

## Database Information
