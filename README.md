# Portal Masjid Baitussalam v2

Rebuild mobile-first dengan Next.js, Supabase, GitHub, dan Vercel.

## 1. Supabase
1. Buat project Supabase.
2. Buka SQL Editor, jalankan `sql/schema.sql`.
3. Authentication > Users > Add user. Buat email/password admin.
4. SQL Editor, masukkan user admin ke profil:
```sql
insert into public.profiles(id,role,full_name)
select id,'admin','Pengelola Baitussalam' from auth.users where email='EMAIL_ADMIN_ANDA';
```

## 2. Lokal
Salin `.env.example` menjadi `.env.local`, lalu isi Project URL dan Publishable Key.
```bash
npm install
npm run dev
```

## 3. GitHub
```bash
git init
git add .
git commit -m "Initial Portal Masjid Baitussalam v2"
git branch -M main
git remote add origin https://github.com/USERNAME/portal-masjid-baitussalam.git
git push -u origin main
```

## 4. Vercel
Import repository GitHub. Tambahkan environment variables:
- `NEXT_PUBLIC_SUPABASE_URL`
- `NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY`

Deploy. Admin berada di `/admin`.

## Keamanan
RLS aktif. Transaksi publik hanya yang `published=true` dan belum dibatalkan. Penghapusan transaksi menggunakan `voided_at`. Jangan pernah memasukkan service role/secret key ke repository atau variabel `NEXT_PUBLIC_*`.

## Kredit
Hamba Allah
