# Campus Find — Campus Lost and Found Portal

Campus Find is a responsive, browser-only Lost and Found web portal built strictly with HTML, CSS, and JavaScript.

## Project Requirements Checklist

- [x] Responsive interface for desktop, tablet, and mobile
- [x] HTML, CSS, and vanilla JavaScript only
- [x] Post lost or found item listings
- [x] Browse sample lost, found, and resolved listings
- [x] Search items by title, description, location, or category
- [x] Filter listings by category, status, and date
- [x] Clear all listing filters
- [x] Form validation for item and ownership claim forms
- [x] Submit ownership claims with proof of ownership
- [x] View submitted claims under My Claims
- [x] Browser localStorage persistence
- [x] Photo URL and device-image upload support
- [x] Sample listings and a sample ownership claim

## Important Notes

- This is a frontend demonstration; no backend or database is used.
- Listings are stored under the localStorage key `campusFind.items`.
- Ownership claims are stored under the localStorage key `campusFind.claims`.
- Listings and claims persist in the current browser only.
- Clearing browser site data removes all posted listings and submitted claims.
- A photo URL or a device image smaller than 2 MB is required when posting an item.
- Product-page URLs are converted to a main product image when supported.
- The sample claim status is `Pending review` and demonstrates the ownership workflow.

## Demonstration Workflow

1. Open the portal at `http://localhost:5500`.
2. Browse the sample listings.
3. Search or filter listings by category, status, or date.
4. Select `Post an item` or `Post a found item`.
5. Complete the required fields and add a photo URL or device image.
6. Publish the listing.
7. Select `Claim item` on a listing.
8. Enter the claimant name, campus email, and ownership proof.
9. Open `My Claims` to verify the submitted claim.

## Run the Project

From the project folder:

```powershell
python -m http.server 5500
```

Then open `http://localhost:5500`.

To reset the demonstration data, open the browser developer tools, run `localStorage.clear()`, and refresh the page.
