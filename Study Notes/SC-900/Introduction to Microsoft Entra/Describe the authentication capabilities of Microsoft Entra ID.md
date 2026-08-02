# Microsoft Entra ID Authentication Capabilities Summary

## 🔐 What is Authentication?
Authentication is the process of **verifying a user's identity** before allowing access to applications, devices, networks, or services.

Microsoft Entra ID supports multiple authentication methods to improve:
- Security
- User experience
- Protection against attacks

---

# 1. Authentication Methods

## 🔑 Passwords
- The most common authentication method.
- Users prove their identity using a secret password.
- Weak passwords are vulnerable to:
  - Brute-force attacks
  - Password spraying
  - Credential theft

✅ Microsoft recommends using passwords with additional security methods or replacing them with passwordless authentication.

---

## 📱 Phone-Based Authentication

### SMS Authentication
- User receives a verification code through text message.
- Can be used for:
  - MFA
  - Self-Service Password Reset (SSPR)

⚠️ Less secure because attackers can perform SIM swap attacks.

### Voice Call Verification
- Automated call sends a verification request.
- User presses a key to confirm identity.
- Used only as a secondary authentication method.

---

## 🔢 OATH Tokens

OATH generates **time-based one-time passwords (TOTP)**.

### Software Tokens
Examples:
- Microsoft Authenticator
- Other authenticator apps

### Hardware Tokens
- Physical key fob devices.
- Generate codes every 30-60 seconds.

Used mainly for:
- MFA
- Password recovery

---

## 🔐 Other Authentication Methods

### Temporary Access Pass (TAP)
- Temporary code created by administrators.
- Used for:
  - New user setup
  - Recovering access
  - Registering passwordless methods

### QR Code Authentication
- Used mainly for frontline workers.
- Users scan a QR code and enter a PIN.

### Email OTP
- Sends a verification code through email.
- Used for:
  - SSPR
  - Guest access

### Authenticator Lite
- MFA capability built into apps like Outlook mobile.
- Allows:
  - Push notifications
  - One-time passwords

### External Authentication Methods
- Allows integration with third-party MFA providers.
- Examples:
  - Duo Security
  - RSA SecurID

---

# 2. Passwordless Authentication

Passwordless authentication removes passwords and uses stronger methods based on:

- Something you have (device/security key)
- Something you are (biometrics)
- Something you know (PIN)

---

## Windows Hello for Business
Uses:
- Device-bound keys
- PIN
- Biometrics

Benefits:
- Protects against credential theft.
- Requires the physical device and biometric/PIN.

---

## Passkeys (FIDO2)

Uses public-key cryptography.

Types:

### Device-Bound Passkeys
- Private key stays on one device.
- Examples:
  - FIDO2 security keys
  - Microsoft Authenticator passkeys

### Synced Passkeys
- Private key syncs across devices.
- Examples:
  - Apple iCloud Keychain
  - Google Password Manager

Benefits:
- Phishing resistant.
- Cannot be reused on fake websites.

---

## Microsoft Authenticator

Supports:

### Passwordless Sign-In
- User confirms a number match.
- Uses:
  - Fingerprint
  - Face recognition
  - PIN

### MFA Push Notifications
- User approves login requests.

### OATH Codes
- Generates verification codes.

---

## Certificate-Based Authentication (CBA)

Uses digital X.509 certificates instead of passwords.

Benefits:
- Passwordless authentication.
- Cloud-native authentication.
- Supports MFA.

---

# 3. Phishing-Resistant Authentication

Phishing-resistant methods prevent attackers from stealing credentials through fake websites.

They use **public key cryptography** where credentials are linked to the correct website.

Examples:

✅ Windows Hello for Business  
✅ FIDO2 Security Keys  
✅ Passkeys  
✅ Microsoft Authenticator Passkeys  
✅ Certificate-Based Authentication  
✅ macOS Platform Credential  

---

# 4. Multifactor Authentication (MFA)

MFA requires **two or more authentication factors**.

## Authentication Factors

### Something You Know
Examples:
- Password
- PIN

### Something You Have
Examples:
- Phone
- Security key
- Trusted device

### Something You Are
Examples:
- Fingerprint
- Face scan

---

## Microsoft Entra MFA Methods

Supported methods:

- Microsoft Authenticator
- Authenticator Lite
- Windows Hello
- Passkeys
- Certificate Authentication
- OATH Tokens
- SMS
- Voice Calls
- Temporary Access Pass

---

# 5. Security Defaults

Security Defaults provide basic identity protection.

They:

✅ Require MFA registration  
✅ Require administrators to use MFA  
✅ Block legacy authentication  
✅ Protect privileged accounts  

Microsoft states MFA blocks over **99.9% of common identity attacks**.

---

# 6. Conditional Access + MFA

Conditional Access provides advanced MFA control.

Organizations can require MFA based on:

- User location
- Device health
- Risk level
- Application sensitivity

Example:

> User accessing company data from a trusted office device → Normal sign-in

> User accessing from an unknown location → MFA required

Requires:
- Microsoft Entra ID Premium P1/P2

---

# 7. Self-Service Password Reset (SSPR)

SSPR allows users to reset passwords without contacting IT.

Benefits:
- Reduces help desk requests.
- Improves productivity.
- Provides audit logs.

Requirements:
- Microsoft Entra license
- SSPR enabled
- Registered authentication methods

---

## SSPR Authentication Methods

Users can verify identity using:

- Microsoft Authenticator
- SMS
- Voice call
- Email OTP
- OATH tokens

---

# 8. Account Recovery

Used when users lose access to all authentication methods.

## SSPR vs Account Recovery

| Feature | SSPR | Account Recovery |
|---|---|---|
| Purpose | Reset forgotten password | Restore identity access |
| Requirement | Existing authentication method | Identity verification |
| Scope | Password reset | Full authentication recovery |

---

# 9. Password Protection

Microsoft Entra Password Protection prevents weak passwords.

It uses:

## Global Banned Password List
Blocks commonly used passwords.

Examples:
- Password123
- Company names
- Common attack passwords

## Custom Banned Password List
Organizations can block:

- Company names
- Locations
- Product names
- Internal terms

---

# 10. Password Protection Against Attacks

Protects against:

## Password Spray Attacks

Attackers try: