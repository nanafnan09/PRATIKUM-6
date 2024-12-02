# PRATIKUM-6
# SUB RUTIN / FUNGSI
Nama: Afnan Dika Ramadhan

NIM: 312410518

KELAS:TI24.A5

MATA KULIAH: Bahasa Pemograman

# Penjelasan Kode Program Manajemen Data Mahasiswa

Pengantar

Kode program manajemen data mahasiswa ini dibuat menggunakan bahasa pemrograman Python. Aplikasi ini bertujuan untuk membantu pengguna dalam melakukan operasi CRUD (Create, Read, Update, Delete) pada database mahasiswa secara interaktif melalui console.

Main Program (`main.py`)

Fitur-Fitur Utama

Program ini menyediakan lima fitur utama:

1.Tambah Data: Memungkinkan pengguna untuk menambahkan informasi mahasiswa baru.

2.Ubah Data: Memungkinkan pengguna untuk mengubah informasi mahasiswa yang sudah ada.

3.Hapus Data: Memungkinkan pengguna untuk menghapus informasi mahasiswa dari database.

4.Tampilkan Data: Memungkinkan pengguna untuk menampilkan semua informasi mahasiswa yang tersimpan.

5.Keluar: Menghentikan aplikasi.

Definisi Fungsi

Berikut adalah definisi fungsi-fungsi dasar yang digunakan dalam program:

`hitung_nilai_akhir(tugas, uts, uas)`

Fungsi ini menghitung nilai akhir mahasiswa berdasarkan bobot:

Tugas: 30%

UTS: 35%

UAS: 35%

```python

def hitung_nilai_akhir(tugas,uts,uas)
"""
Menghitung nilai akhir mahasiswa berdasarkan bobot:
Tugas: 30%, UTS: 35%, UAS: 35%

Parameters:
tugas(float):Nilai tugas mahasiswa.
uts(float): Nilai UTS mahasiswa.
uas(float): Nilai UAS mahasiswa.

returns:
float: Nilai akhir mahasiswa.

"""
return (tugas * 0.30) + (uts * 0.35) + (uas * 0.35)

```

`tampilkan menu()`

Fungsi ini menampilkan menu pilihan kepada pengguna.

```python

def tampilkan menu()
     print("\nMenu Pilihan:")
     print("1. Tambah Data")
     print("2. Ubah Data")
     print("3. Hapus Data")
     print("4. Tanpilkan Data")
     print("5. Keluar")
  
```
`tambah_data(data)`

Fungsi ini meminta input dari pengguna untuk menambahkan data mahasiswa baru ke dalam dictionary.
```python

def tambah_data(data):
      """
       Menambahkan data mahasiswa baru ke dalam dictionary
      
       Parameters:
        None
        
         Returns:
          None 
          
           """
       
       # Input nilai-nilai mahasiswa
       nama = input("Masukkan nama: ")
       tugas = float(input("Masukkan nilai tugas: "))
       uts= float( input (" Masukkan nilai UTS :"))
       uas= float( input ("Masukkan nilai UAS :"))
       
       # Hitung nilai akhir 
       nilai_akir= hitung_nilai_akhir( tugas ,uts,uas )
       
      # Simpan data ke dictionary 
      data [nama]= {
         "Tugas":tugas,
          "UTS ":uts ,
           "UAS ":uas ,  
             "Nilai_Akir ":"{:.2 f}".format(nilai_akir)
              }
              
             print(f"data Untuk {nama} berhasil Ditambahkan.")
```
`ubah_data(data)`

Fungsi ini memungkinkan pengguna untuk mengubah data mahasiswa yang sudah ada berdasarkan nama.

```python
def ubah_data(data):
    """
    Mengubah data mahasiswa berdasarkan nama.
    """
    nama = input("Masukkan nama data yang akan diubah: ")
    if nama in data:
        tugas = float(input("Masukkan nilai tugas baru: "))
        uts = float(input("Masukkan nilai UTS baru: "))
        uas = float(input("Masukkan nilai UAS baru: "))
        nilai_akhir = hitung_nilai_akhir(tugas, uts, uas)
        data[nama] = {'Tugas': tugas, 'UTS': uts, 'UAS': uas, 'Nilai Akhir': nilai_akhir}
        print(f"Data untuk {nama} berhasil diubah.")
    else:
        print(f"Data dengan nama {nama} tidak ditemukan.")
```
`hapus_data`

Fungsi Kode ini ialah untuk menghapus data mahasiswa
```python
def hapus_data(data):
    """
    Menghapus data mahasiswa berdasarkan nama.
    """
    nama = input("Masukkan nama data yang akan dihapus: ")
    if nama in data:
        del data[nama]
        print(f"Data untuk {nama} berhasil dihapus.")
    else:
        print(f"Data dengan nama {nama} tidak ditemukan.")
```
`tampilkan_data`
```python


def tampilkan_data(data):
    """
    Menampilkan seluruh data mahasiswa.
    """
    if data:
        print("\nDaftar Data Mahasiswa:")
        print(f"{'Nama':<15}{'Tugas':<10}{'UTS':<10}{'UAS':<10}{'Nilai Akhir':<15}")
        print("-" * 60)
        for nama, nilai in data.items():
            print(f"{nama:<15}{nilai['Tugas']:<10}{nilai['UTS']:<10}{nilai['UAS']:<10}{nilai['Nilai Akhir']:<15.2f}")
    else:
        print("Tidak ada data yang tersedia.")
```
`Fungsi Utama untuk menjalankan program`

Fungsi ini ialah untuk menjalankan kode 1,2,3,4,5 masing masing kode tersebut ada fungsi seperti tambah data,ubah data,hapus data,tampilkan data,dan keluar program.
```python

def main():
    """
    Fungsi utama untuk menjalankan program.
    """
    data_mahasiswa = {}
    while True:
        tampilkan_menu()
        pilihan = input("Pilih menu (1-5): ")
        if pilihan == '1':
            tambah_data(data_mahasiswa)
        elif pilihan == '2':
            ubah_data(data_mahasiswa)
        elif pilihan == '3':
            hapus_data(data_mahasiswa)
        elif pilihan == '4':
            tampilkan_data(data_mahasiswa)
        elif pilihan == '5':
            print("Keluar dari program.")
            break
        else:
            print("Pilihan tidak valid. Silakan coba lagi.")
```


 
