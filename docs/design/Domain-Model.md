# Domain Model

**Project:** Order Management Platform

**Version:** 1.0 (Draft)

**Author:** Fathia Oyinloye

---

# 1. Purpose

The Domain Model describes the core business concepts of the Order Management Platform and the relationships between them.

Its purpose is to provide a shared understanding of the business domain before designing the database, APIs, or application architecture.

This document focuses on business concepts rather than technical implementation details.

---

# 2. Domain Overview

The Order Management Platform is designed to digitize the sales process of a small import business.

Customers can browse products, express interest in products that are not yet available, place orders, upload proof of payment, track deliveries, and communicate with the business through the platform.

The administrator manages products, inventory, orders, payments, deliveries, customer support, and customer demand from a single system.

The platform aims to reduce manual processes while providing a better customer experience and creating accurate business records.

---

# 3. Core Business Concepts

The business revolves around the following core concepts.

| Business Concept | Description                                                                            |
| ---------------- | -------------------------------------------------------------------------------------- |
| Customer         | A registered person who purchases products.                                            |
| Product          | An item offered for sale by the business.                                              |
| Product Variant  | A specific version of a product distinguished by attributes such as color or size.     |
| Category         | A logical grouping of similar products.                                                |
| Order            | A customer's request to purchase one or more products.                                 |
| Order Item       | A single product variant contained within an order.                                    |
| Payment          | Money paid by a customer towards an order.                                             |
| Inventory        | The available quantity of each product variant.                                        |
| Product Interest | A customer's indication that they would like to purchase a Coming Soon product.        |
| Delivery         | The process of getting an order to the customer.                                       |
| Return Request   | A customer's request to return a faulty product.                                       |
| Support Request  | A request submitted by a customer for assistance.                                      |
| Notification     | A message sent to customers or the administrator when important business events occur. |

These concepts represent the language of the business and serve as the foundation for the system design.

---

# 4. Bounded Contexts

To keep the system modular and maintainable, the business domain is divided into the following logical areas.

## 4.1 Customer Management

Responsible for managing customer accounts, authentication, and customer profiles.

Primary Concepts

* Customer

---

## 4.2 Product Catalog Management

Responsible for managing products displayed to customers.

Primary Concepts

* Product
* Product Variant
* Category
* Product Image

---

## 4.3 Order Management

Responsible for creating, updating, and tracking customer orders.

Primary Concepts

* Order
* Order Item
* Shopping Cart

---

## 4.4 Payment Management

Responsible for recording customer payments and verifying payment proof.

Primary Concepts

* Payment
* Payment Proof

---

## 4.5 Inventory Management

Responsible for maintaining stock availability.

Primary Concepts

* Inventory
* Product Variant

---

## 4.6 Delivery Management

Responsible for tracking customer deliveries.

Primary Concepts

* Delivery
* Delivery Address

---

## 4.7 Customer Engagement

Responsible for helping customers interact with the business before and after purchasing.

Primary Concepts

* Product Interest
* Support Request
* Return Request
* Notification

---

# 5. Domain Entities

This section describes the primary business entities that make up the Order Management Platform.

The purpose of each entity is to explain why it exists within the business rather than how it is implemented.

---

## 5.1 Customer

### Purpose

Represents a registered customer who purchases products through the platform.

### Responsibilities

* Browse products.
* Place orders.
* Make payments.
* Express interest in products.
* Track orders.
* Submit support requests.
* Request returns.

### Collaborates With

* Order
* Payment
* Product Interest
* Support Request
* Return Request
* Delivery

---

## 5.2 Product

### Purpose

Represents an item offered for sale by the business.

### Responsibilities

* Provide product information.
* Support multiple variants.
* Support multiple images.
* Belong to a category.
* Be available for purchase or customer interest.

### Collaborates With

* Category
* Product Variant
* Product Image
* Inventory
* Product Interest

---

## 5.3 Product Variant

### Purpose

Represents a specific variation of a product.

Examples include different colors or sizes.

### Responsibilities

* Maintain its own inventory.
* Maintain its own selling price.
* Represent a purchasable version of a product.

### Collaborates With

* Product
* Inventory
* Order Item

---

## 5.4 Category

### Purpose

Represents a logical grouping of products.

### Responsibilities

* Organize products.
* Improve product browsing.
* Improve product searching.

### Collaborates With

* Product

---

## 5.5 Order

### Purpose

Represents a customer's intention to purchase one or more products.

### Responsibilities

* Contain one or more order items.
* Track the order lifecycle.
* Record customer purchases.
* Receive customer payments.

### Collaborates With

* Customer
* Order Item
* Payment
* Delivery

---

## 5.6 Order Item

### Purpose

Represents an individual product variant within an order.

### Responsibilities

* Store the selected product variant.
* Store the purchased quantity.
* Preserve the product price at the time the order was placed.

### Collaborates With

* Order
* Product Variant

---

## 5.7 Payment

### Purpose

Represents a payment made towards an order.

### Responsibilities

* Record payment information.
* Store payment proof.
* Support administrator verification.
* Maintain payment history.

### Collaborates With

* Order
* Payment Proof

---

## 5.8 Inventory

### Purpose

