# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

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

<img width="1270" height="852" alt="fitness" src="https://github.com/user-attachments/assets/6ef548f6-e1a9-4e0c-94dc-3caa9b099e04" />

### Entities and Attributes
1.Member: MemberID (PK), MemberName, Age

2.Subscription: SubID (PK), StartDate, EndDate

3.WorkoutPlan: PlanID (PK), PlanName, Duration

4.Trainer: TrainerID (PK), TrainerName, Expertise

5,Equipment: EquipID (PK), EquipName, Type

### Relationships and Constraints
  - Registers: One member can have many subscriptions, each subscription belongs to one member
  - Enrolls: A member can join many workout plans, a workout plan can have many members
  - Guides: A trainer can guide multiple workout plans, and a workout plan can have multiple trainers
  - Uses: A workout plan may use many equipment items, and an equipment item may be used in many workout plans


### Assumptions
- Members may exist in the system without enrolling in any workout plan
- A subscription always belongs to exactly one member
- Attendance and payment details are not included in this simplified ER model
- ---

# Scenario B: City Library Event & Book Lending System

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

<img width="1421" height="990" alt="city library" src="https://github.com/user-attachments/assets/d592362d-6d97-4128-af53-1fe596dea7a5" />

### Entities and Attributes

1.Member: MemberID (PK), Name, Email

2.Book: BookID (PK), Title, Author, Category

3.Loan: LoanID (PK), LoanDate, ReturnDate, Fine

4.Event: EventID (PK), EventName, Date, Time

5.Speaker: SpeakerID (PK), SpeakerName, Expertise

6.Room: RoomID (PK), RoomName, Capacity

### Relationships and Constraints

 - Borrows: A member can have many loans, and each loan belongs to one member
 - IncludedIn: Each loan is for one book, and a book may appear in many loan records
 - Registers: A member may register for many events, and an event may have many registered members
 - Has: An event may have many speakers, and a speaker may take part in many events
 - BookedIn: Each event is held in one room, and a room may host multiple events

### Assumptions
- The fine for overdue books is stored but the calculation happens outside the ER model
- Each loan must connect exactly one member and one book
- Room capacity is used to limit event registrations but seat allocation is not modeled
---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:

<img width="1663" height="867" alt="Restaurant" src="https://github.com/user-attachments/assets/9d40bb19-b8a7-433b-883a-810b61b9b284" />

### Entities and Attributes
1.Staff: StaffID (PK), StaffName, Role

2.Customer: CustID (PK), CustName, Phone

3.Order: OrderID (PK), OrderDate, Total

4.MenuItem: ItemID (PK), ItemName, Price

5.Payment: PaymentID (PK), PayMethod

### Relationships and Constraints

- Serves: One staff member can serve many customers
- Places: A customer can place many orders, and each order is linked to one customer
- Contains: An order may include many menu items, and a menu item may appear in many different orders
- Processes: Each order has exactly one payment, and each payment belongs to one order

### Assumptions
 - Table numbers and reservation details are not included in this simplified representation
 - Taxes and service charges are included inside the order total
 - Only one payment is recorded per order

---
