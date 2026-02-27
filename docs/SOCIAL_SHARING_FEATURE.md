# Social Sharing Feature Implementation

## Overview
Social sharing buttons have been successfully integrated into the Mergington High School Activities application, allowing users to easily share activities with their friends on various social media platforms.

## Changes Made

### 1. HTML Changes (`src/static/index.html`)
- Added comprehensive meta tags for social media preview optimization:
  - Open Graph tags for Facebook
  - Twitter Card tags for Twitter/X
  - Description meta tag for search engines

### 2. JavaScript Changes (`src/static/app.js`)
- **New Function**: `shareActivity(platform, activityName, activityDescription, activitySchedule)`
  - Handles sharing on Facebook, Twitter, LinkedIn, and Email
  - Opens platform-specific share dialogs in new windows
  - For email, opens default mail client with pre-filled content
  
- **Updated Function**: `renderActivityCard()`
  - Added social sharing button HTML to each activity card
  - Added event listeners for share button clicks
  - Share buttons placed between activity details and participant list

### 3. CSS Changes (`src/static/styles.css`)
- **New Styles**: Share button container and individual button styles
  - Clean, compact design with icon-based buttons
  - Platform-specific hover colors (Facebook blue, Twitter blue, LinkedIn blue, Email orange)
  - Smooth hover animations with lift effect
  - Responsive circular button design (28px diameter)

## Features

### Supported Platforms
1. **Facebook** 📘
   - Opens Facebook's share dialog
   - Shares current page URL
   
2. **Twitter/X** 🐦
   - Creates pre-filled tweet
   - Includes activity name, description, and hashtags (#MergingtonHigh, #ExtracurricularActivities)
   
3. **LinkedIn** 💼
   - Opens LinkedIn share dialog
   - Shares activity page for professional networking
   
4. **Email** 📧
   - Opens default email client
   - Pre-filled subject: "Check out {Activity Name} at Mergington High School"
   - Pre-filled body with activity details and schedule

### User Interface
- Share buttons appear on every activity card
- Clean, minimal design with icon-based buttons
- "Share:" label for clarity
- Hover effects with platform-specific brand colors
- Tooltips showing platform names
- Positioned between capacity indicator and participant list

### Social Media Preview
When shared on social platforms, the page displays:
- **Title**: "Mergington High School - Extracurricular Activities"
- **Description**: "Explore and sign up for extracurricular activities at Mergington High School. From sports to arts, academic clubs to community service, find your passion!"
- **Preview image**: Placeholder for school logo (URL: https://mergingtonhigh.edu/preview.jpg)

## Implementation Details

### Share Function Logic
```javascript
function shareActivity(platform, activityName, activityDescription, activitySchedule) {
  const url = window.location.href;
  const text = `Check out ${activityName} at Mergington High School! ${activityDescription}`;
  const hashtags = "MergingtonHigh,ExtracurricularActivities";
  
  // Platform-specific URL construction
  // Opens in popup window (600x400) for social platforms
  // Opens mail client for email
}
```

### Button Layout
```html
<div class="share-buttons">
  <span class="share-label">Share:</span>
  <button class="share-button share-facebook">📘</button>
  <button class="share-button share-twitter">🐦</button>
  <button class="share-button share-linkedin">💼</button>
  <button class="share-button share-email">📧</button>
</div>
```

## Benefits
1. **Easy Sharing**: One-click sharing to major social platforms
2. **Increased Visibility**: Students can easily inform friends about activities
3. **Professional Integration**: LinkedIn support for school-to-career initiatives
4. **Email Accessibility**: Email option for parents and guardians
5. **SEO Friendly**: Meta tags improve how links appear when shared
6. **Minimal Design**: Doesn't clutter the existing clean interface

## Technical Notes
- No external dependencies required (uses native Web Share APIs and standard URLs)
- Works across all modern browsers
- Popup blockers may require user permission for share dialogs
- Falls back gracefully if platform is unavailable

## Testing
To test the feature:
1. Navigate to any activity card
2. Click on any share button
3. Verify the appropriate share dialog opens with correct information
4. Test on different platforms to ensure compatibility

## Future Enhancements (Optional)
- Add native Web Share API for mobile devices
- Include share count tracking
- Add more platforms (WhatsApp, Telegram, etc.)
- Implement custom share images per activity
