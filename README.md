# Simple-PHP-mySQL-Band-Schedule

# 🎸 Band Calendar – PHP + MySQL Scheduling App

A lightweight, mobile-friendly calendar and scheduling system for coordinating shows, venues, and band member availability. This app is designed for **private band use** to track events, avoid conflicts, and manage availability without relying on third-party tools.

---

## 🗂 Directory Layout

```
schedule/                          → Root folder of the app
├── ajax/                     → AJAX endpoints (venue/band search, updates)
│   ├── add_band.php
│   ├── add_new_band.php
│   ├── add_new_venue.php
│   ├── autocomplete_bands.php
│   ├── autocomplete_venues.php
│   ├── fetch_shows.php
│   ├── update_band_order.php
│   └── update_show_venue.php
│
├── css/                      → Stylesheets
│   ├── reset.css
│   └── style.css
│
├── includes/                 → Shared PHP files
│   ├── constants.php         → DB credentials (user-defined)
│   ├── connection.php        → MySQL connection setup
│   ├── functions.php         → Helper functions
│   ├── header.php            → HTML + navigation top
│   └── footer.php            → Footer section
│
├── js/
│   └── main.js               → Combined JS for calendar, autocomplete, drag/drop
│
├── index.php                 → Main calendar with list of shows
├── new_show.php              → Form to add a new show
├── edit_show.php             → Edit a specific show (bands, venue, date)
├── block_time.php            → Add/view member unavailability
├── band_list.php             → View/add/edit bands
├── venue_list.php            → View/add/edit venues
├── edit_band.php             → Edit band details
├── edit_venue.php            → Edit venue details

```

---

## 🔧 How to Set Up

1. **Create a MySQL Database and user.**
2. **Open `includes/constants.php`**  
   Enter your credentials:
   ```php
   $DB_NAME = "your_database";
   $DB_USER = "your_user";
   $DB_PASS = "your_password";
   ```
3. **Visit `setup/setup_database.php`** in your browser.  
   This will:
   - Create all tables
   - Populate them with sample bands, shows, venues, and unavailability
   - You’ll get a confirmation message on success

---

## 🧠 Features

### ✅ Show Calendar
- Month grid view with dynamic show markers
- Toggle between upcoming and past events
- Clickable day cells:
  - Add new show
  - Block dates for band members

### 🎤 Band & Venue Management
- Add/edit bands, venues, and contact info
- Drag-and-drop band set order within shows
- Autocomplete input with “Add New” inline

### 🧍‍♂️ Band Member Availability
- Assign unavailability dates to specific members
- View all upcoming blocked dates in a list
- Deletes handled securely via parameter validation

### 🔒 Security
- All database interactions use **prepared statements**
- Inputs are sanitized and filtered
- AJAX requests are handled in a separate `/ajax` folder

### 🖱️ Frontend UX
- Fully responsive
- FontAwesome icons
- Smooth calendar navigation and swipe support
- Vanilla JS (no jQuery required)

---

## 📦 Optional: ZIP-Based Deployment

You can bundle your app into a ZIP and share it directly (for example, to other bandmates). A helper script (`zip_backup.php`) can be added to snapshot your full app directory into a downloadable ZIP archive.

---

## 📝 License

This is a private-use utility, but feel free to fork, modify, and reuse for personal or small group use.
