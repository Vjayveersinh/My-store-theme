# 🛍️ Shopify Gift Guide – Pixel Perfect Figma Implementation

A custom Shopify page built from scratch as part of a technical hiring assessment.
The goal was to translate a Figma design into a fully functional, production-quality Shopify experience using best practices.

---

## 🚀 Live Demo

👉https://9b007c-4.myshopify.com/pages/gift-guide?_pos=1&_sid=04b295f51&_ss=r

---

## 🎯 Project Objective

Recreate a Figma design as a Shopify page with:

* Pixel-perfect UI implementation
* Two custom sections (Banner + Product Grid)
* Dynamic product-driven popup
* Fully functional Add to Cart
* No use of pre-built Dawn sections
* Vanilla JavaScript only

---

## 🧱 Implementation Overview

### 🔹 1. Custom Gift Banner (Built from Scratch)

* Fully customizable via Shopify theme editor
* Editable fields:

  * Heading
  * Description
  * CTA button
* Includes:

  * Hover animation
  * Responsive layout
  * Pixel-aligned spacing from Figma

---

### 🔹 2. Custom Product Grid + Popup

* Displays **6 products (configurable via customizer)**
* Each product opens a **dynamic modal popup**
* No hardcoded data — everything is driven by Shopify product data

---

## 🧠 Core Engineering Highlights

### ✅ Dynamic Product Rendering

Instead of embedding product JSON in the DOM (which can break easily), the popup loads product data using:

```js
/products/{handle}.js
```

✔ Prevents data corruption
✔ Ensures real-time product data
✔ Matches Shopify best practices

---

### ✅ Variant System (Fully Dynamic)

Variants are generated from:

```js
product.variants
```

Supports:

* Color (rendered as selectable swatches)
* Size (rendered as dropdown)

Variant selection is mapped dynamically using:

```js
variant.options[index]
```

✔ No hardcoded variant logic
✔ Works for any product structure

---

### ✅ Add to Cart (Ajax API)

Uses Shopify’s Ajax API:

```js
POST /cart/add.js
```

Features:

* No page reload
* Real-time feedback
* Error handling

---

### 🎁 Advanced Logic (Bonus Requirement)

If user selects:

* **Color = Black**
* **Size = Medium**

👉 Automatically adds:
**Soft Winter Jacket** to cart

Implementation:

* Conditional logic in JS
* Fetch bonus product dynamically
* Add both items in a single cart request

---

## ⚙️ Tech Stack

* Shopify Liquid
* Vanilla JavaScript (no jQuery)
* CSS (custom, no framework)
* Shopify Ajax API

---

## 📁 Project Structure

```
sections/
  ├── custom-gift-banner.liquid
  ├── custom-product-grid-popup.liquid

templates/
  └── page.gift-guide.json
```

## 📱 Responsive Design

* Desktop: 3-column grid
* Mobile: 2-column grid
* Modal adapts for smaller screens

---

## 🧠 Key Engineering Decisions

### 1. Avoided inline product JSON

* Used product handle + fetch instead
* Improves reliability and scalability

### 2. Decoupled UI from data

* UI components are reusable
* Product data is injected dynamically

### 3. Built sections from scratch

* No reliance on Dawn defaults
* Fully custom architecture

---

## 🔍 What I Would Improve Next

* Add loading skeleton for popup
* Improve accessibility (ARIA roles + focus trap)
* Add unit testing for variant logic
* Optimize image loading (srcset tuning)

---

## 👤 Author

**Jayveersinh Vihol**

* GitHub: https://github.com/Vjayveersinh
* Portfolio: https://dc61g20ci9ox4.cloudfront.net
* LinkedIn: https://linkedin.com/in/jayveersinh-vihol-4855a31b7

---

## ⭐ Final Notes

This implementation focuses on:

* Clean, maintainable code
* Shopify best practices
* Real-world scalability
* Strong separation of concerns

---

> Built with the mindset of production readiness, not just test completion.



