h3. Summary
User cannot log into Railway website using a valid email and invalid password, but the system displays an unexpected error message instead of the required validation text.

h3. Environment
* URL: http://railwayb2.somee.com/Account/Login.cshtml
* Browser: Google Chrome (Latest) / Windows 11

h3. Steps to Reproduce
# Navigate to QA Railway Website.
# Click on the "Login" tab.
# Enter a valid email (e.g., hoaingoc5304@gmail.com) and an invalid password.
# Click the "Login" button.

h3. Observed / Actual Result
The system displays the message:
> “Invalid username or password. Please try again.”

h3. Expected Result
The system should display the message according to specification:
> “There was a problem with your login and/or errors exist in your form.”

h3. Attachments
* Screenshot_Bug001_LoginFailedMsg.png
```[cite: 14]

---

### [Ticket #002] [Bug] [Major] Login - System fails to display lockout warning message after 4 consecutive failed attempts
* **Tracker:** Bug
* **Status:** New
* **Priority:** High
* **Category:** Authentication / Security
* **Target Version:** Sprint 1 / v1.0
* **Related Test Case:** TC05 (Tham chiếu TC03 trong log)[cite: 14]
* **Severity:** Major

**Description:**
```text
h3. Summary
System continues to display generic invalid login message after 4 consecutive failed login attempts instead of warning about remaining attempts and upcoming lockout.

h3. Environment
* URL: http://railwayb2.somee.com/Account/Login.cshtml
* Browser: Google Chrome / Edge

h3. Steps to Reproduce
# Navigate to QA Railway Website.
# Click on the "Login" tab.
# Enter a valid email and an invalid password.
# Click the "Login" button.
# Repeat steps 3 and 4 three more times (Total: 4 consecutive failed attempts).

h3. Observed / Actual Result
The system still displays the generic message:
> “Invalid username or password. Please try again.”

h3. Expected Result
The system must display an alert indicating the attempt threshold:
> “You have used 4 out of 5 login attempts. After all 5 have been used, you will be unable to login for 15 minutes.”

h3. Attachments
* Screenshot_Bug002_LockoutWarningMissing.png
```[cite: 14]

---

### [Ticket #003] [Bug] [Normal] Register - Incorrect confirmation message displayed after account creation
* **Tracker:** Bug
* **Status:** New
* **Priority:** Normal
* **Category:** Account / Registration
* **Target Version:** Sprint 1 / v1.0
* **Related Test Case:** TC07[cite: 14]
* **Severity:** Minor / UI Text

**Description:**
```text
h3. Summary
Upon successfully registering a new account, the confirmation message is rendered as "You're here" instead of the formal thank-you notification.

h3. Environment
* URL: http://railwayb2.somee.com/Account/Confirm?...
* Browser: Google Chrome / Windows 11

h3. Steps to Reproduce
# Navigate to QA Railway Website.
# Click on the "Register" tab.
# Fill in valid information for all mandatory fields.
# Click on the "Register" button.

h3. Observed / Actual Result
The system redirects and renders the text:
> “You're here”

h3. Expected Result
The system should display a clear confirmation message:
> “Thank you for registering your account”.

h3. Attachments
* Screenshot_Bug003_RegisterSuccessMsg.png
```[cite: 14]

---

### [Ticket #004] [Bug] [Low] Change Password - Missing exclamation mark at the end of success message
* **Tracker:** Bug
* **Status:** New
* **Priority:** Low
* **Category:** Account / Password Management
* **Target Version:** Sprint 1 / v1.0
* **Related Test Case:** TC09[cite: 14]
* **Severity:** Trivial / Formatting

**Description:**
```text
h3. Summary
Success notification after changing password lacks an exclamation point, deviating from expected UI copy specification.

h3. Environment
* URL: http://railwayb2.somee.com/Account/ChangePassword.cshtml
* Browser: Google Chrome

h3. Steps to Reproduce
# Navigate to QA Railway Website and login with valid credentials.
# Click on the "Change password" tab.
# Enter valid details into Current Password, New Password, and Confirm Password fields.
# Click on the "Change Password" button.

h3. Observed / Actual Result
The notification box displays:
> “Your password has been updated”

h3. Expected Result
The notification box should strictly follow the copy guideline:
> “Your password has been updated!”

h3. Attachments
* Screenshot_Bug004_ChangePwdExclamationMark.png
```[cite: 14]

---

### [Ticket #005] [Bug] [Low] Register - Punctuation missing in field validation messages when Password and PID are blank
* **Tracker:** Bug
* **Status:** New
* **Priority:** Low
* **Category:** Account / Registration Form Validation
* **Target Version:** Sprint 1 / v1.0
* **Related Test Case:** TC11[cite: 14]
* **Severity:** Trivial / Formatting

**Description:**
```text
h3. Summary
Inline validation messages next to empty 'Password' and 'PID/Passport number' fields are missing terminal periods (dots).

