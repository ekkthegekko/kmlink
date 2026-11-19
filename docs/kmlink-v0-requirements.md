# KM Link: Version 0 Requirements Specification

> Product: KM Link
>
> Version: 0.1
>
> Status: Draft
>
> Priority: MVP
>
> Target Release: 19/11/2029

---

# 1. Purpose

## 1.1: Overview

KM Link is a warehouse, inventory, order fulfilment, dispatch and delivery management platform.

The primary goal of KM Link is to provide businesses with a centralised system for:

- Managing products.
- Managing inventory.
- Managing warehouses.
- Managing orders.
- Managing deliveries.
- Tracking fulfilment progress.
- Tracking delivery locations.
- Monitoring operational activity.

The platform must operate independently but support future integrations with third-party systems.

---

## 1.2: Business Goal

A customer places an order through KM Link.

The order is sent to the appropriate warehouse.

Warehouse staff collect and prepare the products.

The order is dispatched and delivered.

Throughout the entire process both the buyer and seller can monitor:

- Order status.
- Fulfilment progress.
- Delivery progress.
- Current location.
- Destination location.
- Important events and updates.

---

## 1.3: Success Criteria

KM Link is considered successful when:

- Customers can place orders.
- Warehouses can fulfil orders.
- Inventory remains accurate.
- Deliveries can be tracked in near real time.
- Businesses can monitor operations.
- Customers receive meaningful updates.
- The platform functions without KM Dine.

---

# 2. User Roles & Permissions

## 2.1: Customer

### Permissions

- Browse products.
- Create orders.
- View own orders.
- Track deliveries.
- View fulfilment progress.
- Request returns.
- Receive notifications.

### Restrictions

- Cannot view other customer information.
- Cannot modify inventory.

---

## 2.2: Supplier

### Permissions

- View assigned orders.
- Manage supplied products.
- Manage product availability.

---

## 2.3: Picker

### Permissions

- View assigned fulfilment tasks.
- Update collection progress.
- Report shortages.
- Report unavailable products.
- Request substitutions.

### Restrictions

- Cannot approve major stock adjustments.

---

## 2.4: Warehouse Manager

### Permissions

- Manage warehouse inventory.
- Approve inventory adjustments.
- Manage fulfilment.
- Manage dispatch.
- Approve order modifications.
- Approve cancellations.

---

## 2.5: Business Owner

### Permissions

- Full business visibility.
- Reporting access.
- User management.
- Warehouse management.

---

## 2.6: Administrator

### Permissions

- Full platform access.

---

# 3. Applications

## 3.1: Buyer Application

### Required Screens

- Login
- Registration
- Forgot Password
- Dashboard
- Product Catalogue
- Product Details
- Basket
- Checkout
- Orders
- Order Details
- Tracking Map
- Notifications
- Settings

---

## 3.2: Seller Application

### Required Screens

- Login
- Registration
- Forgot Password
- Dashboard
- Orders
- Order Details
- Inventory
- Fulfilment
- Dispatch
- Reporting
- Tracking Map
- User Management
- Settings

---

# 4. Authentication & Account Management

## 4.1: Registration

### Requirements

#### AUTH-FR-001

Users shall be able to create accounts.

#### AUTH-FR-002

Businesses shall be able to create organisation accounts.

#### AUTH-FR-003

Email verification shall be supported.

---

## 4.2: Login

### Requirements

#### AUTH-FR-004

Users shall log in using email and password.

#### AUTH-FR-005

Users shall remain authenticated until logout or session expiry.

---

## 4.3: Forgot Password

### Requirements

#### AUTH-FR-006

Users shall be able to request password reset links.

#### AUTH-FR-007

Password reset links shall expire.

---

# 5. Product Management

## 5.1: Product Catalogue

### Requirements

#### PROD-FR-001

Businesses shall be able to create products.

#### PROD-FR-002

Products shall support:

- Name
- Description
- SKU
- Barcode
- Images
- Price

#### PROD-FR-003

Products shall belong to categories.

---

## 5.2: Pricing

### Requirements

#### PROD-FR-004

