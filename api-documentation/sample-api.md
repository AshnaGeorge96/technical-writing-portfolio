# Vehicle Tracking API – Documentation

## Overview
The Vehicle Tracking API allows client applications to retrieve vehicle location data,
manage user authentication, and receive real-time tracking updates.

This documentation provides details on available endpoints, request formats,
and example responses.

---

## Base URL
https://api.vehicletrackingapp.com/v1

---

## Authentication

All API requests require authentication using a Bearer Token.

### Authorization Header
Authorization: Bearer <access_token>

---

## Login API

### Endpoint
POST /auth/login

### Request Body
{
  "email": "user@example.com",
  "password": "password123"
}

### Success Response
{
  "status": "success",
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR..."
}

### Error Response
{
  "status": "error",
  "message": "Invalid credentials"
}

---

## Get Vehicle List

### Endpoint
GET /vehicles

### Response
{
  "vehicles": [
    {
      "vehicleId": "VH001",
      "vehicleName": "Truck 01",
      "status": "Active"
    }
  ]
}

---

## Get Live Vehicle Location

### Endpoint
GET /vehicles/{vehicleId}/location

### Path Parameter

vehicleId – Unique vehicle identifier

### Response
{
  "vehicleId": "VH001",
  "latitude": 10.0234,
  "longitude": 76.3056,
  "lastUpdated": "2026-01-15T10:25:00Z"
}

---

## Error Codes

400 – Bad request  
401 – Unauthorized  
404 – Resource not found  
500 – Internal server error  

---

## Notes
- All responses are returned in JSON format
- Timestamps follow ISO 8601 standard
- Authentication token is required for every request
