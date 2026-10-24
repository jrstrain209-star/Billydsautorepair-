# Billy D's Auto Repair

Static site (`index.html`) with an employee time clock backed by Supabase. Hosted on Vercel.

## Setup

### 1. Supabase
1. Create a project at supabase.com.
2. **SQL Editor** > New query > paste `supabase/schema.sql` > Run. Then run `supabase/002_quotes.sql` the same way (adds quote requests).
3. **Authentication > Users > Add user**: create Billy's manager login (email + password).
4. **Authentication > Sign In / Providers**: turn **off** "Allow new users to sign up" (any signed-in user is a manager).
5. **Project Settings > API**: copy the Project URL and the `anon` public key.
6. In `index.html`, paste them into `SUPABASE_URL` and `SUPABASE_ANON_KEY`.

### 2. GitHub
```bash
cd billyds-autorepair
git init && git add . && git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/billyds-autorepair.git
git push -u origin main
```

### 3. Vercel
1. vercel.com > Add New > Project > import the GitHub repo.
2. Framework preset: **Other**. No build command, no output directory. Deploy.
3. Project > Settings > Domains > add `billydsautorepair.com` and follow the DNS instructions at your registrar.

Every `git push` to `main` redeploys automatically.

## Using the clock
- Manager: Time Clock tab > Manager > sign in > add employees with a PIN.
- Manager: use **Edit** on any punch to fix times or delete it, or **Add missed punch**. New quote requests appear under Quote Requests.
- Employees: pick name, enter PIN, tap Clock In / Out (it toggles).