Businesses shall be able to change product pricing.

#### PROD-FR-005

Price changes shall only affect future orders.

---

# 6. Inventory Management

## 6.1: Inventory Visibility

### Requirements

#### INV-FR-001

Businesses shall be able to monitor inventory levels.

#### INV-FR-002

Inventory shall be tracked by warehouse.

---

## 6.2: Inventory Adjustments

### Requirements

#### INV-FR-003

Warehouse managers may adjust inventory.

#### INV-FR-004

Approved warehouse workers may perform inventory corrections.

#### INV-FR-005

Significant stock increases shall require supporting evidence.

### Accepted Evidence

- Receipt
- Invoice
- Delivery Note
- Uploaded Photograph

---

## 6.3: Audit Trail

### Requirements

#### INV-FR-006

All inventory changes shall record:

- User
- Timestamp
- Previous Quantity
- New Quantity
- Reason
- Supporting Evidence

---

## 6.4: Overselling & Backorders

### Requirements

#### INV-FR-007

Overselling may be enabled.

### Conditions

- Incoming stock is confirmed.
- Delay is acceptable.
- Business permits overselling.

#### INV-FR-008

Backorders shall be supported.

#### INV-FR-009

Pre-orders shall be supported.

---

# 7. Order Management

## 7.1: Order Creation

### Requirements

#### ORD-FR-001

Customers shall be able to place orders.

#### ORD-FR-002

Orders shall generate unique order numbers.

#### ORD-FR-003

Inventory shall be validated during submission.

---

## 7.2: Order Sources

Orders may originate from:

- KM Link
- Manual Entry
- KM Dine
- Future Integrations

---

## 7.3: Order Statuses

### Required Statuses

1. Placed
2. Accepted
3. Awaiting Stock
4. Being Collected
5. Packing
6. Ready For Dispatch
7. Dispatched
8. In Transit
9. Arrived
10. Partially Delivered
11. Cancelled
12. Returned

---

## 7.4: Order Modifications

### Requirements

#### ORD-FR-004

Orders may be modified before dispatch.

### Conditions

- Warehouse approval required.
- Inventory validation required.

---

## 7.5: Order Cancellations

### Requirements

#### ORD-FR-005

Orders may be cancelled before dispatch.

### Conditions

- Warehouse approval required.

---

## 7.6: Price Locking

### Requirements

#### ORD-FR-006

Order pricing shall be locked at the time of purchase.

#### ORD-FR-007

Future product price changes shall not affect existing orders.

---

## 7.7: Partial Fulfilment

### Requirements

#### ORD-FR-008

Orders may be partially fulfilled.

#### ORD-FR-009

Remaining items shall continue through fulfilment.

---

## 7.8: Multi-Warehouse Fulfilment

### Requirements

#### ORD-FR-010

Orders should be fulfilled from a single warehouse whenever possible.

#### ORD-FR-011

Multiple warehouses may fulfil an order if inventory shortages exist.

### Example

Warehouse A:

- 19 Balloons

Warehouse B:

- 1 Balloon

Order:

- 20 Balloons

Result:

- Split fulfilment permitted.

---

# 8. Warehouse Fulfilment

## 8.1: Picking

### Requirements

#### WH-FR-001

Picking tasks shall be generated automatically.

#### WH-FR-002

Pickers shall receive product collection tasks.

---

## 8.2: Progress Updates

### Requirements

#### WH-FR-003

Pickers shall update item collection progress.

### Example

Required:

- 20 Balloons

Progress:

- 5 Collected
- 10 Collected
- 20 Collected

Customers shall be able to view these updates.

---

## 8.3: Packing

### Requirements

#### WH-FR-004

Orders shall be packed before dispatch.

#### WH-FR-005

Packing completion shall generate status updates.

---

# 9. Dispatch & Delivery

## 9.1: Dispatch

### Requirements

#### DEL-FR-001

Warehouses shall dispatch completed orders.

#### DEL-FR-002

Dispatch timestamps shall be recorded.

---

## 9.2: GPS Tracking

### Requirements

#### DEL-FR-003

