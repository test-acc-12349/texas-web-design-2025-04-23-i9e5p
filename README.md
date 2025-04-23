# Texas Web Design Landing Page - Maintenance Guide

This guide will help you maintain and customize the Texas Web Design landing page. It's written for beginners and provides step-by-step instructions for common updates.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the logo and navigation menu. To modify:

1. **Logo Text (TWD)**
```html
<a href="/" class="text-2xl font-bold text-blue-600">TWD</a>
```
- Replace "TWD" with your desired text
- Adjust size using `text-2xl` (options: text-sm, text-base, text-lg, text-2xl, text-3xl)
- Change color using `text-blue-600` (options: text-red-600, text-green-600, etc.)

### Hero Section
Located at the top of the page:
```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold text-gray-900 mb-8 tracking-tight">Texas Web Design</h1>
<p class="text-xl md:text-2xl text-gray-600 mb-12">Professional web design solutions...</p>
```
- Update heading text between `<h1>` tags
- Modify subheading text in the `<p>` tag
- Responsive classes explained:
  - `md:text-5xl`: Applies at medium screens
  - `lg:text-6xl`: Applies at large screens

### Features Section
Each feature card follows this structure:
```html
<div class="bg-white rounded-xl shadow-lg p-8 hover:shadow-xl transition-shadow duration-300">
    <div class="text-blue-600 mb-4">
        <i class="fas fa-server text-4xl"></i>
    </div>
    <h3 class="text-xl font-semibold mb-4">Free Hosting</h3>
    <p class="text-gray-600">Reliable and secure hosting...</p>
</div>
```
To modify:
1. Change icon: Update `fa-server` to any [Font Awesome](https://fontawesome.com/icons) icon
2. Update heading: Modify text in `<h3>` tags
3. Update description: Change text in `<p>` tags

## Fixing Broken Links

### Navigation Menu Links
Current navigation links:
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Features</a>
    <a href="#benefits" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Benefits</a>
    <a href="#faq" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">FAQ</a>
    <a href="#contact" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Contact</a>
</div>
```

To update:
1. Internal links (same page):
   - Keep the `#` symbol
   - Match the `id` of the section you're linking to
   - Example: `href="#features"` links to `<section id="features">`

2. External links:
   - Replace placeholder URLs:
   ```html
   <!-- From -->
   <a href="https://twd.com" class="inline-block bg-blue-600...">
   <!-- To -->
   <a href="https://your-actual-domain.com" class="inline-block bg-blue-600...">
   ```

## Linking Privacy and Terms Pages

### Footer Links
Current privacy and terms links:
```html
<div>
    <h3 class="text-xl font-semibold mb-4">Legal</h3>
    <ul class="space-y-2">
        <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

To add proper links:
1. Create privacy.html and terms.html in your root directory
2. Update the href attributes:
```html
<li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
```

## Troubleshooting

### Common Issues

1. **Broken Internal Links**
   - Ensure section IDs match exactly with href attributes
   - Check for typos in both the link and section ID
   ```html
   <!-- These must match exactly -->
   <a href="#features">Features</a>
   <section id="features">
   ```

2. **Responsive Design Issues**
   - Classes starting with `md:` apply to medium screens and up
   - Classes starting with `lg:` apply to large screens and up
   - Example: `class="text-xl md:text-2xl lg:text-3xl"`

3. **Icon Not Showing**
   - Verify Font Awesome is properly loaded in the head section
   - Check icon class names against [Font Awesome documentation](https://fontawesome.com/icons)
   - Ensure you're using the correct icon prefix (fas, far, fab)

### Need Help?
If you encounter issues:
1. Check the browser's developer tools (F12) for errors
2. Verify all files are in the correct directory
3. Ensure all closing tags are present
4. Validate your HTML at [W3C Validator](https://validator.w3.org/)

Remember to always test your changes across different screen sizes using browser developer tools before deploying to production.