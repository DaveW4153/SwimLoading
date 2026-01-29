# ONBOARDING TESTING GUIDE

## WHAT WE JUST BUILT ✅

1. **Legal Documents** (3 professional documents)
   - Privacy Policy (POPIA compliant)
   - Terms of Service
   - Liability Waiver

2. **Legal Acceptance Screen**
   - 4 checkboxes (Terms, Privacy, Waiver, Data Consent)
   - View links for each document
   - Accept button (disabled until all checked)
   - Saves timestamps to database

3. **Personal Details Screen**
   - Full name, phone, DOB
   - Home address, city, postal code
   - Form validation
   - Saves to database
   - Marks onboarding complete

## SETUP (5 mins)

### Step 1: Add Database Columns

Run this SQL in Supabase:

```sql
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS full_name TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS phone TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS date_of_birth DATE;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS address_line1 TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS city TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS postal_code TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS terms_accepted_at TIMESTAMP;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS privacy_accepted_at TIMESTAMP;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS waiver_accepted_at TIMESTAMP;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS data_consent_at TIMESTAMP;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS onboarding_completed_at TIMESTAMP;
```

### Step 2: Reset Your Profile

Delete your current profile so you go through onboarding:

```sql
DELETE FROM profiles WHERE id = 'df137255-3add-4153-b368-32e06e2be188';
```

---

## TESTING PROCEDURE

### TEST 1: Legal Acceptance Screen

1. Open `swimloading_v2_LEGAL.html`
2. Login with your account
3. **Expected:** See legal acceptance screen (NOT dashboard)
4. **Check:**
   - [ ] 4 checkboxes visible
   - [ ] "Accept All & Continue" button is DISABLED
   - [ ] Lucide icons display (scroll-text, shield-check, alert-triangle, database)
   - [ ] Screen is mobile-responsive
   - [ ] Cancel button works (logs you out)

### TEST 2: Checkbox Validation

1. Check ONE checkbox
2. **Expected:** Button still disabled
3. Check TWO checkboxes
4. **Expected:** Button still disabled
5. Check THREE checkboxes
6. **Expected:** Button still disabled
7. Check FOUR checkboxes
8. **Expected:** Button ENABLED ✅

### TEST 3: Legal Acceptance Save

1. Check all 4 checkboxes
2. Click "Accept All & Continue"
3. **Expected:** Personal details screen appears
4. **Verify in database:**

```sql
SELECT 
    terms_accepted_at, 
    privacy_accepted_at, 
    waiver_accepted_at, 
    data_consent_at
FROM profiles 
WHERE id = 'df137255-3add-4153-b368-32e06e2be188';
```

**Expected:** All 4 timestamps should be set to NOW ✅

### TEST 4: Personal Details Screen

1. **Check UI:**
   - [ ] User icon displays (Lucide)
   - [ ] All fields present
   - [ ] City pre-filled with "Cape Town"
   - [ ] Mobile responsive
   - [ ] Required fields marked with *

2. **Try submitting empty:**
   - Click Continue
   - **Expected:** Alert "Please fill in all required fields"

3. **Fill in all fields:**
   - Full Name: Dave Welensky
   - Phone: +27 82 123 4567
   - DOB: (pick a date)
   - Address: 123 Beach Road
   - City: Cape Town
   - Postal Code: 8001

4. **Click Continue**
5. **Expected:** Dashboard loads! ✅

### TEST 5: Database Verification

```sql
SELECT 
    full_name,
    phone,
    date_of_birth,
    address_line1,
    city,
    postal_code,
    onboarding_completed_at
FROM profiles 
WHERE id = 'df137255-3add-4153-b368-32e06e2be188';
```

**Expected:** All fields populated with your data ✅

### TEST 6: Onboarding Skip (Existing Users)

1. Logout
2. Login again
3. **Expected:** Goes directly to dashboard (NOT onboarding) ✅

---

## SUCCESS CRITERIA ✅

All of these must pass:

- [ ] Legal screen displays with Lucide icons
- [ ] Checkboxes enable/disable button correctly
- [ ] Legal acceptance saves all 4 timestamps
- [ ] Personal details screen displays
- [ ] Form validation works (required fields)
- [ ] Personal details save to database
- [ ] onboarding_completed_at timestamp set
- [ ] Dashboard loads after completion
- [ ] Existing users skip onboarding on next login
- [ ] Mobile responsive (test 375px width)
- [ ] No console errors
- [ ] NO EMOJI ICONS (all Lucide)

---

## IF ANYTHING FAILS

**Problem: Columns don't exist**
- Run the SQL again
- Check for typos

**Problem: Legal screen doesn't appear**
- Check console for errors (Cmd+Option+J)
- Verify profile has no terms_accepted_at

**Problem: Button stays disabled**
- Check browser console for JavaScript errors
- Try clicking checkboxes again

**Problem: Dashboard doesn't load after completion**
- Check console errors
- Verify onboarding_completed_at was set in database

---

## WHAT'S NEXT (Next Session)

After this passes, we add:
1. Emergency contact screen
2. Swimming profile screen
3. Profile photo upload
4. Welcome/success screen

---

## CURRENT STATUS

**Working:**
- ✅ Signup/login
- ✅ Temperature logging
- ✅ Events/RSVP
- ✅ Dashboard
- ✅ Legal acceptance
- ✅ Personal details collection

**Not Yet:**
- ❌ Emergency contacts
- ❌ Swimming profile
- ❌ Photo upload
- ❌ GPS location capture
- ❌ Gamification

**Building step by step. No regressions.** 🎯
