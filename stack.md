 web application/stitch/projects/10230113262862289679/screens/e9f856691f144659b727fe01e4e89df0
# Extra Bite: Full-Stack Implementation Guide

This guide outlines the suggested technical architecture for building the "Extra Bite" app into a fully functional product.

## 1. Suggested Tech Stack
*   **Frontend:** React Native or Flutter (for cross-platform mobile) or Next.js (for a PWA).
*   **Backend:** Node.js with Express or Python with FastAPI.
*   **Database:** PostgreSQL (Relational) for handling users, locations, and orders.
*   **Maps API:** Google Maps Platform (Maps SDK for Mobile, Places API for search).
*   **Storage:** AWS S3 or Google Cloud Storage (for stall and meal photos).

## 2. Core Data Models (Database Schema)

### Locations (Stalls)
- `id`: UUID
- `name`: string (e.g., "UQ Food Chains")
- `address`: string
- `coordinates`: Point (Lat/Long)
- `photo_url`: string
- `rating_avg`: float

### MysteryMeals
- `id`: UUID
- `location_id`: FK
- `total_quantity`: integer
- `remaining_quantity`: integer
- `price`: decimal
- `proportions`: JSON (e.g., `{"main": 0.5, "sides": 0.3, "bakery": 0.2}`)
- `contents_description`: text
- `pickup_window_end`: datetime

### Orders (Purchases)
- `id`: UUID
- `user_id`: UUID (Anonymous Device ID)
- `meal_id`: FK
- `purchase_time`: datetime
- `status`: enum (claimed, picked_up, expired)
- `cost_paid`: decimal
- `weight_grams`: integer (Used for impact tracking)

### Reviews
- `id`: UUID
- `order_id`: FK
- `user_name`: string
- `rating`: integer (1-5)
- `comment`: text
- `photo_urls`: array[string]

## 3. Key Backend Logic (API Endpoints)

### GET `/api/locations/nearby`
- **Params:** `lat`, `long`, `radius=15km`
- **Logic:** Queries the DB for locations within the radius and returns pins for the map.

### GET `/api/locations/:id/details`
- **Logic:** Aggregates location info, current mystery meal availability, and calculated proportions.

### POST `/api/orders/claim`
- **Body:** `meal_id`, `device_id`
- **Logic:** 
  1. Checks `remaining_quantity > 0`.
  2. Decrements `remaining_quantity`.
  3. Creates an `Order` record.
  4. Returns a pickup token.

### GET `/api/user/:device_id/impact`
- **Logic:** 
  1. Sums `weight_grams` from all `Orders` for that device.
  2. Calculates `average_cost` from total paid / total orders.

## 4. Frontend State Management
- Use **Context API** or **Zustand** to track the user's "Anonymous ID" (generated on first open and stored in LocalStorage/AsyncStorage).
- Use **React Query** or **SWR** for real-time updates on meal availability (the progress bar in the details view).

## 5. Security & Authentication
- Since the requirement is "No Login", use **Device Fingerprinting** or a persistent **JWT token** stored in the device's secure storage to link the History and Profile to the specific phone without requiring an email/password.