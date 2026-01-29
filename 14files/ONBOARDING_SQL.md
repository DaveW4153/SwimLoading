# SQL TO RUN BEFORE TESTING ONBOARDING

Run this SQL in Supabase to add the required columns:

```sql
-- Add onboarding columns to profiles table
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS full_name TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS phone TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS date_of_birth DATE;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS address_line1 TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS city TEXT;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS postal_code TEXT;

-- Add legal acceptance timestamps
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS terms_accepted_at TIMESTAMP;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS privacy_accepted_at TIMESTAMP;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS waiver_accepted_at TIMESTAMP;
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS data_consent_at TIMESTAMP;

-- Add onboarding completion
ALTER TABLE profiles ADD COLUMN IF NOT EXISTS onboarding_completed_at TIMESTAMP;

-- Verify columns were added
SELECT column_name, data_type 
FROM information_schema.columns 
WHERE table_name = 'profiles'
ORDER BY column_name;
```

After running this, test the onboarding flow!
