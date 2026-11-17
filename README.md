# Portal Masjid Baitussalam Premium
Next.js + Supabase, mobile-first, siap Vercel.

## Pasang
1. Upload seluruh isi folder ini ke repository GitHub.
2. Jalankan `sql/schema.sql` di Supabase SQL Editor.
3. Buat user di Supabase Authentication.
4. Masukkan profile admin:
```sql
insert into public.profiles(id,full_name,role)
select id,'Pengelola Baitussalam','admin' from auth.users where email='EMAIL_ADMIN';
```
5. Tambahkan di Vercel Environment Variables:
`NEXT_PUBLIC_SUPABASE_URL` dan `NEXT_PUBLIC_SUPABASE_ANON_KEY`.
6. Redeploy Vercel.

## Lokal
`npm install` lalu `npm run dev`.
