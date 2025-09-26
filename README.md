# Post Test 4 - PBO
# Manajemen Perpustakaan Mini (Buku dan Majalah)

# Data diri
Nama : Mochammad Rezky Ramadhan 
NIM : 2409116029 Kelas : A 

# Deskripsi singkat
Program ini adalah pengembangan dari Post Test 3.
Masih bertema Manajemen Perpustakaan Mini, namun kini ditambahkan penerapan:
- **Abstraction** = menggunakan abstract class dan interface
- **Polymorphism** = melalui Overriding & Overloading
- **Nilai Tambah** = menggabungkan abstract class dan interface

Pengguna dapat:
- Menambahkan item baru (Buku / Majalah)
- Melihat daftar item
- Memperbarui data item
- Menghapus item
- Mencari item berdasarkan judul, penulis, atau tahun terbit

Fitur yang diterapkan:  
- **ArrayList** untuk menyimpan daftar item perpustakaan.
- **Packages** untuk pemisahan kode:  
  - `main` = entry point & menu utama.  
  - `model` = struktur data (`ItemPerpustakaan`, `Buku`, `Majalah`, `CetakInfo`) 
  - `service` = logika CRUD dan fitur tambahan.  
- **Minimal 3 class** sudah lebih (`Main`, `Buku`, `Majalah`, `ItemPerpustakaan`, `PerpustakaanService`, `CetakInfo`).  
- **Constructor** digunakan di semua class model.  
- **Access modifier** atribut `private`, method `public`.
- **Encapsulation** = semua atribut menggunakan getter & setter.
- **Inheritance:**
  - `ItemPerpustakaan` sebagai **superclass**
  - `Buku` dan `Majalah` sebagai **subclass**
- **Abstraction:**
  - `abstract class ItemPerpustakaan` = memiliki method abstrak `getInfo()`.
  - `interface CetakInfo` = diimplementasikan oleh `Buku` & `Majalah`.
- **Polymorphism:**
  - `Overriding` = `getInfo()` dan `toString()` di-override pada `Buku` dan `Majalah`.
  - `Overloading` = method `cariItem()` di `PerpustakaanService` memiliki 3 versi:
    - `cariItem(String keyword)`
    - `cariItem(int tahunTerbit)`
    - `cariItem()` (meminta input dari user).
- **Validasi input angka** agar program tidak error saat salah input.
- **Fitur search** untuk mencari berdasarkan judul (atau penulis khusus Buku).

Program ini juga sudah menerapkan MVC (Model-View-Controller):
- Model ItemPerpustakaan, Buku, Majalah
  - Menyimpan struktur data Buku dan Majalah di ItemPerpustakaan serta menyediakan constructor, getter, dan setter.
- Controller (Service.PerpustakaanService)  
  - Menangani logika CRUD (Create, Read, Update, Delete), validasi input, serta fitur pencarian.  
- View (Main.Main)
  - Berperan sebagai entry point program, menampilkan menu ke pengguna, menerima input, dan memanggil method dari PerpustakaanService. 

## Struktur Package

<img width="256" height="251" alt="{FF22972A-CB68-4EB5-B068-CE4DD7219D98}" src="https://github.com/user-attachments/assets/874b1c22-66f1-4b12-b3df-fbfa25ac72b2" />

---

# Alur program
## 1. Saat dijalankan, program menampilkan menu utama:
      1. Tambah item
      2. Lihat daftar item
      3. Update item
      4. Hapus item
      5. Cari item
      6. Keluar
## 2. Penjelasan Menu
1. **Tambah item**  
   - User pilih jenis (Buku / Majalah).
   - Input data sesuai jenis.
   - Data disimpan di ``ArrayList<ItemPerpustakaan>``.

2. **Lihat daftar item**  
   - Menampilkan semua item.
   - Jika kosong, muncul ``"Belum ada item yang tersimpan."``

3. **Update item**  
   - Pilih nomor item.
   - Jika Buku = update judul, penulis, tahun.
   - Jika Majalah = update judul, tahun, edisi. 

4. **Hapus item**  
   - Pilih nomor item = item dihapus dari list.

5. **Cari item**
   pilih mode pencarian:
     - Judul / Penulis
     - Tahun Terbit

6. **Keluar**  
   - Program berhenti dengan pesan:  
     ```
     Terima kasih sudah menggunakan sistem perpustakaan mini.
     ```

---

# Nilai Tambah
```
1. Abstraction:
   - Abstract class: ItemPerpustakaan (method abstrak getInfo()).
   - Interface: CetakInfo (method cetakDetail()).

2. Polymorphism:
   - Overriding:
     * getInfo() dan toString() pada Buku & Majalah.
   - Overloading:
     * cariItem(String keyword)
     * cariItem(int tahunTerbit)
     * cariItem() = memilih mode pencarian.

3. Kombinasi Abstraction & Interface:
   - Buku dan Majalah mewarisi ItemPerpustakaan (abstract class).
   - Buku dan Majalah juga mengimplementasikan CetakInfo (interface).
```



Contoh output:

<img width="259" height="139" alt="{908DC621-AC4D-45A4-8B1D-BDAB93176B00}" src="https://github.com/user-attachments/assets/dc77c999-575c-467d-bcd5-929ece7b951d" />


## Contoh Output
### 1. Tambah item (Buku dan Majalah)

<img width="290" height="280" alt="{A3011CCB-7780-4B7A-8760-DA1ED68F39BC}" src="https://github.com/user-attachments/assets/2970ab18-3960-4676-ad7d-0c5d73fc0336" />
<img width="302" height="273" alt="{075D002A-7A95-4A74-B560-EF3DFEAA6CCE}" src="https://github.com/user-attachments/assets/24875eaf-5898-4ba6-8cc3-41edb99354d2" />

### 2. Lihat item

<img width="352" height="218" alt="{E00CF2BE-E6E6-4B87-AEB2-8A88C1534C8D}" src="https://github.com/user-attachments/assets/6ffdeab7-d49a-4fd2-a30f-dcc56fcd6a94" />

### 3. Update item

<img width="354" height="294" alt="{34463E78-5E04-4862-92CC-13A246ED7969}" src="https://github.com/user-attachments/assets/f670fb83-bda5-46f1-ae7a-0c5fd317958c" />

### 4. Hapus item

<img width="384" height="245" alt="{AC6FDB3B-D08E-494A-BF6A-8D5E51A52A81}" src="https://github.com/user-attachments/assets/d742502e-f66c-4950-82ad-8ef99b7ef07a" />
<img width="361" height="191" alt="{71221A60-B5B2-4FBE-A06F-B505B84D68B6}" src="https://github.com/user-attachments/assets/ebc06962-3f01-4c48-b969-2424415b88ea" />

### 5. Cari item

<img width="359" height="226" alt="{22E1132F-FEA1-4A0D-AA07-0490FFF16E6E}" src="https://github.com/user-attachments/assets/3ddc5d6d-f749-4b76-8ace-35abb181798d" />
<img width="392" height="208" alt="{5C429DCA-E50E-4A11-A82E-CED437DF25E6}" src="https://github.com/user-attachments/assets/c84c5e6e-15e8-4a03-bdce-bb1e547e0e46" />
<img width="378" height="228" alt="{C366F8DA-3C4E-45FF-B7A9-1384BB41302C}" src="https://github.com/user-attachments/assets/0e2d6893-e148-4e4e-8638-20f8b78bc3d7" />
