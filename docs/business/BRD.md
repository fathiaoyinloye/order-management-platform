# Business Requirements Document (BRD)

**Project Name:** Retail Order Management System

**Version:** 0.1 (Draft)

**Author:** Fathia Oyinloye

**Last Updated:** June 2026

---

# 1. Introduction

## 1.1 Purpose

This document defines the business requirements for a Retail Order Management System designed for a small import-based retail business.

The system aims to digitize the ordering process, improve customer experience, simplify inventory management, and reduce reliance on WhatsApp and phone calls for customer interactions.

This document serves as the foundation for software design and development.

---

# 2. Business Background

The business imports products from China and sells them directly to individual customers in Nigeria.

Currently, products are advertised primarily through WhatsApp and other social media platforms. Customers contact the business owner through WhatsApp messages or phone calls to place orders.

Some products are already available in stock, while many products are advertised before they are imported to determine customer demand.

Payments are currently made through bank transfers. Customers may complete payment immediately or make multiple payments before collecting their goods.

Products are delivered through customer pickup, third-party riders, or direct delivery by the business owner.

Customers may return products only if they are genuinely faulty.

---

# 3. Business Problem

The current business process has several challenges:

* Orders are managed manually through WhatsApp and phone calls.
* Customer payment records are difficult to track.
* Customer order history is not centralized.
* Customer interest in future products is tracked manually.
* Inventory levels are difficult to monitor.
* Customers cannot independently check the status of their orders.
* The business owner spends significant time responding to repetitive customer inquiries.

---

# 4. Business Objectives

The system should:

* Provide an online platform for customers to browse products.
* Allow customers to register and manage their accounts.
* Allow customers to express interest in products that are not yet available.
* Allow customers to purchase products that are currently in stock.
* Allow customers to pay for products before they arrive.
* Support multiple payments toward a single purchase.
* Maintain accurate inventory for every product variation.
* Allow customers to track their orders.
* Enable the business owner to manage products, orders, customers, and payments from one system.

---

# 5. Stakeholders

## Primary Stakeholder

* Business Owner (System Administrator)

## Secondary Stakeholders

* Customers
* Delivery Personnel

---

# 6. Current Business Process

1. Products are advertised on WhatsApp.
2. Customers contact the business owner.
3. Orders are recorded manually.
4. Customers pay via bank transfer.
5. Customers send payment proof.
6. The business owner verifies payment.
7. Goods are delivered or picked up.
8. Faulty products may be returned.

---

# 7. Proposed Business Process

1. Customers register on the website.
2. Customers browse products.
3. Customers can:

   * Purchase products currently in stock.
   * Express interest in products that are not yet available.
   * Pay for products before they arrive.
4. Customers upload payment proof.
5. The business owner verifies payments.
6. Customers receive notifications as their order progresses.
7. Customers track order status through the system.
8. Customers receive products through pickup or delivery.

---

# 8. Business Scope

## In Scope

* Customer registration and login
* Product catalog
* Product search
* Product variations (size, color)
* Multiple product images
* Product inventory
* Customer interest registration
* Orders
* Multiple payments
* Payment proof upload
* Delivery management
* Order tracking
* Notifications
* Product returns for faulty goods

## Out of Scope (Version 1)

* Multiple administrators
* Wholesale pricing
* Discount coupons
* Customer reviews
* Loyalty rewards
* Interest-bearing installment financing
* Warehouse management
* Supplier management
* Online payment gateway integration

---

# 9. Business Rules

* Every customer must register before placing an order.
* Each customer has one active phone number.
* Customers may update their phone number.
* One order may contain multiple products.
* One product may have multiple images.
* One product may have multiple variants (size, color).
* Inventory is tracked at the product variant level.
* Customers may upload payment proof.
* Customers may make multiple payments toward the same purchase.
* Customers receive goods only after the required payment conditions are met.
* Customers may express interest in products that have not yet been imported.
* Returns are accepted only for faulty products.
* Orders that have been fully paid cannot be modified.

---

# 10. Assumptions

* The business has a single administrator.
* Customers have internet access.
* Customers can upload payment proof.
* Products are imported based on business demand.

---

# 11. Constraints

* Initial release supports only retail customers.
* Payments are made through bank transfer.
* WhatsApp will be the primary notification channel where supported.
* The system is designed for one business location in Version 1.

---

# 12. Success Criteria

The project will be considered successful if:

* Customers can place orders without contacting the business owner.
* Customer payment records are centrally managed.
* Inventory is accurately tracked.
* Customer interest in future products is recorded digitally.
* Customers can track their own orders.
* The business owner spends less time managing orders manually.

---

## Document Status

Draft Version 0.1

This document will evolve throughout the project as additional business requirements are discovered and validated.
