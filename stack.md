 web application/stitch/projects/10230113262862289679/screens/e9f856691f144659b727fe01e4e89df0
# Extra Bite: App Stack

This repository is currently a static, Vercel-ready prototype exported from Stitch. Each screen lives in its own folder and is served by that folder's `index.html` using Vercel clean URLs.

## 1. Current Prototype Stack
*   **Runtime:** Static HTML pages hosted as clean URL routes (`/welcome`, `/explore`, `/meal`, `/profile`, `/payment_methods`, `/preferences`, etc.).
*   **Styling:** Tailwind CSS loaded from the CDN with per-screen theme tokens.
*   **Typography:** Plus Jakarta Sans for headings/brand text and Be Vietnam Pro for body/labels.
*   **Icons:** Google Material Symbols.
*   **Assets:** Local images in `/photos`, local SVG app icon, and screen-export screenshots/code files retained beside routable pages.
*   **PWA Shell:** `manifest.json`, theme color metadata, and mobile viewport settings on integrated screens.
*   **Deployment:** Vercel static hosting with `cleanUrls` enabled in `vercel.json`.

## 2. Suggested Production Stack
*   **Frontend:** Next.js PWA if staying web-first, or React Native/Flutter for a native mobile app.
*   **Backend:** Node.js with Express/NestJS or Python with FastAPI.
*   **Database:** PostgreSQL for users, anonymous devices, locations, orders, reviews, payment method references, and preferences.
*   **Maps API:** Google Maps Platform or Mapbox for maps, geocoding, and place search.
*   **Payments:** Stripe or a comparable PCI-compliant payment provider. Store provider tokens/customer IDs only, not full card data.
*   **Storage:** AWS S3, Google Cloud Storage, or equivalent object storage for stall, meal, and review photos.
*   **State/Data Fetching:** Zustand or Context for local device/profile state; React Query or SWR for availability, profile, settings, and history data.

## 3. Core Data Models (Database Schema)

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

### PaymentMethods
- `id`: UUID
- `user_id`: UUID (Anonymous Device ID)
- `provider`: string (e.g., Stripe)
- `provider_payment_method_id`: string
- `brand`: string
- `last_four`: string
- `expiry_month`: integer
- `expiry_year`: integer
- `is_default`: boolean

### Preferences
- `user_id`: UUID (Anonymous Device ID)
- `search_radius_km`: integer
- `dietary_restrictions`: array[string]
- `notification_settings`: JSON
- `preferred_food_types`: array[string]

## 4. Key Backend Logic (API Endpoints)

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

### GET `/api/user/:device_id/payment-methods`
- **Logic:** Returns tokenized saved payment methods for the anonymous device profile.

### POST `/api/user/:device_id/payment-methods`
- **Logic:** Creates a payment setup session or stores a provider-returned payment method token.

### GET `/api/user/:device_id/preferences`
- **Logic:** Returns saved search radius, dietary restrictions, notification settings, and food type preferences.

### PUT `/api/user/:device_id/preferences`
- **Logic:** Validates and updates profile preferences used by discovery filters and notifications.

## 5. Frontend State Management
- Use **Context API** or **Zustand** to track the user's "Anonymous ID" (generated on first open and stored in LocalStorage/AsyncStorage).
- Use **React Query** or **SWR** for real-time updates on meal availability (the progress bar in the details view).
- Cache payment methods and preferences by device ID, then invalidate the profile/settings queries after updates.

## 6. Security & Authentication
- Since the requirement is "No Login", use **Device Fingerprinting** or a persistent **JWT token** stored in the device's secure storage to link the History and Profile to the specific phone without requiring an email/password.
- Payment details must be handled by a PCI-compliant provider. The app should never store complete card numbers or CVV values.
