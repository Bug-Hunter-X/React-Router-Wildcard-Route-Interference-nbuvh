# React Router Wildcard Route Bug

This repository demonstrates a common, yet subtle, issue in React Router v6 when using wildcard routes (`/*`).  Placing a wildcard route after more specific routes can prevent those routes from ever matching. This leads to the wildcard route (often a 404 Not Found page) being rendered even when a valid route exists.

## Bug Description
The provided `App.js` file contains a `BrowserRouter` with several routes. The wildcard route (`/*`) appears last.  This placement causes the wildcard route to always match, regardless of the URL, effectively overriding the `/about` route.

## Solution
The solution involves reordering the routes, placing the wildcard route *before* more specific routes. This ensures that the wildcard only matches when no other route is applicable.