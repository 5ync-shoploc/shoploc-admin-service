# Shoploc Admin Service

## Overview

`shoploc-admin-service` is a backend microservice responsible for
administration and management operations of the Shoploc platform.

It provides administrative APIs for managing the platform, monitoring
business entities, and performing privileged management operations.

The service is part of the Shoploc microservices architecture.

## Responsibilities

The Admin Service is responsible for:

- Managing platform administration operations
- Managing administrative users and permissions
- Managing merchants and organizations from an administrative perspective
- Managing platform configuration when required
- Managing administrative actions
- Providing administration APIs
- Providing operational information to administrators
- Supporting platform monitoring and management operations

The Admin Service contains administration-related business logic.

Authentication and identity management remain the responsibility of
`shoploc-identity-service`.

Product management remains the responsibility of
`shoploc-catalog-service`.

Order management remains the responsibility of
`shoploc-order-service`.

## Architecture

```text
                         Admin Client
                              │
                              ▼
                    ┌─────────────────────┐
                    │   Shoploc API       │
                    │      Gateway        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    Admin Service    │
                    │                     │
                    │ Administration      │
                    │ Merchants           │
                    │ Organizations       │
                    │ Permissions         │
                    │ Platform Management │
                    └──────────┬──────────┘
                               │
                ┌──────────────┼──────────────┐
                ▼              ▼              ▼
           Identity        Catalog         Order
           Service         Service         Service