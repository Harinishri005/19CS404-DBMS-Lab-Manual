# Experiment 1: Entity-Relationship (ER) Diagram

##  Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

##  Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

##  Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# EX:1  ER DIAGRAM

## NAME: HARINISHRI S
## REG.NO : 212223090008

## Scenario A:
Hospital

## ER Diagram:

![ER git](https://github.com/user-attachments/assets/0bf66402-d7db-43b3-a1f1-cbe54362a80f)


## Entities and Attributes:

### Department:

Dept_ID (Primary Key)

Name

Head

### Doctor:

Doctor_ID (Primary Key)

Name

Contact_No

Email

Specialization

Work_Schedule

### Patient:

Patient_ID (Primary Key)

Name

DOB

Gender

Address

Contact_No

Email

Work_Schedule

### Appointments:

App_ID (Primary Key)

Date

Time

Reason

Add_Notes

### Medical Records:

Med_Rec_ID (Primary Key)

Diagnosis

Medications

Treatment

Test Results



## Relationships and Constraints:

### Specialized (Department → Doctor):

One Department can have many Doctors.

A Doctor belongs to one Department. (1:N cardinality)

### Assigned (Doctor → Appointments):

One Doctor can be assigned to multiple Appointments.

An Appointment is assigned to one Doctor. (1:N cardinality)

### Book (Patient → Appointments):

One Patient can book multiple Appointments.

Each Appointment is booked by one Patient. (1:N cardinality)

### Contain (Patient → Medical Records):

One Patient can have multiple Medical Records.

Each Medical Record belongs to one Patient. (1:N cardinality)

### Check (Doctor → Medical Records):

One Doctor can check multiple Medical Records.

Each Medical Record is checked by one Doctor. (1:N cardinality)

## Extension (Prerequisite / Billing):

### Billing (Extension Idea):
Billing could be modeled by adding a new entity called Billing with attributes like Bill_ID, Amount, Payment_Method, and Payment_Status.
It would have relationships with Appointments (each appointment generates a bill) and Patients (patients are billed for their appointments).

## Design Choices:

1. I chose the main entities such as Doctor, Patient, Appointments, Department, and Medical Records because they represent the core operations of a hospital.

2. Relationships like Specialized, Assigned, Book, and Contain were added to represent the real-world interaction between these entities.

3. I assumed that each appointment is uniquely identified and linked to one doctor and one patient.

4. Work schedules for both doctors and patients are stored to manage availability.

5. Medical records are detailed to include diagnosis, medications, treatment, and test results for better patient history tracking.

# Scenario B: 
City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
![WhatsApp Image 2025-08-28 at 21 41 52_0d3b2057](https://github.com/user-attachments/assets/067a8872-0a16-4d0f-80c3-cde5fbe2cb97)

### Entities and Attributes

| Entity | Attributes (PK, FK)                | Notes   |
|--------|--------------------                |----------|
| User   |user_id (PK), name,mobile_no, address |Identifies the user.|  
| Permission| per_id (PK), per_module, per_name|Defines permissions granted to the user.|       
|Trainer| trainer_id (PK), name, mobile, email|Represents trainers managing the members.|      
| Member|mem_id (PK), mem_type, mem_name, mem_mobile, mem_email| Represents gym members.|       
| Fitness|fit_id (PK), fit_type, fit_desc|Defines the fitness programs.|          


### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|User - Permission|1:N|Mandatory (A user must have at least one permission) | A user can have multiple permissions.|     
| User - Trainer| N:M|Optional (User may or may not be a trainer)| A user can manage many trainers and vice versa.|
| Trainer - Fitness|1:N|Mandatory (A trainer must be associated with at least one fitness type)|Trainers manage fitness types.|
|Member - Fitness|N:M|Optional (Members may or may not be associated with a fitness type)|A member can be associated with multiple fitness types.|

# Scenario C: 
City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
![WhatsApp Image 2025-08-28 at 21 50 47_6450048c](https://github.com/user-attachments/assets/034cadae-7259-4771-b862-b124130efb47)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|Member|member_id (PK), name|Represents library members.|
|Book|book_id (PK), title|Represents books available for loan.|
|Loan|loan_id (PK), date, return_date, member_id (FK), book_id (FK)|Represents the loan transactions between members and books.|
|Event|event_id (PK), name, date|Represents events that members can register for.|
|Speaker|speaker_id (PK), name|Represents speakers for events.|


### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|Member - Loan|1:N|Mandatory (A member must have at least one loan)|A member can loan multiple books, but a loan belongs to one member.|
|Book - Loan|1:N|Mandatory (A book must be loaned to at least one member)|A book can be loaned to multiple members over time, but a loan record is for one book.|
|Member - Event|M:N|Optional (A member may or may not register for an event)|Members can register for many events, and each event can have many members.|
|Speaker - Event|M:N|Optional (An event may or may not have a speaker)|An event can have multiple speakers, and a speaker can be assigned to multiple events.|
### Assumptions
- Member-Book Loan System: A Member can borrow multiple Books with a Loan representing each borrowing transaction, which includes the loan and return dates.
- Event Participation: Members can register for multiple Events, and each Event can have multiple Members attending, with optional speakers.
- Speaker-Event Association: Events may feature one or more Speakers, and a Speaker can be involved in multiple Events.



## Result: 

Thus, the ER diagram for the three scenarios was successfully designed, and the entities, relationships, and constraints were clearly represented.
