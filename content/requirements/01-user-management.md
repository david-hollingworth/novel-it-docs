---
title: "01 User Management"
description: "Requirements for authentication, registration, and password reset"
draft: false
revision: "2.0"
revision_date: "20-Apr-2026"
---

*Phase 4 features (FEAT-0104 Profile Management, FEAT-0105 User Preferences) are out of scope for this pass and have no requirements entries here.*

---

## R-FUNC-0101.01 User account registration

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0101](/novel-it-docs/features/01-user-management/#feat-0101-user-registration) |

### Statement

The system SHALL allow a new user to create an account by providing a unique username, an email address, and a password.

### Rationale

Account creation is the entry point for all application use. Without it no user can access any Novel-It functionality.

### Acceptance Criteria

```gherkin
@T-FUNC-0101.01.01
Scenario: Successfully register a new account
  Given I am not logged in
  And I am on the registration page
  When I enter a username that does not already exist
  And I enter a valid email address
  And I enter a password
  And I enter the same password for confirmation
  And I click the Register button
  Then my account is created
  And I am redirected to the login page
```

### Verification Method

Manual Test

## R-SEC-0101.01 Username uniqueness

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0101](/novel-it-docs/features/01-user-management/#feat-0101-user-registration) |

### Statement

The system SHALL reject a registration attempt where the submitted username is already in use, and SHALL display an error message informing the user that the username is unavailable.

### Rationale

Usernames are used to identify users at login. Duplicate usernames would make authentication ambiguous and unreliable.

### Acceptance Criteria

```gherkin
@T-SEC-0101.01.01
Scenario: Attempt to register with an existing username
  Given a user account with the username "david" already exists
  And I am on the registration page
  When I enter the username "david"
  And I complete the remaining fields
  And I click the Register button
  Then my account is not created
  And I see an error message indicating the username is already taken
```

### Verification Method

Manual Test

## R-SEC-0101.02 Password minimum complexity

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0101](/novel-it-docs/features/01-user-management/#feat-0101-user-registration) |

### Statement

The system SHALL reject a registration attempt where the submitted password does not meet the minimum complexity requirements, and SHALL display an error message describing the requirement that was not met.

### Rationale

A minimum password complexity requirement reduces the risk of accounts being compromised by trivial or common passwords.

### Acceptance Criteria

```gherkin
@T-SEC-0101.02.01
Scenario: Attempt to register with a non-compliant password
  Given I am on the registration page
  When I enter a password that does not meet the minimum complexity requirements
  And I enter the same password for confirmation
  And I click the Register button
  Then my account is not created
  And I see an error message describing the unmet password requirement
```

### Verification Method

Manual Test

## R-DATA-0101.01 Email address stored at registration

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0101](/novel-it-docs/features/01-user-management/#feat-0101-user-registration) |

### Statement

The system SHALL store the email address provided at registration against the user account.

### Rationale

The email address is captured at registration to support Phase 4 features including forgotten password recovery and multi-user collaboration. Storing it from the outset avoids a data migration later.

### Acceptance Criteria

```gherkin
@T-DATA-0101.01.01
Scenario: Email address is persisted at registration
  Given I am on the registration page
  When I register a new account with a valid email address
  Then the email address I provided is stored against my account
```

### Verification Method

Manual Test

## R-FUNC-0101.02 Password confirmation at registration

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0101](/novel-it-docs/features/01-user-management/#feat-0101-user-registration) |

### Statement

The system SHALL require the user to enter their chosen password twice during registration and SHALL reject the submission if the two entries do not match.

### Rationale

Requiring password confirmation at the point of entry reduces the risk of a user locking themselves out of a newly created account due to a typing error.

### Acceptance Criteria

```gherkin
@T-FUNC-0101.02.01
Scenario: Password is entered only once
  Given I am on the registration page
  When I enter a unique user name
  And I enter a password in the password field
  And I don't enter a value in the confirm password field
  And I click the Register button
  Then my account is not created
  And I see an error message indicating the passwords do not match

@T-FUNC-0101.02.02
Scenario: Passwords do not match at registration
  Given I am on the registration page
  When I enter a unique user name
  And I enter a password in the password field
  And I enter a different value in the confirm password field
  And I click the Register button
  Then my account is not created
  And I see an error message indicating the passwords do not match
```

### Verification Method

Manual Test

> **Note:** The email address is not used for any functional purpose in Phase 1. No automated emails are sent as part of registration or any other Phase 1 workflow.

## R-FUNC-0102.01 Login with username and password

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0102](/novel-it-docs/features/01-user-management/#feat-0102-login-and-logout) |

### Statement

The system SHALL allow a registered user to log in by submitting their username and password, and on success SHALL redirect them to their novels list.

### Rationale

Login is the gateway to all application functionality. Without it no authenticated user can access their work.

### Acceptance Criteria

```gherkin
@T-FUNC-0102.01.01
Scenario: Successfully log in
  Given I am a registered user
  And I am on the login page
  When I enter my username and correct password
  And I click the Login button
  Then I am redirected to my novels list

@T-FUNC-0102.01.02
Scenario: Attempt to log in with an incorrect password
  Given I am a registered user
  And I am on the login page
  When I enter my username and an incorrect password
  And I click the Login button
  Then I am not logged in
  And I remain on the login page
```

### Verification Method

Manual Test

## R-FUNC-0102.02 Logout

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0102](/novel-it-docs/features/01-user-management/#feat-0102-login-and-logout) |

### Statement

The system SHALL allow a logged-in user to log out, and on logout SHALL terminate their session and redirect them to the login page.

### Rationale

Users must be able to end their session to prevent unauthorised access when leaving a shared or unattended device.

### Acceptance Criteria

```gherkin
@T-FUNC-0102.02.01
Scenario: Successfully log out
  Given I am logged in
  When I click the Logout button
  Then my session is terminated
  And I am redirected to the login page

@T-FUNC-0102.02.02
Scenario: Attempt to access the application after logging out
  Given I have logged out
  When I attempt to navigate to my novels list directly
  Then I am redirected to the login page
```

### Verification Method

Manual Test

## R-SEC-0102.01 Unauthenticated access is denied

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0102](/novel-it-docs/features/01-user-management/#feat-0102-login-and-logout) |

### Statement

The system SHALL deny access to all application pages and content to any user who is not authenticated, and SHALL redirect unauthenticated requests to the login page.

### Rationale

All user content is private. An unauthenticated user must not be able to view or interact with any novel, character, scene, or other content belonging to any account.

### Acceptance Criteria

```gherkin
@T-SEC-0102.01.01
Scenario: Unauthenticated user attempts to access a protected page
  Given I am not logged in
  When I navigate directly to any application URL other than the login or registration page
  Then I am redirected to the login page
  And I cannot see any application content
```

### Verification Method

Manual Test

## R-USER-0102.01 Login failure message does not reveal account existence

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0102](/novel-it-docs/features/01-user-management/#feat-0102-login-and-logout) |

### Statement

The system SHALL display a generic error message on login failure that does not indicate whether the username or the password was incorrect.

### Rationale

Disclosing which credential was wrong allows an attacker to enumerate valid usernames. A non-specific message protects users from account discovery attacks.

### Acceptance Criteria

```gherkin
@T-USER-0102.01.01
Scenario: Login fails due to unknown username
  Given I am on the login page
  When I enter a username that does not exist and any password
  And I click the Login button
  Then I see a generic error message that does not confirm or deny whether the username exists

@T-USER-0102.01.02
Scenario: Login fails due to incorrect password
  Given I am a registered user
  And I am on the login page
  When I enter my correct username and an incorrect password
  And I click the Login button
  Then I see the same generic error message as for an unknown username
```

### Verification Method

Manual Test

## R-FUNC-0103.01 Password change for authenticated users

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0103](/novel-it-docs/features/01-user-management/#feat-0103-password-reset) |

### Statement

The system SHALL allow a logged-in user to change their password by entering their current password and a new password that meets the minimum complexity requirements.

### Rationale

Users must be able to change their password when they choose to. This is a basic account security requirement.

### Acceptance Criteria

```gherkin
@T-FUNC-0103.01.01
Scenario: Successfully change password
  Given I am logged in
  And I am on the password reset page
  When I enter my current password correctly
  And I enter a new password that meets the minimum complexity requirements
  And I confirm the new password
  And I click the Save button
  Then my password is updated
  And I see a confirmation message

@T-FUNC-0103.01.02
Scenario: Attempt to change password with incorrect current password
  Given I am logged in
  And I am on the password reset page
  When I enter an incorrect current password
  And I click the Save button
  Then my password is not changed
  And I see an error message
```

### Verification Method

Manual Test

## R-FUNC-0103.02 Password confirmation on password change

| | |
|---|---|
| **Status** | Draft |
| **Phase** | 1 |
| **Relates to** | [FEAT-0103](/novel-it-docs/features/01-user-management/#feat-0103-password-reset) |

### Statement

The system SHALL require the user to enter their new password twice when changing their password and SHALL reject the submission if the two entries do not match.

### Rationale

Requiring confirmation of the new password reduces the risk of a user inadvertently setting an unintended password and being unable to log back in.

### Acceptance Criteria

```gherkin
@T-FUNC-0103.02.01
Scenario: New passwords do not match on password change
  Given I am logged in
  And I am on the password reset page
  When I enter my current password correctly
  And I enter a new password in the new password field
  And I enter a different value in the confirm new password field
  And I click the Save button
  Then my password is not changed
  And I see an error message indicating the passwords do not match
```

### Verification Method

Manual Test

> **Note:** A forgotten password recovery flow via email is out of scope for Phase 1. Users who cannot log in must contact their server administrator to have their password reset directly.
