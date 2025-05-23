# CloudHost Landing Page Maintenance Guide

This guide will help you maintain and customize the CloudHost landing page. Whether you're new to web development or just getting started, follow these detailed instructions to make updates while preserving the design integrity.

## Table of Contents
- [Updating Text and Styling](#updating-text-and-styling)
- [Managing Links](#managing-links)
- [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
- [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains your logo and navigation menu:

```html
<header class="fixed w-full bg-white/95 backdrop-blur-sm z-50 border-b border-gray-100">
    <nav class="container mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
        <a href="#" class="text-2xl font-bold text-blue-600">CloudHost</a>
        <!-- Navigation items -->
    </nav>
</header>
```

To modify:
1. Change logo text: Replace "CloudHost" with your brand name
2. Adjust logo color: Modify `text-blue-600` to other colors (e.g., `text-red-600`)
3. Update navigation items in the `<div class="hidden md:flex space-x-8">` section

### Hero Section
The main headline and introduction:

```html
<h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold text-gray-900 leading-tight mb-6">
    Best Cloud Hosting for Non-Technical Users & Agencies 2025
</h1>
```

To modify:
1. Update headline text between the `<h1>` tags
2. Adjust text size using Tailwind classes:
   - `text-4xl`: Mobile size
   - `sm:text-5xl`: Tablet size
   - `lg:text-6xl`: Desktop size

### Features Section
Each feature card follows this structure:

```html
<div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-shadow duration-300">
    <!-- Icon container -->
    <div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center mb-6">
        <!-- SVG icon -->
    </div>
    <h3 class="text-xl font-semibold mb-4">Feature Title</h3>
    <p class="text-gray-600">Feature description</p>
</div>
```

To modify:
1. Update feature title in the `<h3>` tag
2. Change description in the `<p>` tag
3. Modify icon by replacing SVG code
4. Adjust colors using Tailwind classes:
   - Background: `bg-blue-100`
   - Text: `text-gray-600`

## Managing Links

### Navigation Menu Links
Current navigation links:

```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Features</a>
    <a href="#benefits" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Benefits</a>
    <a href="#contact" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Contact</a>
</div>
```

To update links:
1. Locate the `href` attribute
2. For internal links (same page):
   - Use `#section-id` format
   - Ensure corresponding section has matching ID
3. For external links:
   - Replace with full URL (e.g., `href="https://example.com"`)

### Footer Links
Current placeholder links in footer:

```html
<ul class="space-y-2">
    <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">About Us</a></li>
    <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Blog</a></li>
    <li><a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">Careers</a></li>
</ul>
```

To update:
1. Replace `href="#"` with actual URLs
2. Maintain consistent styling classes
3. Test all links after updating

## Adding Privacy and Terms Pages

### Step 1: Create New Pages
Create two new files:
- `privacy.html`
- `terms.html`

### Step 2: Update Footer Links
Locate the legal section in the footer:

```html
<div>
    <h4 class="text-lg font-semibold mb-4">Legal</h4>
    <ul class="space-y-2">
        <li><a href="privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

Replace the `href="#"` with:
- `href="privacy.html"` for Privacy Policy
- `href="terms.html"` for Terms of Service

## Troubleshooting

### Common Issues and Solutions

1. **Broken Links**
   - Check for typos in `href` attributes
   - Verify file names match exactly
   - Ensure files are in the correct directory

2. **Responsive Design Issues**
   - Keep Tailwind's responsive prefixes:
     - `sm:` for tablet (640px+)
     - `md:` for medium screens (768px+)
     - `lg:` for large screens (1024px+)

3. **Animation Problems**
   - Check AOS attributes:
```html
data-aos="fade-up"
data-aos-delay="100"
```
   - Verify AOS script is loaded at bottom of page
   - Ensure AOS initialization is present:
```html
<script>
    AOS.init({
        duration: 1000,
        once: true,
    });
</script>
```

### Need Help?
If you encounter issues:
1. Check browser console for errors
2. Verify all files are in the correct location
3. Test on multiple browsers
4. Ensure all required scripts are loaded

Remember to always backup your files before making changes!