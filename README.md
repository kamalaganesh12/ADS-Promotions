<!DOCTYPE html>
<html lang="en">
<head>
Declares the document as HTML5 and sets the language to English.

📱 2. Meta Tags & SEO

html

<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
Sets the character encoding and makes the site mobile-friendly.

html

<title>AppAd Network – Promote & Monetize Your Apps</title>
Page title (shows in browser tabs and search results).

html

<meta name="description" ...>
<meta name="keywords" ...>
<meta property="og:title" ...>
<meta property="og:description" ...>
<meta property="og:image" ...>
<meta property="og:url" ...>
These SEO and social media tags help when the link is shared or indexed by search engines (Open Graph tags for Facebook, LinkedIn, etc.).

🎨 3. CSS Styling

css

:root {
  --primary: #10B981; /* Green */
  --dark: #0F172A;    /* Dark background */
  --light: #F9FAFB;   /* Light background */
  --text: #1F2937;    /* Main text color */
}
Defines color variables used throughout the page.

css


header, section, footer {
  padding, colors, fonts, responsiveness
}
The CSS styles the layout: headers, buttons, images, grids, media queries for mobile, etc.

Features like hover effects and responsive flexbox layout are used.

🔥 4. Firebase Integration (JavaScript Module)

html

<script type="module">
  import { initializeApp } from "firebase-app.js";
  import { getFirestore, collection, addDoc, serverTimestamp } from "firebase-firestore.js";
This loads Firebase SDK v9 (modular) and imports Firestore functions.

js

  const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    ...
  };
  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);
Initializes Firebase with your project credentials (replace "YOUR_API_KEY" etc.).

js

  window.sendSignup = async function(e) {
    e.preventDefault();
    const email = document.getElementById('user-email').value;

    if (!email) {
      alert('Please enter your email');
      return;
    }

    try {
      await addDoc(collection(db, 'signups'), {
        email,
        createdAt: serverTimestamp()
      });
      alert('Thank you! We will be in touch.');
      document.getElementById('user-email').value = '';
    } catch(err) {
      console.error('Error writing to Firestore', err);
      alert('Oops! Something went wrong.');
    }
  };
Handles form submission:

Gets the email input

Adds it to Firestore (signups collection)

Shows a confirmation message

Handles errors gracefully

🖼️ 5. Main Website Content
  
header
html


<h1>Promote Your App. Monetize Everywhere.</h1>
<p>Target the right users...</p>
<a href="...">Get Started Free</a>
Hero section with a heading, description, and CTA button.

section – Features
html

<div class="features">
  <div class="feature">...</div>
</div>
Three core features: Promotion, Monetization, Analytics.

section.apps-showcase
html

<h2>Apps We Power</h2>
<div class="apps-grid">
  <img src="..." alt="App name">
</div>
Shows app logos (demo images used via placeholder).

section – Testimonials
html

<blockquote>“Our app installs tripled...”</blockquote>
A quote from a fictional customer for social proof.

section.cta – Signup Form
html


<form onsubmit="sendSignup(event)">
  <input id="user-email" ...>
  <button>Join Beta</button>
</form>
A simple form to collect user emails using Firebase.

Includes link to sign up page as an alternative.

🧾 6. Footer
  
html

<footer>
  <p>&copy; 2025 AppAd Network. All rights reserved.</p>
</footer>
Copyright.
