web application/stitch/projects/10230113262862289679/screens/e64be16cf2ec40de809e525054075837
# Project Summary: Extra Bite - Food Rescue App

## Core Concept & Mission
Extra Bite is a streamlined, location-based food rescue application specifically designed for university campuses, school areas, and food courts. Its mission is to minimize food waste by providing a centralized platform for the distribution of surplus meals from multiple food vendors in a single location (e.g., a university student union).

## Key Product Principles
- **No Friction:** No login or registration required. The app is open-and-use.
- **Location-Centric:** Focuses on high-density food areas like "UQ Food Chains" (Union Complex, St Lucia).
- **The "Mystery Meal" Model:** Instead of individual menu items, vendors offer "Mystery Meals" at a fixed price, representing a curated selection of their daily surplus.
- **Visual Branding:** A modern, "Organic Vitality" theme utilizing a primary purple brand color and high-quality imagery to elevate the food rescue experience.

## Technical & Functional Requirements by Screen

### 1. Welcome Screen (Onboarding)
- **Visuals:** High-impact landing page with the "Extra Bite" logo.
- **Key Data:** Real-time impact tracker (e.g., "4,281 lbs saved today").
- **CTA:** Large "Let's Get Started" button that leads directly to the map.
- **Secondary Action:** Simple "Log In" link for legacy users (though the primary flow is anonymous).

### 2. Explore Screen (Home / Discovery)
- **Interface:** Full-screen interactive map (initially centered on Brisbane/University areas).
- **Functionality:** 
  - Search bar for specific locations or "Use current location" button.
  - Map pins representing specific food stall collection points.
- **Feature Card:** A prominent card for featured locations (e.g., "UQ Food Chains") showing:
  - Rating (e.g., 4.8 stars).
  - Distance (e.g., 250m away).
  - Real photo of the actual stall/area to help with physical navigation.

### 3. Mystery Meal Details Screen
- **Imagery:** A photo collection/gallery showcasing the variety of possible meals.
- **Status Tracking:** A progress bar showing availability (e.g., "7 meals remaining" or "86% claimed").
- **Information:** 
  - Exact address (Union Complex, Ground Floor, St Lucia QLD 4067).
  - "What's inside?" section describing today's general surplus variety.
- **Proportional Graph:** A unique horizontal bar chart visualizing the meal's makeup from different vendors (e.g., 50% Main Course, 30% Green Box, 20% The Bakery) using custom icons for each store.
- **CTA:** "Claim Mystery Meal for $5.00" button with a notice about the pickup time window.

### 4. Order History Screen
- **Layout:** Vertical list of past purchases.
- **Features:** 
  - Details for each order (Meal name, Date, Price).
  - **Rating System:** Star-based rating system for every purchase.
  - **Social Proof:** "Rate Us to see what everyone else has to say" prompt that acts as the gateway to the community reviews.

### 5. Location Reviews (Standalone Page)
- **Interface:** A dedicated feedback store accessed via History or the Mystery Meal Details.
- **Structure:** 
  - Global rating summary (e.g., 4.8/5 based on 1,284 reviews).
  - User-generated content including names (e.g., Kobe Jackson, Mayumi Komukai), star ratings, text critiques, and uploaded photos.
  - Filterable by "Most Recent" or "With Photos".

### 6. Profile Screen
- **User Dashboard:** 
  - **Individual Impact:** "Total Food Saved" displayed prominently in grams (calculated based on individual meal data).
  - **Efficiency Metric:** "Average Cost per Meal" highlighting the savings compared to retail prices.
- **Navigation:** Quick links to Order History, Payment Methods, and Preferences.

## Design System: "Organic Vitality"
- **Primary Color:** Deep Purple (#51247A).
- **Typography:** Plus Jakarta Sans (Modern, friendly).
- **Components:** Rounded corners (8px-16px), subtle shadows, and a clean white/light-gray surface palette for a premium feel.