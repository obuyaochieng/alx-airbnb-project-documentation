# User Stories - Airbnb Clone Backend

## Overview
This document contains user stories derived from the use case diagram. Each user story follows the format: **"As a [user type], I want to [action] so that [benefit]."**

---

## User Stories

### US-001: User Registration
**As a** new user  
**I want to** register an account  
**So that** I can access the platform and start using its features

**Acceptance Criteria:**
- User can create account with email and password
- System validates email format and password strength
- User receives confirmation upon successful registration
- User can choose role (Guest or Host) during registration

**Related Use Cases:** Signup, Superhost

---

### US-002: Browse Properties
**As a** guest  
**I want to** browse available properties  
**So that** I can find suitable accommodations for my trip

**Acceptance Criteria:**
- System displays list of available properties
- Each property shows key details (name, location, price)
- Properties can be filtered by location, price, and amenities
- User can view property images and descriptions

**Related Use Cases:** Browse menu, Search room, Available Property

---

### US-003: Search and Filter Properties
**As a** guest  
**I want to** search properties by location and apply filters  
**So that** I can find accommodations that meet my specific needs

**Acceptance Criteria:**
- User can enter location (city or address) to search
- User can filter by price range using "Enter Price Range"
- User can filter by room type using "Enter Room Type"
- User can apply multiple filters simultaneously
- Search results update based on applied filters

**Related Use Cases:** Search room, Enter Price Range, Enter Room Type, Apply More Filters, Select Property, Form Option

---

### US-004: Book Property
**As a** guest  
**I want to** book a property for specific dates  
**So that** I can secure accommodation for my stay

**Acceptance Criteria:**
- User can select check-in and check-out dates
- System verifies property availability using "Confirm Availability"
- User can enter number of guests
- System calculates total price automatically
- User can review booking details before confirming
- Booking is created only after successful payment

**Related Use Cases:** Instant Book, Check ID card/ID, Confirm Availability, Book Property, Enter check-in, Enter check-out, Number of guests, Calculation Policy

---

### US-005: Make Payment
**As a** guest  
**I want to** securely pay for my booking  
**So that** I can confirm my reservation

**Acceptance Criteria:**
- User can choose payment method (Credit Card, Debit Card, PayPal)
- Payment information is processed securely
- System validates payment details
- User receives payment confirmation
- Booking status changes to "confirmed" after successful payment

**Related Use Cases:** Make Payment, Credit Card, Debit Card, PayPal, Confirm Availability

---

### US-006: View Booking History
**As a** guest  
**I want to** view my past and upcoming bookings  
**So that** I can track my reservations

**Acceptance Criteria:**
- User can access booking history from their profile
- System displays all bookings (past, current, upcoming)
- Each booking shows property name, dates, and status
- User can click on booking to view full details

**Related Use Cases:** Initial Book, Request To Book

---

### US-007: Write Property Review
**As a** guest  
**I want to** review a property after my stay  
**So that** I can share my experience with other users

**Acceptance Criteria:**
- User can only review properties where stay is completed
- User can provide star rating (1-5)
- User can write detailed comment about their experience
- Review is published immediately after submission
- Host receives notification of new review

**Related Use Cases:** Enter Reviews, Strict

---

### US-008: List Property
**As a** host  
**I want to** create a property listing  
**So that** I can rent out my property to guests

**Acceptance Criteria:**
- Host can enter property details (name, description, location)
- Host can upload multiple property images
- Host can set pricing using "Enter Price Range"
- Host can specify amenities using "Enter Amenities"
- Host can define house rules and policies
- Listing is saved and visible to guests after approval

**Related Use Cases:** Private room, House or Apartment, Search room, Enter Price Range, Enter Amenities, Calculation Policy

---

### US-009: Manage Property Availability
**As a** host  
**I want to** update my property's availability  
**So that** I can control when my property can be booked

**Acceptance Criteria:**
- Host can access property calendar
- Host can block specific dates as unavailable
- Host can unblock previously blocked dates
- Changes are reflected immediately
- Guests cannot book blocked dates

**Related Use Cases:** Available Property, Confirm Availability

---

### US-010: Respond to Booking Requests
**As a** host  
**I want to** accept or decline booking requests  
**So that** I can manage reservations for my property

**Acceptance Criteria:**
- Host receives notification of new booking request
- Host can view booking details (dates, guest count, guest profile)
- Host can accept booking using "Confirmation"
- Host can decline booking with optional reason
- Guest is notified of host's decision
- Accepted bookings appear on host's calendar

**Related Use Cases:** Request To Book, Confirmation, Flexible

---

### US-011: Receive Payments
**As a** host  
**I want to** receive payments for confirmed bookings  
**So that** I can earn income from my property

**Acceptance Criteria:**
- Host receives payout after guest check-in
- System calculates host earnings (total minus service fee)
- Host can view payment history
- Host can track pending and completed payouts
- Payments are processed automatically

**Related Use Cases:** Enter Payments, Date Of Member Join, Confirm Availability

---

### US-012: Send and Receive Messages
**As a** user (guest or host)  
**I want to** communicate with other users  
**So that** I can ask questions or share information about bookings

**Acceptance Criteria:**
- User can send messages to other users
- User receives real-time notifications of new messages
- Message history is preserved
- User can view conversation threads
- Messages are only visible to sender and recipient

