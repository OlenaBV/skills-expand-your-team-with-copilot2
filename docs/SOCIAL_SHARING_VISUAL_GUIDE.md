# Social Sharing Feature - Visual Guide

## What Users See

Each activity card now includes social sharing buttons that allow users to easily share activities with their friends and family.

### Activity Card Layout

```
╔═══════════════════════════════════════════════════════════╗
║  ┌────────────────────────────────────────┐   [SPORTS]   ║
║  │ Soccer Team                             │              ║
║  └────────────────────────────────────────┘              ║
║                                                            ║
║  Join the school soccer team and compete in matches       ║
║                                                            ║
║  Schedule: Tuesdays and Thursdays, 3:30 PM - 5:30 PM     ║
║                                                            ║
║  ▓▓░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░  18%            ║
║  4 enrolled                         18 spots left         ║
║                                                            ║
║  ───────────────────────────────────────────────────      ║
║  Share: 📘  🐦  💼  📧                                    ║
║  ───────────────────────────────────────────────────      ║
║                                                            ║
║  Current Participants:                                    ║
║  • liam@mergington.edu                                    ║
║  • noah@mergington.edu                                    ║
║                                                            ║
║  [ Register Student ]                                     ║
╚═══════════════════════════════════════════════════════════╝
```

### Share Buttons

The share buttons are displayed as circular icons with clean, minimal design:

- **📘 Facebook** - Blue background on hover (#1877f2)
- **🐦 Twitter** - Light blue background on hover (#1da1f2)
- **💼 LinkedIn** - Dark blue background on hover (#0077b5)
- **📧 Email** - Orange background on hover (#ff6f00)

### User Interaction

1. **Hover Effect**: When users hover over a button:
   - Button lifts slightly (translateY(-2px))
   - Background changes to platform's brand color
   - Icon scales up slightly (1.1x)
   - Subtle shadow appears below

2. **Click Action**:
   - **Facebook**: Opens Facebook share dialog in popup window (600x400px)
   - **Twitter**: Opens Twitter/X with pre-filled tweet including activity name, description, and hashtags
   - **LinkedIn**: Opens LinkedIn share dialog
   - **Email**: Opens user's default email client with pre-filled subject and body

### Example Share Content

When sharing "Soccer Team" on Twitter:
```
Check out Soccer Team at Mergington High School! 
Join the school soccer team and compete in matches

https://mergingtonhigh.edu/

#MergingtonHigh #ExtracurricularActivities
```

When sharing via Email:
```
Subject: Check out Soccer Team at Mergington High School

Body:
Check out Soccer Team at Mergington High School! 
Join the school soccer team and compete in matches

Schedule: Tuesdays and Thursdays, 3:30 PM - 5:30 PM

Learn more: https://mergingtonhigh.edu/
```

## Accessibility Features

### Reduced Motion Support
Users who have enabled "prefers-reduced-motion" in their system settings will see:
- No button lift animation
- No icon scaling animation
- Colors still change on hover for feedback

### Tooltips
Each button has a tooltip that appears on hover showing the platform name:
- "Share on Facebook"
- "Share on Twitter"
- "Share on LinkedIn"
- "Share via Email"

### Keyboard Accessibility
All buttons are keyboard accessible:
- Tab to navigate between buttons
- Enter or Space to activate

## Responsive Design

The share buttons adapt to different screen sizes:
- **Desktop**: All 4 buttons displayed in a row
- **Tablet**: All 4 buttons with slightly reduced spacing
- **Mobile**: All 4 buttons wrap appropriately

## Browser Compatibility

The feature works in all modern browsers:
- Chrome/Edge: Full support
- Firefox: Full support
- Safari: Full support
- Mobile browsers: Full support

### Popup Blocker Handling
If a user has popup blockers enabled, the browser will:
1. Show a notification that the popup was blocked
2. Allow the user to allow popups for the site
3. Email option always works as it uses mailto: links

## Security Features

1. **Description Sanitization**: 
   - Activity descriptions are truncated to 200 characters
   - HTML entities are encoded (&, <, >, ", ')
   - Prevents XSS attacks through share URLs

2. **URL Encoding**:
   - All parameters are properly encoded
   - Hashtags are URL-encoded for safety
   - Prevents URL injection attacks

3. **No External Dependencies**:
   - Uses native browser APIs
   - No third-party scripts loaded
   - Minimal security surface area

## SEO Benefits

Meta tags added to the page improve how links appear when shared:

### Open Graph (Facebook, LinkedIn)
```html
<meta property="og:type" content="website" />
<meta property="og:title" content="Mergington High School - Extracurricular Activities" />
<meta property="og:description" content="Explore and sign up for extracurricular activities..." />
```

### Twitter Cards
```html
<meta property="twitter:card" content="summary_large_image" />
<meta property="twitter:title" content="Mergington High School - Extracurricular Activities" />
<meta property="twitter:description" content="Explore and sign up for extracurricular activities..." />
```

### Result
When someone shares the page, social media platforms display:
- **Title**: "Mergington High School - Extracurricular Activities"
- **Description**: "Explore and sign up for extracurricular activities at Mergington High School. From sports to arts, academic clubs to community service, find your passion!"
- Clean, professional appearance

## Usage Statistics (Potential)

After deployment, you could track:
- Which platform is most popular for sharing
- Which activities are shared most often
- Share conversion rates (views from shared links)

## Future Enhancements

Possible improvements for future iterations:
1. Native Web Share API for mobile devices
2. WhatsApp sharing option
3. Copy-to-clipboard functionality
4. Share count display
5. Custom preview images per activity
6. Share tracking analytics
