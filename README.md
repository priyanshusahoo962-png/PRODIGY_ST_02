# PRODIGY_ST_02

Compatibility testing for a basic web page, Prodigy InfoTech Software Testing Internship

## Prodigy InfoTech – Software Testing Task 02
### Compatibility Testing of an E-commerce Web Page

**Tester:** Priyanshu Priyadarshi Sahoo

---

## Objective

Testing a simple e-commerce web page across different browsers and devices, check for layout issues, broken links, and functionality discrepancies, and recommend fixes.

## Website Tested

- **Website:** https://shoplane-by-lassie.netlify.app/
- **Type:** E-commerce website (Shoplane)

## Test Environment

| Item | Details |
|---|---|
| Operating System | Windows |
| Browsers | Google Chrome (version: 155.0.8059.82(64-bit)), Microsoft Edge (version: 155.0.4283.62( 64-bit)), Mozilla Firefox (version: 158.0 (64-bit)) |
| Screen sizes | Desktop (1920×1080), Mobile (Vivo Y20G) via Chrome DevTools device emulation |
| Testing Date | 16 October 2026 |

> Safari was not tested because it is not available on Windows.

## Scope

- Navigation menu links
- Top banner
- Footer links (Helpful Links and Online Store)
- Page layout on desktop, tablet, and mobile sizes
- Behavior across browsers

## Compatibility Matrix

| Feature / Link | Chrome | Edge | Firefox | Mobile size | 
|---|---|---|---|---|
| Navigation: Clothing | ❌ | ❌ | ❌ | ❌ | 
| Navigation: Accessories | ❌ | ❌ | ❌ | ❌ |
| Top banner link | ❌ | ❌ | ❌ | ❌ | 
| Footer: Home | ❌ | ❌ | ❌ | ❌ | 
| Footer: About | ❌ | ❌ | ❌ | ❌ |
| Footer: Contact | ❌ | ❌ | ❌ | ❌ |
| Footer: Men Clothing | ❌ | ❌ | ❌ | ❌ |
| Footer: Women Clothing | ❌ | ❌ | ❌ | ❌ |
| Footer: Men Accessories | ❌ | ❌ | ❌ | ❌ |
| Footer: Women Accessories | ❌ | ❌ | ❌ | ❌ |
| Page layout | ✅ | ✅ | ⚠️Minor font difference | ✅ | 

✅ = works, ❌ = issue, ⚠️ = minor issue

## Issues Found

### Issue 1: Clothing and Accessories navigation links show "Page not found"
- **Type:** Broken link
- **Severity:** High
- **Where:** Main navigation menu
- **Steps:** 1. Open the website 2. Click "Clothing" or "Accessories" in the menu
- **Expected:** The matching product listing page opens
- **Actual:** "Page not found" message is shown
- **Screenshot:** `screenshots/issue1.png`
- **Recommended fix:** Correct the link URLs so they point to existing pages, or create the missing pages.

### Issue 2: Top banner does not open anything when clicked
- **Type:** Broken link / functionality
- **Severity:** Medium
- **Where:** Banner at the top of the home page
- **Steps:** 1. Open the website 2. Click the top banner
- **Expected:** Banner opens its linked page (offer or collection)
- **Actual:** Nothing opens
- **Screenshot:** `screenshots/issue2.png`
- **Recommended fix:** Add a working link to the banner, or remove the clickable styling if it is not meant to be a link.

### Issue 3: Footer "Helpful Links" (Home, About, Contact) do not open
- **Type:** Broken link
- **Severity:** High
- **Where:** Footer, Helpful Links section
- **Steps:** 1. Scroll to the footer 2. Click Home, About, or Contact
- **Expected:** The matching page opens
- **Actual:** The pages do not open
- **Screenshot:** `screenshots/issue3.png`
- **Recommended fix:** Fix the link paths and make sure the About and Contact pages exist.

### Issue 4: Footer "Online Store" links do not open
- **Type:** Broken link
- **Severity:** High
- **Where:** Footer, Online Store section (Men Clothing, Women Clothing, Men Accessories, Women Accessories)
- **Steps:** 1. Scroll to the footer 2. Click each of the four links
- **Expected:** The matching category page opens
- **Actual:** None of the four links open
- **Screenshot:** `screenshots/issue4.png`
- **Recommended fix:** Correct the link URLs to existing category pages
-
- ### Issue 5: Font rendering differs slightly in Firefox
- **Type:** Layout / visual (cross-browser)
- **Severity:** Low
- **Where:** SHOPLANE logo text and the "Clothing For Men And Women" heading
- **Browser:** Mozilla Firefox (compared with Google Chrome)
- **Steps:** 1. Open https://shoplane-by-lassie.netlify.app/ in Chrome 2. Open the same page in Firefox 3. Compare the logo and the heading text
- **Expected:** Text looks the same in all browsers
- **Actual:** In Firefox, the SHOPLANE logo appears thinner than in Chrome, and the heading "Clothing For Men And Women" has wider letter spacing, so it is slightly longer
- **Screenshots:** `screenshots/issue5_chrome.png`, `screenshots/issue5_firefox.png`
- **Recommended fix:** Define a complete font stack with fallback fonts (for example `font-family: "Lato", Arial, sans-serif;`), set `font-weight`, `letter-spacing` and `font-size` explicitly, and make sure the web fonts are loaded the same way for all browsers..

## Recommended Fixes (General)

| Problem | Recommendation |
|---|---|
| Links lead to "Page not found" | Check every `href` path and make sure the target page or route exists |
| Website hosted on Netlify with client-side routing | Add a `_redirects` file with `/* /index.html 200` so page routes load correctly |
| Banner not clickable | Wrap the banner in a working `<a>` link |
| Broken links not noticed before release | Test all links before deployment using a link checker |

## Conclusion

The website was tested on multiple browsers and screen sizes. The main problem found was multiple broken navigation and footer links that lead to "Page not found" or do not open at all. Fixing the link paths would resolve most of the issues.

## What I Learned

- How to test a web page across browsers and screen sizes
- How to identify and document broken links and layout issues
- How to write a defect report with steps, severity, and recommended fixes
- Why cross-browser and responsive testing matter before release
