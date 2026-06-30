**Core Domain** 

Product

Product Variant

Order

Order Item

Customer

Payment

Inventory


**Supporting Domain** 


Category

Product Image

Interest

Shopping Cart

Cart Item

Delivery

Address

Support Request

Return Request

Notification





Customer
    │
    ├── Places ─────────────► Order
    │                           │
    │                           ├── Contains ─────► Order Item
    │                           │                      │
    │                           │                      ▼
    │                           │               Product Variant
    │                           │                      │
    │                           │                      ▼
    │                           │                 Product
    │                           │
    │                           └── Receives ───► Payment
    │
    ├── Expresses ───────────► Interest
    │                              │
    │                              ▼
    │                         Product
    │
    └── Creates ─────────────► Support Request