# 🐾 The Abu Dhabi Pet Map - Softr Setup Guide

**Complete step-by-step guide to building your searchable pet directory in Softr**

---

## 📋 Overview

We'll build:
- **Interactive map** with color-coded markers
- **Searchable directory** with filters
- **Category pages** (Vets, Groomers, Cafes, etc.)
- **Individual business pages** with details
- **Mobile-responsive** design

**Time to complete:** 2-3 hours

---

## 🎯 Step 1: Set Up Airtable (30 minutes)

### 1.1 Create Airtable Account
1. Go to [airtable.com](https://airtable.com)
2. Sign up (Free plan is fine to start)
3. Click **"Create a base"** → **"Start from scratch"**
4. Name it: **"Abu Dhabi Pet Map"**

### 1.2 Import Your CSV

**IMPORTANT:** We need to add coordinates for the map to work!

1. **Download the enhanced CSV** (I'll create this for you below with coordinates)
2. In Airtable, click **"Add or import"** → **"CSV file"**
3. Select `listings_seed_with_coords.csv`
4. Airtable will auto-detect columns → Click **"Import"**

### 1.3 Configure Field Types

After import, update these field types:

| Field Name | Change Type To | Configuration |
|------------|----------------|---------------|
| **Name** | Single line text | ✅ Primary field |
| **Category** | Single select | Click + add all categories as options |
| **District** | Single select | Click + add all districts as options |
| **Contact_Number** | Phone number | Country: UAE (+971) |
| **WhatsApp_Link** | URL | Keep as URL |
| **Website** | URL | Keep as URL |
| **Pet_Policy_Details** | Long text | Enable rich text |
| **Address** | Long text | Or Single line text |
| **Hours** | Single line text | Keep as is |
| **Latitude** | Number | Format: Decimal (precision: 5) |
| **Longitude** | Number | Format: Decimal (precision: 5) |
| **Location** | **FORMULA** | See formula below ⬇️ |

### 1.4 Create Location Formula Field

**Critical for Softr maps!** Softr needs a special location field.

1. Click **"+"** to add new field
2. Name it: **"Location"**
3. Type: **Formula**
4. Paste this formula:
```
CONCATENATE({Latitude}, ",", {Longitude})
```

This combines your coordinates into the format Softr needs.

### 1.5 Add Helpful Views

Create these views for better organization:

**View: By Category**
- Group by: Category
- Sort by: Name (A→Z)

**View: By District**
- Group by: District
- Sort by: Name (A→Z)

**View: Vets Only**
- Filter: Category contains "Veterinary"

**View: Pet-Friendly Venues**
- Filter: Category contains "Pet-Friendly"

**View: Open 24/7**
- Filter: Hours contains "24/7"

### 1.6 Add Color-Coding (Optional but Nice!)

In Airtable, you can color-code your Single Select options:

**Category colors:**
- Veterinary Clinic → 🔴 Red
- Pet Grooming → 🟣 Purple
- Pet Boarding → 🔵 Blue
- Pet Shop → 🟠 Orange
- Pet-Friendly Restaurant → 🟢 Green
- Pet-Friendly Cafe → 🟢 Green
- Pet-Friendly Hotel → 🔵 Teal
- Pet Training → 🟣 Purple
- Pet Transportation → 🟡 Yellow
- Pet Recreation → 🟢 Lime
- Pet Adoption → 🩷 Pink

---

## 🚀 Step 2: Connect Softr to Airtable (15 minutes)

### 2.1 Create Softr Account
1. Go to [softr.io](https://softr.io)
2. Sign up (Free plan allows 1 published app - perfect!)
3. Click **"Create new app"**

### 2.2 Choose Template or Start Fresh

**Option A: Use Template** (Faster)
- Select **"Directory"** template
- This gives you a good starting structure

**Option B: Start from Scratch**
- Choose **"Blank app"**
- More control, but takes longer

I recommend **Option A** for your weekend launch.

### 2.3 Connect Your Airtable

1. In Softr, click **"Settings"** (bottom left)
2. Go to **"Integrations"**
3. Click **"Connect to Airtable"**
4. Click **"Add base"**
5. Authorize Softr to access Airtable
6. Select your **"Abu Dhabi Pet Map"** base
7. Select the **"Listings"** table (or whatever you named it)
8. Click **"Save"**

✅ You're now connected! Your data will sync automatically.

---

## 🗺️ Step 3: Create the Map Page (45 minutes)

### 3.1 Add New Page

1. Click **"Pages"** in left sidebar
2. Click **"+ Add page"**
3. Name it: **"Map View"**
4. Choose template: **"List with map"** (if available) or **"Blank"**

### 3.2 Add Map Block

1. Click **"+ Add block"**
2. Select **"Map"** block
3. Configure:

**Data Source:**
- Table: `Listings`
- View: `All records` (or create a custom view)

**Map Settings:**
- **Location field:** Select your `Location` formula field
- **Map style:** Choose "Standard" or "Satellite"
- **Default zoom:** 11 (shows all of Abu Dhabi)
- **Default center:**
  - Latitude: `24.4539`
  - Longitude: `54.3773`

**Marker Settings:**
- **Marker color by:** Category
- **Custom colors:** Match your category colors
  - Veterinary Clinic: `#E74C3C` (red)
  - Pet Grooming: `#9B59B6` (purple)
  - Pet Boarding: `#3498DB` (blue)
  - Pet Shop: `#E67E22` (orange)
  - Pet-Friendly Restaurant: `#27AE60` (green)
  - Pet-Friendly Cafe: `#229954` (dark green)
  - Pet-Friendly Hotel: `#16A085` (teal)
  - Pet Training: `#5B2C6F` (indigo)
  - Pet Transportation: `#F39C12` (yellow)
  - Pet Recreation: `#2ECC71` (lime)
  - Pet Adoption: `#E91E63` (pink)

**Popup Settings:**
- **Title:** `{Name}`
- **Fields to show:**
  - Category
  - Contact_Number
  - Hours
  - Address
- **Actions:**
  - ✅ "View details" button
  - ✅ Custom button: "Call" → `tel:{Contact_Number}`
  - ✅ Custom button: "WhatsApp" → `{WhatsApp_Link}`

### 3.3 Add Search and Filters

**Above the map, add:**

1. **Search bar:**
   - Click "+ Add block" → "Search"
   - Search fields: Name, Category, District, Pet_Policy_Details
   - Placeholder: "🔍 Search for vets, groomers, cafes..."

2. **Category filter:**
   - Click "+ Add block" → "Filter"
   - Filter by: Category
   - Display as: Dropdown or Pills/Chips
   - Label: "Category"

3. **District filter:**
   - Add another filter
   - Filter by: District
   - Display as: Dropdown
   - Label: "Location"

4. **Quick Filter Buttons** (Optional):
   - Add custom buttons above map
   - "Vets" → Filters to Veterinary Clinic
   - "Cafes" → Filters to Pet-Friendly Cafe/Restaurant
   - "Emergency 24/7" → Filters where Hours contains "24/7"

---

## 📋 Step 4: Create Directory List Page (30 minutes)

### 4.1 Add List Page

1. **Pages** → **"+ Add page"**
2. Name it: **"Directory"** or **"All Listings"**
3. Choose template: **"List"**

### 4.2 Configure List Block

1. **Data source:** Listings table
2. **Layout:** Choose "List" or "Cards"
3. **Items per page:** 20

**Card Design:**
- **Image:** (Skip for now, can add later)
- **Title:** `{Name}`
- **Subtitle:** `{Category} · {District}`
- **Description:** `{Pet_Policy_Details}` (truncate to 150 chars)
- **Bottom text:** `{Hours}`

**Action buttons:**
- Primary button: "View Details" → Goes to detail page
- Secondary buttons:
  - "📞 Call" → `tel:{Contact_Number}`
  - "💬 WhatsApp" → Opens `{WhatsApp_Link}`
  - "🌐 Website" → Opens `{Website}`

### 4.3 Add Sidebar Filters

In the page layout, add a **left sidebar** with:

1. **Search box** (same as map page)
2. **Category filter** (checkbox list or pills)
3. **District filter** (checkbox list)
4. **Custom filters:**
   - "Open 24/7" → Checkbox → Filters Hours contains "24/7"
   - "Has WhatsApp" → Checkbox → Filters WhatsApp_Link is not empty

**Sort options:**
- Alphabetical (A-Z)
- Category
- District

---

## 📄 Step 5: Create Detail Page (20 minutes)

### 5.1 Add Detail Page

This auto-generates when you add a list, but configure it:

1. Go to **Pages** → Find your detail page
2. Name it: **"Business Details"** or **"{Name}"**

### 5.2 Configure Layout

**Header Section:**
- **Title:** `{Name}` (large, bold)
- **Subtitle:** `{Category}` (with category color badge)
- **Tags:** `{District}`

**Contact Section:**
- **Phone:** `{Contact_Number}` (clickable)
- **WhatsApp:** Button → `{WhatsApp_Link}`
- **Website:** Button → `{Website}`
- **Address:** `{Address}` with "Get Directions" button

**Details Section:**
- **Hours:** `{Hours}`
- **About:** `{Pet_Policy_Details}` (full text, formatted)

**Map Section:**
- Add small map block showing just this location
- Use the `{Location}` field

**Action Buttons:**
- Large "📞 Call Now" → `tel:{Contact_Number}`
- "💬 WhatsApp" → `{WhatsApp_Link}`
- "🗺️ Get Directions" → `https://www.google.com/maps/search/?api=1&query={Latitude},{Longitude}`
- "🌐 Visit Website" → `{Website}`

---

## 🎨 Step 6: Design & Branding (30 minutes)

### 6.1 Set Theme

**Settings → Design:**

1. **Colors:**
   - Primary color: `#3B82F6` (blue)
   - Secondary color: `#9B59B6` (purple)
   - Accent: `#10B981` (green)

2. **Typography:**
   - Heading font: Inter or Poppins
   - Body font: Inter or Open Sans

3. **Spacing:** Medium or Comfortable

### 6.2 Customize Header

1. **Logo:** Add paw icon 🐾 or upload custom logo
2. **Site name:** "The Abu Dhabi Pet Map"
3. **Tagline:** "Your Complete Pet Services Directory"

### 6.3 Add Navigation

**Top menu:**
- Home
- Map View
- Directory
- About
- Submit a Business (optional)

**Footer:**
- About
- Contact
- Pet Laws & Regulations (link to your markdown)
- Social media links

### 6.4 Homepage Design

Create a **landing page** with:

1. **Hero section:**
   - Title: "The Abu Dhabi Pet Map 🐾"
   - Subtitle: "Find vets, groomers, pet-friendly cafes & more"
   - CTA button: "Explore Map" → Goes to map page

2. **Quick stats:**
   - "71+ Pet Services"
   - "10+ Categories"
   - "All Abu Dhabi Districts"

3. **Category cards:**
   - 3-4 cards with icons
   - "Veterinary Care" → Filters to vets
   - "Pet-Friendly Dining" → Filters to cafes
   - "Grooming & Boarding" → Filters to services

4. **Featured listings:**
   - Show 6-8 top businesses (maybe filtered by Featured field)

5. **CTA section:**
   - "Own a pet business? Get listed!"
   - Button: "Submit Your Business"

---

## 🔧 Step 7: Advanced Features (Optional - 30 min)

### 7.1 Add "Open Now" Badge

1. In Airtable, create a **Formula field** named `Is_Open_Now`
2. Formula (simplified):
```
IF(
  FIND("24/7", {Hours}),
  "🟢 Open Now",
  "🔴 Check Hours"
)
```

3. In Softr, display this as a badge on cards

### 7.2 Add Favorite/Save Feature

1. Enable **User accounts** in Softr (Settings → Users)
2. Add "Save" button on listings
3. Create "My Favorites" page

### 7.3 Add Submission Form

1. Create a new table in Airtable: "Submissions"
2. In Softr, add a **Form block**
3. Connect to "Submissions" table
4. Fields:
   - Business Name
   - Category (dropdown)
   - Contact Number
   - WhatsApp
   - Website
   - Description
   - District
5. Add to navigation: "Submit a Business"

### 7.4 Add Analytics

1. Settings → Integrations
2. Add Google Analytics
3. Paste your GA4 tracking ID

---

## 🚀 Step 8: Publish & Deploy (15 minutes)

### 8.1 Preview & Test

1. Click **"Preview"** button (top right)
2. Test on desktop and mobile
3. Check:
   - ✅ Map loads correctly
   - ✅ All markers appear
   - ✅ Filters work
   - ✅ Search works
   - ✅ Phone/WhatsApp buttons work
   - ✅ Detail pages display properly

### 8.2 Publish

1. Click **"Publish"** (top right)
2. Free plan URL: `your-app-name.softr.app`
3. Or connect custom domain (paid plans)

### 8.3 Set SEO

**Settings → SEO:**
- **Site Title:** "The Abu Dhabi Pet Map - Pet Services Directory"
- **Meta Description:** "Find vets, groomers, pet-friendly cafes, boarding, and more in Abu Dhabi. Complete directory of 71+ pet services with map, contact info, and reviews."
- **Favicon:** Upload paw icon
- **OG Image:** Create social share image (1200x630px)

---

## 📱 Mobile Optimization Checklist

- ✅ Map is responsive
- ✅ Filters collapse into hamburger menu
- ✅ Cards stack vertically
- ✅ Phone/WhatsApp buttons are large and tappable
- ✅ Search bar is sticky at top
- ✅ Detail pages are readable on small screens

---

## 🐛 Troubleshooting

### Map Not Showing Markers?

**Check:**
1. Location field has values (not empty)
2. Location formula is correct: `CONCATENATE({Latitude}, ",", {Longitude})`
3. Latitude/Longitude are valid numbers
4. Map block is connected to correct field

**Fix:**
```
In Airtable, check Location field:
Should show: "24.4539,54.3773"
NOT: "null,null" or empty
```

### Markers in Wrong Location?

**Issue:** Coordinates might be swapped or incorrect

**Fix:**
1. Verify Latitude is between 24.3 - 24.6 (Abu Dhabi range)
2. Verify Longitude is between 54.2 - 54.7 (Abu Dhabi range)
3. If wrong, check your CSV data

### Search Not Working?

**Check:**
1. Search block is connected to correct table
2. Search fields are selected
3. Try searching for exact name first

### Filters Not Applying?

**Check:**
1. Filter block is on same page as list/map
2. Filter field exists in Airtable
3. Values match exactly (case-sensitive!)

---

## 💡 Pro Tips

### Tip 1: Test Your Location Formula
In Airtable, add a test record:
- Latitude: `24.4539`
- Longitude: `54.3773`
- Location should automatically show: `24.4539,54.3773`

### Tip 2: Batch Edit in Airtable
Select multiple records → Right-click → Edit to update many at once

### Tip 3: Use Airtable Views for Softr
Create separate views for different pages:
- "Map View" → All records
- "Featured" → Only Featured = true
- "Emergency Vets" → Hours contains "24/7"

### Tip 4: Add Loading States
In Softr, customize "Loading..." text to be more friendly:
"🐾 Finding pet services near you..."

### Tip 5: Create Category Landing Pages
Make separate pages for each major category:
- `/veterinary-clinics` → Filtered list of vets
- `/pet-friendly-cafes` → Filtered list of cafes
- Better for SEO!

---

## 📊 Recommended Airtable Structure

```
Table: Listings
├── Name (Single line text) - Primary
├── Category (Single select)
├── District (Single select)
├── Contact_Number (Phone)
├── WhatsApp_Link (URL)
├── Website (URL)
├── Pet_Policy_Details (Long text)
├── Address (Long text)
├── Hours (Single line text)
├── Latitude (Number)
├── Longitude (Number)
├── Location (Formula) ← CRITICAL FOR MAP!
├── Featured (Checkbox) - Optional
├── Date_Added (Created time) - Auto
└── Photos (Attachment) - For later

Views:
├── All Listings (Default)
├── By Category (Grouped)
├── By District (Grouped)
├── Featured Only (Filtered)
├── Vets Only (Filtered)
└── Pet-Friendly Venues (Filtered)
```

---

## 🎯 Your Softr Launch Checklist

### Before Publishing:
- [ ] All 71 businesses imported to Airtable
- [ ] Latitude/Longitude added for each business
- [ ] Location formula field created and working
- [ ] Category and District as Single Select
- [ ] Map page created with working markers
- [ ] Directory list page with filters
- [ ] Detail pages configured
- [ ] Search functionality tested
- [ ] Mobile view checked
- [ ] Hero/landing page designed
- [ ] Navigation menu set up
- [ ] Footer links added
- [ ] SEO settings configured

### After Publishing:
- [ ] Test all links on live site
- [ ] Share link with 5 friends for feedback
- [ ] Post on social media
- [ ] Submit to Google Search Console
- [ ] Add Google Analytics
- [ ] Monitor for errors

---

## 🆘 Need Help?

**Softr Resources:**
- [Softr Documentation](https://docs.softr.io/)
- [Softr Community](https://community.softr.io/)
- [YouTube Tutorials](https://www.youtube.com/c/Softr)

**Airtable Resources:**
- [Airtable Support](https://support.airtable.com/)
- [Formula Field Guide](https://support.airtable.com/hc/en-us/articles/203255215)

---

Ready to build! I'll now create the enhanced CSV with coordinates...
