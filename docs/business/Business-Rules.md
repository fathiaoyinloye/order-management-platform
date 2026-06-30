# Business Rules

**Project:** Order Management Platform

**Version:** 1.0 (Draft)

**Author:** Fathia Oyinloye

---

# 1. Introduction

## 1.1 Purpose

This document defines the business rules that govern the Order Management Platform.

Business rules describe the policies and constraints that must always be enforced regardless of the technology used to implement the system.

These rules provide the foundation for application design, database constraints, API validation, and system testing.

---

# 2. Customer Rules

---

## BR-001

**Category**

Identity

**Rule**

Each customer shall register with a unique phone number.

**Reason**

The phone number is the primary identifier for every customer.

---

## BR-002

**Category**

Identity

**Rule**

A customer account shall not become active until the phone number has been successfully verified.

**Reason**

This prevents fake or invalid accounts from being created.

---

## BR-003

**Category**

Identity

**Rule**

A customer may have only one active account.

**Reason**

Duplicate customer accounts make order and payment tracking unreliable.

---

## BR-004

**Category**

Security

**Rule**

Only authenticated customers may place orders, express interest, upload payment proof, submit support requests, or request returns.

**Reason**

These actions must always be associated with an identified customer.

---

## BR-005

**Category**

Identity

**Rule**

When a customer changes their phone number, the new phone number shall be verified before becoming the customer's active phone number.

**Reason**

Ownership of the new phone number must be confirmed.

---

## BR-006

**Category**

Security

**Rule**

Customers shall only access information that belongs to their own account.

**Reason**

Customer information must remain private.

---

## BR-007

**Category**

Security

**Rule**

Only the administrator may manage products, inventory, deliveries, and payment verification.

**Reason**

These activities directly affect business operations.

---

# 3. Product Rules

---

## BR-008

**Category**

Catalog

**Rule**

Every product shall belong to exactly one category.

**Reason**

Products must be organized consistently for browsing and searching.

---

## BR-009

**Category**

Catalog

**Rule**

Every product shall have at least one product variant.

**Reason**

Customers purchase product variants rather than the generic product.

---

## BR-010

**Category**

Catalog

**Rule**

Each product variant shall belong to exactly one product.

**Reason**

A variant represents a specific version of a single product.

---

## BR-011

**Category**

Catalog

**Rule**

Every product variant shall maintain its own inventory quantity.

**Reason**

Different variants may have different stock levels.

---

## BR-012

**Category**

Catalog

**Rule**

A product may contain multiple images.

**Reason**

Customers should be able to view the product from different perspectives.

---

## BR-013

**Category**

Lifecycle

**Rule**

Every product shall have one current product status.

**Allowed Values**

* Coming Soon
* Available
* Out of Stock
* Archived

**Reason**

The current status determines how customers may interact with the product.

---

## BR-014

**Category**

Lifecycle

**Rule**

Archived products shall not be available for purchase or product interest.

**Reason**

Archived products are no longer offered by the business.

---

# 4. Product Interest Rules

---

## BR-015

**Category**

Interest

**Rule**

Customers may express interest only in products whose status is **Coming Soon**.

**Reason**

Interest is used to measure demand for products that are not yet available.

---

## BR-016

**Category**

Interest

**Rule**

A customer may have only one active interest for a product.

**Reason**

Duplicate interest records provide inaccurate demand information.

---

## BR-017

**Category**

Interest

**Rule**

A customer may update the requested quantity while the product remains in the **Coming Soon** state.

**Reason**

Customer demand may change before the product becomes available.

---

## BR-018

**Category**

Interest

**Rule**

Expressing interest shall not reserve inventory.

**Reason**

Interest indicates demand but does not represent a purchase commitment.

---

## BR-019

**Category**

Interest

**Rule**

When a Coming Soon product becomes Available, all customers who expressed interest shall be notified.

**Reason**

Interested customers should be informed that the product can now be purchased.

---

## BR-020

**Category**

Interest

**Rule**

An interest record shall remain associated with both the customer and the product.

**Reason**

Historical interest data may be useful for future business analysis.

---

## BR-021

**Category**

Interest

**Rule**

Customers may remove their interest from a product while it remains in the **Coming Soon** state.

**Reason**

Customers should be free to change their purchasing intentions before the product becomes available.

---

# Business Rules (Part 2)

---

# 5. Shopping Cart Rules

---

## BR-022

**Category**

Shopping Cart

**Rule**

Only authenticated customers may maintain a shopping cart.

**Reason**

The shopping cart belongs to a specific customer account.

---

## BR-023

**Category**

Shopping Cart

**Rule**

A shopping cart shall belong to exactly one customer.

**Reason**

Each customer manages their own shopping cart independently.

---

## BR-024

**Category**

Shopping Cart

**Rule**

A customer may have only one active shopping cart at a time.

**Reason**

Maintaining a single active cart simplifies the checkout process.

---

## BR-025

**Category**

Shopping Cart

**Rule**

A shopping cart may contain one or more cart items.