Represents the available stock for a product variant.

### Responsibilities

* Track available stock.
* Reflect inventory adjustments.
* Support stock availability checks.

### Collaborates With

* Product Variant
* Order Item

---

## 5.9 Product Interest

### Purpose

Represents a customer's interest in purchasing a product that is currently marked as **Coming Soon**.

### Responsibilities

* Record customer demand for products that are not yet available.
* Store the customer's requested quantity.
* Notify the customer when the product becomes available.

### Collaborates With

* Customer
* Product

---

## 5.10 Support Request

### Purpose

Represents a request submitted by a customer for assistance.

### Responsibilities

* Allow customers to communicate with the administrator.
* Maintain the conversation history.
* Track the current status of the request.

### Collaborates With

* Customer
* Administrator

---

## 5.11 Return Request

### Purpose

Represents a customer's request to return a faulty product.

### Responsibilities

* Record the reason for the return.
* Track the review process.
* Record the administrator's decision.

### Collaborates With

* Customer
* Order

---

## 5.12 Delivery

### Purpose

Represents the fulfillment of a customer's order.

### Responsibilities

* Store the selected delivery method.
* Track the delivery progress.
* Record the delivery address.

### Collaborates With

* Order
* Customer

---

## 5.13 Notification

### Purpose

Represents a message sent by the platform when an important business event occurs.

### Responsibilities

* Notify customers.
* Notify the administrator.
* Record notification delivery.

### Collaborates With

* Customer
* Administrator

---

# 6. Value Objects

Value Objects describe concepts that have no identity of their own. They exist only as part of another entity.

| Value Object | Purpose                                                                 |
| ------------ | ----------------------------------------------------------------------- |
| Phone Number | Represents the customer's contact number and login identifier.          |
| Address      | Represents the delivery location for an order.                          |
| Money        | Represents a monetary value such as a product price or payment amount.  |
| Quantity     | Represents the number of product units.                                 |
| OTP          | Represents a one-time verification code used during phone verification. |

---

# 7. Enumerations

Enumerations represent business states that are shared across the system.

## Product Status

* Coming Soon
* Available
* Out of Stock
* Archived

---

## Order Status

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

---

## Payment Status

* Pending Verification
* Verified
* Rejected

---

## Product Interest Status

* Expressed
* Notified
* Closed

---

## Return Request Status

* Pending
* Approved
* Rejected

---

## Support Request Status

* Open
* In Progress
* Resolved
* Closed

---

## Delivery Status

* Pending
* Ready for Pickup
* Out for Delivery
* Delivered

---

# 8. Aggregate Roots

Aggregate Roots are the primary entities responsible for maintaining business consistency within the domain.

## Customer Aggregate

Aggregate Root

* Customer

Contains

* Product Interest
* Support Request

The Customer aggregate is responsible for customer-related activities.

---

## Product Aggregate

Aggregate Root

* Product

Contains

* Product Variant
* Product Image
* Inventory

The Product aggregate is responsible for maintaining the product catalogue and inventory.

---

## Order Aggregate

Aggregate Root

* Order

Contains

* Order Item
* Payment
* Delivery

The Order aggregate is responsible for managing the complete lifecycle of a customer order.

---

# 9. Domain Relationships

The following relationships describe how the core business entities interact.

* A Customer places many Orders.
* An Order belongs to one Customer.
* An Order contains one or more Order Items.
* Each Order Item references one Product Variant.
* A Product belongs to one Category.
* A Category contains many Products.
* A Product contains one or more Product Variants.
* A Product may contain multiple Product Images.
* A Product Variant has one Inventory record.
* A Customer may express interest in many Products.
* A Product may have many interested Customers.
* An Interest belongs to one Customer and one Product.
* An Order may receive one or more Payments.
* Each Payment belongs to one Order.
* A Payment contains one Payment Proof.
* An Order has one Delivery.
* A Customer may submit many Support Requests.
* A Customer may submit many Return Requests.

---

# 10. Design Decisions

The following decisions guide the design of the domain model.

## Product Variant is an Entity

A Product Variant is modeled as an entity because inventory and pricing are managed independently for each variant.

For example, a black bag may have a different stock quantity from a brown bag.

---

## Inventory is Managed Per Product Variant

Inventory is associated with Product Variants rather than Products because customers purchase specific variants, not the generic product.

---

## Product Interest is Separate from Orders

Expressing interest does not create an order, reserve inventory, or require payment.

Its purpose is to measure customer demand and notify interested customers when the product becomes available.

---

## Payments Belong to Orders

A Payment has no business meaning without an Order. Therefore, every payment must be associated with exactly one order.

---

## One Customer, One Account

Each customer account is identified by a unique phone number.

Phone number verification is required before an account becomes active.

---

## Notifications Support Business Processes

Notifications are considered supporting functionality rather than core business entities. They exist to improve communication between the platform, customers, and the administrator.

---

## Simplicity First

The domain model is intentionally designed around the current needs of the business.

Future features such as wholesale pricing, multiple administrators, supplier management, promotions, and online payment gateways will be added by extending the existing model rather than redesigning it.

---

# Document Status

Draft Version 1.0

This document will evolve as the business grows and new domain concepts are introduced.
