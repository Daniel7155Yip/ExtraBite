web application/stitch/projects/10230113262862289679/screens/94313cb28aea43b08dc9dbdbc636b4f4
# Extra Bite: Technical Architecture & Workflow Mapping

This document outlines the relationship between the exported folders and the core user journey for the Extra Bite food rescue application.

## 1. The Core Folders & Their Roles

| Folder Name | Component / Responsibility | Key Content |
| :--- | :--- | :--- |
| `welcome_to_extra_bite` | **Onboarding Entry Point** | The splash screen with the "Let's Get Started" CTA. |
| `stitch_extra_Bite_map` | **Core Navigation & Map Assets** | The underlying map engine and interactive location pins. |
| `Explore Brisbane` | **Discovery Hub** | The main map view featuring search and the location cards (e.g., UQ Food Chains). |
| `Mystery_Meal Details` | **Product Specifics** | The high-fidelity details for a specific location, including the proportional graph and photo collection. |
| `Order_history` | **User Activity Log** | The list of past purchases and the entry point for the rating/review flow. |
| `Location_reviews` | **Social Proof Store** | The standalone page containing user feedback from Kobe, Mayumi, and others. |
| `Profile` | **Individual Impact Dashboard** | User stats including "Total Food Saved" (grams) and "Average Cost per Meal". |
| `Organic_vitality` | **Design System (Global)** | The shared CSS, design tokens (Purple branding), and shared UI components (Top Nav, Bottom Bar). |

---

## 2. Functional Workflow (The User Journey)

### Flow A: Discovery to Claim
1. **Entry:** User starts at `welcome_to_extra_bite`.
2. **Search:** Clicking "Let's Get Started" routes the user to `Explore Brisbane`.
3. **Selection:** User interacts with the `stitch_extra_Bite_map` pins or the featured card to select a location.
4. **Detail:** User is routed to `Mystery_Meal Details` to see availability and meal proportions.
5. **Action:** User clicks "Claim Mystery Meal", which processes the purchase and updates the history.

### Flow B: Post-Purchase & Feedback
1. **History:** User opens `Order_history` to view past rescues.
2. **Rating:** User rates an item in the history list.
3. **Reviews:** Rating an item "unlocks" or provides a link to `Location_reviews` where they can see community feedback.
4. **Alt Access:** Users can also view `Location_reviews` directly from a star-link in `Mystery_Meal Details`.

### Flow C: Impact Tracking
1. **Stats:** User navigates to `Profile`.
2. **Data Sync:** The app calculates total grams saved by aggregating data from the `Order_history` folder items.
3. **Display:** Shows real-time savings metrics using the `Organic_vitality` visual style.

---

## 3. Global Dependencies
*   **Navigation:** All primary folders (except Welcome) depend on the `BottomNavBar` component defined in `Organic_vitality`.
*   **Branding:** Every screen pulls its color palette (#51247A) and typography (Plus Jakarta Sans) from the `Organic_vitality` theme files.
*   **Assets:** Icons used for the proportional graph in `Mystery_Meal Details` are shared globally across the app shell.