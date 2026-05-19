# 📚 Library Management System

> A comprehensive, menu-driven Library Management System built with Python. Manage books, members, and loans with ease!

![Python](https://img.shields.io/badge/Python-3.7+-blue?style=flat-square&logo=python)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)

## ✨ Features

- 📖 **Book Management**: Add and manage books in the library with unique IDs, titles, and authors
- 👥 **Member Registration**: Register library members with contact information
- 🔄 **Loan Management**: Track book borrowing and returns with automatic loan IDs
- 📊 **View Operations**: Display all books, members, and active/closed loans
- ⚠️ **Error Handling**: Comprehensive exception handling with custom error messages
- 🎨 **User-Friendly Interface**: Interactive menu-driven CLI with clear visual feedback
- ✅ **Input Validation**: Validates all user inputs before processing

## 🏗️ Architecture

### Directory Structure

```
library-management-system/
├── models/                    # Data models
│   ├── __init__.py
│   ├── book.py               # Book class definition
│   ├── member.py             # Member class definition
│   └── loan.py               # Loan class definition
├── service/                   # Business logic
│   ├── __init__.py
│   └── library_service.py    # LibraryService class
├── exceptions.py              # Custom exception classes
├── main.py                    # CLI interface
├── README.md                  # This file
└── .gitignore                 # Git ignore rules
```

### Class Hierarchy

**Book**
- `book_id` (str): Unique identifier
- `title` (str): Book title
- `author` (str): Author name
- `available` (bool): Availability status
- Methods: `borrow()`, `return_book()`

**Member**
- `member_id` (str): Unique identifier
- `name` (str): Member name
- `email` (str): Email address

**Loan**
- `loan_id` (str): Unique identifier
- `book` (Book): Reference to borrowed book
- `member` (Member): Reference to member
- `loan_date` (datetime): Borrow date/time
- `return_date` (datetime): Return date/time (if returned)
- `is_active` (bool): Active status
- Methods: `close_loan()`

**LibraryService**
- Core business logic for all operations
- Methods for CRUD operations on books, members, and loans
- Exception handling and validation

## 🚀 Getting Started

### Prerequisites

- Python 3.7 or higher
- pip (Python package manager)

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/clarkgueta59-blip/library-management-system.git
   cd library-management-system
   ```

2. **Create a virtual environment** (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Run the application**:
   ```bash
   python main.py
   ```

## 📖 Usage Guide

### Main Menu Options

```
==================================================
        LIBRARY MANAGEMENT SYSTEM
==================================================
1. Add Book          - Add a new book to the library
2. Register Member   - Register a new library member
3. Borrow Book       - Create a loan record
4. Return Book       - Return a borrowed book
5. View Books        - Display all books
6. View Members      - Display all members
7. View Loans        - Display all loans
8. Exit              - Close the program
==================================================
```

### Example Workflow

```
🎉 Welcome to the Library Management System!

1. Add a Book
   - Book ID: B001
   - Title: The Great Gatsby
   - Author: F. Scott Fitzgerald
   ✅ Book added: The Great Gatsby

2. Register a Member
   - Member ID: M001
   - Name: John Doe
   - Email: john@example.com
   ✅ Member registered: John Doe

3. Borrow a Book
   - Book ID: B001
   - Member ID: M001
   ✅ John Doe borrowed The Great Gatsby
      Loan ID: L001

4. Return the Book
   - Loan ID: L001
   ✅ John Doe returned The Great Gatsby
      Loan ID: L001
```

## 🛡️ Error Handling

The system includes comprehensive error handling with custom exceptions:

- **BookNotFoundError**: Raised when a book ID doesn't exist
- **MemberNotFoundError**: Raised when a member ID doesn't exist
- **BookUnavailableError**: Raised when attempting to borrow an already borrowed book
- **LoanNotFoundError**: Raised when a loan ID doesn't exist

All errors are caught and displayed with user-friendly messages.

## 💾 Data Storage

The system uses in-memory storage:
- **Books**: Dictionary (book_id → Book)
- **Members**: Dictionary (member_id → Member)
- **Loans**: List of Loan objects
- **Loan Counter**: Auto-incremented for generating loan IDs

**Note**: Data is lost when the program exits. For persistent storage, consider implementing database integration.

## 🔮 Future Enhancements

- [ ] Database integration (SQLite/PostgreSQL)
- [ ] User authentication and login system
- [ ] Fine calculation for overdue books
- [ ] Book search and filtering capabilities
- [ ] Member borrowing history
- [ ] Reservation system for unavailable books
- [ ] Email notifications for due dates
- [ ] Admin dashboard with statistics
- [ ] Data export to CSV/PDF
- [ ] Multi-user support with roles

## 📝 Code Quality

- ✅ Well-documented with docstrings
- ✅ Type hints for better IDE support
- ✅ Clean code principles followed
- ✅ Modular architecture for easy maintenance
- ✅ Comprehensive error handling
- ✅ Input validation

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

Please ensure your code follows the existing style and includes appropriate documentation.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

**clarkgueta59-blip**

## 🙏 Acknowledgments

- Thanks to the Python community for excellent documentation
- Inspired by real-world library management needs
- Built with ❤️ for learning and practical application

## 📞 Support

For issues, questions, or suggestions:

1. **GitHub Issues**: Open an issue on the repository
2. **Email**: Contact the project maintainer
3. **Discussions**: Use GitHub Discussions for questions

---

**⭐ If you find this project helpful, please consider giving it a star!**

Happy library managing! 📚✨
