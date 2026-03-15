# Fishery Onboard Edge Server

## Overview

Fishery Onboard Edge Server is a shipboard infrastructure platform designed to support digital services on fishing vessels operated by the fleet.

The server acts as a **local edge computing node** deployed on each vessel and provides the following key functions:

- Internet billing and access control for crew
- Local database storage
- Authentication services
- Synchronization with shore infrastructure
- Fleet analytics data collection
- Platform for additional onboard services

The system is designed to operate **autonomously at sea**, even with limited or intermittent connectivity.

---

## Core Purpose

The primary function of this server is to support the **fleet internet billing system**, replacing manual voucher distribution with an automated system.

Crew members authenticate using their assigned ID and receive controlled internet access based on configured policies.

Key requirements:

- per-user traffic quota
- monthly limits
- session tracking
- usage analytics
- administrative access for radio officer

---

## Main Services

The onboard edge server runs several core services.

### Authentication

FreeRADIUS is used for user authentication and integration with the network captive portal.

### Database

PostgreSQL stores:

- crew database
- traffic accounting
- session logs
- voucher / quota history
- analytics data

### Billing API

A backend service manages:

- quota assignment
- session validation
- usage accounting

### Web Interface

A local web interface provides access for:

- radio officer
- onboard administration

Features include:

- crew usage overview
- manual quota management
- diagnostics

### Data Synchronization

Aggregated usage data is periodically synchronized with the shore server for:

- centralized analytics
- backup
- fleet-wide reporting

---

## Deployment Model

Each vessel runs a dedicated onboard server.
