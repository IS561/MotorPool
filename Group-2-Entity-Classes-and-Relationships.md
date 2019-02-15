## Entity Classes

**1. Driver**: A collection of drivers who are eligible for borrowing university-owned vehicles. Each driver who is eligible for borrowing university-owned vehicles is an individual of this class.

Driver attributes
* Employee ID (Text)
* Name (Text) 
* Work Phone (Text)
* Address (Text)
* Driver License Number (Text)
* Sex (Text)
* Date of Hire (Date)
* Date of Birth (Date)

**2. University of Kentucky Administration Department**:
The administration department of the University of Kentucky that receives driver information from the driver information agency.

University of Kentucky Administration Department attributes
* Address (Text)
* Phone Number (Text)

**3. UK-Owned Motor Vehicle**
A collection of vehicles that are owned by the University of Kentucky that are available to be borrowed by approved drivers. Each individual in this entity class is one UK-owned motor vehicle.

UK-Owned Motor Vehicle attributes
* Driver (Text)
* Department (Text)
* License Plate (Text)

**4. UK Risk Management**
UK Risk Management is the company that has a car insurance contract with the university. Thus, the UK Risk Management represents as a whole to be the individual in this entity class.

UK Risk Management attributes
* Address (Text)
* Phone Number (Text)

**5. Motor Vehicle Record (MVR) Release and Information Form**:
A collection of forms submitted by drivers who want to borrow UK-owned vehicles. These forms are being used by the University's Risk Management department to get information about the applicants’ driving records.

Motor Vehicle Record (MVR) Release and Information Form attributes
* Driver Information (Text)
* Department Information (Text) 
* Sign Date (Time)

**6. Motor Vehicle Insurance**
A class of insurances that cover drivers who have the university's permission to borrow  UK-owned vehicles.

Motor Vehicle Insurance attributes
* Insurance Policy (Text)
* Driver Information (Text)  
* Vehicle Information (Text)  
* Amount (Number)

**7. Accident**:
A UK-owned vehicle accident that is involved in operating the official university business.

Accident attributes
* Date and Time (Date)
* Location of the Accident (Text)
* Police Department Reported (Text)
* Origin and Destination of the Trip (Text)
* Police Case Number (Text)

**8. Vehicle Accident Report**
A report for an accident that is happened during operating official university business and involves a UK-owned vehicle.

Vehicle Accident Report attributes
* Date and Time (Date)
* Location of the Accident (Text)
* Name of Driver (Text)
* Home Address (Text)
* Phone (Text)
* Driver License Number (Text)
* Vehicle Damage (Text)
* Claim Amount (Number)

**9. Claim**
A collection of requests to an insurance company for compensations in accordance with the university’s motor vehicle insurance policy.

Vehicle Accident Report attributes
* Insurance Carrier (Text)
* Name of Driver (Text)
* Home Address (Text)
* Phone (Text)
* Driver License Number (Text)
* Description of Injuries (Text)
* Vehicle Damage (Text)
* Claim Amount (Number)

**10. Driver Information Agency**
An agency that stores information of drivers that can be made available for the university. The university uses the information to do the background check on applicants to make decisions on whether approving borrowing UK-owned vehicle requests or not.

Driver Information Agency attributes
* Name (Text)
* Address (Text)
* Phone Number (Text)
* Fax (Text)

**11. Passenger Van Driver**
A collection of employees who work at the University of Kentucky that drive a 12 or 15 passenger van. 

Passenger Van Driver attributes
* Employee ID (Text)
* Name (Text) 
* Work Phone (Text)
* Address (Text)
* Driver License Number (Text)
* Sex (Text)
* Date of Hire (Date)
* Date of Birth (Date)
* Login Credentials (Text)
* Passed the Test (Boolean)

**12. Driver Safety Awareness Training Course Test**
A compulsory test offered by UK Environmental Health and Safety and to be taken by passenger van drivers before they are allowed to drive these vehicles.

Driver Safety Awareness Training Course Test attributes
* Course Content (Text)
* Test (Text)

**13. Training Result:**
A collection of results taken by van drivers after completing the course, and they reflect whether certain drivers have got approval to drive passenger vans or not.

Training Result attributes
* Grade (Number)
* Pass (Boolean)

14. **Department Administrator**:
Department Administrator is a class of employees of the University of Kentucky that has responsibilities including approving the expenditure of departmental funds, approving employee drivers, approving non-employee drivers with express permission, and approving some emergency drivers to use Text Messaging while driving.

Department Administrator attributes
* Name (Text)
* Work Phone (Text)
* Address (Text)
* City (Text)
* ST (Text)
* Zip (Text)
* Sex (Text)
* Date of Birth (Date)
* Number of Funds Approved (Number)
* Number of Approved Employee Drivers (Number)
* Number of Approved Non-Employee Drivers (Number)
* Number of Approved TM Employees (Number)

***

## Relationships
**1. Drives**
* Scope note: A driver drives a UK-owned motor vehicle.
* Domain: Driver
* Codomain: UK-owned Motor Vehicle
* Arity: 2 (binary relationship) 
* Cardinality: 1-to-1

**2. Files**
* Scope note: A driver files the insurance claim as formal demand of compensation.
* Domain: Driver
* Codomain: Claim
* Arity: 2 (binary relationship)
* Cardinality: 1-to-many

**3. Covers**
* Scope note: A motor vehicle insurance covers accidents that involve UK-owned vehicles during the process of operating * university business. 
* Domain: Motor Vehicle Insurance
* Codomain: Accident
* Arity: 2 (binary relationship) 
* Cardinality: 1-to-many

**4. Shares information**
* Scope note: A driver information agency shares driver information with the University of Kentucky administration department so that the department can make decisions on whether approving drivers’ applications or not.
* Domain: Driver Information Agency
* Codomain: University of Kentucky Administration Department
* Arity: 2 (binary relationship) 
* Cardinality: 1-to-1

**5. Takes**
* Scope note: A passenger van driver takes the driver safety awareness training course test to be allowed to drive a van.
* Domain: Passenger van driver
* Codomain: Driver Safety Awareness Training Course Test
* Arity: 2 (binary relationship)
* Cardinality: many-to-many 

**6. Approves**
* Scope note: The department administrator approves a driver’s application of borrowing a UK-owned vehicle.
* Domain: Department Administrator
* Codomain: Driver
* Arity: 2 (binary relationship) 
* Cardinality: 1-to-many
