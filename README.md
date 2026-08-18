Prompt:
# Kisan Saathi — Smart Farming Assistant

Build a complete modern mobile-first farming application called **Kisan Saathi** for Indian farmers.

Tagline:

**"Smart Farming, Better Future"**

The application must be simple enough for farmers who may not be comfortable with technology.

---

## 1. DESIGN SYSTEM

Use a professional agricultural design.

Primary color:

* Agricultural green

Secondary:

* White

Supporting colors:

* Light green backgrounds
* Dark green text
* Soft neutral gray backgrounds

Design rules:

* Mobile-first
* Large buttons
* Large touch targets
* Rounded cards
* Rounded buttons
* Clear icons
* Simple language
* High readability
* Good contrast
* Minimal animations
* No unnecessary visual complexity
* Responsive on Android, iPhone, tablet and desktop
* Professional but friendly farming appearance

Use farming icons such as:

* Leaf
* Crop
* Farm
* Tractor
* Weather
* Water
* Bug
* Camera
* Farmer

---

# 2. TECHNOLOGY

Use:

* React
* TypeScript
* Tailwind CSS
* Supabase
* Supabase Authentication
* Supabase Database
* Supabase Storage where required

Use a modular architecture.

Organize the project into reusable:

* Components
* Pages
* Layouts
* Hooks
* Services
* Database utilities
* Authentication utilities

Do not use fake authentication.

Do not hard-code farmer information.

Use real authenticated Supabase user data.

---

# 3. SPLASH SCREEN

Create a professional splash screen.

Show:

🌾 Kisan Saathi

**Smart Farming, Better Future**

Use a simple agricultural logo combining:

* Leaf
* Crop
* Farmer/farming concept

Show a subtle loading indicator.

After approximately 2 seconds:

If authenticated:
→ Dashboard

If not authenticated:
→ Welcome

---

# 4. WELCOME SCREEN

Create:

**Welcome to Kisan Saathi**

Subtitle:

**Your smart farming companion**

Create three feature cards:

🌱 Manage Your Crops

🌦️ Check Weather

🧑‍🌾 Get Farming Support

Buttons:

**Login**

**Create Account**

Keep the layout extremely simple.

---

# 5. LOGIN

Create secure login.

Fields:

* Mobile Number or Email
* Password

Features:

* Show/hide password
* Remember session
* Forgot Password
* Login
* Create New Account

Validation:

* Required fields
* Valid email/mobile
* Password required

Friendly messages:

"Please enter your mobile number or email."

"Please enter your password."

"Invalid login details. Please try again."

After successful authentication:

→ Dashboard

Use Supabase Authentication.

Never manually store passwords.

---

# 6. REGISTRATION

Create farmer registration.

Fields:

* Full Name
* Mobile Number
* Email Address optional
* Password
* Confirm Password

Validation:

* Full name required
* Valid mobile number
* Valid email if entered
* Password minimum 8 characters
* Password confirmation must match

Button:

**Create Account**

Link:

**Already have an account? Login**

After successful registration:

→ Farmer Profile Setup

Use Supabase Authentication.

---

# 7. FORGOT PASSWORD

Create password recovery.

Field:

* Email Address

Button:

**Send Reset Link**

Message:

"If an account exists with this email, a password reset link will be sent."

Use Supabase password recovery.

After request:

Show a success confirmation.

---

# 8. FARMER PROFILE SETUP

After registration show:

**Complete Your Profile**

Fields:

* Farmer Name
* Village
* District
* State
* Preferred Language
* Profile Photo optional

Language:

* English
* Hindi
* Gujarati

Button:

**Continue to Kisan Saathi**

Save information to Supabase.

---

# 9. DATABASE

Create a Supabase `profiles` table.

Columns:

* id
* user_id
* full_name
* mobile
* email
* village
* district
* state
* language
* profile_photo_url
* created_at
* updated_at

`user_id` must reference the authenticated Supabase user.

Enable Row Level Security.

Policies:

A farmer can:

* SELECT only their own profile
* INSERT only their own profile
* UPDATE only their own profile

A farmer must NEVER be able to access another farmer's profile.

Do not expose authentication secrets.

---

# 10. DASHBOARD

Create the main Farmer Dashboard.

Top section:

**Namaste, [Farmer Name] 👋**

**Welcome to Kisan Saathi**

Load farmer name dynamically from the Supabase profile.

Do not hard-code the name.

---

## Summary Cards

Create:

🌱 My Crops

**0 Crops**

🚜 My Farms

**0 Farms**

💧 Today's Tasks

**0 Tasks**

🔔 Notifications

**0 New**

Use real database values when future modules are added.

---

# 11. QUICK SERVICES

Create a large touch-friendly grid.

🌱 My Crops

🚜 My Farms

🌦️ Weather

💰 Mandi Prices

📸 Crop Scan

🐛 Pest & Disease

🧪 Crop Health

🧑‍🌾 Farming Tips

For features not implemented in Part 1:

Show a professional:

**Coming Soon**

state.

Do not create fake data.

---

# 12. CROP SCAN FOUNDATION

Add a dedicated **Crop Scan** entry in the dashboard.

This feature will later allow the farmer to:

1. Open camera
2. Take crop/leaf photo
3. Upload image
4. AI analyzes the image
5. Identify possible:

   * Pest
   * Disease
   * Nutrient deficiency
   * Healthy crop
