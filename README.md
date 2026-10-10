# 💪 B14-A7-Bazar Dor

---

## 📅 Deadline For 60 marks: 10 October | ⏱️11:59PM
## 📅 Deadline For 50 marks: 11 October | ⏱️11:59PM
## 📅 Deadline for 30 marks: Any time after 11 October 2026

---
# API's
## Main_API_URL: https://openapi.programming-hero.com/api/bazardor
## BASE_URL_1: https://api.api-store.workers.dev/api/bazardor
## BASE_URL_2: https://api.abcz.workers.dev/api/bazardor (alternative)

Endpoints:  
**All Products:**
```
/products
```

**Filter:**
```
/products?category=chal
```    
**Single Product:**
```
/products/1
```

**Categories:**
```
/categories
```    

**Single Category:**
```
/categories/chal
```

---

## 🐣 Basic Requirements (Must Do for Everyone)
- Your app must work on all screen sizes — mobile, tablet, and desktop
- Make at least 8 Git commits with clear, meaningful messages
- Your app must run without any errors after deployment
- Add a nice README.md file with your project name, description, technologies used, and features(minimum 5)

---

# 🔧 Main Requirements — 50 Marks


### 1. 🔝 Navbar

- Design the Navbar exactly like the Figma.
- Put your logo on the left side: `🛒 বাজার দর` + Bangla date underneath.
- Put your navigation links in a second row / middle — category links.
- The active category link should look different (highlighted).
- **Right-side auth buttons**: `সাইন ইন` + `সাইন আপ`. When logged in, show profile / sign-out instead.
- **Price ticker (marquee) below navbar**: infinite scrolling strip showing `emoji + name + দাম টাকা/একক + ▲/▼ %` 

---

### 2. 🅱️ Hero / Banner

- Eyebrow / small text
- Main heading
- Subtitle
- A primary **CTA button**
  - It scrolls the user down to the `#সব-পণ্য` section on the same page (an anchor link, not a route change).
- A **banner/hero image** on the right side..


---

### 3. ⚖️ The Product Sections (Home Page)

- **Section A — “আজ দাম বেড়েছে ▲”**: Top 6 risers. 
- **Section B — “আজ দাম কমেছে ▼”**: Top 6 fallers. 
- **Section C — “সব পণ্য” with subtitle** .
- Display all products from JSON data as cards in a **responsive grid** (3-4 cols on large screens, collapses on mobile). Must be responsive.
- Each card must show:
  - 📷 Emoji / illustration (e.g. `🍚 🫘 🫙 🥔 🧅 🌶️ 🐟 🍗 🥚 🫚 🧄`)
  - 📛 Product name (e.g. “স্বর্ণমাছি চাল”, “মিনিকেট চাল”, “ইলিশ মাছ”, “পেঁয়াজ”)
  - 🖇️ Unit line (e.g. `প্রতি কেজি`, `প্রতি লিটার`, `প্রতি ডজন`, `প্রতি পিস`)
  - 🔴 Price row: label `আজকের দাম` + value (e.g. `১৪৮ টাকা`, `১,৮৫০ টাকা` — Bengali digits) + change badge `▲ ২.১% / ▼ ২.৯% / —০.০%` (green up, red down, gray flat)
- 🧭 Clicking a card navigates the user to that product’s **Detail Page**.

---

### 4. Product Details Page — Layout (`/product/[slug]`)

**Protected route — requires login.**

**Top — Summary:**
- Emoji + Title
- Subtitle/description (market summary line)
- Category tags (e.g. `সবজি`, `চাল`)
- Unit (`প্রতি কেজি / লিটার / ডজন / পিস`)


**Price - Summary** 
- Minimum Price
- Maximum Price 
- Average Price 


**বাজারভিত্তিক আজকের দাম** 
- Show all the data like figma based on different Bazar. You can do this section Design like figma or as you want. 


### 5. Category Page
- Title + icon 
- **Sort control**: `সাজান: ডিফল্ট | দাম: কম থেকে বেশি | দাম: বেশি থেকে কম` (see C1).
- **Loading state**: show skeleton / “Loading…” while fetching before the list renders.
- **Product cards list**: same card design as Home (thumbnail emoji, title e.g. “আলু”, “পেঁয়াজ”, “ঢেঁড়স”, unit e.g. “প্রতি কেজি”, price + change badge).
- **Empty state** (when category has no items / invalid slug): 404-style message + CTA button **“হোম পেজে ফিরে যান”** (links back to `/`).


