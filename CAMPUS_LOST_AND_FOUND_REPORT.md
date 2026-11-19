# CAMPUS LOST AND FOUND WEB PORTAL

## Capstone Report

**Project:** Campus Lost and Found Web Portal  
**Technology:** HTML, CSS, and JavaScript  
**Backend Demonstration:** Browser localStorage  
**Date:** November 19, 2026

---

# 1. INTRODUCTION

This report presents the development of a Campus Lost and Found Web Portal for a Coursera web-development capstone project. The project applies the knowledge and skills acquired through the course specialization to a practical problem faced by students: reporting, searching for, and recovering misplaced campus belongings.

Campus communities often rely on informal messages, notice boards, or scattered social-media posts to exchange information about lost and found items. These methods are difficult to search, may contain incomplete information, and do not provide a consistent ownership-claim workflow. The proposed portal provides a centralized, responsive interface where users can publish lost or found listings, search and filter records, submit ownership claims, and review claim activity.

The application was developed using only HTML, CSS, and vanilla JavaScript. It does not use a database or server-side framework. Browser localStorage is used as the demonstration backend, with listings stored under `campusFind.items` and claims stored under `campusFind.claims`. The project demonstrates front-end structure, responsive design, DOM manipulation, form validation, filtering, event handling, and browser persistence.

# 2. PROBLEM STATEMENT

Students need a convenient and reliable way to report lost or found belongings and verify ownership claims. Existing informal methods do not provide consistent item categories, dates, locations, search controls, or a dedicated claim process. The problem is that relevant details may be difficult to locate, claims may be poorly documented, and information may become unavailable when it is shared through temporary or unstructured channels.

The project addresses the following functional problem:

> How can a campus community quickly publish, search, filter, and claim lost or found items using a lightweight, accessible, and responsive web application?

The solution must support:

1. Posting both lost and found items.
2. Browsing sample listings.
3. Searching by item name, description, location, or category.
4. Filtering by category, status, and date.
5. Validating listing and claim forms.
6. Recording ownership claims with supporting proof.
7. Persisting listings and claims in the browser.
8. Supporting desktop and mobile screens.

# 3. METHODOLOGY

## 3.1 Methodological Approach

A rapid iterative development approach was used. The interface was first organized into two main views: Browse Listings and My Claims. The lost-and-found workflow was then divided into smaller components: data storage, listing display, filters, item submission, claim submission, validation, and responsive layout.

The project was implemented as a static web application consisting of:

- `index.html` for semantic page structure and forms.
- `styles.css` for responsive design and visual presentation.
- `app.js` for state management, rendering, validation, filtering, and localStorage operations.
- `README.md` for setup and demonstration instructions.

## 3.2 System Design and Data Model

Each listing is represented as a JavaScript object with an ID, status, category, title, description, location, date, contact email, resolved state, and photo. Each ownership claim contains a claim ID, item ID, item name, claimant name, campus email, proof of ownership, status, and submission date.

The storage keys are:

| Data | localStorage Key | Purpose |
|---|---|---|
| Listings | `campusFind.items` | Stores posted and sample items |
| Claims | `campusFind.claims` | Stores submitted and sample claims |

## 3.3 Analysis and Development Methods

The following methods were used:

- **DOM querying and event handling** to connect buttons, forms, and filters.
- **FormData and HTML validation** to check required fields and email formats.
- **Array filtering** to combine search, category, status, and date criteria.
- **String matching** to search across item names and descriptions.
- **Template-based rendering** to generate listing and claim cards dynamically.
- **Responsive CSS media queries** to support desktop, tablet, and mobile layouts.
- **Browser localStorage** to maintain demonstrations between page refreshes.
- **FileReader** to convert a device image smaller than 2 MB into a displayable data URL.
- **Image fallback logic** to preserve listing presentation if a remote image fails to load.

## 3.4 Methodological Choice and Justification

Vanilla HTML, CSS, and JavaScript were selected to meet the project constraints and demonstrate core front-end concepts without framework dependency. localStorage was used because the assignment requested a browser-based demonstration backend. This approach avoids unnecessary server setup while still demonstrating data persistence.

The application also distinguishes Lost, Found, and Resolved statuses. Lost and found items remain claimable, while resolved items are presented as returned and cannot receive another claim.

# 4. ANALYSIS AND RESULTS

## 4.1 Development Tools

The project was developed and tested in Visual Studio Code and served using Python's local static HTTP server.

| Tool | Use |
|---|---|
| Visual Studio Code | Source editing and diagnostics |
| HTML5 | Page structure and forms |
| CSS3 | Styling and responsive layout |
| JavaScript | Application logic and localStorage |
| Python HTTP Server | Local project hosting |
| Browser Developer Tools | Local-storage and interface testing |

## 4.2 Feature Analysis

The application is organized into a browse view and a claim activity view. The browse view includes a search field and filters for category, status, and date. The post form supports Lost and Found statuses, item details, contact information, photo URL entry, and device-image upload. The claim form collects the claimant's name, campus email, and proof of ownership.

