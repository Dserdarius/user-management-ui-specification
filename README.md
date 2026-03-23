# user-management-ui-specification

## 1. Overview 
This Document describes the User management screen. The screen allows administrators to manage users by viewing, filtering, creating, and updating user information.

## 2. Layout Structure
The screen is divided into two main sections:
- **Left Panel:** User list (table)
- **Right Panel:** User form (create/update)

## 3. Initial Page State
When the page loads:
- User table is displayed with existing users
- Form on the right is empty or populated based on selection
- "Hide Disabled User" is unchecked by default
- "New User" button is visible

## 4. UI Components
### 4.1 Header Actions
#### New User Button
- Type: Button
- Label: "+ New User"
- Behavior:
  - Clears the form
  - Prepares screen for new user entry

#### Hide Disabled User
- Type: Checkbox
- Label: "Hide Disabled User"
- Default: Unchecked
- Behavior:
  - Checked → Disabled users are hidden from the table
  - Unchecked → All users are shown

#### Save User Button
- Type: Button
- Location: Top-right
- Behavior:
  - Saves new or updated user
  - Validates input before saving

### 4.2 User Table (Left Panel)
Columns:
**Column Name | Description**       
ID            | Unique identifier 
User Name     | User name         
Email         | User email        
Enabled       | true / false      

Features:
- Sort icons on column headers
- Row selection enabled
- Selected row is highlighted
Behavior:
- Clicking a row loads user data into the form
- Table updates after save

### 4.3 User Form (Right Panel)
#### Section Title
- "New User"
#### Input Fields

**Field        | Type         | Description**
Username       | Text Input   | Required 
Display Name   | Text Input   | Required 
Phone          | Text Input   | Optional 
Email          | Text Input   | Required 
User Roles     | Dropdown     | Single-select 
Enabled        | Checkbox     | Active status 

### 4.4 User Roles Dropdown
- Type: Single-select dropdown
- Options:
  - Guest
  - Admin
  - SuperAdmin
- Behavior:
  - Selected roles are displayed in input
  - Only one role can be chosen 

## 5. User Interactions
### Selecting a User
1. Click a row in the table
2. User details appear in the form

### Creating a New User
1. Click "+ New User"
2. Form is cleared
3. Enter user details
4. Click "Save User"
5. New user appears in table

### Updating a User
1. Select user from table
2. Modify fields
3. Click "Save User"
4. Table updates

### Filtering Disabled Users
1. Check "Hide Disabled User"
2. Disabled users are hidden
3. Uncheck to show all users

## 6. Validation Rules
- Username: Required
- Display Name: Required
- Email: Must be valid format
- Role must be selected

## 7. Error Handling
- Empty required fields → "This field is required"
- Invalid email → "Invalid email format"
- Save failure → "Unable to save user"

## 8. Success Messages
- "User saved successfully"
- "User updated successfully"
- "User enabled succesfully"

## 9. UX Notes
- Selected row should be visually highlighted
- Form should clearly indicate edit vs new mode
- Save button should be disabled if form is invalid

## 10. Assumptions
- Roles are predefined
