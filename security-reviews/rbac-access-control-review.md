# Role-Based Access Control (RBAC) Review

## Scenario

A financial application contains the following roles:

### Finance Analyst

**Permissions**

* View Financial Reports
* Create Purchase Requests
* Approve Purchase Requests
* Modify Vendor Records

### Finance Manager

**Permissions**

* View Financial Reports
* Create Purchase Requests
* Approve Purchase Requests
* Modify Vendor Records
* Manage User Access

---

## Findings

### Excessive Privileges Assigned to Finance Analyst

**Severity:** High

The Finance Analyst role includes both request creation and approval capabilities. This creates a Segregation of Duties (SoD) concern because the same user can initiate and approve transactions without independent review.

### Inappropriate Administrative Access

**Severity:** Critical

The Finance Manager role includes user access management privileges. Access provisioning and role administration should be restricted to designated administrative roles and governed through established access management processes.

### Least Privilege Violations

**Severity:** High

Several permissions appear broader than necessary for the intended business responsibilities. Access should be limited to only what is required to perform assigned job functions.

---

## Risks

* Unauthorized or unapproved transactions
* Increased risk of fraud
* Audit findings during compliance reviews
* Regulatory or internal policy violations
* Weak enforcement of segregation of duties

---

## Recommendations

### Finance Analyst

**Retain**

* View Financial Reports
* Create Purchase Requests

**Remove**

* Approve Purchase Requests
* Modify Vendor Records

### Finance Manager

**Retain**

* View Financial Reports
* Approve Purchase Requests
* Modify Vendor Records

**Remove**

* Manage User Access

### Administrative Access

Create a dedicated administrative role responsible for:

* User provisioning
* Role assignments
* Access reviews
* Access certification

---

## Final Assessment

The current RBAC design introduces unnecessary risk due to excessive permissions and inadequate segregation of duties. Aligning access with least privilege principles and separating administrative responsibilities would improve security, compliance, and audit readiness.
