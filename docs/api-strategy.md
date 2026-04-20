# API Testing Strategy

## Scope
- Restful Booker API
- Authentication, Booking, CRUD operations

## Test Types
- Functional API testing
- Contract validation
- Negative testing
- Response time validation

## Covered Endpoints
- POST /auth
- GET /booking
- GET /booking/:id
- POST /booking
- PUT /booking/:id
- DELETE /booking/:id

## Validation Points
- HTTP status codes
- Response schema
- Response time (<1s)
- Headers (Content-Type)
- Token validation

## Tools
- Postman
- Newman (CI execution)

## Risks
- API downtime
- Inconsistent test data