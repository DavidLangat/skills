---
name: backend-integration
description: Analyze frontend requirements and existing templates to systematically design and implement a complete, production-ready backend architecture.
---

# backend-integration

The purpose of this skill is to take an existing frontend application/codebase and a backend template, starter project, architecture, or specification, understand what the frontend requires, and design a complete backend implementation that can support the frontend.

The skill should move systematically from:

```
Frontend
   ↓
Understand Features
   ↓
Extract Backend Requirements
   ↓
Backend Architecture
   ↓
Apps / Modules
   ↓
Database Schema
   ↓
API Contracts
   ↓
Permissions & Business Rules
   ↓
Specifications
   ↓
Tickets
   ↓
Implementation
   ↓
Verification
```

The skill must be able to work with web and mobile applications. It must work independently and must not depend on another skill.

---

## 1. Core Objective

The core principle is:

**Build the backend required by the frontend, based on evidence from the existing UI and project requirements, rather than inventing unnecessary functionality.**

The skill should analyze the frontend and determine:
* What data the frontend needs
* What entities exist
* What operations users perform
* What APIs are required
* What authentication is required
* What authorization is required
* What business rules exist
* What database tables/models are required
* What relationships exist
* What backend modules/apps are required
* What integrations are required
* What background jobs are required
* What files/services need to be created
* What work needs to be divided into tickets

The result should be an implementation-ready backend plan and, when requested, the actual backend implementation.

---

## 2. Inputs

The skill should accept combinations of:

### Frontend
Examples: React, Next.js, Vue, Angular, React Native, Expo, Flutter, HTML/CSS/JavaScript

The frontend may be provided as:
* Source code
* Repository
* Existing project
* Screenshots
* Component files
* Routes
* API service files
* Mock data
* Forms
* UI designs

### Backend Template
The backend template may contain:
* Existing project structure
* Framework
* Database configuration
* Authentication setup
* Docker configuration
* Environment configuration
* Existing modules
* Base models
* API conventions
* Coding standards
* Deployment configuration

The skill must inspect and respect the template rather than replacing it unnecessarily.

---

## 3. First Principle: Inspect Before Designing

Before proposing a backend:
1. Inspect the frontend.
2. Inspect the backend template.
3. Identify existing backend functionality.
4. Identify existing API conventions.
5. Identify frontend routes/screens.
6. Identify forms and data requirements.
7. Identify mocked/static data.
8. Identify authentication assumptions.
9. Identify external integrations.
10. Identify reusable existing backend components.

Do not immediately create a new architecture.
Reuse existing infrastructure where appropriate.

---

## 4. Frontend Reverse Engineering

Analyze the frontend as a source of backend requirements.

Identify:

**Screens**
For example: Login, Dashboard, Products, Product Details, Orders, Checkout, Profile, Settings, Admin

**Components**
Identify components that imply backend data: ProductCard, OrderTable, UserProfile, TransactionList, NotificationList, BookingForm

**Forms**
For every form determine: Fields, Required fields, Optional fields, Validation, Submission behavior, Expected response, Error states

**Actions**
Identify: Create, Read, Update, Delete, Search, Filter, Sort, Upload, Approve, Reject, Publish, Archive, Export, Assign, Cancel, Pay, Refund, Invite, Verify

These actions should become backend requirements where appropriate.

---

## 5. Feature Extraction

Convert frontend behavior into backend features.

**Example:**
* Frontend: "Create Product" form
* Backend requirement: Product creation API
* Data: Product, Category, Image, Price, Inventory
* Rules: Authenticated user, Admin/merchant permission
* API: POST `/products`
* Database: `products`, `categories`, `product_images`

Do this systematically for the entire application.

---

## 6. Backend Capability Matrix

Create a matrix connecting frontend requirements to backend capabilities.

| Frontend Feature | Backend Capability | Entity | API | Auth |
| :--- | :--- | :--- | :--- | :--- |
| Login | Authentication | User | POST `/auth/login` | Public |
| Product List | Product retrieval | Product | GET `/products` | Auth |
| Create Product | Product creation | Product | POST `/products` | Admin |
| Order Details | Order retrieval | Order | GET `/orders/:id` | User |

The matrix should expose missing backend requirements.

---

## 7. Domain Discovery

Identify the application’s business domains.

For example:
```
E-commerce
├── Users
├── Authentication
├── Products
├── Categories
├── Inventory
├── Orders
├── Payments
├── Shipping
├── Notifications
└── Reviews
```

Do not assume every application needs these domains.
Discover them from the frontend and requirements.

---

## 8. Backend Apps / Modules

Divide the backend into logical apps/modules.

For example:
```
backend/
├── auth/
├── users/
├── products/
├── orders/
├── payments/
├── notifications/
└── common/
```

