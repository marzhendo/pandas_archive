# Pandas Archive - Catatan Pembelajaran

Repository ini berisi kumpulan latihan dan pembelajaran library **Pandas** menggunakan Python.

---

## Chapter 1: Dasar-Dasar Pandas

### 📚 Konsep yang Dipelajari

#### 1. Membuat DataFrame
- **Dari Dictionary**: Cara paling umum membuat DataFrame dengan struktur `{kolom: [values]}`
- **Dari List of Lists**: Alternatif dengan menentukan data dan nama kolom secara terpisah

```python
# Dari Dictionary
df = pd.DataFrame({'kolom1': [val1, val2], 'kolom2': [val3, val4]})

# Dari List of Lists
data = [[val1, val2], [val3, val4]]
df = pd.DataFrame(data, columns=['kolom1', 'kolom2'])
```

#### 2. Eksplorasi Data
| Method | Fungsi |
|--------|--------|
| `df.head(n)` | Menampilkan n baris pertama |
| `df.tail(n)` | Menampilkan n baris terakhir |
| `df.info()` | Menampilkan informasi struktur DataFrame |
| `df.describe()` | Statistik deskriptif (mean, std, min, max, dll) |
| `df.dtypes` | Menampilkan tipe data setiap kolom |
| `df.shape` | Menampilkan dimensi DataFrame (baris, kolom) |

#### 3. Seleksi Kolom
- **Series (Single Column)**: Mengambil 1 kolom saja
  ```python
  df['nama_kolom']  # atau df.nama_kolom
  ```
- **Multiple Columns**: Mengambil lebih dari 1 kolom
  ```python
  df[['kolom1', 'kolom2', 'kolom3']]
  ```

#### 4. Manipulasi Data

**Menambah Kolom Baru:**
```python
df['kolom_baru'] = df['kolom1'] * df['kolom2']
```

**Rename Kolom:**
```python
df = df.rename(columns={'nama_lama': 'nama_baru'})
```

**Drop Kolom/Baris:**
```python
df.drop('nama_kolom', axis=1)  # Hapus kolom
df.drop(index_baris, axis=0)    # Hapus baris
```

#### 5. Sorting Data
```python
# Ascending (kecil ke besar)
df.sort_values(by='nama_kolom', ascending=True)

# Descending (besar ke kecil)
df.sort_values(by='nama_kolom', ascending=False)
```

#### 6. Filtering Data

**Single Condition:**
```python
df[df['kolom'] > nilai]
df[df['kolom'] == 'nilai_string']
```

**Multiple Conditions:**
```python
# AND (&) - semua kondisi harus terpenuhi
df[(df['kolom1'] > 100) & (df['kolom2'] < 50)]

# OR (|) - salah satu kondisi terpenuhi
df[(df['kolom1'] > 100) | (df['kolom2'] < 50)]
```

#### 7. Handling Missing Values (NaN)
```python
import numpy as np

# Mendeteksi missing values
df.info()  # Terlihat dari non-null count

# Menghapus baris dengan NaN
df.dropna()
```

#### 8. Input/Output CSV
```python
# Membaca CSV
df = pd.read_csv('nama_file.csv')

# Menyimpan ke CSV
df.to_csv('nama_file.csv', index=False)
```

---

### 📁 Daftar File Latihan

| File | Deskripsi |
|------|-----------|
| `contact_list.ipynb` | Membuat DataFrame, read/write CSV, filtering |
| `apps_data.ipynb` | Menambah kolom, sorting, rename kolom |
| `data_apps.ipynb` | Eksplorasi data (head, tail, info, describe), drop kolom/baris |
| `dungeon.ipynb` | Series vs Multiple Columns, filtering dengan multiple kondisi |
| `fate_series.ipynb` | Membuat DataFrame, export CSV, akses kolom |
| `movie.ipynb` | Membuat DataFrame, sorting data |
| `other_movie.ipynb` | Handling missing values (np.nan) |
| `toko_gadget.ipynb` | Operasi aritmatika antar kolom, filtering premium products |

---

### ✅ Evaluasi Pembelajaran

| Topik | Status |
|-------|--------|
| Membuat DataFrame dari berbagai sumber | ✅ Paham |
| Eksplorasi data dengan info(), describe(), shape | ✅ Paham |
| Seleksi kolom (Series & Multiple Columns) | ✅ Paham |
| Manipulasi kolom (add, rename, drop) | ✅ Paham |
| Sorting data | ✅ Paham |
| Filtering dengan single/multiple conditions | ✅ Paham |
| Read/Write file CSV | ✅ Paham |
| Handling missing values | ✅ Paham |

---

### 🎯 Topik Selanjutnya (Chapter 2)

- Groupby dan Aggregasi
- Merge dan Join DataFrame
- Pivot Tables
- Advanced Filtering dengan query()
- Apply dan Lambda Functions
- Data Cleaning lebih lanjut

---

*Last updated: February 2026*