h3. Environment
* URL: http://railwayb2.somee.com/Account/Register.cshtml
* Browser: Google Chrome

h3. Steps to Reproduce
# Navigate to QA Railway Website and click on the "Register" tab.
# Input a valid email address.
# Leave "Password", "Confirm Password", and "PID/Passport number" fields completely blank.
# Click the "Register" button.

h3. Observed / Actual Result
* Top banner: “There're errors in the form. Please correct the errors and try again.” (Pass).
* Next to Password: “Invalid password length” (Missing trailing period).
* Next to PID: “Invalid ID length” (Missing trailing period).

h3. Expected Result
Inline field errors should include trailing periods:
* Password field: “Invalid password length.”
* PID field: “Invalid ID length.”

h3. Attachments
* Screenshot_Bug005_InlineValidationDots.png
```[cite: 14]

---

### [Ticket #006] [Bug] [Critical] Forgot Password - Server 500 SmtpFailedRecipientException when requesting password reset (Blocks empty token testing)
* **Tracker:** Bug
* **Status:** New
* **Priority:** Urgent
* **Category:** Infrastructure / Email Service / Password Reset
* **Target Version:** Sprint 1 / v1.0
* **Related Test Case:** TC12[cite: 14]
* **Severity:** Blocker / Critical

**Description:**
```text
h3. Summary
ASP.NET runtime throws SmtpFailedRecipientException on ForgotPassword page when submitting email, crashing the page and completely blocking password recovery / token validation testing.

h3. Environment
* URL: http://railwayb2.somee.com/Account/ForgotPassword.cshtml
* Framework: ASP.NET WebPages / System.Net.Mail

h3. Steps to Reproduce
# Navigate to QA Railway Login page.
# Click on the "Forgot Password" link.
# Enter the email address of an existing registered account.
# Click the "Send Instructions" button.

h3. Observed / Actual Result
* HTTP 500 Unhandled Exception screen:
> "Server Error in '/' Application."
> "Mailbox unavailable. The server response was: that smtp username is not allowed to send"
> "Exception Details: System.Net.Mail.SmtpFailedRecipientException: Mailbox unavailable."
> "Source File: ...\Account\ForgotPassword.cshtml, Line: 38 (WebMail.Send)"
* Test Blocked: Tester cannot receive the reset token email to test subsequent scenarios (empty token / invalid token).

h3. Expected Result
* Mail service should dispatch instructions smoothly without throwing server-side exceptions.
* User should be directed to the token/password reset flow where leaving the token blank displays:
  - Header: “The password reset token is incorrect or may be expired. Visit the forgot password page to generate a new one.”
  - Inline error: “The password reset token is invalid.”

h3. Stack Trace / Attachments
* Server trace: Line 38 WebMail.Send(to: email, subject: "Please reset your password")
* Screenshot_Bug006_SMTP_Crash.png
```[cite: 14]

---

### [Ticket #007] [Bug] [Critical] Forgot Password - Unhandled SMTP Exception prevents verification of mismatched password confirmation
* **Tracker:** Bug
* **Status:** New
* **Priority:** Urgent
* **Category:** Infrastructure / Email Service / Password Reset
* **Target Version:** Sprint 1 / v1.0
* **Related Test Case:** TC13[cite: 14]
* **Severity:** Blocker / Critical

**Description:**
```text
h3. Summary
Same root cause as Bug #006: Failure of WebMail/SMTP relay blocks execution and verification of password confirmation mismatch during password reset.

h3. Environment
* URL: http://railwayb2.somee.com/Account/ForgotPassword.cshtml

h3. Steps to Reproduce
# Navigate to QA Railway Login page -> Click "Forgot Password".
# Enter registered email and click "Send Instructions".

h3. Observed / Actual Result
Server crashes with `SmtpFailedRecipientException: that smtp username is not allowed to send` at Line 38. The process halts prior to opening the reset form.

h3. Expected Result
Email delivers properly. When accessing the Password Change Form and entering mismatched passwords:
* Banner error: “Could not reset password. Please correct the errors and try again.”
* Inline error next to Confirm Password: “The password confirmation did not match the new password.”

