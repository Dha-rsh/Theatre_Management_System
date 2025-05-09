Title: Book My Ticket
--------------------
Target Audience: Theatre Managers, Booking Agents

End users:  Public peoples, Students, Families, Movie Buffs, Theatre Enthusiasts, Event Organizers

Type: B2C(Business to Customer)

Timeline: 1 month

Budget: 1lakh

Total Members: 6

Features: 
---------
    • Search for Movies/Events - Users can search for movies and events based on genres, dates, and locations.
    
    • Seat Availability and Layout - seat availability with a graphical layout to select seats.
    
    • Show Scheduling - Admin can manage movie schedules, showtimes, and screen availability.
    
    • Ticket Booking -Online booking with seat selection, updates offline selection to ensure no double-booking.
    
    • Payment -Secure online payments.
    
    • Ticket Cancellation/Refund Option - Users can cancel tickets and request refunds.
    
    • User Reviews and Ratings for Movies/Events -Users can rate and review movies.
    
    • Admin Panel -Admin can manage schedules, sales data, customer information, and generate reports.
    
    • Movie Information -Movie details page displaying cast, ratings, showtimes, etc.
    
    • Email/SMS Notifications - Users receive confirmations, reminders,  messages related to bookings.

Future Features:
---------------
    • Reward Points - Earn points on every booking,redeem for discounts, free tickets, or snacks
    
    • Voice & Chatbot Support - Book or cancel tickets via voice commands or AI chat assistant
    
    • Waitlist & Auto Booking - Add users to a waitlist for sold-out shows and auto-book when seats open
    
    • Dynamic Pricing: Price variations based on demand, time, and seat location.


1. Class User
{
    - userID: int
    - userName: String
    - email: String
    - password: String
    - phoneNumber: String
    - role: String  // "admin", "customer"
}
  
2. Class MovieEvent
{
    - eventID: int
    - title: String
    - type: String  // "Movie" or "Event"
    - genre: String
    - language: String
    - description: String
    - cast: List<String>
    - duration: String
    - releaseDate: Date
    - rating: float
    - posterURL: String
  } 
3. Class Schedule
{
    - scheduleID: int
    - eventID: int
    - screenID: int
    - date: Date
    - showTime: String
    - totalSeats: int
    - availableSeats: int
  } 
4. Class Screen
{
    - screenID: int
    - name: String
    - theaterID: int
    - totalSeats: int
    - layout: String  // JSON or XML for graphical layout mapping
  } 
5. Class Theater
{
    - theaterID: int
    - name: String
    - location: String
    - contactInfo: String
  } 
6. Class Seat
{
    - seatID: int
    - screenID: int
    - row: String
    - number: int
    - seatType: String  // e.g., "Regular", "VIP"
  } 
7. Class Booking
{
    - bookingID: int
    - userID: int
    - scheduleID: int
    - bookedSeats: List<String>  // ["A1", "A2"]
    - bookingTime: DateTime
    - status: String  // "Confirmed", "Cancelled", "Refunded"
    - totalAmount: float
    - paymentID: int
  }

8. Class Payment
    {
    - paymentID: int
    - bookingID: int
    - amount: float
    - paymentMethod: String  // "Credit Card", "UPI", etc.
    - paymentStatus: String  // "Success", "Failed", "Refunded"
    - paymentDate: DateTime
    }

9. Class Cancellation
{
    - cancellationID: int
    - bookingID: int
    - cancelledOn: DateTime
    - refundAmount: float
    - refundStatus: String  // "Pending", "Completed"
  }

10. Class Review
{
    - reviewID: int
    - userID: int
    - eventID: int
    - rating: int  // 1 to 5
    - comment: String
    - reviewDate: Date
}

11. Class AdminPanel
{
    - totalUsers: int
    - totalBookings: int
    - revenue: float
    - activeSchedules: List<Schedule>
    - customerQueries: List<String>
    - reportsGenerated: List<String>
}

12. Class Notification
{
    - notificationID: int
    - userID: int
    - message: String
    - type: String  // "Confirmation", "Reminder", "Refund"
    - sentVia: String  // "Email", "SMS"
    - sentOn: DateTime
}

13. Class SearchFilter
{
    - keyword: String
    - genre: String
    - date: Date
    - location: String
    - type: String  // "Movie" or "Event"
}