The exact structure must follow the backend framework.
* For Django, these may be Django apps.
* For Spring Boot, they may be modules/packages.
* For Node.js, they may be domain modules.
* For Laravel, they may be domains/modules.

The skill should use terminology appropriate to the chosen backend technology.

---

## 9. Module Definition

For every backend module define:
* Module:
* Purpose:
* Responsibilities:
* Entities:
* APIs:
* Business Rules:
* Permissions:
* Dependencies:
* External Integrations:
* Background Jobs:
* Events:

Avoid creating modules that contain unrelated responsibilities.

---

## 10. Database Schema Discovery

Infer the required database schema from the frontend and business requirements.

Identify:
* Entities
* Fields
* Data types
* Primary keys
* Foreign keys
* Relationships
* Constraints
* Indexes
* Unique constraints
* Nullable fields
* Defaults
* Audit fields
* Soft deletion where appropriate

**Example:**
```
User
├── id
├── email
├── password_hash
├── first_name
├── last_name
├── status
├── created_at
└── updated_at
```

---

## 11. Relationships

Explicitly determine relationships.

**Examples:**
```
User
  └── has many Orders
Order
  ├── belongs to User
  └── has many OrderItems
OrderItem
  └── belongs to Product
```

Identify: One-to-one, One-to-many, Many-to-many.
Do not create relationships merely because they are technically possible.

---

## 12. Schema Normalization

Design schemas using appropriate normalization principles.

Avoid:
* Repeated fields
* Storing relational data as arbitrary strings
* Unnecessary JSON blobs
* Duplicate data
* Unclear ownership

Use JSON/document fields only when they are appropriate for the domain.

---

## 13. API Contract Design

For every frontend operation, define an API contract.

**Example:**
POST `/api/products`
Request:
```json
{
  "name": "string",
  "description": "string",
  "price": "number",
  "category_id": "string"
}
```
Response:
```json
{
  "id": "string",
  "name": "string",
  "description": "string",
  "price": "number",
  "category": "{...}"
}
```

Define: HTTP method, Endpoint, Authentication, Authorization, Request, Response, Validation, Errors, Pagination, Filtering, Sorting, Search.

---

## 14. API Consistency

Follow consistent API conventions.

Define:
* Naming
* URL structure
* HTTP semantics
* Status codes
* Error format
* Pagination format
* Filtering
* Sorting
* Search
* Versioning where appropriate

Do not create inconsistent endpoints for similar operations.

---

## 15. Authentication

Determine authentication requirements from the frontend.

Consider:
* Login
* Registration
* Logout
* Password reset
* Email verification
* Phone verification
* Sessions
* Access tokens
* Refresh tokens
* Social authentication where required

Do not implement authentication mechanisms that are not required by the application.

---

## 16. Authorization

Identify roles and permissions.

For example:
```
Admin
├── Manage users
├── Manage products
└── View reports

Merchant
├── Manage own products
└── View own orders

Customer
├── View products
├── Create orders
└── View own orders
```

The skill must distinguish:
* Authentication: Who are you?
* Authorization: What are you allowed to do?

Never rely solely on frontend route protection for security.

---

## 17. Business Rules

Extract business rules from: UI behavior, Validation, Status transitions, Conditional rendering, Existing mock data, Existing API calls, User flows.

For example:
Order: `pending → confirmed → processing → shipped → delivered`

Document allowed transitions.
Do not invent business rules without evidence.
If a rule is unclear, identify it as an assumption.

---

## 18. State Machines

For entities with meaningful lifecycle states, define state transitions.

Example:
`Draft ↓ Published ↓ Archived`
Or:
`Pending ↓ Approved ↓ Completed`

Prevent invalid state transitions at the backend level.

---

## 19. Validation

For every input identify: Required fields, Type, Format, Length, Range, Uniqueness, Cross-field validation, Business validation.

Validation should exist on the backend even if the frontend already validates the input.
Never trust frontend validation for security or business integrity.

---

## 20. File and Media Handling

If the frontend uploads: Images, Documents, Videos, Profile pictures, Attachments
determine: Storage, File validation, Size limits, MIME validation, Access control, Metadata, Upload APIs, Deletion, Replacement, Security considerations.

Do not store large binary files directly in the database unless there is a justified reason.

---

## 21. External Integrations

Identify external services required by the frontend.

Examples: M-Pesa, Paystack, Stripe, Email, SMS, Push notifications, Maps, Cloud storage, Authentication providers.

For each integration define:
* Service:
* Purpose:
* Credentials:
* API:
* Webhook:
* Failure Handling:
* Retry Strategy:
* Security:

Never expose secret credentials to the frontend.

---

## 22. Background Jobs

