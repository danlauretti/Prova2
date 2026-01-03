# 🗂️ Abu Dhabi Pet Map - Airtable Structure & Softr Categories

## 📊 AIRTABLE TABLE STRUCTURE (What to Import)

### Your "Listings" Table Should Have These Fields:

```
┌─────────────────────────────────────────────────────────────┐
│  FIELD NAME          │  TYPE           │  DESCRIPTION        │
├─────────────────────────────────────────────────────────────┤
│  Name               │  Single line    │  Business name      │
│  Category           │  Single select  │  Type of service ⭐ │
│  District           │  Single select  │  Abu Dhabi area     │
│  Contact_Number     │  Phone          │  +971 format        │
│  WhatsApp_Link      │  URL            │  wa.me link         │
│  Pet_Policy_Details │  Long text      │  Description        │
│  Website            │  URL            │  Business site      │
│  Address            │  Long text      │  Full address       │
│  Hours              │  Single line    │  Opening hours      │
│  Latitude           │  Number         │  For map (decimal)  │
│  Longitude          │  Number         │  For map (decimal)  │
│  Location           │  Formula        │  ⚠️ CRITICAL! ⚠️    │
└─────────────────────────────────────────────────────────────┘

⚠️ CRITICAL FORMULA for "Location" field:
   CONCATENATE({Latitude}, ",", {Longitude})
```

---

## 🏷️ CATEGORY OPTIONS (Single Select Field)

### Add These 11 Categories to Your "Category" Field:

```
CATEGORY LIST (Copy/Paste into Airtable):

1. Veterinary Clinic
2. Emergency Vet 24/7
3. Pet Grooming
4. Pet Grooming & Pet Taxi
5. Pet Boarding
6. Pet Boarding & Daycare
7. Pet Boarding & Adoption
8. Pet Shop
9. Aquarium & Pet Shop
10. Aquarium Shop
11. Pet-Friendly Restaurant
12. Pet-Friendly Cafe
13. Pet-Friendly Hotel
14. Pet-Friendly Apartment
15. Pet Training
16. Pet Transportation
17. Pet Daycare & Sitting
18. Pet Recreation
19. Pet Adoption & Rescue
```

### 🎨 Color Coding for Categories (in Airtable):

```
🔴 RED Categories (Veterinary):
   - Veterinary Clinic
   - Emergency Vet 24/7

🟣 PURPLE Categories (Grooming):
   - Pet Grooming
   - Pet Grooming & Pet Taxi

🔵 BLUE Categories (Boarding):
   - Pet Boarding
   - Pet Boarding & Daycare
   - Pet Boarding & Adoption

🟠 ORANGE Categories (Shops):
   - Pet Shop
   - Aquarium & Pet Shop
   - Aquarium Shop

🟢 GREEN Categories (Dining):
   - Pet-Friendly Restaurant
   - Pet-Friendly Cafe

🔵 TEAL Categories (Hotels):
   - Pet-Friendly Hotel
   - Pet-Friendly Apartment

🟣 INDIGO Categories (Training):
   - Pet Training

🟡 YELLOW Categories (Transport):
   - Pet Transportation
   - Pet Daycare & Sitting

🟢 LIME Categories (Recreation):
   - Pet Recreation

🩷 PINK Categories (Adoption):
   - Pet Adoption & Rescue
```

---

## 📍 DISTRICT OPTIONS (Single Select Field)

### Add These Districts to Your "District" Field:

```
DISTRICT LIST (Copy/Paste into Airtable):

1. Al Muroor
2. Khalifa City
3. Khalifa City A
4. Al Khalidiyah
5. Musaffah ICAD I
6. Musaffah
7. Yas Island
8. Yas Bay Waterfront
9. Yas Marina
10. Saadiyat Island
11. Al Reem Island
12. Al Raha Beach
13. Al Bateen
14. Al Nahyan
15. Near Airport
16. Near National Hospital
17. Al Khubeirah
18. Al Reef Villas
19. Al Mushrif
20. Al Salam Street
21. Al Hisn
22. Tourist Club Area
23. Al Rahah
24. Al Raha
25. Muroor
26. Various
27. Abu Dhabi
28. Mobile Service
29. UAE-wide
30. Abu Dhabi & Dubai
```

