
# Flight Tracker
## Problem Description
A description of the problem that you are modeling describing it in sufficient detail that makes sense in the context of your data model.

## Group Name and Members

Group 21482_ 6

[Aaron Fritchley](https://github.com/aafritch/MIST-4610)

[Mason Layfield](https://github.com/MasontLayfield/MIST4610-MySQL-Database-Project)

-Alexandra Shalikashvili

Simran Simran

-Ashley Skaggs

## Data Model
![project data model  73](https://user-images.githubusercontent.com/128408107/228953445-a43ebdff-0630-4f7c-a080-b53fe4ba4204.jpg)
**Explanation**

## Data Dictionary

**Table: AIRCRAFT**
| Column Name     | Description                                        | Data Type | Size | Format | Key? |
| --------------- | -------------------------------------------------- | --------- | ---- | ------ | ---- |
| aircraftID      | Unique sequential number identifying each aircraft | Text      | 45   |        | PK   |
| aircraftType    | Type of aircraft                                   | Text      | 45   |        |      |
| seatingCapacity | Indicates the number of seats in the aircraft      | Text      | 45   |        |      |

**Table: AIRLINE**
| Column Name | Description                           | Data Type | Size | Format | Key? |
| ----------- | ------------------------------------- | --------- | ---- | ------ | ---- |
| airlineID   | Unique number identifying the airline | Text      | 45   |        | PK   |
| airlineName | The airline’s name                    | Text      | 45   |        |      |
| websiteURL  | The airline’s website                 | Text      | 45   |        |      |
| homeCountry | The airline’s home country            | Text      | 45   |        |      |

**Table: AIRPORT**
| Column Name | Description                                 | Data Type | Size | Format | Key? |
| ----------- | ------------------------------------------- | --------- | ---- | ------ | ---- |
| airportID   | Unique number identifying the airport       | Text      | 45   |        | PK   |
| airportName | The airport’s name                          | Text      | 45   |        |      |
| city        | The city in which the airport is located    | Text      | 45   |        |      |
| state       | The state in which the airport is located   | Text      | 45   |        |      |
| country     | The country is which the airport is located | Text      | 45   |        |      |

**Table: CREW**
| Column Name     | Description                                           | Data Type | Size | Format | Key?         |
| --------------- | ----------------------------------------------------- | --------- | ---- | ------ | ------------ |
| crewMemberID    | Unique sequential number identifying each crew member | Text      | 45   |        | PK           |
| crewType        | The crew member’s role/position                       | Text      | 45   |        |              |
| crewFullName    | The crew member’s name                                | Text      | 45   |        |              |
| crewPhoneNumber | The crew member’s phone number                        | Text      | 45   |        |              |
| crewHomeCountry | The crew member’s home country                        | Text      | 45   |        |              |
| supervisorID    | The supervisor’s ID number                            | Text      | 45   |        | FK(ref.CREW) |

**Table: FLIGHT**
| Column Name             | Description                                                       | Data Type | Size | Format | Key?             |
| ----------------------- | ----------------------------------------------------------------- | --------- | ---- | ------ | ---------------- |
| flightID                | Unique sequential number identifying each flight                  | Text      | 45   |        | PK               |
| Airline_airlineID       | Indicates the ID of the airline that is carrying out the flight   | Text      | 45   |        | FK(ref. AIRLINE) |
| Airport_airportIDdepart | Indicates the departing time of the airport supporting the flight | Text      | 45   |        | FK(ref. AIRPORT) |
| Airport_airportIDarrive | Indicates the arrival time of the airport supporting the flight   | Text      | 45   |        | FK(ref.AIRPORT)  |

**Table: LUGGAGE**
| Column Name           | Description                                         | Data Type | Size | Format | Key?              |
| --------------------- | --------------------------------------------------- | --------- | ---- | ------ | ----------------- |
| luggageID             | Unique sequential number identifying each bag       | Text      | 45   |        | PK                |
| luggageWeight         | The weight of each bag(luggage)                     | Text      | 45   |        |                   |
| luggageDesc           | The description of the luggage                      | Text      | 45   |        |                   |
| Trip_tripID           | Indicates the trip that the luggage is on           | Text      | 45   |        | FK(ref.TRIP)      |
| Passenger_passengerID | Indicates the passenger that the luggage belongs to | Text      | 45   |        | FK(ref.PASSENGER) |

**Table: Passenger**
| Column Name  | Description                                         | Data Type | Size | Format | Key?          |
| ------------ | --------------------------------------------------- | --------- | ---- | ------ | ------------- |
| passengerID  | Unique sequential number identifying each passenger | Text      | 45   |        | PK            |
| firstName    | The passenger’s first name                          | Text      | 45   |        |               |
| lastName     | The passenger’s last name                           | Text      | 45   |        |               |
| emailAddress | The passenger’s email address                       | Text      | 45   |        |               |
| phoneNumber  | The passenger’s phone number                        | Text      | 45   |        |               |
| city         | The city in which the passenger resides             | Text      | 45   |        |               |
| state        | The state in which the passenger resides            | Text      | 45   |        |               |
| country      | The country in which the passenger resides          | Text      | 45   |        |               |
| Trip_tripID  | Indicates the trip the passenger is taking          | Text      | 45   |        | FK(ref. TRIP) |

**Table: SEAT**
| Column Name | Description                                 | Data Type | Size | Format | Key?          |
| ----------- | ------------------------------------------- | --------- | ---- | ------ | ------------- |
| seatNumber  | Unique number identifying the specific seat | Text      | 45   |        | PK            |
| Trip_tripID | Indicates the trip that the seat is on      | Text      | 45   |        | FK(ref. TRIP) |

**Table: SEAT_HAS_PASSENGER**
| Column Name           | Description                             | Data Type | Size | Format | Key?              |
| --------------------- | --------------------------------------- | --------- | ---- | ------ | ----------------- |
| Seat_seatNumber       | Indicates the seat the passenger is in  | Text      | 45   |        | FK(ref.SEAT)      |
| Passenger_passengerID | Indicates the passenger that has a seat | Text      | 45   |        | FK(ref.PASSENGER) |

**Table: TRIP** 
| Column Name         | Description                                          | Data Type | Size | Format      | Key?              |
| ------------------- | ---------------------------------------------------- | --------- | ---- | ----------- | ----------------- |
| tripID              | Unique sequential number identifying the trip        | Text      | 45   |             | PK                |
| tripDate            | The date of the trip                                 | Text      | 45   | YYYY-MM-DD? |                   |
| tripDepartTime      | The departure time for the trip                      | Text      | 45   |             |                   |
| tripArriveTime      | The arrival time for the trip                        | Text      | 45   |             |                   |
| Flight_flightID     | Indicates the flight that is carrying out the trip   | Text      | 45   |             | FK(ref. FLIGHT)   |
| Aircraft_aircraftID | Indicates the aircraft that is carrying out the trip | Text      | 45   |             | FK(ref. AIRCRAFT) |

**Table: TRIP_HAS_CREW**
| Column Name       | Description                                   | Data Type | Size | Format | Key?          |
| ----------------- | --------------------------------------------- | --------- | ---- | ------ | ------------- |
| Trip_tripID       | Indicates the trip that has a crew member     | Text      | 45   |        | FK(ref.TRIP)  |
| Crew_crewMemberID | Indicates the crew member that is on the trip | Text      | 45   |        | FK(ref. CREW) |

## Queries

Q1 - Write a query to list airports from most busy to least busy and the total number of departing passengers in each. <br />
<img width="583" alt="Screenshot 2023-03-30 at 5 10 00 PM" src="https://user-images.githubusercontent.com/128408107/228965484-aae3f957-4d7f-47ea-8ce6-8b95f187e494.png"> <br />
Description:

Q2 - Write a query to list the number of passengers from each country (if at least one citizen was present) who flew from Hartsfield-Jackson to John F. Kennedy <br />
<img width="659" alt="Screenshot 2023-03-30 at 5 14 02 PM" src="https://user-images.githubusercontent.com/128408107/228966024-2797ede2-7548-4afc-8c78-ab015dc60220.png"> <br />
Description:

Q3 - list out the names of supervisors and the crew members they supervised on if the number they supervise is greater than 3 <br />
<img width="710" alt="Screenshot 2023-03-30 at 5 15 29 PM" src="https://user-images.githubusercontent.com/128408107/228966243-015a39ba-4808-4340-83e4-8e1de739ccef.png"> <br />
Description:

## Query Matrix
|                       | Q1 | Q2 | Q3 | Q4 | Q5 | Q6 | Q7 | Q8 | Q9 | Q10 |
| --------------------- | -- | -- | -- | -- | -- | -- | -- | -- | -- | --- |
| Multiple table join   | X  | X  |    |    |    | X  |    |    | X  |     |
| subquery              |    |    |    | X  |    | X  |    | X  | X  |     |
| Correlated subquery   |    |    |    |    |    | X  |    |    |    |     |
| GROUP BY              | X  |    |    |    | X  |    |    |    |    |     |
| GROUP BY with HAVING  |    |    | X  |    |    |    |    |    |    |     |
| Multi condition WHERE |    | X  |    |    |    | X  |    |    |    |     |
| Built-in function     |    | X  |    | X  | X  | X  |    | X  |    |     |
| REGEXP                |    |    |    |    |    |    | X  |    |    |     |
| ROUND                 |    |    |    |    | X  |    |    |    |    |     |
| CONCAT                |    |    |    |    | X  |    |    |    |    |     |
| NOT EXISTS            |    |    |    |    |    |    |    |    | X  |     |

## Database Information
Our queries are stored as Procedures in the ns_21482_6 server in the format TP_Qx.
