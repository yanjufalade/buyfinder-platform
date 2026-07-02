# BuyFinder Domain Model

Version: 1.0

Status: Approved

Author: Adeyanju Falade

---

# Overview

The BuyFinder domain model defines the core business concepts used throughout the platform.

Every database table, Java entity, API endpoint, and business rule must map back to one or more of these concepts.

---

# Core Domains

## Identity & Access

Responsible for authentication and authorization.

### User

A registered individual who accesses the platform.

Types:

- Buyer
- Supplier
- Administrator
- Finance Officer
- Auditor
- Support Officer

---

## Procurement

The heart of BuyFinder.

### Purchase Request

A buyer's intention to purchase a product or service.

Contains:

- Title
- Description
- Quantity
- Budget
- Category
- Delivery Location
- Delivery Deadline
- Status

---

### Offer

A supplier's response to a Purchase Request.

Contains:

- Offered Price
- Delivery Time
- Product Description
- Images
- Warranty
- Notes

---

### Award

Represents the supplier selected by the buyer.

Only one offer may be awarded per Purchase Request.

---

## Finance

### Wallet

Represents funds belonging to a user.

Supports:

- Deposits
- Withdrawals
- Escrow
- Refunds

---

### Escrow

Temporary holding of funds until buyer confirmation.

States:

- Pending
- Released
- Refunded
- Cancelled

---

### Transaction

Represents every financial movement.

Examples:

- Deposit
- Withdrawal
- Escrow Hold
- Escrow Release
- Refund
- Commission

---

## Delivery

### Delivery Confirmation

Confirms successful receipt of goods.

Possible outcomes:

- Accepted
- Rejected
- Disputed

---

## Administration

### Audit Log

Records every important system event.

Examples:

- Login
- Payment
- Approval
- Refund
- Escrow Release

---

### Feature Flag

Allows administrators to enable or disable platform capabilities.

Examples:

- Escrow Enabled
- Registration Enabled
- Maintenance Mode
- AI Features

---

# Business Relationships

Buyer

↓

creates

↓

Purchase Request

↓

receives

↓

Offers

↓

selects

↓

Award

↓

Delivery

↓

Payment Released

---

# Domain Rules

A Purchase Request belongs to exactly one Buyer.

A Supplier may submit multiple Offers.

A Buyer may receive multiple Offers.

Only one Offer may be awarded.

Every payment creates a Transaction.

Every Escrow references one Transaction.

Every important business event creates an Audit Log.

---

# Future Domains

AI Assistant

Supplier Reputation

Recommendations

Fraud Detection

Procurement Analytics

Contract Management

Inventory Integration

Enterprise Reporting