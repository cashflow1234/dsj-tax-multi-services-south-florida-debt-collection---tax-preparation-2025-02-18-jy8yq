# DSJ Tax Landing Page Maintenance Guide

This guide provides detailed instructions for maintaining and customizing the DSJ Tax landing page. Whether you're new to web development or need a quick reference, follow these steps to make common updates safely and effectively.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the company logo and navigation menu. To update:

```html
<!-- Logo Text -->
<div class="text-2xl font-bold bg-gradient-to-r from-blue-500 to-purple-600 bg-clip-text text-transparent">
    DSJ Tax  <!-- Update company name here -->
</div>

<!-- Navigation Menu Items -->
<div class="hidden md:flex space-x-8">
    <a href="#services" class="text-gray-300 hover:text-white transition-colors duration-300">Services</a>
    <!-- Add or modify menu items here -->
</div>
```

**Key Tailwind Classes Explained:**
- `hidden md:flex`: Hides on mobile, shows as flex on medium screens
- `space-x-8`: Adds horizontal spacing between menu items
- `text-gray-300`: Sets text color to light gray

### Hero Section
To update the main headline and subtext:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight mb-8 bg-gradient-to-r from-blue-400 to-purple-500 bg-clip-text text-transparent">
    <!-- Update main headline here -->
</h1>

<p class="text-xl md:text-2xl text-gray-300 mb-12">
    <!-- Update subheading here -->
</p>
```

**Responsive Text Sizes:**
- `text-4xl`: Base size for mobile
- `md:text-5xl`: Medium screens
- `lg:text-6xl`: Large screens

### Features Section
To modify feature cards:

```html
<div class="bg-gray-900 rounded-2xl p-8 hover:transform hover:scale-105 transition-all duration-300">
    <div class="w-16 h-16 bg-gradient-to-r from-blue-500 to-purple-600 rounded-full mb-6">
        <!-- Icon container -->
    </div>
    <h3 class="text-xl font-semibold mb-4">
        <!-- Feature title -->
    </h3>
    <p class="text-gray-400">
        <!-- Feature description -->
    </p>
</div>
```

## Fixing Broken Links

### Current Link Structure
The page contains these types of links:

1. Navigation Menu Links (Internal):
```html
<a href="#services">Services</a>
<a href="#features">Features</a>
<a href="#benefits">Benefits</a>
<a href="#faq">FAQ</a>
```

2. Call-to-Action Links (External):
```html
<a href="https://form.jotform.com/250476421727054">Get Started</a>
```

### Updating Links
To update any link:

1. Locate the `<a>` tag
2. Modify the `href` attribute
3. Update the link text between the opening and closing tags

Example:
```html
<!-- Before -->
<a href="#services">Services</a>

<!-- After -->
<a href="/services.html">Our Services</a>
```

**Important:** For internal page sections, keep the `#` prefix (e.g., `#features`). For external links, use complete URLs starting with `https://`.

## Linking Privacy and Terms Pages

### Adding Policy Links
Locate the footer section and update the legal links:

```html
<div>
    <h4 class="text-lg font-semibold mb-4">Legal</h4>
    <ul class="space-y-2">
        <li><a href="/privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="/terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

### Creating New Policy Pages
1. Create new files: `privacy.html` and `terms.html`
2. Copy the header and footer from `index.html`
3. Add your policy content between them
4. Ensure consistent styling by using the same Tailwind classes

## Troubleshooting

### Common Issues and Solutions

1. **Broken Layout on Mobile**
   - Check for proper responsive classes (`md:`, `lg:` prefixes)
   - Ensure `hidden md:flex` is used for mobile menu

2. **Gradient Text Not Showing**
   - Verify all three classes are present:
     ```html
     bg-gradient-to-r from-blue-400 to-purple-500 bg-clip-text text-transparent
     ```

3. **Links Not Working**
   - For section links (#services, #features), ensure IDs exist in the HTML
   - Check for typos in href attributes
   - Verify external URLs start with `https://`

### Need Help?
If you encounter issues:
1. Check the browser's developer tools (F12) for errors
2. Verify all Tailwind CSS classes are spelled correctly
3. Ensure the Tailwind CDN link is working in the header
4. Test responsive layouts using browser developer tools

Remember to always test changes across different devices and browsers before deploying to production.