**Reason**

Customers often purchase multiple products in a single order.

---

## BR-026

**Category**

Shopping Cart

**Rule**

The same product variant shall not appear more than once in a shopping cart.

**Reason**

Duplicate items should be represented by updating the quantity instead of creating multiple cart items.

---

## BR-027

**Category**

Shopping Cart

**Rule**

Customers may update or remove cart items before placing an order.

**Reason**

Customers should be able to modify their intended purchase before checkout.

---

## BR-028

**Category**

Shopping Cart

**Rule**

A shopping cart becomes inactive after a successful order is placed.

**Reason**

A completed checkout represents the end of that shopping session.

---

# 6. Order Rules

---

## BR-029

**Category**

Order

**Rule**

Every order shall belong to exactly one customer.

**Reason**

Orders must always be traceable to the customer who placed them.

---

## BR-030

**Category**

Order

**Rule**

An order shall contain at least one order item.

**Reason**

An order without items has no business meaning.

---

## BR-031

**Category**

Order

**Rule**

Each order item shall reference exactly one product variant.

**Reason**

Customers purchase specific variants rather than generic products.

---

## BR-032

**Category**

Order

**Rule**

The selling price of an order item shall be preserved when the order is placed.

**Reason**

Future product price changes shall not affect existing orders.

---

## BR-033

**Category**

Order

**Rule**

Every order shall have a unique order number.

**Reason**

Order numbers uniquely identify customer purchases.

---

## BR-034

**Category**

Order

**Rule**

A fully paid order shall not be modified.

**Reason**

Completed purchases must remain consistent.

---

## BR-035

**Category**

Order

**Rule**

Only unpaid orders may be cancelled by the customer.

**Reason**

Payments require administrator review before cancellation or refund decisions.

---

## BR-036

**Category**

Order

**Rule**

Every order shall have one current order status.

**Allowed Values**

* Pending Payment
* Partially Paid
* Payment Submitted
* Payment Verified
* Processing
* Ready for Pickup
* Out for Delivery
* Delivered
* Completed
* Return Requested
* Returned
* Cancelled

**Reason**

The order status represents the current stage of the purchase lifecycle.

---

## BR-037

**Category**

Order

**Rule**

Order statuses shall progress according to the business workflow.

**Reason**

Orders shall not move backwards or skip required business stages unless authorized by the administrator.

---

## BR-038

**Category**

Order

**Rule**

Customers shall be able to view the complete history of their own orders.

**Reason**

Customers should always be able to track previous purchases.

---

## BR-039

**Category**

Order

**Rule**

An order may contain products that are marked as **Coming Soon**.

**Reason**

Customers are allowed to purchase products before they become available.

---

# 7. Payment Rules

---

## BR-040

**Category**

Payment

**Rule**

Every payment shall belong to exactly one order.

**Reason**

Payments have no business meaning without an associated order.

---

## BR-041

**Category**

Payment

**Rule**

An order may receive multiple payments.

**Reason**

Customers may complete payment over multiple transactions.

---

## BR-042

**Category**

Payment

**Rule**

Every payment shall include proof of payment.

**Reason**

Version 1 uses manual bank transfer verification.

---

## BR-043

**Category**

Payment

**Rule**

Only the administrator may verify or reject a payment.

**Reason**

Payment verification is a controlled business process.

---

## BR-044

**Category**

Payment

**Rule**

A payment shall have one verification status.

**Allowed Values**

* Pending Verification
* Verified
* Rejected

**Reason**

The verification status communicates the outcome of administrator review.

---

## BR-045

**Category**

Payment

**Rule**

Rejected payments shall not contribute toward the amount paid for an order.

**Reason**

Only verified payments are recognized by the business.

---

## BR-046

**Category**

Payment

**Rule**

Verified payments shall contribute toward the outstanding balance of an order.

**Reason**

The order balance must accurately reflect confirmed payments.

---

## BR-047

**Category**

Payment

**Rule**

Customers may submit additional payments until the required payment amount has been verified.

**Reason**

Customers may complete payment through multiple bank transfers.

---

## BR-048

**Category**

Payment

**Rule**

Every payment verification decision shall be recorded.

**Reason**

The business must maintain an audit trail of payment decisions.

---

## BR-049

**Category**

Payment

**Rule**

Customers shall be notified whenever a payment is verified or rejected.

**Reason**

Customers should be informed of the outcome of payment verification.

---



# Business Rules (Part 3)

---

# 8. Inventory Rules

---

## BR-050

**Category**

Inventory

**Rule**

Inventory shall be maintained at the product variant level.

**Reason**

Each product variant has its own stock quantity.

---

## BR-051

**Category**

Inventory

**Rule**

Inventory quantity shall never be negative.

**Reason**

Negative inventory does not represent a valid business state.

---

## BR-052

**Category**

Inventory

**Rule**

Customers shall not purchase quantities greater than the available inventory for a product variant.

**Reason**

The business cannot sell stock that is unavailable.

---

