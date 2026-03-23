---
title: "01 User Management"
description: "Requirements for authentication, registration, and user preferences"
draft: false
---

## R-FUNC-00101 User Registration

| | |
|---|---|
| **Status** | Draft |
| **Priority** | High |
| **Category** | FUNC |
| **Relates to** | [FEAT-0101](/features/01-user-management/#feat-0101-user-registration) |

### Statement

The system SHALL allow users to register a new account using their email address and a password.

### Rationale

Users need individual accounts to maintain private, persistent access to their novels and settings.

### Acceptance Criteria

```gherkin
Scenario: Successfully register a new account
  Given I am not logged in
  And I am on the registration page
  When I fill in my email address
  And I fill in a valid password
  And I click the "Register" button
  Then I should receive a verification email
  And I should see a message asking me to verify my email
```

### Verification Method

Manual Test

---

## R-FUNC-00102 Login and Logout

| | |
|---|---|
| **Status** | Draft |
| **Priority** | High |
| **Category** | FUNC |
| **Relates to** | [FEAT-0102](/features/01-user-management/#feat-0102-login-and-logout) |

### Statement

The system SHALL allow registered users to log in using their username and password, and to log out.

### Rationale

Secure authenticated access is fundamental to a multi-user application.

### Acceptance Criteria

```gherkin
Scenario: Successfully log in
  Given I am a registered user
  And I am on the login page
  When I enter my username and password
  And I click the "Login" button
  Then I should be redirected to my dashboard
  And I should see my novels listed

Scenario: Successfully log out
  Given I am logged in
  When I click the "Logout" link
  Then I should be redirected to the login page
  And I should no longer have access to my dashboard
```

### Verification Method

Manual Test

---

## R-FUNC-00103 Password Reset

| | |
|---|---|
| **Status** | Draft |
| **Priority** | High |
| **Category** | FUNC |
| **Relates to** | [FEAT-0103](/features/01-user-management/#feat-0103-password-reset) |

### Statement

The system SHALL allow users to reset their password via their registered email address.

### Rationale

Users must have a way to regain access to their account without support intervention.

### Acceptance Criteria

```gherkin
Scenario: Successfully reset password
  Given I am not logged in
  And I am on the login page
  When I click the "Forgot password" link
  And I enter my registered email address
  And I click the "Send reset link" button
  Then I should receive a password reset email
  And following the link should allow me to set a new password
```

### Verification Method

Manual Test

---

## R-FUNC-00104 Profile Management

| | |
|---|---|
| **Status** | Draft |
| **Priority** | High |
| **Category** | FUNC |
| **Relates to** | [FEAT-0104](/features/01-user-management/#feat-0104-profile-management) |

### Statement

The system SHALL allow users to update their profile information including username, email address, and avatar.

### Rationale

Users need to keep their account information current and personalised.

### Acceptance Criteria

```gherkin
Scenario: Successfully update profile
  Given I am logged in
  And I am on my profile page
  When I change my display name
  And I click the "Save" button
  Then I should see a success message
  And my new display name should appear in the navigation bar
```

### Verification Method

Manual Test

---

## R-FUNC-00105 User Preferences

| | |
|---|---|
| **Status** | Draft |
| **Priority** | High |
| **Category** | FUNC |
| **Relates to** | [FEAT-0105](/features/01-user-management/#feat-0105-user-preferences) |

### Statement

The system SHALL allow users to configure editor preferences including theme and font size, set a daily word count goal, and configure preferred export formats.

### Rationale

Writers have individual preferences that affect their productivity and comfort.

### Acceptance Criteria

```gherkin
Scenario: Set a daily word count goal
  Given I am logged in
  And I am on my preferences page
  When I set my daily word count goal to 500
  And I click the "Save" button
  Then I should see a success message
  And my daily goal should be displayed on my dashboard
```

### Verification Method

Manual Test