6. Show:

   * Possible issue
   * Confidence level
   * Symptoms
   * Suggested next steps
   * When to seek expert verification

For Part 1, create the UI foundation only.

Create a clean placeholder page:

**Crop Health Scan**

"Take a clear photo of your crop or leaf to check for possible problems."

Buttons:

**📷 Take Photo**

**🖼️ Choose Photo**

Show:

**AI crop diagnosis will be available soon.**

Do not fake AI results.

Prepare the architecture so an AI vision API can be connected later.

---

# 13. PEST AND DISEASE FOUNDATION

Create a future-ready data model for crop health analysis.

Potential fields:

* id
* user_id
* crop_id
* image_url
* diagnosis_type
* diagnosis_name
* confidence
* symptoms
* recommendations
* created_at

Diagnosis types:

* pest
* disease
* nutrient_deficiency
* healthy
* unknown

If confidence is low, future AI results should say:

**"We are not confident about this result. Please take another clear photo or consult an agriculture expert."**

Never present uncertain AI results as guaranteed facts.

---

# 14. BOTTOM NAVIGATION

Create:

🏠 Home

🌱 Crops

🌦️ Weather

👤 Profile

Navigation must work.

Use active-state highlighting.

Make navigation large and easy to tap.

---

# 15. PROFILE PAGE

Create a basic Profile page.

Show:

* Profile photo
* Farmer name
* Mobile
* Email
* Village
* District
* State
* Preferred language

Actions:

**Edit Profile**

**Logout**

Logout must use Supabase Authentication.

---

# 16. PROTECTED ROUTES

Implement protected routing.

Public pages:

* Splash
* Welcome
* Login
* Registration
* Forgot Password

Protected pages:

* Dashboard
* Profile
* Crops
* Weather
* Crop Scan

If an unauthenticated user attempts to open a protected page:

→ Redirect to Login.

If authenticated:

→ Allow access.

Persist the Supabase session.

---

# 17. ERROR STATES

Implement:

Loading state

Empty state

Network error

Authentication error

Database error

Validation error

Success state

Use simple farmer-friendly language.

Examples:

"Please enter your mobile number."

"Your account has been created successfully."

"Your profile has been saved."

"Something went wrong. Please try again."

"Internet connection seems unavailable."

---

# 18. MOBILE UX

Optimize specifically for Indian smartphones.

Requirements:

* Large buttons
* Large icons
* Readable text
* Simple navigation
* Avoid tiny text
* Avoid crowded screens
* Minimum comfortable touch target
* Responsive cards
* Responsive dashboard

Test:

* Android phone
* iPhone
* Tablet
* Desktop browser

---

# 19. FUTURE AI ARCHITECTURE

Keep the code ready for future AI integration.

Create a service abstraction such as:

`cropDiagnosisService`

The service should eventually accept:

* Crop image
* Crop type
* Optional location
* Optional farmer description

And return structured information:

* diagnosis
* diagnosis_type
* confidence
* symptoms
* severity
* recommendations
* prevention
* expert_verification_required

Do NOT connect a fake AI API.

Do NOT generate fake diagnosis results.

Keep the service replaceable so a real computer-vision/AI model can be connected later.

---

# 20. FUTURE FEATURES — DO NOT IMPLEMENT YET

Prepare architecture for:

### Farm Management

* Add farm
* Farm size
* Soil type
* Location
* Irrigation method

### Crop Management

* Add crop
* Sowing date
* Expected harvest
* Crop stage
* Crop health

### Weather

* Current weather
* Rain forecast
* Temperature
* Humidity
* Wind
* Farming alerts

### Mandi

* Crop prices
* Nearby markets
* Price trends

### Farming Assistant

* Ask farming questions
* Voice input
* Hindi
* Gujarati
* English

### Crop Health AI

* Leaf disease detection
* Pest detection
* Nutrient deficiency detection
* Crop health analysis
* Image history

Do not implement these features now.

Only create the foundation required for future integration.

---

# 21. SECURITY

Implement:

* Supabase Authentication
* Protected routes
* Session persistence
* Secure logout
* Row Level Security
* User-specific database access
* Secure storage access

Never:

* Store passwords manually
* Put passwords in database tables
* Hard-code authentication credentials
* Expose Supabase service-role keys in frontend
* Allow users to read another user's profile

Use environment variables for public configuration.

Never expose secret keys in frontend code.

---

# 22. FINAL TESTING

Before considering Part 1 complete, test:

1. New farmer registration
2. Login
3. Logout
4. Forgot password
5. Profile creation
6. Profile update
7. Protected dashboard
8. Session persistence
9. Database security
10. RLS policies
11. Navigation
12. Mobile responsiveness
13. Loading states
14. Error states
15. Empty states
16. Crop Scan foundation
17. No fake authentication
18. No hard-coded farmer name

Fix all errors before finishing.

The final application should feel like a real production-quality Indian farming application, not a generic template.

App name:

**Kisan Saathi**

Tagline:

**Smart Farming, Better Future**

Focus this first version on:

**Authentication + Farmer Profile + Supabase Database + Dashboard + Navigation + Crop Scan Foundation**

Do not add unnecessary features.
app bana kardo ei ka and best dizayn me bana vo