## BR-053

**Category**

Inventory

**Rule**

Inventory adjustments shall only be performed by the administrator.

**Reason**

Inventory directly affects business operations.

---

## BR-054

**Category**

Inventory

**Rule**

Every inventory adjustment shall be recorded.

**Reason**

Inventory changes must be traceable for auditing and reconciliation.

---

## BR-055

**Category**

Inventory

**Rule**

The administrator shall be notified when inventory falls below the configured low-stock threshold.

**Reason**

The business should replenish stock before products become unavailable.

---

# 9. Delivery Rules

---

## BR-056

**Category**

Delivery

**Rule**

Every order shall have one selected delivery method.

**Reason**

The business must know how the customer expects to receive the order.

---

## BR-057

**Category**

Delivery

**Rule**

Orders marked for delivery shall include a delivery address.

**Reason**

A delivery cannot be completed without a destination.

---

## BR-058

**Category**

Delivery

**Rule**

Customers may update their delivery address only before the order enters the Processing status.

**Reason**

Changing the address after processing may disrupt fulfillment.

---

## BR-059

**Category**

Delivery

**Rule**

Only the administrator may update the delivery status.

**Reason**

Delivery progress is managed by the business.

---

## BR-060

**Category**

Delivery

**Rule**

Customers shall be able to view the current delivery status of their own orders.

**Reason**

Customers should always know the progress of their deliveries.

---

# 10. Return Rules

---

## BR-061

**Category**

Returns

**Rule**

Only delivered orders may have return requests submitted.

**Reason**

Products cannot be returned before they have been received.

---

## BR-062

**Category**

Returns

**Rule**

Only faulty products may be eligible for return.

**Reason**

Version 1 supports returns for faulty products only.

---

## BR-063

**Category**

Returns

**Rule**

Each return request shall be associated with exactly one order.

**Reason**

Every return must reference the original purchase.

---

## BR-064

**Category**

Returns

**Rule**

Only the administrator may approve or reject a return request.

**Reason**

Return decisions are controlled by the business.

---

## BR-065

**Category**

Returns

**Rule**

Customers shall be notified whenever a return request is approved or rejected.

**Reason**

Customers should receive the outcome of their request.

---

# 11. Support Rules

---

## BR-066

**Category**

Support

**Rule**

Only authenticated customers may submit support requests.

**Reason**

Support requests must be associated with a customer account.

---

## BR-067

**Category**

Support

**Rule**

Every support request shall belong to exactly one customer.

**Reason**

The business must know who submitted each request.

---

## BR-068

**Category**

Support

**Rule**

Support requests shall remain linked to the customer's account.

**Reason**

Support history provides context for future interactions.

---

## BR-069

**Category**

Support

**Rule**

Only the administrator may respond to customer support requests.

**Reason**

Customer support is managed by the business owner.

---

## BR-070

**Category**

Support

**Rule**

Customers shall be notified whenever a response is added to one of their support requests.

**Reason**

Customers should know when the business has responded.

---

# 12. Notification Rules

---

## BR-071

**Category**

Notification

**Rule**

Notifications shall be generated whenever a defined business event occurs.

**Reason**

Customers and the administrator should remain informed about important activities.

---

## BR-072

**Category**

Notification

**Rule**

Notification delivery shall not prevent completion of the business operation.

**Reason**

A temporary messaging failure should not stop order processing or payment verification.

---

## BR-073

**Category**

Notification

**Rule**

The notification channel shall be configurable.

**Reason**

The business may switch between WhatsApp, SMS, or other providers without changing business logic.

---

# 13. General Rules

---

## BR-074

**Category**

Data Integrity

**Rule**

Every business record shall have a unique identifier.

**Reason**

Business records must be uniquely identifiable.

---

## BR-075

**Category**

Audit

**Rule**

Important business actions shall be recorded for auditing purposes.

**Examples**

* Product creation
* Product updates
* Inventory adjustments
* Payment verification
* Order cancellation
* Return approval
* Return rejection

**Reason**

Business operations should be traceable.

---

## BR-076

**Category**

Security

**Rule**

Customers shall access only their own information.

**Reason**

Customer privacy must be protected.

---

## BR-077

**Category**

Validation

**Rule**

The system shall reject invalid or incomplete business data.

**Reason**

Only valid information should be stored.

---

## BR-078

**Category**

Availability

**Rule**

Archived products shall remain available for historical reporting but shall not be visible for purchase.

**Reason**

Historical records must remain accurate while preventing new purchases.

---

## BR-079

**Category**

Consistency

**Rule**

The system shall maintain consistent business data after every completed operation.

**Reason**

Business records must remain reliable.

---

## BR-080

**Category**

Maintainability

**Rule**

Business rules shall be enforced consistently throughout the platform.

**Reason**

The same business process should produce the same outcome regardless of where it is executed.

---

# Document Status

Draft Version 1.0

This document defines the business policies governing Version 1 of the Order Management Platform.

Business rules shall evolve only when business requirements change.

