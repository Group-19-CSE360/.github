# SunDevil Bookstore

**CSE 360 Fall 2024 Project**

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies & Frameworks](#technologies--frameworks)
- [Installation](#installation)
- [Usage](#usage)
- [Team Members](#team-members)
- [Contributions](#contributions)
- [Testing](#testing)
- [Data Design](#data-design)
- [Conclusions](#conclusions)
- [Contact](#contact)

---

## Overview

SunDevil Bookstore is a comprehensive online platform designed to facilitate the buying and selling of books within the university community. Developed as part of the CSE 360 Fall 2024 project, the system supports multiple user roles, including Buyers, Sellers, and Admins, each with distinct functionalities. The application ensures a seamless user experience through a responsive GUI and robust backend services.

---

## Features

### Core Functionalities

1. **Sign-Up and Login**
   - **Sign-Up:** Users can create accounts by providing their first name, last name, email, password, and username. By default, users are assigned the "Buyer" role. Users can request the "Seller" role, which requires admin approval.
   - **Login:** Unified login for Buyers, Sellers, and Admins with input validation and error messaging. Includes a secure "Forgot Password" flow with email recovery and OTP verification.

2. **User Profile Management**
   - Users can edit their personal information, including name, email, and password. Password resets require current password validation.

3. **Buyer Functionalities**
   - **Book Browsing:** Browse books with filters for category (e.g., Computer Science, Mathematics) and condition (Like New, Moderately Used, Heavily Used). Search functionality by title or author.
   - **Cart Management:** View cart items with details like ISBN, publisher, condition, price, and totals including tax and admin fees. Users can adjust quantities, remove items, and proceed to checkout integrated with myASU finances.

4. **Seller Functionalities**
   - **Book Listings:** Sellers can list books by providing title, condition, category, original price, and images. Selling prices are calculated by the system and require admin approval.
   - **Listing Management:** Manage current listings with status indicators and view sales statistics categorized by category and revenue.

5. **Admin Functionalities**
   - **Statistics:** Access sales data by category, condition, and time period, visualized through graphs and tables.
   - **User Account Management:** View, add, edit, delete, promote/demote users, and ban or restrict accounts.
   - **Transaction Overview:** Detailed view of all transactions with filtering, sorting, and CSV export capabilities.
   - **System Configuration:** Adjust pricing formulas, condition multipliers, and admin profit margins.

### Additional Technical Features

- **Input Validation:** Ensures data integrity across all user inputs.
- **Role-Based Access Control:** Tailors functionalities and views based on user roles.
- **Error Handling:** Provides context-specific error messages to enhance user experience.
- **Data Export:** Allows exporting user and transaction data in CSV format.
- **Dynamic Pricing:** Implements modifiable condition adjustments and profit margins.
- **Responsive GUI Design:** Delivers a consistent and intuitive user interface across different roles.

---

## Technologies & Frameworks

- **Java:** Core programming language used for application logic.
- **JavaFX:** Framework for building the graphical user interface.
- **SQLite:** Lightweight database for data storage and management.
- **Maven:** Build automation and dependency management tool.

---
## Usage

Upon launching the application, users can:

- **Sign Up** as a Buyer or request Seller access.
- **Log In** using their credentials.
- **Browse and Search** for books based on various criteria.
- **Manage their Cart** and proceed to checkout.
- **Sellers** can list new books and monitor their sales.
- **Admins** have access to comprehensive system controls and analytics.

---

## Team Members

**Team 19**

- **James Hu** ([jameshu-asu](https://github.com/jameshu-asu))
- **Jaya Adithya Pavuluri** ([jay2044](https://github.com/jay2044))
- **Sahil Sinha** ([sayhilel](https://github.com/sayhilel))
- **Shubham Khalkho** ([Shubhoom123](https://github.com/Shubhoom123))
- **Vineet Yerramsett** ([vineety-cs](https://github.com/vineety-cs))

---

## Contributions

### Technical Summary

**SunDevil Bookstore System:**

- **Core Features:** Implemented user authentication, profile management, buyer and seller functionalities, and admin controls.
- **Key Technical Elements:** Ensured robust input validation, role-based access, comprehensive error handling, data visualization, and responsive GUI design.

### Development Team Contributions

- **James Hu, Jaya Adithya Pavuluri, Sahil Sinha:** Developed the GUI walkthrough and project overview sections.
- **Shubham Khalkho:** Led the GUI walkthrough development.
- **Vineet Yerramsett:** Managed the project overview documentation.

---

## Testing

### Testing Plan Overview

- **Manual Testing:** Verified UI accessibility, field validations, navigation flows, and error handling.
- **Automated Testing:** Ensured backend data consistency, input validations, and business logic integrity.

### Test Coverage Highlights

- **Login & Authentication:** Validated role-based access and secure password handling.
- **Profile Management:** Ensured accurate updates to user information.
- **Book Browsing & Cart Operations:** Tested search filters, cart updates, and checkout processes.
- **Admin Controls:** Verified user management, transaction overviews, and system configurations.
- **Data Export:** Confirmed accurate CSV exports of user and transaction data.

### Failed Tests Writeup

- **Password Reset (Forgot Password):** Not implemented due to limitations with live database and SMTP setup.
- **Transaction Processing:** Payment integration pending, requiring an online payment provider.
- **Advanced User Management:** Features like banning and promoting users were excluded due to time constraints.
- **Transaction Filters:** Additional database functionalities needed for advanced filtering were not implemented.

---

## Data Design

### Entities

1. **Users**
   - **Attributes:** ID, name, email, role, status.
   - **Relationships:** Managed by `UserManager` and `SessionManager`.

2. **Books**
   - **Attributes:** ID, title, author, price, condition, seller_id.
   - **Relationships:** Handled by `BookListings` and `Cart`.

3. **Cart**
   - **Attributes:** Selected books, quantities, total cost.
   - **Relationships:** Controlled by `CartController` and `PaymentSystem`.

4. **Transactions**
   - **Attributes:** ID, buyer_id, seller_id, amount, admin_profit.
   - **Relationships:** Managed by `TransactionManager`.

5. **ApprovalSystem**
   - **Relationships:** Interfaces with Admin and `ListingManager`.

6. **SalesStatisticsCalculator**
   - **Relationships:** Utilizes Admin and `Database`.

### Key Attributes

- **Users:** `id`, `name`, `email`, `role`, `status`.
- **Books:** `id`, `title`, `author`, `price`, `condition`, `seller_id`.
- **Transactions:** `id`, `buyer_id`, `seller_id`, `amount`, `admin_profit`.

---

## Conclusions

### What Worked

- **MVC Architecture:** Maintained a clear separation of concerns, enhancing code maintainability.
- **Database Management:** Centralized interactions through `DatabaseManager.java` ensured efficient data handling.
- **Team Collaboration:** Effective communication and regular updates facilitated smooth project progression.

### What Didn't Work

- **Frontend Technology Shift:** Transitioning from HTML to JavaFX caused initial delays.
- **Feature Scope Limitations:** Certain features like comprehensive password reset and advanced transaction filtering were not implemented due to time constraints.

### Lessons Learned

- **Regular Client Engagement:** Continuous check-ins help accommodate evolving requirements.
- **Comprehensive Documentation:** Maintaining clear and detailed documentation supports better collaboration and project tracking.

### Defect Management

- **Early Phases:** Minimal defects with straightforward issues.
- **Phase 3 Challenges:** Encountered approximately 30 defects related to merge conflicts and complex bugs, which were resolved collaboratively.

---

## Contact

For any queries or contributions, please reach out to the team members via their GitHub profiles:

- **James Hu:** [jameshu-asu](https://github.com/jameshu-asu)
- **Jaya Adithya Pavuluri:** [jay2044](https://github.com/jay2044)
- **Sahil Sinha:** [sayhilel](https://github.com/sayhilel)
- **Shubham Khalkho:** [Shubhoom123](https://github.com/Shubhoom123)
- **Vineet Yerramsett:** [vineety-cs](https://github.com/vineety-cs)

---

## Project Deliverables

1. **Technical Presentation:**  
   [View Presentation](https://drive.google.com/file/d/1tRCHFX7j1RB0c2HsIGri8V7MsihUtOKu/view?usp=sharing)

2. **Final Class Diagram:**  
   Includes high-resolution `.asta` and image files.

---

© 2024 SunDevil Bookstore Project Team