h3. Notes
* Relates to Ticket #006 (Duplicate root cause in backend email configuration).
```[cite: 14]

---

### [Ticket #008] [Bug] [Low] Book Ticket - Header text capitalization mismatch on Success Page
* **Tracker:** Bug
* **Status:** New
* **Priority:** Low
* **Category:** Booking / UI Typography
* **Target Version:** Sprint 1 / v1.0
* **Related Test Case:** TC14[cite: 14]
* **Severity:** Minor / UI Text

**Description:**
```text
h3. Summary
Header on ticket booking confirmation page uses sentence case "Ticket booked successfully!" instead of Title Case "Ticket Booked Successfully!".

h3. Environment
* URL: http://railwayb2.somee.com/Page/SuccessPage.cshtml
* Browser: Google Chrome

h3. Steps to Reproduce
# Login with an active account.
# Navigate to the "Book ticket" tab.
# Select Depart date, Depart from: "Sài Gòn", Arrive at: "Nha Trang".
# Select Seat type: "Soft bed with air conditioner", Ticket amount: "1".
# Click "Book ticket".

h3. Observed / Actual Result
Heading displays:
> “Ticket booked successfully!”

h3. Expected Result
Heading should maintain Title Case formatting:
> “Ticket Booked Successfully!”

h3. Attachments
* Screenshot_Bug008_TicketBookedCapitalization.png
```[cite: 14]

---

### [Ticket #009] [Support / Clarification] Inactive account login verification blocked by missing activation email mechanism
* **Tracker:** Support / Question
* **Status:** In Progress
* **Priority:** Normal
* **Assignee:** Ms. My (QA Lead / PM)
* **Category:** Test Design / Specification Clarification
* **Related Test Case:** TC08[cite: 14]

**Description:**
```text
h3. Background & Issue
In Test Case TC08 ("User can't login with an account that hasn't been activated"), the precondition requires creating an unactivated account, attempting login, and asserting the message:
> “Invalid username or password. Please try again.”

h3. Actual System Limitation
On the test environment (http://railwayb2.somee.com), the system auto-activates or fails to send an activation email upon registration. Consequently, an "inactive account" state cannot be created or simulated via standard UI steps.

h3. Redundancy Risk
1. Logging in with a newly registered account behaves like an active account (already verified in TC01).
2. Inputting dummy/incorrect credentials to trigger the error message overlaps with TC03.

h3. Request for Guidance
Could you please clarify the expected approach for TC08:
* Should backend test data be prepared directly in the database (setting `IsActive = 0` / `EmailConfirmed = false`)?
* Or should TC08 be marked as "Blocked / Out of Scope" until the mail relay issue is resolved?
```[cite: 14]

---

# III. BẢNG TỔNG HỢP THEO DÕI TẬP TRUNG (Dashboard View)

| Ticket ID | Tracker | Category | Summary | TC ID | Priority | Severity | Status |
| :---: | :---: | :--- | :--- | :---: | :---: | :---: | :---: |
| **#001** | Bug | Authentication | Sai thông báo lỗi khi nhập sai mật khẩu[cite: 14] | TC03 | High | Major | New |
| **#002** | Bug | Security | Không hiển thị cảnh báo khóa tài khoản sau 4 lần sai[cite: 14] | TC05 / TC03 | High | Major | New |
| **#003** | Bug | Registration | Thông báo đăng ký hiển thị "You're here" thay vì lời cảm ơn[cite: 14] | TC07 | Normal | Minor | New |
| **#004** | Bug | Password | Thiếu dấu chấm than (!) ở thông báo đổi mật khẩu thành công[cite: 14] | TC09 | Low | Trivial | New |
| **#005** | Bug | Registration | Thiếu dấu chấm kết câu ở thông báo lỗi Password & PID trống[cite: 14] | TC11 | Low | Trivial | New |
| **#006** | Bug | Mail / Server | Lỗi SmtpFailedRecipientException chặn kiểm thử Empty Reset Token[cite: 14] | TC12 | Urgent | Blocker | New |
| **#007** | Bug | Mail / Server | Lỗi SMTP chặn kiểm thử Mismatched Confirm Password[cite: 14] | TC13 | Urgent | Blocker | New |
| **#008** | Bug | Booking | Sai định dạng viết hoa ở tiêu đề đặt vé thành công[cite: 14] | TC14 | Low | Minor | New |
| **#009** | Support | QA Process | Làm rõ phương án kiểm thử TC08 do không có luồng kích hoạt email[cite: 14] | TC08 | Normal | - | Assigned |

<FollowUp label="Bạn có muốn xuất toàn bộ các ticket này thành file CSV/Excel để import trực tiếp vào Redmine không?" query="Hãy tạo file CSV mẫu chuẩn định dạng Redmine để import các ticket này vào hệ thống."/>
