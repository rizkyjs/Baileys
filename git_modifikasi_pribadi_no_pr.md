
# 🧑‍💻 Panduan Git Lengkap – Modifikasi Pribadi dari Fork (Tanpa Pull Request)

Dokumentasi ini dibuat khusus untuk kamu yang ingin **memodifikasi project hasil fork** dari GitHub untuk **pemakaian pribadi** saja, tanpa perlu membuat Pull Request ke repo aslinya.

---

## ✅ 1. Setup Awal (Dilakukan Sekali)

```bash
# Clone dari repo fork kamu
git clone https://github.com/rizkyjs/Baileys.git
cd Baileys

# Tambahkan remote ke repo asli
git remote add upstream https://github.com/WhiskeySockets/Baileys.git

# Buat branch pribadi untuk modifikasi
git checkout -b Baileys/rizky-custom
```

---

## 🔁 2. Alur Kerja Sebelum Mulai Ngoding (Setiap Kali Mau Mulai)

Selalu ambil update terbaru dari repo asli agar tidak ketinggalan perubahan penting.

```bash
# Pindah ke branch master
git checkout master

# Tarik update dari repo asli
git pull upstream master

# Pindah ke branch pribadi
git checkout Baileys/rizky-custom

# Gabungkan perubahan terbaru dari master ke branch kamu
git merge master
```

---

## 🛠️ 3. Alur Saat Sedang Ngoding

```bash
# Lihat status perubahan
git status

# Lihat isi perubahan (opsional)
git diff

# Tambahkan perubahan ke staging
git add .

# Commit perubahan
git commit -m "Deskripsi perubahan fitur pribadi"
```

---

## ☁️ 4. Push ke Fork GitHub (Backup Online Pribadi)

```bash
git push origin Baileys/rizky-custom
```

> Ini akan menyimpan branch modifikasi kamu di GitHub milikmu sendiri.

---

## 🔄 5. Sinkronisasi Lagi di Lain Waktu

Setelah beberapa hari/minggu dan repo asli ada update, ulangi langkah ini:

```bash
git checkout master
git pull upstream master

git checkout Baileys/rizky-custom
git merge master
```

---

## 🧪 6. Kembali ke Commit Sebelumnya (Opsional)

```bash
# Lihat daftar commit
git log --oneline

# Checkout ke commit tertentu (sementara)
git checkout [id_commit]

# Kembali ke branch utama
git checkout Baileys/rizky-custom

# Reset permanen ke commit lama
git reset --hard [id_commit]
```

---

## 🧹 7. Menghapus Branch (Jika Sudah Tidak Digunakan)

```bash
# Hapus branch lokal
git branch -d Baileys/rizky-custom

# Hapus branch dari GitHub
git push origin --delete Baileys/rizky-custom
```

---

## 🔄 8. Bedanya `git pull` vs `git fetch`

| Perintah     | Apa yang Dilakukan                                                                       | Otomatis Merge? | Kapan Digunakan                  |
|--------------|--------------------------------------------------------------------------------------------|-----------------|----------------------------------|
| `git fetch`  | Mengambil update dari remote **tanpa menggabungkan** ke branch aktif                      | ❌ Tidak         | Untuk review dulu sebelum merge |
| `git pull`   | Mengambil update dari remote **dan langsung menggabungkan** ke branch aktif               | ✅ Ya            | Kalau ingin langsung update      |

---

## 📌 Istilah Penting

- `origin` = repo fork kamu di GitHub
- `upstream` = repo asli (WhiskeySockets/Baileys)
- `checkout` = pindah branch atau commit
- `merge` = gabungkan isi branch lain ke branch aktif
- `commit` = simpan snapshot perubahan
- `push` = kirim commit ke GitHub
- `pull` = ambil update dari remote
- `fetch` = ambil update tanpa gabung otomatis

---

### ✅ Kesimpulan

Kamu bebas ngoding, commit, dan push ke repo pribadi (`rizkyjs/Baileys`) tanpa mengganggu repo asli.  
Tidak perlu membuat Pull Request karena ini murni untuk pemakaian pribadi.

Selamat ngoding! 🚀