Determine whether the backend requires asynchronous processing.

Examples: Email sending, Notifications, Image processing, Reports, Exports, Scheduled tasks, Payment reconciliation, Cleanup jobs.

Do not introduce queues merely because they are popular.
Use them when the workload or user experience justifies them.

---

## 23. Notifications

If the frontend has notifications, determine: Notification entity, Notification types, Read/unread state, Recipient, Delivery channels, Push notifications, Email, SMS, In-app notifications.

---

## 24. Search, Filtering and Pagination

When frontend screens contain: Search bars, Filters, Sorting, Pagination, Infinite scrolling
design backend support accordingly.

Define: Search:, Filtering:, Sorting:, Pagination:, Page size:, Maximum page size:.
Do not return unlimited records.

---

## 25. Reporting and Analytics

If dashboards display: Revenue, Sales, Transactions, Users, Performance metrics, Charts
determine: Data source, Aggregations, Filters, Date ranges, Permissions, Query requirements.

Do not calculate sensitive or expensive analytics entirely on the client.

---

## 26. Security

The backend design must consider: Authentication, Authorization, Input validation, SQL injection, XSS where applicable, CSRF where applicable, Rate limiting, Password hashing, Secrets management, Secure file uploads, API abuse, Data exposure, Sensitive information, Audit logging, CORS, Encryption where appropriate.

Security must be enforced server-side.

---

## 27. Auditability

For important business systems, determine whether the backend needs: Created timestamps, Updated timestamps, Created by, Updated by, Deleted by, Audit logs, Activity history.

Do not add full audit systems to simple applications unnecessarily.

---

## 28. Backend Architecture

Produce a backend architecture diagram or textual structure.

Example:
```
Frontend
   │
   ▼
API Layer
   │
   ▼
Application / Service Layer
   │
   ├── Auth
   ├── Users
   ├── Products
   ├── Orders
   └── Payments
   │
   ▼
Data Access Layer
   │
   ▼
Database
```

Adapt this to the backend framework.

---

## 29. Backend Template Integration

When a backend template is provided:

First determine:
Framework, Existing structure, Existing dependencies, Existing configuration, Existing database setup, Existing authentication, Existing patterns, Existing error handling, Existing API conventions.

Then extend the template.
Do not replace the template unless there is a strong technical reason.
Follow its established conventions when they are reasonable.

---

## 30. Specification Generation

After analyzing the frontend, create complete backend specifications.

The specification should include:
1. System Overview
2. Backend Architecture
3. Domains / Apps
4. Database Schema
5. Relationships
6. API Specification
7. Authentication
8. Authorization
9. Business Rules
10. Validation
11. External Integrations
12. Background Jobs
13. Notifications
14. File Storage
15. Error Handling
16. Security
17. Testing Requirements
18. Deployment Considerations

---

## 31. Ticket Generation

After creating the specifications, convert them into implementation tickets.

The workflow must be:
`Frontend ↓ Requirements ↓ Specification ↓ Backend Modules ↓ Tickets`

Tickets must be implementation-ready.

---

## 32. Ticket Structure

Every ticket should contain:
* Ticket ID:
* Title:
* Module:
* Type:
* Priority:
* Description:
* Objective:
* Requirements:
* Implementation Details:
* API Changes:
* Database Changes:
* Business Rules:
* Acceptance Criteria:
* Dependencies:
* Testing Requirements:

Do not create vague tickets such as "Build backend."
Instead create specific tickets such as "Implement Product creation and update APIs."

---

## 33. Ticket Granularity

Tickets should be:
* Independently understandable
* Small enough to implement
* Large enough to provide meaningful progress
* Clearly scoped
* Testable

Avoid tickets that are too tiny (e.g., Create Product variable).
Avoid tickets that are too large (e.g., Build entire backend).
Aim for meaningful engineering units.

---

## 34. Ticket Dependencies

Identify dependencies.

Example:
```
BE-001 Database foundation
      ↓
BE-002 Authentication
      ↓
BE-003 Users
      ↓
BE-004 Products
      ↓
BE-005 Orders
      ↓
BE-006 Payments
```

However, avoid unnecessary sequential dependencies.
Tickets that can be developed independently should remain independent.

---

## 35. Ticket Priority

Use:
* **P0 — Critical:** Required for the application to function securely.
* **P1 — High:** Required for core functionality.
* **P2 — Medium:** Important supporting functionality.
* **P3 — Low:** Enhancements or secondary functionality.

---

## 36. Acceptance Criteria

Every implementation ticket must have clear acceptance criteria.

Prefer:
* Given:
* When:
* Then:

Example:
```
Given an authenticated admin user
When the user submits valid product data
Then the API creates the product
And returns HTTP 201
And the product is persisted in the database
```

