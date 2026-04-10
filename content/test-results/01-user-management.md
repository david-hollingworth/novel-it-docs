---
title: "01 User Management"
description: "Test execution records for authentication, registration, and password reset"
draft: false
---

## R-FUNC-0101.01 User account registration

**Scenario:** Successfully register a new account

{{< test-results id="T-FUNC-0101.01.01" file="01-user-management" >}}

## R-SEC-0101.01 Username uniqueness

**Scenario:** Attempt to register with an existing username

{{< test-results id="T-SEC-0101.01.01" file="01-user-management" >}}

## R-SEC-0101.02 Password minimum complexity

**Scenario:** Attempt to register with a non-compliant password

{{< test-results id="T-SEC-0101.02.01" file="01-user-management" >}}

## R-DATA-0101.01 Email address stored at registration

**Scenario:** Email address is persisted at registration

{{< test-results id="T-DATA-0101.01.01" file="01-user-management" >}}

## R-FUNC-0101.02 Password confirmation at registration

**Scenario:** Password is entered only once

{{< test-results id="T-FUNC-0101.02.01" file="01-user-management" >}}

**Scenario:** Passwords do not match at registration

{{< test-results id="T-FUNC-0101.02.02" file="01-user-management" >}}

## R-FUNC-0102.01 Login with username and password

**Scenario:** Successfully log in

{{< test-results id="T-FUNC-0102.01.01" file="01-user-management" >}}

**Scenario:** Attempt to log in with an incorrect password

{{< test-results id="T-FUNC-0102.01.02" file="01-user-management" >}}

## R-FUNC-0102.02 Logout

**Scenario:** Successfully log out

{{< test-results id="T-FUNC-0102.02.01" file="01-user-management" >}}

**Scenario:** Attempt to access the application after logging out

{{< test-results id="T-FUNC-0102.02.02" file="01-user-management" >}}

## R-SEC-0102.01 Unauthenticated access is denied

**Scenario:** Unauthenticated user attempts to access a protected page

{{< test-results id="T-SEC-0102.01.01" file="01-user-management" >}}

## R-USER-0102.01 Login failure message does not reveal account existence

**Scenario:** Login fails due to unknown username

{{< test-results id="T-USER-0102.01.01" file="01-user-management" >}}

**Scenario:** Login fails due to incorrect password

{{< test-results id="T-USER-0102.01.02" file="01-user-management" >}}

## R-FUNC-0103.01 Password change for authenticated users

**Scenario:** Successfully change password

{{< test-results id="T-FUNC-0103.01.01" file="01-user-management" >}}

**Scenario:** Attempt to change password with incorrect current password

{{< test-results id="T-FUNC-0103.01.02" file="01-user-management" >}}

## R-FUNC-0103.02 Password confirmation on password change

**Scenario:** New passwords do not match on password change

{{< test-results id="T-FUNC-0103.02.01" file="01-user-management" >}}



