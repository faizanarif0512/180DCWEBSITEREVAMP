# 180DC IIT KGP Website - Testimonials Process

This guide documents how to add, edit, or remove client and partner testimonials on the **Testimonials** page of the website.

---

## Page Structure
The Testimonials page is located inside the single-page HTML template (`index.html`) under the container:
```html
<div class="page" id="page-testimonials">
```

All testimonial cards are wrapped inside the grid container:
```html
<div class="test-grid">
  <!-- Testimonial cards go here -->
</div>
```

---

## Method 1: Ask the AI Assistant (Recommended)
You can simply copy-paste the feedback you receive from your clients into the chat, and the AI assistant will format and add it for you. 

To help the assistant apply it correctly, please provide it in the following format:
```text
Quote: "The testimonial text."
Name: First Last name
Designation: Role, Organisation Name
Initial: The first letter of their first name (used for the initials avatar bubble)
```

### Example:
> **Quote:** "Their operational playbook streamlined our supply chain, increasing delivery efficiency by 40%."  
> **Name:** Rajesh Kumar  
> **Designation:** Head of Logistics, Goonj NGO  
> **Initial:** R  

---

## Method 2: Manual Update (Direct HTML Editing)
If you are editing `index.html` manually, follow these steps:

1. Open `index.html` in your text editor.
2. Search for `id="page-testimonials"` or `<div class="test-grid">`.
3. Copy the template snippet below.
4. Paste it inside `<div class="test-grid">` either at the top (to show first) or at the bottom.
5. Replace the placeholder content with your client details.

### Testimonial HTML Template
```html
<div class="test-card reveal">
  <div class="test-quote">&ldquo;Your testimonial quote text goes here.&rdquo;</div>
  <div class="test-author">
    <div class="test-av">I</div> <!-- The letter for the circle avatar bubble -->
    <div>
      <h4>Client Full Name</h4>
      <p>Role/Title, Client Organisation Name</p>
    </div>
  </div>
</div>
```

### Delay Classes (Optional)
If you add multiple testimonials, you can stagger their fade-in animations on load by adding delay helper classes (`d1`, `d2`) to the `test-card` class:
* Card 1: `class="test-card reveal"` (fades in instantly)
* Card 2: `class="test-card reveal d1"` (fades in with 150ms delay)
* Card 3: `class="test-card reveal d2"` (fades in with 300ms delay)

---

## Styling Notes
* **Color System**: The circular avatar bubble is styled using `var(--gd)` (dark background) and `var(--gl)` (official light Atlantis green outlines), ensuring it automatically matches the global brand theme.
* **Hover Interaction**: Cards expand automatically and expand the custom cursor size when hovered.
* **Responsive Layout**: The grid automatically shifts from a 3-column layout on desktop to a 1-column layout on mobile devices.
