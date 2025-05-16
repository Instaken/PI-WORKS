# PI-WORKS
This is the answer of the 5th question in the Technical Questionnaire for PI.Works

# User Interface Specification Document

## Screen: User Management Interface

### Purpose

This document describes the specifications of the user management screen, including its UI components, expected behaviors, and interactions. It is intended for developers implementing the UI using modern web frameworks.

---

## 1. **Page Overview**

The user management interface allows system administrators to manage platform users. Actions include:

* Viewing current users.
* Adding new users.
* Filtering and hiding disabled users.
* Updating user information.

---

## 2. **UI Components & Behavior**

### 2.1 User Table (Left Panel)

* **Fields:**

  * ID (auto-generated)
  * User Name
  * Email
  * Enabled (true/false)
* **Behaviors:**

  * Users are listed in a tabular view.
  * The table can be sorted by clicking the arrow icons in the column headers.
  * Disabled users can be hidden via the "Hide Disabled User" toggle button.

### 2.2 Buttons (Top)

* `+ New User`:

  * Clears the form on the right to allow entry of a new user.
* `Hide Disabled User`:

  * Filters the table to hide rows where "Enabled" is false.
* `Save User`:

  * Saves the data in the form (new or updated).
  * Validates all required fields before submitting.

---

### 2.3 New User Form (Right Panel)

* **Fields:**

  * **Username** (text, required)
  * **Display Name** (text)
  * **Phone** (text, optional)
  * **Email** (email, required)
  * **User Roles** (dropdown multi-select with options: Guest, Admin, SuperAdmin)
  * **Enabled** (checkbox, true/false)

* **Behavior:**

  * When a user is selected in the table, this form is populated with that user's data for editing.
  * Validation:

    * `Username` and `Email` are required.
    * `Email` must be a valid email format.
  * The `Enabled` checkbox reflects the active status of the user.

---

## 3. **Initial State**

* All users (enabled and disabled) are visible by default.
* No user is selected initially.
* The form on the right is empty until a user is selected or the "New User" button is clicked.

---

## 4. **Error & Success Handling**

* On failed validation, display messages inline below each field.
* On save success, a green notification should appear: `"User saved successfully."`
* On save failure, a red notification should appear: `"Error saving user. Please try again."`

---

## 5. **Notes for Developers**

* Ensure proper tab-index for keyboard accessibility.
* All fields should be clearly labeled.
* Use standard web components or UI libraries that match the current platform design.
* Make sure changes are persistent and updated in the backend after saving.

---

## 6. **Dependencies**

* Backend APIs:

  * `GET /users`
  * `POST /users`
  * `PUT /users/{id}`

---

## 7. **Future Enhancements (Optional)**

* Add search functionality.
* Add pagination.
* Show user creation/modification timestamps.


