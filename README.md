# Royal Portrait AI 👑 (Vercel)

Ubah selfie kamu jadi potret kerajaan dengan AI!

## Cara Deploy ke Vercel

### 1. Siapkan API Key fal.ai
- Daftar di https://fal.ai
- Buka Dashboard → Keys → Create Key
- Copy API key-nya (format: `fal_xxxxx:yyyyy`)

### 2. Deploy ke Vercel

**Opsi A: Via Git (Recommended)**
1. Push folder ini ke GitHub repo
2. Buka https://vercel.com → "Add New Project"
3. Import repo dari GitHub
4. Klik Deploy

**Opsi B: Via Vercel CLI**
```bash
npm i -g vercel
cd RoyalPortraitAI-Vercel
vercel
```

### 3. Set Environment Variable (PENTING!)
1. Di Vercel dashboard → pilih project kamu
2. Settings → Environment Variables
3. Tambah:
   - Name: `FAL_KEY`
   - Value: `fal_xxxxx:yyyyy` (API key dari fal.ai)
   - Environment: Production, Preview, Development (centang semua)
4. **Redeploy** project setelah set variable

### 4. Test
- Buka URL site kamu (xxx.vercel.app)
- Upload selfie → Pilih style → Generate

## Struktur Project

```
RoyalPortraitAI-Vercel/
├── public/
│   └── index.html          ← Frontend
├── api/
│   ├── submit.js            ← Submit job ke fal.ai queue
│   ├── status.js            ← Cek status job
│   └── result.js            ← Ambil hasil
├── vercel.json              ← Vercel config
└── README.md
```

## Vercel vs Netlify

| Fitur             | Vercel (free)        | Netlify (free)       |
|-------------------|----------------------|----------------------|
| Function timeout  | 10 detik             | 10 detik             |
| Function calls    | 100K / bulan         | 125K / bulan         |
| Bandwidth         | 100 GB               | 100 GB               |
| Deploy            | Git + CLI + Dashboard| Git + Drag-drop      |
| Custom domain     | ✅ Gratis            | ✅ Gratis            |

Keduanya sama baiknya untuk project ini karena polling dilakukan dari browser, bukan dari function.

## Biaya
- **Vercel**: Gratis (Hobby plan)
- **fal.ai**: ~$0.03-0.05 per gambar (pay-per-use)