Acceptance criteria must be testable.

---

## 37. Testing Tickets

Include backend testing requirements.

Consider:
Unit tests, Integration tests, API tests, Authentication tests, Authorization tests, Validation tests, Database tests, Webhook tests, Error handling tests.

Security-sensitive functionality should receive explicit tests.

---

## 38. Frontend-to-Backend Mapping

Create a final mapping showing how the frontend connects to the backend.

Example:
```
Frontend Screen
      ↓
Frontend Action
      ↓
API Endpoint
      ↓
Backend Module
      ↓
Service
      ↓
Database
```

For example:
```
ProductList
   ↓
GET products
   ↓
GET /api/products
   ↓
Products module
   ↓
ProductService
   ↓
products table
```

This mapping is critical.

---

## 39. Missing Requirements

If the frontend requires something that cannot be determined confidently:

Do not invent it silently.

Mark it as:
```
ASSUMPTION
[assumption]
WHY:
[reason]
NEEDS CONFIRMATION:
[question]
```

Separate: Confirmed requirements, Inferred requirements, Assumptions, Unknowns.

---

## 40. Backend Completeness Check

Before declaring the backend plan complete, verify:
- [ ] Every major frontend screen has backend requirements identified
- [ ] Every form has backend handling identified
- [ ] Every important frontend action has an API
- [ ] Required entities have been identified
- [ ] Database relationships are defined
- [ ] Authentication is defined
- [ ] Authorization is defined
- [ ] Validation is defined
- [ ] Business rules are defined
- [ ] State transitions are defined where needed
- [ ] External integrations are identified
- [ ] File handling is defined
- [ ] Search/filter/pagination requirements are defined
- [ ] Notifications are considered
- [ ] Error handling is defined
- [ ] Security requirements are defined
- [ ] Testing requirements are defined
- [ ] Frontend-to-backend mapping exists
- [ ] All major work has been converted into tickets
- [ ] Tickets have acceptance criteria
- [ ] Ticket dependencies are identified
- [ ] Assumptions are clearly separated from requirements

---

## 41. Implementation Mode

When the user asks the skill to actually build the backend:

Follow this sequence:
1. Inspect frontend
2. Inspect backend template
3. Generate requirements
4. Generate specification
5. Confirm assumptions if necessary
6. Create/update backend modules
7. Create database schema
8. Create migrations
9. Create APIs
10. Implement business logic
11. Implement authentication/authorization
12. Implement integrations
13. Add tests
14. Connect frontend
15. Run verification
16. Report implementation

Do not skip directly from frontend inspection to code generation for complex applications.

---

## 42. No Fake Backend

Do not create endpoints that merely return hardcoded mock responses just to make the frontend appear functional.

When implementing the backend:
* Persist real data.
* Implement real validation.
* Implement real authorization.
* Implement real relationships.
* Handle real errors.
* Use real database operations.

Mocks may be used for testing where appropriate, but must not be presented as a complete backend.

---

## 43. No Unnecessary Backend

Do not create backend functionality that has no evidence in: Frontend, Backend template, Product requirements, Business requirements.

Avoid speculative modules.

If a potentially useful feature is discovered, classify it separately as:
**OPTIONAL FUTURE FEATURE**

Do not include it in the core implementation plan.

---

## 44. Final Deliverables

When performing a full backend analysis, produce:
1. Backend Overview
2. Frontend Feature Inventory
3. Backend Capability Matrix
4. Domain / Module Architecture
5. Database Schema
6. Entity Relationships
7. API Specification
8. Authentication & Authorization
9. Business Rules
10. External Integrations
11. Security Requirements
12. Testing Strategy
13. Frontend → Backend Mapping
14. Implementation Tickets
15. Ticket Dependencies
16. Assumptions / Open Questions
17. Implementation Order

---

## 45. Final Architecture Principle

The backend should be designed around the application’s actual domains and business capabilities, not around individual frontend components.

For example, do not create: `DashboardBackend`, `ProductCardBackend`, `ProductTableBackend`.
Instead create: `Products`, `Orders`, `Users`, `Payments`, `Inventory`.

The frontend components consume backend capabilities.

---

## 46. Independence Requirement

The skill must be completely standalone.
It must not depend on: API design skills, Database skills, Architecture skills, Testing skills, Project management skills, UI/UX skills, Refactoring skills, SEO skills.

It may use project-specific conventions when available, but it must contain everything necessary to analyze and design the backend.

---

## Final Principle

Start from the frontend’s real requirements, understand the business domain, design the backend around those domains, define the data and APIs clearly, and turn the complete specification into small, testable implementation tickets. Never invent backend functionality without evidence, and never build a fake backend merely to satisfy the UI.