### 6. Authentication (`/signin`, `/signup`)

- **Sign In**: User Login: The user will  show  a Login page with a form , so that the user can Log in this application. 
    - Show a Title for Login.  & Form with following fields ( Email , Password , Login button ) 
    - If the user Login successfully then navigate him to his Home page. If not, show him an error with toast / error message anywhere in the form.

    - There will be some other options like:
        - Show the user a Link for Register  so that he can go to the register page. 
        - Show users a Social Login Button ( Google/GitHub/any other social login ) . on Clicking it user authenticate with Google Navigate him to  his Home page.
- **Sign Up**: User Registration: Create a register page with a form , so that the user can register himself in this application. 
    - Show a Title for registration and a Form with following fields( Name , Email, Password & Register Button ) 
    - If the user Register successfully then navigate him to his login page.
    - If not, show him an error with toast / error message anywhere in the form.


    - There will be some other options like 
        - Show the user a Link for Login so that he can go to the Login page. 
        - Show users a Social Login Button ( Google/GitHub/any other social login ) . on Clicking it user authenticate with Google Navigate the user to the Home page.

- Use **BetterAuth** (email/password + Google + GitHub), toast on success/error, skeleton loaders.
- Show relevant **toast notification** on login / signup / logout / validation error.
-  💡Don’t implement email verification or forget password method as it will inconvenience the examiner. If you want, you can add these after receiving the assignment result.

--- 

### 7. Footer
- Match the Figma.
- **Left**: `বাজার দর — প্রয়োজনীয় পণ্যের দাম এক নজরে।`
- **Right**: *“সকল দাম সম্ভাব্য; বাজার অবস্থার ওপর নির্ভর করে পরিবর্তিত হয়।”*

### 8. Responsive Design
- The entire website must work correctly on mobile, tablet, and desktop screen sizes (grid collapses correctly, navbar + ticker stays usable, hero stacks, `btn-sm sm:btn-md`, `max-w-6xl` container, etc.).

---

#	Requirement
- Add a 404 Page for any unknown/invalid route (e.g. `/category/invalid`, `/product/unknown` → friendly  404 + “হোম পেজে ফিরে যান”)
- Show a loading animation ( `skeleton`) while the product data is being fetched on the Home / Category page
- Show a relevant toast notification for auth + protected-route redirects (use `react-hot-toast` / `data-rht-toaster`).
- Make sure reloading any page after deployment does not cause an error (dynamic `[slug]` routes must work on Vercel — no hard 404 on refresh)

---

# Challenge Requirements — 10 Marks

### C1. - **Sort dropdown**:
“সাজান” → options `ডিফল্ট`, `দাম: কম থেকে বেশি`, `দাম: বেশি থেকে কম` (default `ডিফল্ট`, with chevron icon). Must handle Bengali numerals correctly (sort by numeric value, not string).

### C2. GitHub README
- Add a well-designed `README.md` that includes:
  - Project name (বাজার দর / BazarDor)
  - Short description
  - Technologies used
  - 5 key features of the project

### C3. - Update Information Feature
- In My Profile route there will be an update button. On clicking it,  Take user to another route 
- Show user a form with an input field (  Name ), An Update Information button.

Follow this documentation: https://better-auth.com/docs/concepts/users-accounts#update-user 


---

### 🛠️ Technologies to Use
Technology	Purpose
- Next.js ->	Build the UI
- App router(Next.js) +	Handle page navigation
- Tailwind CSS + Any component library	Styling and responsiveness(DaisyUI, Hero UI)
- TypeScript / JavaScript
- BetterAuth

### 🚀 Deployment
Deploy your project on Vercel, Netlify, Cloudflare Pages, or anywhere else before submitting.

## 📬 Submission
Fill in both links before submitting:

- Live Link:
- GitHub Repository Link:


### Notes : You can use Bengali or English language for core website information or any kind of text.
