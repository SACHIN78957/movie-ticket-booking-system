# 🎬 Movie Ticket Booking System

A console-based **Movie Ticket Booking System** developed in **C++** using Object-Oriented Programming and System Design principles. The project demonstrates how a real-world booking system can be designed using modular classes, UML diagrams, SOLID principles, and multiple payment methods.

## 🚀 Features

- 🎥 Movie and show management
- 💺 Seat availability and booking
- 🪑 Silver, Gold, and Platinum seat categories
- 💰 Automatic ticket price calculation
- 💳 UPI, Card, and Cash payment options
- ✅ Booking confirmation and ticket generation
- ❌ Booking cancellation
- 🔄 Seat release after cancellation
- ⚠️ Invalid input and booking validation
- 📊 UML Class Diagram
- 🔄 UML Sequence Diagram
- 🧩 Modular C++ implementation
- 🏗️ SOLID principle-based design

## 🛠️ Tech Stack

- **Language:** C++
- **Standard:** C++17
- **Concepts:** OOP, System Design, UML, SOLID
- **STL:** Vector and standard containers
- **Compiler:** g++
- **Version Control:** Git & GitHub

## 🏗️ Main Classes

| Class | Responsibility |
|---|---|
| `Movie` | Stores movie details |
| `Cinema` | Manages cinema screens |
| `Screen` | Manages seats |
| `Seat` | Represents seat number and category |
| `Show` | Connects movie, screen, and show timing |
| `ShowSeat` | Maintains seat availability |
| `Customer` | Stores customer details |
| `Booking` | Represents a booking |
| `BookingService` | Handles booking and cancellation |
| `Payment` | Abstract payment interface |
| `UpiPayment` | Handles UPI payments |
| `CardPayment` | Handles card payments |
| `CashPayment` | Handles cash payments |
| `PriceCalculator` | Calculates ticket price |
| `TicketPrinter` | Displays ticket details |

## 🔄 Booking Workflow

```text
Select Movie
     ↓
Select Show
     ↓
View Seat Layout
     ↓
Select Available Seat
     ↓
Calculate Price
     ↓
Select Payment Method
     ↓
Process Payment
     ↓
Confirm Booking
     ↓
Generate Ticket
💳 Payment Architecture

The project uses an abstract Payment class with separate implementations for UPI, Card, and Cash.

             Payment
            /   |   \
          UPI  Card  Cash

This approach makes the payment system easier to extend with additional payment methods.

💰 Seat Pricing
Seat Type	Price
Silver	₹150
Gold	₹250
Platinum	₹400

The PriceCalculator calculates the total amount based on the selected seat categories.

🧩 SOLID Principles

The project demonstrates important SOLID principles:

SRP: Different classes handle different responsibilities.
OCP: New payment methods can be added without changing existing payment logic.
LSP: Payment implementations can be used through the Payment abstraction.
ISP: Classes are designed around their specific responsibilities.
DIP: Booking logic works with the payment abstraction instead of depending on a specific payment type.
📐 Design Documentation

The repository includes:

Requirement Analysis
Noun–Verb Analysis
Relationship Analysis
UML Class Diagram
UML Sequence Diagram
SOLID Principle Mapping
Demo Run
Compilation Instructions
⚙️ How to Run

Clone the repository:

git clone https://github.com/SACHIN78957/movie-ticket-booking-system.git

Navigate to the project directory:

cd movie-ticket-booking-system
cd "movie ticket booking system"

Compile:

g++ -std=c++17 main.cpp -o movie_booking

Run:

Windows
movie_booking.exe
Linux / macOS
./movie_booking
🖥️ Application Menu
1. List Movies
2. List Shows for a Movie
3. Display Seat Layout
4. Book Ticket
5. Cancel Booking
6. Exit
🧪 Edge Cases Handled
Attempting to book an already booked seat
Invalid seat selection
Invalid movie/show selection
Invalid booking ID
Payment failure
Booking cancellation and seat release
💾 Database

The current version does not use an external database. Data is maintained in memory using C++ objects and STL containers.

A database such as MySQL or PostgreSQL can be integrated in a future version for persistent storage.

🔮 Future Enhancements
Database integration
User authentication
Admin dashboard
Online payment gateway
Real-time seat locking
Booking history
Email/SMS ticket confirmation
Web-based frontend and REST API
👨‍💻 Author

Sachin Lakheda

GitHub:
https://github.com/SACHIN78957/movie-ticket-booking-system

⭐ If you find this project useful, consider giving the repository a star!
