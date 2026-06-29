# Challenge 1 - Access Another User's Vehicle Details (BOLA)

## Overview

The API exposes vehicle details using a user-supplied `vehicleId`. Although authentication is required, the application does not verify whether the authenticated user owns the requested vehicle, allowing unauthorized access to another user's data.

---

## Target Endpoint

```http
GET /identity/api/v2/vehicle/{vehicleId}
```

---

## Reconnaissance

While browsing the application, vehicle-related requests were intercepted using **Burp Suite**. The API accepted a `vehicleId` parameter and returned vehicle details based on the supplied identifier, making it a potential target for authorization testing.

<p align="center">
  <img src="../screenshots/BOLA/01_recon.png" width="100%">
</p>

---

## Exploitation Process

1. Login with a valid account.
2. Intercept a request containing `vehicleId`.
3. Replace it with another valid `vehicleId`.
4. Forward the request.
5. Observe that another user's vehicle details are returned.

<p align="center">
  <img src="../screenshots/BOLA/02_modified_request.png" width="100%">
</p>

---

## Evidence

The modified request returned vehicle information belonging to another user, confirming a Broken Object Level Authorization (BOLA) vulnerability.

<p align="center">
  <img src="../screenshots/BOLA/03_response.png" width="100%">
</p>

---

## Impact

An authenticated attacker can access sensitive vehicle information belonging to other users by modifying object identifiers.

---

## Remediation

* Verify resource ownership on every request.
* Return **HTTP 403 Forbidden** for unauthorized access.
* Enforce server-side authorization checks.
