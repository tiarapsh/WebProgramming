# Wireframe & User Flow — SIMPUS-Mini

Sub-CPMK: Design the UI/UX of the application (project).

The existing pages (Home, Add/List Books, Add/List Members — Jobsheets 1-3) don't yet include Login, Officer Dashboard, and Borrowing/Return features. This document designs wireframes for those pages before implementation starting in Jobsheet 5 and onwards.

## Actors
- **Guest**: can only view the book catalog (Home, Book List) without signing in.
- **Officer**: signs in to access all CRUD features and borrowing transactions.


## User Flow — Borrow Book

```
[Officer Sign In] -> [Dashboard] -> [Select "New Borrowing" menu]
        -> [Select Member] -> [Select Book (stock > 0)]
        -> [Save] -> [Book stock decreases by 1] -> [Back to Dashboard]
```

## User Flow — Return Book

```
[Dashboard] -> [Select "Return" menu] -> [Search active transaction (member/book)]
        -> [Mark "Returned"] -> [Book stock increases by 1]
        -> [Back to Dashboard]
```

## User Flow — Search Overdue Loans
```
[Officer Sign In] -> [Dashboard] -> [Select "Borrowing" menu]
        -> [Filter by Status: "Overdue"] -> [Click "Search / Filter"]
        -> [Display list of members with overdue loans and late fees]
        -> [Optional: Select member to view details / send reminder]
        -> [Back to Dashboard]

```

## Wireframe: Login Page

```
+--------------------------------------+
|              SIMPUS-Mini             |
|--------------------------------------|
|                                      |
|        [ Officer Sign In ]          |
|                                      |
|   Username : [______________]       |
|   Password : [______________]       |
|                                      |
|          [   Sign In   ]            |
|                                      |
|   Don't have an account? Sign up    |
+--------------------------------------+
```

## Wireframe: Officer Dashboard

```
+-----------------------------------------------------+
| SIMPUS-Mini      Home | Books | Members | Borrowing | (Officer Name) Logout |
|-------------------------------------------------------|
|  [Total Books]   [Total Members]   [Currently Borrowed]    |
|                                                         |
|  Quick Actions:                                        |
|  [ + New Borrowing ]   [ + Return ]                    |
|                                                         |
|  Recent Transactions                                  |
|  --------------------------------------------------    |
|  Member | Book | Borrow Date | Status                  |
+-----------------------------------------------------+
```

## Wireframe: Book Borrowing Form

```
+--------------------------------------+
|  Book Borrowing Form                 |
|--------------------------------------|
|  Member : [ dropdown select member ] |
|  Book    : [ dropdown, stock > 0 ]   |
|  Borrow Date : [ auto: today ]       |
|                                      |
|          [  Save Borrowing  ]       |
+--------------------------------------+
```

## Wireframe: Book Return Form

```
+--------------------------------------+
|  Book Return                         |
|--------------------------------------|
|  Search active transaction:          |
|  [ member name / book title ______] |
|                                      |
|  Member | Book | Borrow Date | [Return] |
+--------------------------------------+
```

## Wireframe: Member Borrow History

```
+--------------------------------------+
|  Borrow History — Siti Aminah        |
|--------------------------------------|
|  Book            | Borrow   | Return | Status      |
|  Laskar Pelangi   | 01/07    | 10/07   | Completed   |
|  Bumi Manusia     | 15/07    | -       | Borrowed    |
+--------------------------------------+
```

## Register New Member

```
+-----------------------------------------------------------------------+
|  SIMPUS-Mini                               [Home] [Book List] [Login] |
+-----------------------------------------------------------------------+
|                                                                       |
|  REGISTER NEW MEMBER                                                  |
|  Fill in your details below to request a library membership card.     |
|                                                                       |
|  Full Name:                                                           |
|  [___________________________________________________________]        |
|                                                                       |
|  Student ID (NIM) / National ID (NIK):                                |
|  [___________________________________________________________]        |
|                                                                       |
|  Study Program / Department:                                          |
|  [Select Study Program                                      v]        |
|                                                                       |
|  Email Address:                                                       |
|  [___________________________________________________________]        |
|                                                                       |
|  Phone / WhatsApp Number:                                             |
|  [___________________________________________________________]        |
|                                                                       |
|  Password:                                                            |
|  [***********************************************************]        |
|                                                                       |
|  Confirm Password:                                                    |
|  [***********************************************************]        |
|                                                                       |                       
|                                                                       |
|  [ Submit Registration ]                                              |
|                                                                       |
|  Already registered? [Sign in here]                                   |
|                                                                       |
+-----------------------------------------------------------------------+
| (c) SIMPUS-Mini 2026 -                                                |
+-----------------------------------------------------------------------+
```


## Consistency with Existing Design
- Accent colors, navbar typography, and table/card styles follow `assets/css/style.css` built in Jobsheets 2-3.
- Navbar will add a **Borrowing** menu and login status indicator (officer name / Logout button) starting implementation in Jobsheet 10.
- Edge cases to handle during implementation: books with zero stock cannot be selected in borrowing forms; members with overdue fees are validated in Jobsheet 12 (independent assignment).