**Related Use Cases:** Email, Enter Reviews, Feedback, Google, Ames, Sign up

---

### US-013: Manage Profile
**As a** user  
**I want to** update my profile information  
**So that** I can keep my account details current

**Acceptance Criteria:**
- User can edit personal information (name, email, phone)
- User can upload profile picture
- User can update password
- Changes are saved immediately
- User receives confirmation of updates

**Related Use Cases:** Check ID card/ID, Superhost, Date Of Member Join

---

### US-014: Apply Property Filters
**As a** guest  
**I want to** use advanced filters when searching  
**So that** I can narrow down results to find the perfect property

**Acceptance Criteria:**
- User can filter by multiple criteria simultaneously
- Available filters include:
  - Price range ("Enter Price Range")
  - Room type ("Enter Room Type")  
  - Amenities ("Enter Amenities")
  - More options ("Apply More Filters")
- Filters can be cleared or modified
- Results update dynamically as filters are applied

**Related Use Cases:** Enter Price Range, Enter Room Type, Enter Amenities, Apply More Filters, Form Option

---

### US-015: View Property Details
**As a** guest  
**I want to** view complete property information  
**So that** I can make an informed booking decision

**Acceptance Criteria:**
- Property page displays all details (description, amenities, rules)
- User can view all property images
- User can see host information ("House or Apartment")
- User can read existing reviews ("Enter Reviews")
- User can check availability calendar
- Location is shown on map

**Related Use Cases:** Select Property, Available Property, House or Apartment, Enter Reviews

---

### US-016: Set Cancellation Policy
**As a** host  
**I want to** define cancellation policy for my property  
**So that** I can protect myself from last-minute cancellations

**Acceptance Criteria:**
- Host can choose from predefined policies (Flexible, Strict)
- Policy options include:
  - Flexible cancellation ("Flexible")
  - Strict cancellation ("Strict")
  - Custom policy ("Calculation Policy")
- Policy is displayed to guests before booking
- Refunds are calculated automatically based on policy

**Related Use Cases:** Flexible, Strict, Calculation Policy

---

### US-017: Track Check-in/Check-out
**As a** guest or host  
**I want to** manage check-in and check-out times  
**So that** I can coordinate arrival and departure

**Acceptance Criteria:**
- Guest can specify expected check-in time
- Host can set check-in and check-out time windows
- System sends reminders before check-in/check-out
- Both parties can view check-in/check-out details

**Related Use Cases:** Enter check-in, Enter check-out, Confirm Availability

---

### US-018: Verify User Identity
**As a** platform administrator  
**I want to** verify user identities  
**So that** I can maintain platform security and trust

**Acceptance Criteria:**
- Users can upload ID documents for verification
- System validates ID information
- Verified users receive badge/indicator
- Hosts can require verified guests for bookings

**Related Use Cases:** Check ID card/ID, Superhost

---

### US-019: Provide Feedback
**As a** user  
**I want to** submit feedback about the platform  
**So that** I can help improve the service

**Acceptance Criteria:**
- User can access feedback form
- User can describe their experience or issue
- User can attach screenshots (optional)
- Feedback is submitted to support team
- User receives acknowledgment of submission

**Related Use Cases:** Feedback, Enter Reviews

---

### US-020: Integrate Social Login
**As a** new user  
**I want to** sign up using my social media account  
**So that** I can register quickly without creating new credentials

**Acceptance Criteria:**
- User can sign up using Google account
- User can connect other social accounts
- Profile information is imported from social account
- User can link/unlink social accounts after registration

**Related Use Cases:** Google, Ames, Sign up

---

## User Story Mapping

### Epic 1: Guest Experience
- US-001: User Registration
- US-002: Browse Properties
- US-003: Search and Filter Properties
- US-004: Book Property
- US-005: Make Payment
- US-006: View Booking History
- US-007: Write Property Review

### Epic 2: Host Management
- US-008: List Property
- US-009: Manage Property Availability
- US-010: Respond to Booking Requests
- US-011: Receive Payments
- US-016: Set Cancellation Policy

### Epic 3: Communication
- US-012: Send and Receive Messages
- US-019: Provide Feedback

### Epic 4: User Profile & Security
- US-013: Manage Profile
- US-018: Verify User Identity
- US-020: Integrate Social Login

### Epic 5: Search & Discovery
- US-014: Apply Property Filters
- US-015: View Property Details

---

## Prioritization

### Must Have (MVP)
- US-001: User Registration
- US-002: Browse Properties
- US-004: Book Property
- US-005: Make Payment
- US-008: List Property

### Should Have (Phase 2)
- US-003: Search and Filter Properties
- US-006: View Booking History
- US-009: Manage Property Availability
- US-010: Respond to Booking Requests
- US-012: Send and Receive Messages

### Nice to Have (Phase 3)
- US-007: Write Property Review
- US-013: Manage Profile
- US-016: Set Cancellation Policy
- US-018: Verify User Identity
- US-020: Integrate Social Login

---

## Conclusion
These user stories capture all the core interactions from the use case diagram, providing a clear roadmap for developing the Airbnb Clone backend system. Each story is designed to deliver value to users while maintaining a focus on essential functionality.