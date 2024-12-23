# Next.js 15 Router.push() Query Parameters Issue

This repository demonstrates a problem with using `router.push()` in Next.js 15 to redirect with query parameters.  The redirect itself works, but the query parameters are not included in the URL.

## Bug Description

When navigating from `/about` to `/` using `router.push({ pathname: '/', query: { name: 'John Doe' } })`, the URL becomes `/` instead of `/\?name=John Doe`. 

## Reproduction Steps

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate to `/about`.
5. Click the button to go to the home page.
6. Observe that the URL is `/`, not `/\?name=John Doe`, even though the query parameter was included in the router.push call.

## Expected Behavior

The URL should be `/\?name=John Doe` after clicking the button, reflecting the query parameter passed to `router.push()`. 

## Actual Behavior

The URL is `/` without any query parameters.

## Solution

The problem was resolved by using the correct way of passing query parameters to router.push(). In this case, changing query parameter to searchParams solves the problem