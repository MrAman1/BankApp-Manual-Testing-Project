# UI / UX Testing Checklist – Banking Application

## General Layout & Consistency
- [ ] Consistent fonts, colors, and branding across all screens
- [ ] Alignment of labels, fields, and buttons is consistent
- [ ] No overlapping or truncated text on any screen
- [ ] Consistent button naming (e.g., "Submit" vs "Proceed" used consistently)
- [ ] Currency values consistently formatted (e.g., ₹ symbol, comma separators, 2 decimal places)
- [ ] Dates consistently formatted across the app (e.g., DD-MMM-YYYY)

## Forms & Input Fields
- [ ] Mandatory fields are clearly marked (e.g., with `*`)
- [ ] Field-level validation messages appear near the relevant field
- [ ] Placeholder text disappears correctly on input
- [ ] Password/MPIN fields are masked with a show/hide toggle
- [ ] Tab order moves logically through form fields
- [ ] Numeric-only fields reject alphabetic input at UI level

## Navigation
- [ ] Menu items and breadcrumbs are consistent across pages
- [ ] Back/Cancel buttons behave predictably and don't lose unsaved warnings
- [ ] Logout is accessible from every authenticated screen

## Responsiveness
- [ ] Layout adapts correctly on desktop, tablet, and mobile viewports
- [ ] No horizontal scroll on standard screen widths
- [ ] Touch targets (buttons/links) are appropriately sized on mobile

## Cross-Browser
- [ ] Verified on Chrome, Firefox, and Edge (latest versions)
- [ ] Verified on Android and iOS native/mobile-web apps
- [ ] No console errors in browser dev tools on key screens

## Accessibility (Basic)
- [ ] Sufficient color contrast for text/background
- [ ] Form fields have associated labels
- [ ] Error/success messages are not conveyed by color alone

## Feedback & Loading States
- [ ] Loading indicators shown during API calls (e.g., fetching balance, submitting transfer)
- [ ] Success/error toasts or banners are clear and dismissible
- [ ] No duplicate submission possible while a request is in progress (button disabled/spinner shown)
