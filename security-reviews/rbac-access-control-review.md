# Role-Based Access Control (RBAC) Review

## Scenario

A financial application contains the following roles:

### Finance Analyst

Permissions:
- View Financial Reports
- Create Purchase Requests
- Approve Purchase Requests
- Modify Vendor Records

### Finance Manager

Permissions:
- View Financial Reports
- Create Purchase Requests
- Approve Purchase Requests
- Modify Vendor Records
- Manage User Access

---

## Findings

### Excessive Privileges Assigned to Finance Analyst

Severity: High

The Finance Analyst role includes both request creation and approval capabilities.

This creates a Segregation of Duties (SoD) conflict because the same individual can initiate and approve transactions.

### Inappropriate Administrative Access

Severity: Critical

The Finance Manager role includes user access management privileges.

User provisioning and access administration should be restricted to authorized administrative personnel and governed by established access control procedures.

### Principle of Least Privilege Violations

Severity: High

Several permissions exceed the responsibilities typically required for the assigned business functions.

Users should receive only the minimum level of access necessary to perform their job duties.

---

## Risks

- Unauthorized transactions
- Fraud risk
- Audit findings
- Compliance violations
- Inadequate segregation of duties

---

## Recommendations

### Finance Analyst

Retain:
- View Financial Reports
- Create Purchase Requests

Remove:
- Approve Purchase Requests
- Modify Vendor Records

### Finance Manager

Retain:
- View Financial Reports
- Approve Purchase Requests

Remove:
- Manage User Access

### Administrative Access

Create a dedicated administrative role responsible for:

- User provisioning
- Role assignments
- Access reviews
- Access certification activities

---

## Final Assessment

The current RBAC design introduces unnecessary risk through excessive permissions and inadequate segregation of duties. Redesigning roles according to least privilege and separation of responsibilities would significantly improve security, compliance, and audit readiness.