Delivery tracking shall utilise GPS.

#### DEL-FR-004

Location shall update every 10 metres of movement.

### Tracking Data

- Latitude
- Longitude
- Direction
- Timestamp

---

## 9.3: Customer Tracking

### Requirements

#### DEL-FR-005

Customers shall view delivery progress in real time.

#### DEL-FR-006

Customers shall view destination information.

#### DEL-FR-007

Businesses shall view delivery locations.

---

## 9.4: Returns

### Requirements

#### DEL-FR-008

Returns before dispatch belong to Order Management.

#### DEL-FR-009

Returns after dispatch belong to Delivery Management.

---

# 10. Notifications

## 10.1: Channels

### Supported Channels

- Push Notifications
- SMS
- Email
- In-App Notifications
- System Banners

---

## 10.2: Notification Events

Notifications shall be generated for:

- Order Created
- Order Accepted
- Awaiting Stock
- Picking Started
- Picking Updated
- Picking Complete
- Packed
- Dispatched
- In Transit
- Delivered
- Cancelled
- Returned

---

# 11. Reporting

## 11.1: Order Reporting

### Reports

- Orders by Status
- Orders by Customer
- Outstanding Orders
- Cancelled Orders

---

## 11.2: Fulfilment Reporting

### Reports

- Picking Performance
- Warehouse Performance
- Fulfilment Times

---

## 11.3: Inventory Reporting

### Reports

- Stock Levels
- Inventory Adjustments
- Inventory Discrepancies
- Backorders

---

## 11.4: Delivery Reporting

### Reports

- Delivery Times
- Delivery Success Rate
- Failed Deliveries

---

# 12. Subscription Management

## 12.1: Membership Plans

Available billing periods:

- Monthly
- Quarterly
- Annually

---

## 12.2: Membership Rules

### Requirements

#### SUB-FR-001

All plans shall provide the same platform functionality.

#### SUB-FR-002

Billing period shall be the only difference between plans.

#### SUB-FR-003

Cancellation shall not immediately revoke access.

#### SUB-FR-004

Customers retain access until the paid period expires.

---

# 13. Accessibility

## 13.1: Accessibility Features

### Requirements

#### ACC-FR-001

The system shall support:

- Dark Mode
- Adjustable Text Sizes
- Dictation
- Screen Readers
- Keyboard Navigation

#### ACC-FR-002

The system shall comply with WCAG accessibility principles.

---

# 14. Performance & Technical Requirements

## 14.1: Connectivity

### Requirements

#### TECH-FR-001

Users must be online to perform actions.

Examples:

- Place Orders
- Modify Orders
- Adjust Inventory
- Update Deliveries

---

## 14.2: Offline Access

### Requirements

#### TECH-FR-002

Users shall continue viewing previously loaded information while offline.

Examples:

- Previous Orders
- Inventory Snapshots
- Historical Data

#### TECH-FR-003

Users shall not be automatically logged out due to connection loss.

---

## 14.3: Performance

### Requirements

#### TECH-FR-004

The platform should support orders containing approximately 1,000 items.

#### TECH-FR-005

The platform shall support multiple warehouses and businesses.

---

# 15. Integrations

## 15.1: Current Priority

- Standalone KM Link

---

## 15.2: Future Integrations

- KM Dine
- POS Systems
- Ecommerce Platforms
- Accounting Platforms
- Mapping Services

---

# 16. MVP Scope

## 16.1: Included In Version 0

- Authentication
- Product Catalogue
- Inventory Management
- Order Management
- Warehouse Fulfilment
- Dispatch
- GPS Tracking
- Delivery Tracking
- Notifications

---

## 16.2: Deferred Until Later Versions

- AI Features
- Forecasting
- Advanced Analytics
- Advanced Route Optimisation
- Complex Automation

---

# 17. Delivery Strategy

## 17.1: Development Approach

Development shall follow:

- Working MVP First
- Continuous Updates
- Incremental Feature Releases

## 17.2: Launch Objective

Target Launch Date:

**19 November 2029**

No fixed deadline shall override product quality or stability.
