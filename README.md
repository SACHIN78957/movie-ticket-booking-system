🎬 Movie Ticket Booking System
A console-based Movie Ticket Booking System in C++ designed with a modular, object-oriented structure.
This project was developed as a System Design / OOP project to demonstrate how a real-world ticket-booking workflow can be divided into focused classes, connected through clear responsibilities and relationships.
✨ Key Features
🎥 Display currently available movies
🕐 Display shows for selected movies
💺 Display seat availability for a show
🎟️ Book one or multiple seats
💰 Calculate ticket price according to seat category
💳 Support multiple payment modes:
UPI
Card
Cash
✅ Confirm booking only after successful payment
❌ Reject already-booked or invalid seats
🔄 Release seats when payment fails
🧾 Generate and display booking tickets
🚫 Cancel confirmed bookings
♻️ Make cancelled seats available again
⚠️ Handle invalid menu and payment choices
🧠 System Design Concepts
The project focuses on translating a booking problem into an object-oriented design.
Main Classes
Class	Responsibility
`Movie`	Stores movie information such as title, language and duration
`Seat`	Represents a physical seat and its category
`Screen`	Manages seats belonging to a screen
`Cinema`	Contains the cinema's screens
`Show`	Represents a scheduled movie screening
`ShowSeat`	Maintains seat availability for a particular show
`Customer`	Stores customer information
`Booking`	Represents a booking and its state
`Payment`	Abstract payment contract
`UpiPayment`	UPI payment implementation
`CardPayment`	Card payment implementation
`CashPayment`	Cash payment implementation
`PriceCalculator`	Calculates the total booking amount
`TicketPrinter`	Displays the confirmed ticket
`BookingService`	Coordinates the booking and cancellation workflow
💳 Payment Design
`Payment` is treated as an abstraction with concrete implementations:
```text
                 Payment
                    ▲
          ┌─────────┼─────────┐
          │         │         │
        UPI        Card      Cash
```
This allows the booking workflow to work with a payment abstraction instead of being tightly coupled to one payment method.
🏗️ Booking Workflow
```text
Select Movie
     ↓
Select Show
     ↓
View Seat Layout
     ↓
Select Seat(s)
     ↓
Validate Availability
     ↓
Calculate Fare
     ↓
Select Payment Method
     ↓
Payment Successful?
   ↙           ↘
 No             Yes
 ↓               ↓
Release Seats   Confirm Booking
                 ↓
             Print Ticket
```
🛡️ Edge Cases
The application demonstrates several important failure conditions:
Already Booked Seat
If a customer tries to select a seat that has already been booked, the booking request is rejected.
Failed Payment
If payment fails, the booking is not confirmed and the selected seats are released.
Cancellation
After a confirmed booking is cancelled, the associated seats become available again.
Invalid Input
Invalid menu choices, show selections, seat numbers and payment choices are handled with appropriate messages.
🧩 SOLID Principles
The design applies the following SOLID principles:
S — Single Responsibility Principle
Different classes handle different responsibilities:
`PriceCalculator` → pricing
`TicketPrinter` → ticket output
`BookingService` → booking workflow
Payment classes → payment behaviour
O — Open/Closed Principle
New payment methods can be introduced as additional `Payment` implementations without rewriting the overall booking workflow.
L — Liskov Substitution Principle
`UpiPayment`, `CardPayment` and `CashPayment` can be used wherever the `Payment` abstraction is expected.
I — Interface Segregation Principle
The payment abstraction remains focused on the operation required by this system instead of adding unrelated operations.
D — Dependency Inversion Principle
The booking workflow works with the `Payment` abstraction rather than depending directly on one concrete payment implementation.
📁 Project Structure
```text
movie-ticket-booking-system/
│
└── movie ticket booking system/
    │
    ├── main.cpp
    │
    ├── Movie.cpp
    ├── Seat.cpp
    ├── Screen.cpp
    ├── Cinema.cpp
    ├── Show.cpp
    ├── ShowSeat.cpp
    ├── Customer.cpp
    ├── Booking.cpp
    ├── BookingService.cpp
    │
    ├── Payment.cpp
    ├── UpiPayment.cpp
    ├── CardPayment.cpp
    ├── CashPayment.cpp
    │
    ├── PriceCalculator.cpp
    ├── TicketPrinter.cpp
    │
    ├── class diagram.png
    ├── noun-verb analysis.png
    ├── requirement analysis.png
    ├── sequential diagram.png
    │
    ├── 04_Relationships.txt
    ├── 08_SOLID_Mapping.txt
    ├── 09_Demo_Run.txt
    └── 10_Compilation.txt
```
⚙️ Requirements
C++ compiler with C++17 support
GCC / MinGW or another compatible C++ compiler
Terminal / Command Prompt
No external libraries are required.
🚀 How to Run
1. Clone the repository
```bash
git clone https://github.com/SACHIN78957/movie-ticket-booking-system.git
```
2. Open the project directory
```bash
cd movie-ticket-booking-system
cd "movie ticket booking system"
```
3. Compile
The project is organized so that `main.cpp` includes the individual `.cpp` implementation files.
```bash
g++ -std=c++17 main.cpp -o movie_booking
```
4. Run
Windows
```bash
movie_booking.exe
```
Linux / macOS
```bash
./movie_booking
```
🖥️ Console Menu
The application provides the following menu:
```text
===== MOVIE TICKET BOOKING =====
1. List movies
2. List shows for a movie
3. Display seat layout
4. Book ticket
5. Cancel booking
6. Exit
```
🎫 Example Booking Flow
```text
Select a show
      ↓
Display available seats
      ↓
Enter number of seats
      ↓
Enter seat numbers
      ↓
Choose payment method
      ↓
Payment successful
      ↓
Booking confirmed
      ↓
Ticket generated
```
📐 Design Artifacts
The repository also contains the design documentation created for the project:
Requirement analysis
Noun–verb analysis
Relationship analysis
UML class diagram
UML sequence diagram
SOLID mapping
Compilation instructions
Demo run documentation
🔮 Possible Future Improvements
The current implementation is intentionally focused on the core system-design problem. Possible extensions include:
Database persistence
User authentication
Admin movie/show management
Online payment gateway integration
Multiple cinema locations
Booking history
Refund processing
REST API / web interface
Concurrent booking protection
👨‍💻 Author
Sachin Lakheda
GitHub: SACHIN78957
Repository: movie-ticket-booking-system
---
⭐ If you find this project useful, feel free to explore the code and design artifacts.