Table 4.1 summarizes the principal implemented features.

**Table 4.1: Implementation and validation summary**

| Component | Required Method | Implemented Result |
|---|---|---|
| Listing creation | Required-field validation | Item information is checked before submission |
| Email validation | HTML email format | Invalid campus-email values are rejected |
| Search | Text matching | Title, description, location, and category are searchable |
| Category filter | Select value matching | Listings are filtered by selected category |
| Status filter | Lost, Found, or Resolved matching | Listing status can be isolated |
| Date filter | Exact date matching | Listings are filtered by reporting date |
| Device photo | FileReader and 2 MB limit | Device images are stored safely as data URLs |
| Photo URL | URL field and image rendering | Remote product or item photos are displayed |
| Ownership claim | Claim form and proof field | Claims are stored and shown in My Claims |
| Persistence | localStorage API | Items and claims survive browser refreshes |
| Responsive layout | CSS media queries | Layout adapts to desktop and mobile screens |

## 4.3 Sample Data Analysis

At initial load, the application provides five sample listings and one sample ownership claim.

**Table 4.2: Sample listing distribution**

| Metric | Count |
|---|---:|
| Total sample listings | 5 |
| Found listings | 2 |
| Lost listings | 2 |
| Electronics listings | 2 |
| Documents listings | 1 |
| Clothing listings | 1 |
| Bags listings | 1 |
| Sample ownership claims | 1 |

The sample claim has a `Pending review` status. This demonstrates the complete ownership workflow without marking the underlying item as resolved.

## 4.4 Workflow Test Results

The major workflows were tested through the browser interface.

**Table 4.3: Functional test results**

| Test | Procedure | Expected Result | Result |
|---|---|---|---|
| Load portal | Open local server URL | Sample listings and controls appear | Passed |
| Search | Enter a location or item term | Matching listings remain visible | Passed |
| Category filter | Choose a category | Only matching listings appear | Passed |
| Status filter | Choose Lost or Found | Matching status appears | Passed |
| Date filter | Select a sample date | Listings for that date appear | Passed |
| Clear filters | Select Clear | All listings return | Passed |
| Post missing fields | Submit an incomplete form | Validation message appears | Passed |
| Post complete listing | Enter all required fields and photo source | Listing is added and saved | Passed |
| Upload large image | Select a file above 2 MB | Large upload is rejected | Passed |
| Submit claim | Complete claim fields | Claim appears in My Claims | Passed |
| Refresh browser | Reload the page | localStorage items and claims remain | Passed |

## 4.5 Key Findings

Several findings emerged from the implementation:

1. A centralized listing interface makes lost-and-found information easier to locate than disconnected messages.
2. Combining multiple filters improves usability because users can narrow searches by category, status, and date.
3. Required-field and email validation reduce incomplete or malformed submissions.
4. Supporting both photo URLs and device uploads makes the portal useful in both online and physical campus scenarios.
5. localStorage is suitable for a functional demonstration, but it is browser-specific and not appropriate for production use.
6. A separate claim view creates a clear record of ownership evidence and review status.

## 4.6 Knowledge and Skills Applied

HTML and CSS were used to build a semantic and responsive interface. JavaScript and DOM APIs were used to implement dynamic rendering, event handling, filtering, validation, and browser persistence. The project also applied program-design skills such as data modeling, defensive parsing, user-feedback messages, and fallback handling for image or storage failures.

The methodology was informed by the course emphasis on practical development: defining the problem, planning application features, implementing components, testing workflows, analyzing results, and documenting limitations. These steps supported the final outcome and demonstrated that a small web application can address a realistic campus coordination problem without external infrastructure.

# 5. CONCLUSION

The Campus Lost and Found Web Portal successfully demonstrates a complete lost-and-found workflow using HTML, CSS, JavaScript, and browser localStorage. The project addressed the problem of scattered and difficult-to-search campus information by providing a centralized interface for lost and found listings.

The application includes responsive layouts, lost and found status distinctions, sample listings, search functionality, category/status/date filtering, listing validation, photo support, ownership claims, claim activity, and persistent browser storage. The sample claim demonstrates that ownership evidence can be collected and reviewed, while the localStorage keys provide a simple demonstration of persistent state.

The project is significant because it applies front-end concepts to a practical community need and presents the complete journey from problem identification to implementation and testing. The main limitation is that localStorage is not shared across devices or users. It also cannot provide authentication, approval controls, notifications, or secure data synchronization.

Future improvements should include:

- A server-side database for records shared across users.
- Secure student authentication.
- Administrator approval or claim-resolution controls.
- Image upload support with server-side storage.
- Notifications when claims are submitted or approved.
- Location maps and campus-building selection.
- Item-status history and claim audit logs.
- Automated unit and browser tests.

The completed prototype fulfills the requested course project scope and provides a functional foundation for a real campus lost-and-found service.
