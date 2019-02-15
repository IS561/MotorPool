## Entity Classes

**1. Driver** 
A collection of drivers who are eligible for borrowing university-owned vehicles. Each driver who is eligible for borrowing university-owned vehicles is an individual of this class. If the driver is a van driver, that driver needs to take a driver safety awareness training course and pass the training course test.

Driver attributes
* Employee ID (Text)
* Name (Text)
* Driver License Number (Text)
* Driver Type (Text)
* Approved or Not (Boolean)
* Training Course Pass or Not (Boolean)

**2. UK(University of Kentucky)-Owned Motor Vehicle**
A collection of vehicles that are owned by the University of Kentucky that are available to be borrowed by approved drivers. Each individual in this entity class is one UK-owned motor vehicle.

UK-Owned Motor Vehicle attributes
* License Plate (Text)
* Department (Text)
* Type (Text)

**3. Risk Management**
A collection of risk management departments that verifies Motor Vehicle Record (MVR) Release and Information Forms filled out by drivers. The UK Risk Management is an individual of this entity class.

Risk Management attributes
* Department ID (Text)
* Address (Text)
* Phone Number (Text)

**4. Motor Vehicle Record (MVR) Release and Information Form**:
A collection of forms filled out by drivers who want to borrow UK-owned vehicles. These forms are being used by the university's Risk Management department to verify information about the applicants’ driving records.

Motor Vehicle Record (MVR) Release and Information Form attributes
* Driver License Number (Text)
* Driver Name (Text)
* Department ID (Text) 
* Sign Date (Time)

**5. Motor Vehicle Insurance**
A class of insurances that cover UK-owned vehicles.

Motor Vehicle Insurance attributes
* Insurance Name (Text)
* Insurance Policy (Text)
* Coverage (Number)
* Procedure (Text)

**6. Accident**
UK-owned vehicle accidents that took place in operating the official university business.

Accident attributes
* Driver License Number (Text)
* Vehicle plate (Text)
* Date and Time (Date)
* Location of the Accident (Text)
* Police Department Reported (Text)
* Origin and Destination of the Trip (Text)
* Police Case Number (Text)

**7. Vehicle Accident Report**
A collection of reports for accidents that happened during operating official university business which involve UK-owned vehicles.

Vehicle Accident Report attributes
* Report ID (Text)
* Date and Time (Date)
* Location of the Accident (Text)
* Name of Driver (Text)
* Driver License Number (Text)
* Vehicle Plate (Text)
* Vehicle Damage (Text)
* Claim Amount (Number)

**8. Claim**
A collection of claims to an insurance company for compensations in accordance with the university’s motor vehicle insurance policy.

Vehicle Accident Report attributes
* Claim ID (Text)
* Insurance Carrier (Text)
* Name of Driver (Text)
* Driver License Number (Text)
* Description of Injuries (Text)
* Vehicle Plate (Text)
* Vehicle Damage (Text)
* Claim Amount (Number)

**9. Driver Safety Awareness Training Course**
A collection of compulsory training courses offered by UK Environmental Health and Safety Department that need to be taken by van drivers before they are allowed to drive vans.

Driver Safety Awareness Training Course attributes
* Course ID (Text)
* Course Content (Text)
* Test (Text)

**10. Department Administrator**
Department Administrator is a class of employees of the University of Kentucky of different departments that have responsibilities including approving employee drivers, approving non-employee drivers with express permission, and approving some emergency drivers to use Text Messaging while driving.

Department Administrator attributes
* Employee ID (Text)
* Department ID (Text)
* Name (Text)

***

## Relationships
**1. Drives**
* Scope note: A driver drives a UK-owned motor vehicle.
* Domain: Driver
* Codomain: UK-owned Motor Vehicle
* Arity: 2 (binary relationship) 
* Cardinality: many-to-many

**2. Files**
* Scope note: A driver files the insurance claim as formal demand of compensation.
* Domain: Driver
* Codomain: Claim
* Arity: 2 (binary relationship)
* Cardinality: 1-to-many

**3. Covers**
* Scope note: A motor vehicle insurance covers UK-owned vehicles in case of accidents happend during the process of operating university business. 
* Domain: Motor Vehicle Insurance
* Codomain: Vehicle
* Arity: 2 (binary relationship) 
* Cardinality: 1-to-many

**4. Takes**
* Scope note: A van driver takes the driver safety awareness training course.
* Domain: Van Driver
* Codomain: Driver Safety Awareness Training Course
* Arity: 2 (binary relationship)
* Cardinality: many-to-many 

**5. Approves**
* Scope note: The department administrator approves the MVR Release and Information Form of borrowing a UK-owned vehicle filled out by a driver.
* Domain: Department Administrator
* Codomain: Motor Vehicle Record (MVR) Release and Information Form
* Arity: 2 (binary relationship) 
* Cardinality: many-to-many
