# Product Requirements Document (PRD)

**Project:** Order Management Platform

**Version:** 1.1 (Draft)

**Author:** Fathia Oyinloye

---

# 1. Introduction

## 1.1 Purpose

This document defines the functional and non-functional requirements for the Order Management Platform.

The platform is designed to help small businesses manage their products, customers, orders, inventory, payments, deliveries, customer support, and customer communication from a single platform.

Customers should be able to browse products, place orders, express interest in products that are not yet available, upload payment proof, track their orders, and communicate with the business without relying primarily on phone calls or WhatsApp conversations.

This document serves as the primary source of product requirements for the design, development, testing, and maintenance of the platform.

---

# 2. Product Vision

Build a secure, scalable, and maintainable Order Management Platform that digitizes the sales process for small businesses while providing an excellent customer experience and supporting future business growth.

---

# 3. Product Goals

The platform shall:

* Reduce manual order processing.
* Reduce customer dependence on WhatsApp for placing orders.
* Improve inventory visibility.
* Improve payment tracking.
* Improve customer experience.
* Provide a centralized management system for the business owner.
* Support future expansion without requiring major architectural changes.

---

# 4. Product Principles

The following principles shall guide all product decisions.

* The website shall be the primary platform for customer interactions.
* WhatsApp shall be used primarily as a notification channel in Version 1.
* Business records shall remain accurate, consistent, and traceable.
* The platform shall be designed for future extensibility.
* Version 1 shall focus only on solving the business's current problems.
* Simplicity shall be preferred over unnecessary complexity.

---

# 5. Target Users

## Customer

Individual customers purchasing products from the business.

Customers use the platform to:

* Browse products
* Search products
* Place orders
* Express interest in upcoming products
* Upload payment proof
* Track orders
* Submit support requests

---

## Administrator

The business owner responsible for managing the platform.

The administrator uses the platform to:

* Manage products
* Manage inventory
* Verify payments
* Process customer orders
* Respond to customer support requests
* Track customer demand
* Manage deliveries

---

# 6. Functional Requirements

## 6.1 Authentication & Account Management

### Description

The platform shall provide secure customer authentication and account management.

### Requirements

The system shall:

* Allow customers to register using their phone number.
* Verify ownership of the phone number using a One-Time Password (OTP).
* Prevent account activation until the phone number has been verified.
* Allow customers to log in securely.
* Allow customers to reset forgotten passwords.
* Allow customers to update their profile information.
* Allow customers to change their phone number.
* Require phone number verification whenever the phone number changes.
* Prevent unauthorized access to protected resources.
* Allow customers to log out securely.

### Version 1

OTP delivery shall be provided through a configurable messaging provider.

The implementation may use:

* SMS
* WhatsApp

The delivery channel shall be an implementation decision and shall not affect business logic.

---

## 6.2 Product Management

### Description

The platform shall allow customers to browse products while allowing the administrator to manage the product catalogue.

### Requirements

The system shall:

* Display products available for purchase.
* Display products marked as Coming Soon.
* Organize products into categories.
* Allow customers to search for products.
* Display detailed product information.
* Display multiple images for each product.
* Support multiple product variants.
* Display stock availability for each product variant.
* Display product price.
* Display product availability status.

The administrator shall be able to:

* Create products.
* Update products.
* Archive products.
* Upload product images.
* Manage product variants.
* Manage product categories.

---

## 6.3 Product Interest Management

### Description

The platform shall allow customers to express interest in products that are not yet available.

The purpose of this feature is to help the business understand customer demand before importing products.

### Requirements

The system shall:

* Allow customers to express interest only in products marked as **Coming Soon**.
* Allow customers to specify the quantity they are interested in purchasing.
* Allow customers to update the requested quantity while the product remains in the Coming Soon state.
* Allow only one active interest record per customer for a product.
* Record customer demand for business planning.
* Notify interested customers when the product becomes available.

Expressing interest shall **not** reserve inventory.

---

## 6.4 Shopping Cart

### Description

The platform shall allow customers to prepare products before placing an order.

### Requirements

The system shall:

* Allow customers to add products to the shopping cart.
* Allow customers to update product quantities.
* Allow customers to remove products from the cart.
* Calculate the order total.
* Validate stock availability before checkout.
* Save the customer's cart until the order is completed or the cart is cleared.

---

## 6.5 Order Management

### Description

The platform shall manage customer orders from creation until completion.

Orders may contain products that are currently available or products marked as **Coming Soon**.

When a customer places an order for a Coming Soon product, the order shall remain pending until the product becomes available.

### Requirements

The system shall:

* Allow customers to place orders.
* Allow customers to order products marked as **Coming Soon**.
* Generate a unique order number.
* Maintain order history.
* Allow customers to view order details.
* Allow customers to track order status.
* Prevent modification of fully paid orders.
* Allow cancellation of unpaid orders.
* Notify customers whenever the order status changes.

---

## 6.6 Payment Management

### Description

The platform shall support manual payment verification using bank transfers.

Customers may make one or more payments toward an order.

### Requirements

The system shall:

* Support multiple payments for a single order.
* Allow customers to upload proof of payment for every payment made.
* Maintain complete payment history.
* Allow administrators to verify payments.
* Allow administrators to reject invalid payments.
* Record the verification decision.
* Notify customers whenever a payment is approved.
* Notify customers whenever a payment is rejected.

Payments shall be made outside the platform through bank transfer during Version 1.

---

## 6.7 Inventory Management

### Description

The platform shall maintain accurate inventory for every product variant.

### Requirements

The system shall:

* Track stock at the product variant level.
* Prevent customers from purchasing quantities greater than the available stock.
* Update inventory whenever products are sold.
* Allow administrators to manually adjust inventory.
* Record inventory adjustments.
* Notify administrators when inventory falls below a configurable threshold.

---


---

## 6.8 Delivery Management

### Description

The platform shall allow customers to receive their orders either through pickup or delivery while allowing the administrator to monitor the delivery progress.

### Requirements

The system shall:

* Allow customers to choose a delivery method during checkout.
* Allow customers to provide a delivery address for delivery orders.
* Allow customers to update their delivery address before the order is processed.
* Allow administrators to update the delivery status.
* Allow customers to track the delivery status of their orders.
* Notify customers whenever the delivery status changes.

---

## 6.9 Notification Management

### Description

The platform shall notify customers and the administrator whenever important business events occur.

Version 1 shall use a configurable messaging provider. The implementation may use WhatsApp or SMS. The notification service shall be designed to support additional channels in future versions without changing the business logic.

### Customer Notifications

The system shall notify customers when:

* Registration is successful.
* Phone number verification is completed.
* An order has been placed.
* Payment proof has been received.
* A payment has been approved.
* A payment has been rejected.
* A product they expressed interest in becomes available.
* The status of an order changes.
* An order is ready for pickup.
* An order has been shipped.
* An order has been been delivered.
* A return request has been approved.
* A return request has been rejected.
* A response has been added to one of their support requests.

### Administrator Notifications

The system shall notify the administrator when:

* A new customer registers.
* A new order is placed.
* Payment proof is uploaded.
* A customer expresses interest in a product.
* Inventory falls below the configured threshold.
* A return request is submitted.
* A new support request is submitted.

---

## 6.10 Return Management

### Description

The platform shall allow customers to request the return of faulty products.

### Requirements

The system shall:

* Allow customers to submit return requests for faulty products.
* Allow customers to
