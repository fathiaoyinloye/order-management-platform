# Glossary

**Project:** Order Management Platform

**Version:** 1.0

**Author:** Fathia Oyinloye

---

# Purpose

This glossary defines the business terms used throughout the project.

The purpose of this document is to ensure that developers, testers, designers, and stakeholders use consistent terminology when discussing, designing, implementing, and testing the system.

---

# A

## Administrator

The business owner responsible for managing the platform.

The administrator manages products, inventory, orders, payments, deliveries, customer support, and customer communications.

---

# C

## Category

A logical grouping of similar products.

Examples include:

* Bags
* Shoes
* Clothing
* Electronics

A product belongs to one category.

---

## Coming Soon

A product status indicating that the product is not currently available for purchase from inventory but is expected to arrive in the future.

Customers may:

* Express interest
* Place an order

---

## Customer

A registered user who purchases products through the platform.

Customers can:

* Browse products
* Place orders
* Upload payment proof
* Track orders
* Express interest
* Submit support requests

---

# D

## Delivery

The process of transferring purchased products from the business to the customer.

Delivery may occur through:

* Customer Pickup
* Local Delivery

---

## Delivery Address

The location provided by the customer for order delivery.

---

## Delivery Status

The current stage of a delivery.

Examples include:

* Ready for Pickup
* Out for Delivery
* Delivered

---

# I

## Interest

A customer's indication that they would like to purchase a Coming Soon product when it becomes available.

Expressing interest:

* Does not create an order.
* Does not reserve inventory.
* Does not require payment.

The primary purpose of interest is to help the business estimate customer demand.

---

## Inventory

The quantity of products currently available for sale.

Inventory is tracked at the Product Variant level.

---

# O

## Order

A customer's request to purchase one or more products.

An order contains one or more order items and progresses through predefined order statuses until completion or cancellation.

An order may contain products that are marked as Coming Soon.

---

## Order Item

A single product variant and quantity within an order.

One order may contain multiple order items.

---

## OTP (One-Time Password)

A temporary verification code sent to a customer's registered phone number to verify ownership of the phone number.

---

# P

## Payment

A monetary amount paid by a customer toward an order.

Version 1 supports bank transfer payments.

One order may have multiple payments.

---

## Payment Proof

An image or document uploaded by the customer as evidence that a payment has been made.

Each payment shall have its own payment proof.

---

## Payment Verification

The administrator's review of uploaded payment proof.

A payment may be:

* Pending Verification
* Verified
* Rejected

---

## Phone Number

The primary identifier used to register and identify customers.

Each customer may have only one active phone number.

---

## Product

An item offered for sale by the business.

A product contains general information such as:

* Name
* Description
* Category

A product may have multiple variants.

---

## Product Image

An image associated with a product.

A product may have multiple images.

---

## Product Status

The current availability of a product.

Supported statuses are:

* Coming Soon
* Available
* Out of Stock
* Archived

---

## Product Variant

A specific version of a product.

Variants distinguish products by attributes such as:

* Color
* Size

Each variant maintains its own inventory and price.

Examples:

Leather Bag

* Black
* Brown
* Pink

or

Running Shoe

* Black / Size 40
* Black / Size 41
* White / Size 42

---

# R

## Return Request

A request submitted by a customer to return a faulty product.

Each request is reviewed by the administrator before approval or rejection.

---

# S

## Shopping Cart

A temporary collection of products selected by a customer before placing an order.

The cart is not an order until checkout is completed.

---

## Stock

The quantity available for a specific product variant.

Stock is reduced when products are sold and may also change through administrator inventory adjustments.

---

## Support Request

A message submitted by a customer to the administrator requesting assistance.

Examples include:

* Payment issues
* Delivery issues
* Product enquiries
* Faulty products
* General enquiries

Support requests remain linked to the customer's account.

---

# V

## Variant

See **Product Variant**.

---

# Business Concepts

The platform is built around the following core business concepts:

* Customer
* Administrator
* Category
* Product
* Product Variant
* Product Image
* Inventory
* Shopping Cart
* Order
* Order Item
* Payment
* Payment Proof
* Product Interest
* Delivery
* Return Request
* Support Request
* Notification

These concepts form the foundation of the domain model, database design, backend implementation, frontend implementation, and system testing.

---

# Document Status

Draft Version 1.0

This glossary will evolve as new business concepts are introduced.
