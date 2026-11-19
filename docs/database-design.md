# KM Link: Database Design

## Businesses

### Fields

- Id
- Name
- Address
- Email
- Phone
- Subscription Plan
- Created Date

---

## Users

### Fields

- Id
- Business Id
- First Name
- Last Name
- Email
- Password
- Role
- Active

---

## Warehouses

### Fields

- Id
- Business Id
- Name
- Address
- Manager Id

---

## Products

### Fields

- Id
- Business Id
- SKU
- Name
- Description
- Price
- Barcode
- Active

---

## Inventory

### Fields

- Id
- Product Id
- Warehouse Id
- Quantity
- Reserved Quantity
- Available Quantity

---

## Orders

### Fields

- Id
- Customer Id
- Order Number
- Status
- Total
- Created Date

---

## Order Items

### Fields

- Id
- Order Id
- Product Id
- Quantity
- Unit Price

---

## Deliveries

### Fields

- Id
- Order Id
- Driver Id
- Status
- GPS Location
- Dispatch Time
- Delivery Time

---

## Notifications

### Fields

- Id
- User Id
- Type
- Message
- Sent Date
- Read