---

## 🗺️ VISUAL: Airtable Table Structure

```
┌──────────────────────────────────────────────────────────────────────────────────────┐
│ Name                    │ Category          │ District      │ Contact_Number        │
├──────────────────────────────────────────────────────────────────────────────────────┤
│ Pets Oasis Abu Dhabi   │ Veterinary Clinic │ Al Muroor     │ +971 2 676 7100      │
│ British Vet Centre     │ Veterinary Clinic │ Khalifa City  │ +971 2 550 4111      │
│ Akiba Dori             │ Pet-Friendly Rest │ Yas Bay       │ +971 4 770 7949      │
│ The Lighthouse         │ Pet-Friendly Cafe │ Yas Bay       │ +971 2 236 7831      │
│ Pet Pavilion           │ Veterinary Clinic │ Musaffah      │ +971 2 559 0453      │
└──────────────────────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────────────────────┐
│ WhatsApp_Link              │ Website                    │ Address                   │
├──────────────────────────────────────────────────────────────────────────────────────┤
│ https://wa.me/971558693022 │ petsoasisabudhabi.ae      │ 66 Al Majarrah St...     │
│ https://wa.me/971508230780 │ britvet.com               │ Al Fursan St...          │
│                            │                            │ The Pier, Yas Bay...     │
│                            │ thelighthouse.ae           │ BW 101-4, Yas Bay...     │
│ https://wa.me/971502209922 │ petpavilion.ae            │ Plot M35, Street 13...   │
└──────────────────────────────────────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────────────────────────────────────┐
│ Hours              │ Latitude   │ Longitude  │ Location              │ Pet_Policy... │
├──────────────────────────────────────────────────────────────────────────────────────┤
│ Mon-Sun 9am-9pm   │ 24.447044  │ 54.383701  │ 24.447044,54.383701  │ Full-service..│
│ Mon-Fri 8am-10pm  │ 24.418329  │ 54.548001  │ 24.418329,54.548001  │ 24/7 emergency│
│ Daily 12pm-12am   │ 24.495877  │ 54.608156  │ 24.495877,54.608156  │ Dogs welcome..│
│ Mon-Thu 8am-12am  │ 24.492156  │ 54.610523  │ 24.492156,54.610523  │ Pet-friendly..│
│ Mon-Thu 9am-8pm   │ 24.350034  │ 54.497774  │ 24.350034,54.497774  │ Comprehensive.│
└──────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 🎯 SOFTR MAP BLOCK CONFIGURATION

### When Adding Map Block in Softr:

```
┌─────────────────────────────────────────────────────────────┐
│  MAP BLOCK SETTINGS                                         │
├─────────────────────────────────────────────────────────────┤
│  Data Source:                                               │
│  ├─ Table: Listings                                         │
│  └─ View: All records                                       │
│                                                              │
│  Location Settings:                                         │
│  ├─ Location field: Location ⚠️ SELECT THIS!               │
│  ├─ Default center latitude: 24.4539                        │
│  ├─ Default center longitude: 54.3773                       │
│  └─ Default zoom level: 11                                  │
│                                                              │
│  Marker Settings:                                           │
│  ├─ Color markers by: Category                             │
│  ├─ Marker icon: Default (pin)                             │
│  └─ Enable clustering: Yes                                  │
│                                                              │
│  Popup Content:                                             │
│  ├─ Title: {Name}                                           │
│  ├─ Show fields:                                            │
│  │   ├─ Category                                            │
│  │   ├─ Contact_Number                                      │
│  │   ├─ Hours                                               │
│  │   └─ Address                                             │
│  └─ Action buttons:                                         │
│      ├─ View details                                        │
│      ├─ Call (tel:{Contact_Number})                         │
│      └─ WhatsApp ({WhatsApp_Link})                          │
└─────────────────────────────────────────────────────────────┘
```

---

## 🎨 SOFTR CATEGORY COLOR SETTINGS

### In Softr Map Block → Marker Colors:

```
┌──────────────────────────────────────────────────────┐
│  CATEGORY                    │  HEX COLOR            │
├──────────────────────────────────────────────────────┤
│  Veterinary Clinic           │  #E74C3C (red)        │
│  Emergency Vet 24/7          │  #C0392B (dark red)   │
│  Pet Grooming                │  #9B59B6 (purple)     │
│  Pet Grooming & Pet Taxi     │  #8E44AD (dark purple)│
│  Pet Boarding                │  #3498DB (blue)       │
│  Pet Boarding & Daycare      │  #2980B9 (dark blue)  │
│  Pet Boarding & Adoption     │  #1ABC9C (turquoise)  │
│  Pet Shop                    │  #E67E22 (orange)     │
│  Aquarium & Pet Shop         │  #D35400 (dark orange)│
│  Aquarium Shop               │  #D35400 (dark orange)│
│  Pet-Friendly Restaurant     │  #27AE60 (green)      │
│  Pet-Friendly Cafe           │  #229954 (dark green) │
│  Pet-Friendly Hotel          │  #16A085 (teal)       │
│  Pet-Friendly Apartment      │  #138D75 (dark teal)  │
│  Pet Training                │  #5B2C6F (indigo)     │
│  Pet Transportation          │  #F39C12 (yellow)     │
│  Pet Daycare & Sitting       │  #3498DB (blue)       │
│  Pet Recreation              │  #2ECC71 (lime)       │
│  Pet Adoption & Rescue       │  #E91E63 (pink)       │
└──────────────────────────────────────────────────────┘
```

---

## 📋 SOFTR LIST BLOCK CONFIGURATION

### For Directory/List Pages:

```
┌─────────────────────────────────────────────────────────────┐
│  LIST BLOCK SETTINGS                                        │
├─────────────────────────────────────────────────────────────┤
│  Data Source:                                               │
│  ├─ Table: Listings                                         │
│  └─ View: All records                                       │
│                                                              │
│  Layout:                                                    │
│  ├─ Style: Cards or List                                    │
│  └─ Items per page: 20                                      │
│                                                              │
│  Card Content:                                              │
│  ├─ Title: {Name}                                           │
│  ├─ Subtitle: {Category} · {District}                       │
│  ├─ Description: {Pet_Policy_Details} (truncate 150 chars) │
│  └─ Bottom text: {Hours}                                    │
│                                                              │
│  Buttons:                                                   │
│  ├─ Primary: "View Details" → Detail page                  │
│  ├─ Secondary: "📞 Call" → tel:{Contact_Number}           │
│  ├─ Secondary: "💬 WhatsApp" → {WhatsApp_Link}            │
│  └─ Secondary: "🌐 Website" → {Website}                    │
│                                                              │
│  Filters:                                                   │
│  ├─ By Category (dropdown or pills)                        │
│  ├─ By District (dropdown)                                 │
│  └─ Search: Name, Category, District, Pet_Policy_Details   │
└─────────────────────────────────────────────────────────────┘
```

---

## 🔍 SOFTR SEARCH BLOCK CONFIGURATION

```
┌─────────────────────────────────────────────────────────────┐
│  SEARCH BLOCK SETTINGS                                      │
├─────────────────────────────────────────────────────────────┤
│  Connected to: Listings table                               │
│                                                              │
│  Search in fields:                                          │
│  ├─ ✅ Name                                                 │
│  ├─ ✅ Category                                             │
│  ├─ ✅ District                                             │
│  ├─ ✅ Pet_Policy_Details                                   │
│  └─ ✅ Address                                              │
│                                                              │
│  Placeholder text:                                          │
│  "🔍 Search for vets, groomers, cafes..."                   │
│                                                              │
│  Search behavior:                                           │
│  ├─ Live search: Yes (updates as you type)                 │
│  └─ Minimum characters: 2                                   │
└─────────────────────────────────────────────────────────────┘
```

---

## 🎯 SOFTR FILTER BLOCKS CONFIGURATION

### Filter Block 1: Category Filter

```
┌─────────────────────────────────────────────────────────────┐
│  FILTER BLOCK - CATEGORY                                    │
├─────────────────────────────────────────────────────────────┤
│  Filter by: Category                                        │
│  Display as: Pills / Chips                                  │
│  Label: "Category"                                          │
│  Options:                                                   │
│  ├─ Show all options                                        │
│  ├─ Allow multiple selection: Yes                          │
│  └─ Show count: Yes (e.g., "Vets (15)")                    │
└─────────────────────────────────────────────────────────────┘
```

### Filter Block 2: District Filter

```
┌─────────────────────────────────────────────────────────────┐
│  FILTER BLOCK - DISTRICT                                    │
├─────────────────────────────────────────────────────────────┤
│  Filter by: District                                        │
│  Display as: Dropdown                                       │
│  Label: "Location"                                          │
│  Options:                                                   │
│  ├─ Show all options                                        │
│  ├─ Allow multiple selection: Yes                          │
│  └─ Sort: Alphabetical                                      │
└─────────────────────────────────────────────────────────────┘
```

---

## 📱 WHAT YOUR SOFTR PAGE SHOULD LOOK LIKE

```
┌────────────────────────────────────────────────────────────────┐
│  🐾 The Abu Dhabi Pet Map                          [Menu ≡]   │
│  ┌──────────────────────────────────────────────────────────┐ │
│  │ 🔍 [Search for vets, groomers, cafes...        ]        │ │
│  └──────────────────────────────────────────────────────────┘ │
│                                                                │
│  Category: [All ▼]    Location: [All Districts ▼]            │
│                                                                │
│  ┌──────────────────────────────────────────────────────────┐ │
│  │                                                          │ │
│  │                  [INTERACTIVE MAP]                       │ │
│  │                                                          │ │
│  │     🔴 🔴 🟣 🔵 🟠 🟢 🔵 ← Markers                      │ │
│  │                                                          │ │
│  │     Click any marker to see details!                    │ │
│  │                                                          │ │
│  └──────────────────────────────────────────────────────────┘ │
│                                                                │
│  Showing 70 of 70 pet services                                │
└────────────────────────────────────────────────────────────────┘
```

---

## ✅ IMPORT CHECKLIST

Before importing to Airtable:

- [ ] Download `listings_seed_with_coords.csv`
- [ ] Check file has these columns:
  - [ ] Name, Category, District
  - [ ] Contact_Number, WhatsApp_Link, Website
  - [ ] Address, Hours
  - [ ] **Latitude, Longitude** ⚠️ CRITICAL!
  - [ ] Pet_Policy_Details
- [ ] File has 70 rows (+ header row)
- [ ] Ready to import!

After importing to Airtable:

- [ ] Change Category to "Single select"
- [ ] Change District to "Single select"
- [ ] Add new field "Location" with formula:
      `CONCATENATE({Latitude}, ",", {Longitude})`
- [ ] Verify Location shows: "24.4539,54.3773" format
- [ ] Ready for Softr!

---

## 🎨 EXAMPLE: What Categories Look Like in Softr

```
Map with category pills above it:

[All (70)] [🏥 Vets (15)] [✂️ Grooming (6)] [🏨 Boarding (8)]
[🛍️ Shops (8)] [🍽️ Cafes (9)] [🏨 Hotels (10)] [More ▼]

When clicked, map filters to show only that category!
```

---

## 🆘 COMMON MISTAKES TO AVOID

❌ **DON'T:**
- Manually type Latitude/Longitude (use my CSV!)
- Forget the Location formula field
- Use "Multi-select" for Category (use "Single select")
- Import without coordinates

✅ **DO:**
- Import `listings_seed_with_coords.csv`
- Add Location formula: `CONCATENATE({Latitude}, ",", {Longitude})`
- Set Category and District as "Single select"
- Test the map before publishing

---

Ready to import? Use the file: **listings_seed_with_coords.csv**

Now tell me what you see in your Softr studio and I can help you configure it! 📸
