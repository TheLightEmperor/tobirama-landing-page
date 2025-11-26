# Admin Panel Guide - Tobirama Landing Page

## Overview
The admin panel allows you to edit all content on the Tobirama Senju landing page without touching the HTML directly. All changes are saved to your browser's localStorage and persist across page reloads.

## How to Access the Admin Panel

1. **Open the landing page** in your browser
2. **Scroll to the bottom** and click the **⚙️ Admin** button
3. A login form will appear

## Admin Login

**Default Password:** `admin123`

To change the password:
1. Open `tobirama_landing_page.html` in a text editor
2. Find the line: `const ADMIN_PASSWORD = "admin123";`
3. Replace `"admin123"` with your desired password
4. Save the file

## Editable Sections

### About Tab
- Edit the main description of Tobirama Senju

### Abilities Tab
- Edit 4 ability descriptions:
  - Ability 1
  - Ability 2
  - Ability 3
  - Ability 4

### Gallery Tab
- Edit the URLs of 3 gallery images
- Use full URLs like: `https://example.com/image.jpg` or relative paths like `images/photo.jpg`

### Videos Tab
- Edit the file paths for 2 videos
- Default format: `videos/video1.mp4`, `videos/video2.mp4`
- Place your video files in the `videos/` folder

### Projects Tab
- Edit 3 projects with:
  - **Title**: Project name
  - **Description**: What the project is about
  - **Link**: Project URL (e.g., `https://example.com/project`)
  - **GitHub**: GitHub repository URL (e.g., `https://github.com/user/repo`)

### Contributions Tab
- Edit the contributions/achievements description

## Saving Changes

1. Edit any field in the admin panel
2. Click **"Save Changes"** button
3. You'll see a confirmation message
4. Changes appear immediately on the page

## Debugging / Console Output

When you save changes, detailed logs are written to the browser console. To view them:

1. Press **F12** to open Developer Tools
2. Go to the **Console** tab
3. Look for messages like:
   - `=== SAVING ADMIN CHANGES ===` (when save starts)
   - `✓ [Section] updated` (when items are updated successfully)
   - `✗ [Section] not found` (if there's an issue)
   - `=== SAVE COMPLETE ===` (when save finishes)

## Data Persistence

- All changes are automatically saved to browser localStorage
- Data persists even if you close and reopen the browser
- localStorage is per-domain, so changes won't sync across different devices/browsers
- To reset to defaults, clear your browser's localStorage for this site

## Troubleshooting

### Changes don't appear on the page
- Check the browser console (F12) for error messages
- Verify you clicked "Save Changes"
- Try refreshing the page and logging in again

### Admin button doesn't work
- Make sure JavaScript is enabled in your browser
- Check the console for any JavaScript errors

### Form fields are empty when I login
- The page content may be loading. Wait a moment and try again
- Check the console to see if DOM elements were found

### Password doesn't work
- Default password is: `admin123` (case-sensitive)
- If you changed it, make sure you remember the exact password

## File Structure

```
landing page anime/
├── tobirama_landing_page.html    # Main file (contains everything)
├── images/                        # Folder for gallery images
│   ├── 453dec815224a5fda2d5c1d382a83850.jpg
│   ├── 9034c154cbf825ac21afac44b87e0753.jpg
│   └── Tobirama main.jpg
├── videos/                        # Folder for videos
│   ├── video1.mp4
│   └── video2.mp4
└── ADMIN_PANEL_GUIDE.md          # This file
```

## Local Testing

To test locally:

```bash
cd "path/to/landing page anime"
npx serve -p 8000
```

Then open `http://localhost:8000/tobirama_landing_page.html` in your browser.

## Deployment

The site is ready for deployment to Vercel, GitHub Pages, or any static hosting:

1. All content is in a single `tobirama_landing_page.html` file
2. No server-side processing needed
3. Place the `images/` and `videos/` folders in the same directory

See `VERCEL_DEPLOYMENT.md` for deployment instructions.

## Technical Details

- **Framework**: Vanilla HTML5/CSS3/JavaScript
- **Storage**: Browser localStorage
- **State Management**: In-memory + localStorage
- **Styling**: CSS Grid, Flexbox, Custom Properties
- **Animations**: CSS Keyframes (fadeInUp, slideInDown, pulse, etc.)

## Recent Fix (v2)

**Issue Fixed**: Admin panel form fields were not updating page content after save.

**Root Cause**: The About section was missing an `id="about"` attribute, causing the JavaScript selector to fail.

**Solution**: Added proper ID attribute to the About section. Added comprehensive console logging to help identify future issues.

**Commit**: `ce204ec` - "Fix admin panel: Add id='about' to About section, add verbose logging to saveAdminChanges()"
