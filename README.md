# Little Lemon Chicago — Table Booking Web Application

**Meta Front-End Developer Capstone Project** by **Billy Simba**

A responsive, accessible React web application built for the **Little Lemon** Mediterranean restaurant in Chicago, featuring an interactive table reservation system connected to the booking API with live slot availability, client-side + HTML5 validation, double-booking prevention, confirmation summaries, and comprehensive Jest / React Testing Library unit tests.

---

## Features & Rubric Coverage

- **UX/UI Design System:** Faithful Little Lemon Chicago brand palette (`#495E57` olive green, `#F4CE14` lemon yellow, `#EE9972` / `#FBDABB` accents, `#EDEFEE` cloud neutral), `Markazi Text` display headings, `Karla` body typography, and full landing flow (`Hero / CallToAction`, `Specials`, `CustomersSay`, `Chicago` story, `BookingPage`, and `ConfirmedBooking`).
- **Semantic HTML & Open Graph Protocol (OGP):** Uses React fragments around semantic `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, and `<footer>` landmarks, plus SEO `<meta name="description">` and Open Graph (`og:title`, `og:description`, `og:image`, `og:type`) tags in `public/index.html`.
- **Responsive Layout:** CSS Grid and Flexbox layouts with responsive breakpoints for desktop, tablet (`<= 960px`), and mobile (`<= 640px`), including an accessible collapsible mobile navigation menu.
- **Lifted Booking State & API Integration:** `Main.js` manages available times using `useReducer(updateTimes, [], initializeTimes)` powered by `fetchAPI(date)` and `submitAPI(formData)` (with a deterministic local fallback in `src/utils/bookingAPI.js`). Confirmed bookings remove booked time slots from the active session and navigate to `/confirmed` (`ConfirmedBooking`).
- **Form Validation & Edge-Case Handling:** Combines HTML5 constraints (`required`, `min`, `max`, `type="date"`, `type="number"`, `type="email"`) with pure React validation helpers (`src/utils/validation.js`), actionable inline `role="alert"` error messages, disabled submit state while invalid, and graceful handling when no time slots remain.
- **WCAG & ARIA Accessibility:** Keyboard skip link, explicit `<label htmlFor>` associations on every field, `aria-label="On Click"` on primary interactive controls, `aria-required`, `aria-invalid`, `aria-describedby`, `aria-live` status updates, and high-contrast focus outlines.
- **Automated Unit Tests:** Complete Jest + React Testing Library test suites (`src/App.test.js` and `src/BookingForm.test.js`) covering static rendering, `initializeTimes` / `updateTimes` reducer logic, HTML5 validation attributes, JavaScript validation valid/invalid paths, form submission, and edge cases.

---

## Project Structure

```text
little-lemon-capstone/
├── public/
│   ├── index.html              # Semantic HTML shell, OGP meta tags, fonts, API script
│   └── og-little-lemon.svg     # Open Graph social preview card
├── src/
│   ├── components/
│   │   ├── BookingForm.js      # Controlled reservation form with validation & slots
│   │   ├── BookingSlot.js      # Interactive available-time chip component
│   │   ├── CallToAction.js     # Homepage hero CTA banner
│   │   ├── Chicago.js          # Restaurant backstory section
│   │   ├── ConfirmedBooking.js # Post-submission confirmation summary view
│   │   ├── CustomersSay.js     # Guest testimonials grid
│   │   ├── Footer.js           # Site footer with navigation, contact & hours
│   │   ├── Header.js           # Brand header wrapping Nav
│   │   ├── Main.js             # Router + lifted useReducer booking state + submitForm
│   │   ├── Nav.js              # Responsive navigation bar
│   │   └── Specials.js         # Weekly specials cards grid
│   ├── data/
│   │   └── menuData.js         # Specials & testimonials data with inline SVG visuals
│   ├── pages/
│   │   ├── AboutPage.js
│   │   ├── BookingPage.js
│   │   ├── HomePage.js
│   │   └── MenuPage.js
│   ├── utils/
│   │   ├── bookingAPI.js       # fetchAvailableTimes / submitBookingData API wrapper
│   │   └── validation.js       # Pure date, time, guests, occasion, email validators
│   ├── App.css                 # Responsive Grid/Flexbox brand styles
│   ├── App.js                  # Root fragment + BrowserRouter
│   ├── App.test.js             # App & reducer unit tests
│   ├── BookingForm.test.js     # Form rendering, HTML5/JS validation & edge-case tests
│   ├── index.css               # Design tokens & base reset
│   ├── index.js                # React 18 entry point
│   └── setupTests.js           # Jest DOM matchers
└── package.json
```

---

## Getting Started

### Prerequisites
- **Node.js** (v18 or higher recommended)
- **npm** (v9 or higher)

### Installation
```bash
git clone <repository-url>
cd little-lemon-capstone
npm install
```

### Run Development Server
```bash
npm start
```
Open [http://localhost:3000](http://localhost:3000) in your browser and click **Reserve a Table** or **Reservations** in the navigation bar.

### Run Unit Tests
```bash
npm test -- --watchAll=false
```

### Build for Production
```bash
npm run build
```
