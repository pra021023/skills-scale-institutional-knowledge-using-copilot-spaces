# TravelGo - Software Requirements Specification (SRS)

Version: 1.0  
Date: 2026-06-24

## 1. Project overview

TravelGo is a responsive web application that enables users to discover, plan, and book travel experiences including flights, hotels, and activities.

### Recommended stack

- Framework: React 19 + TypeScript
- Styling: Tailwind CSS or Material UI
- State management: Redux Toolkit or React Query
- Routing: React Router v7
- Build tool: Vite
- Testing: Vitest + React Testing Library

## 2. User roles

1. Guest user: Browse destinations; cannot book
2. Registered user: Full booking, itinerary, and profile access
3. Admin: Manage destinations, listings, and users

## 3. Functional requirements

### 3.1 Authentication

- FR-01 User can register with email and password
- FR-02 User can log in / log out
- FR-03 User can reset password via email link
- FR-04 Social login via Google and Facebook
- FR-05 JWT-based session management with auto-refresh

### 3.2 Home / landing page

- FR-06 Hero section with search bar (destination, dates, guests)
- FR-07 Featured destinations carousel
- FR-08 Trending trips section
- FR-09 Promotional banners
- FR-10 Customer testimonials / reviews section

### 3.3 Destination search and discovery

- FR-11 Search destinations by city, country, or keyword
- FR-12 Results as card grid with photo, name, rating, price
- FR-13 Filters: price range, rating, category, travel type
- FR-14 Sorting: price (asc/desc), rating, popularity
- FR-15 Map view toggle for interactive map
- FR-16 Infinite scroll or pagination

### 3.4 Destination detail page

- FR-17 Photo gallery / image carousel
- FR-18 Description, highlights, and travel tips
- FR-19 Average rating and user reviews with photos
- FR-20 Nearby attractions
- FR-21 Weather widget

### 3.5 Flight search and booking

- FR-22 Search one-way, round-trip, or multi-city flights
- FR-23 Results include airline, duration, stops, and price
- FR-24 Filters by airline, stops, departure time, cabin class
- FR-25 Select flight and proceed to passenger details form
- FR-26 Seat selection map
- FR-27 Ancillaries: extra baggage, meal preference, travel insurance

### 3.6 Hotel search and booking

- FR-28 Search by destination, check-in/check-out, rooms, guests
- FR-29 Hotel cards with thumbnail, star rating, price per night
- FR-30 Filters: star rating, amenities, distance, meal plan
- FR-31 Hotel detail page with room types, amenities, and map
- FR-32 Room selection with occupancy and bed type options

### 3.7 Activities and experiences

- FR-33 Browse destination activities (tours, adventures, cultural events)
- FR-34 Activity detail with description, inclusions, and schedule
- FR-35 Add activities to trip itinerary

### 3.8 Trip itinerary planner

- FR-36 Create named trip with start/end dates
- FR-37 Drag-and-drop day-by-day itinerary builder
- FR-38 Add flights, hotels, and activities to specific days
- FR-39 Trip summary with total estimated cost
- FR-40 Export itinerary as PDF
- FR-41 Share itinerary via link or email

### 3.9 Booking and checkout

- FR-42 Multi-step checkout: Review -> Traveller Details -> Payment -> Confirm
- FR-43 Payments: card, PayPal, wallet
- FR-44 Apply promo codes and coupons
- FR-45 Booking confirmation with reference number
- FR-46 Confirmation email with booking summary

### 3.10 User profile and dashboard

- FR-47 View/edit profile (name, photo, contact, preferences)
- FR-48 View upcoming and past bookings
- FR-49 Cancel or modify booking (within policy window)
- FR-50 Wishlist destinations
- FR-51 Loyalty points / rewards balance
- FR-52 Manage payment methods

### 3.11 Notifications

- FR-53 In-app notification bell for updates and offers
- FR-54 Email notifications for confirmations and reminders
- FR-55 Browser push notifications for price drop alerts

### 3.12 Admin panel

- FR-56 CRUD for destinations, hotels, flights, activities
- FR-57 View and manage all user bookings
- FR-58 Manage promotional banners and coupon codes
- FR-59 Analytics dashboard for bookings, revenue, destinations

## 4. Non-functional requirements

- NFR-01 Performance: FCP < 1.5s; LCP < 2.5s
- NFR-02 Fully responsive on mobile/tablet/desktop
- NFR-03 WCAG 2.1 AA accessibility compliance
- NFR-04 SEO via SSR or pre-rendering for public pages
- NFR-05 HTTPS-only, XSS/CSRF protection, no frontend secrets
- NFR-06 Scalable component-driven architecture; lazy-loaded routes
- NFR-07 Support latest 2 versions of major browsers
- NFR-08 i18n ready (English + one additional language)
- NFR-09 Minimum 70% unit/integration coverage
- NFR-10 Offline cache for last viewed itinerary (PWA/SW)

## 5. UI and UX requirements

- UX-01 Modern travel-inspired design
- UX-02 Sticky top nav with search, avatar, notifications
- UX-03 Floating "My Trip" cart with count
- UX-04 Skeleton loaders for async fetches
- UX-05 Empty states with illustration and CTA
- UX-06 Toast notifications for success/error/info
- UX-07 Dark mode toggle
- UX-08 Smooth transitions and micro-animations

## 6. Route structure

- `/` Home / Landing
- `/search` Destination search results
- `/destinations/:id` Destination detail
- `/flights/search` Flight search results
- `/hotels/search` Hotel search results
- `/hotels/:id` Hotel detail
- `/activities/:id` Activity detail
- `/trips` My trips list
- `/trips/:id` Trip itinerary planner
- `/checkout` Booking checkout
- `/booking/confirmation/:id` Booking confirmation
- `/profile` User profile
- `/profile/bookings` Booking history
- `/profile/wishlist` Saved destinations
- `/login` Login
- `/register` Register
- `/admin/*` Admin panel

## 7. API integration requirements

- API-01 REST JSON APIs via React Query
- API-02 Base URL via `VITE_API_BASE_URL`
- API-03 Auth token on protected requests via Axios interceptor
- API-04 Global error boundary for API failures
- API-05 Third-party APIs: Google Maps and OpenWeather

## 8. Out of scope (v1.0)

- Backend/API development
- Native iOS/Android apps
- Car rental booking
- Standalone travel insurance purchase
- Multi-currency real-time conversion

## 9. Deliverables

1. Source code repository
2. Deployed staging URL
3. Storybook component documentation
4. README with setup/build/deployment
5. Test coverage report
