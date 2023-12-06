# Jarkom-Modul-4-B21-2023

# Anggota Kelompok

| **No** | **Nama**                         | **NRP**    |
| ------ | -------------------------------- | ---------- |
| 1      |Anneu Tsabita Putri               | 5025211026 |
| 2      | Cavel Ferrari                    | 5025211198 |

## Soal
<img width="759" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/4236613b-43ce-491f-9a7f-7722f55ca87f">
Untuk mengerjakan modul 4, kami mengimplementasikan CIDR dengan menggunakan GNS3 dan VLSM dengan menggunakan CPT

## CIDR
### Topologi pada GNS3
![topologiCIDR](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/ef6b8786-a2dd-4f77-b02f-9121d821497b)

### Subnetting
Teknik CIDR (Classless Inter-Domain Routing) didasarkan pada jumlah komputer atau host dalam suatu subnet. Berbeda dengan pendekatan tradisional, CIDR memungkinkan penggunaan subnet dengan panjang yang dapat disesuaikan, tidak terbatas pada kelas tertentu. CIDR memperoleh subnet besar dengan menggabungkan beberapa subnet kecil (agregasi), efisien dalam penggunaan alamat IP. Fleksibilitas ini meningkatkan efisiensi, mengurangi pemborosan, dan mendukung pertumbuhan jaringan yang dinamis.
![pp](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/b14434b4-b43b-41b0-8e17-d150eee59644)

### Rute dan Penggabungan
![rute](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/e369d722-a867-4462-aa3a-4c9961121700)
![satu](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/3946a928-b2e0-4fba-9372-eeecf6532c25)
![dua](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/3af6e54a-020d-4f10-9659-1ecafe0b0833)
![tiga](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/3decec00-57f2-4bba-bbfb-36afb0b86ac8)
![empat](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/5a081b6d-4874-4d18-9682-047db21c72ea)
![lima](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/7d6e1f93-8fd3-4c10-aa67-35824a20c0ae)
![enam](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/c511a243-5aa6-425c-9ce0-5d497be33a1b)
![tujuh](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/ba85e5a2-c39a-4453-b6d4-26ab7c34f2c0)
![delapan](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/2510e09a-89c3-40e2-8515-ae11cee1dc6c)

### Pembagian IP
Langkah selanjutnya adalah hitung pembagian IP dengan tree berdasarkan penggabungan subnet yang telah dilakukan. Dari proses penggabungan yang telah dilakukan, didapatkan sebuah subnet besar dengan netmask /14. Kali ini dapat menggunakan NID `10.19.0.0` dengan netmask `255.252.0.0`. Prefix IP yang digunakan sesuai Prefix IP Kelompok, dalam hal ini kelompok B21 adalah `10.19`.
![CIDR_B21](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/edc2f61e-e25d-4594-a286-5b115ac55fac)

Berdasarkan penghitungan, maka didapatkan pembagian IP sebagai berikut.
![ipcidr](https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/114276069/f15e86c2-f5c8-4370-8f19-d8ddfb71210b)

### Routing
Pada GNS3, routing dilakukan pada device router dengan perintah `route add -net <NID subnet> netmask <netmask> gw <IP gateway>`. Agar semua subnet dapat saling terhubung, akan ditambahkan konfigurasi static routing pada setiap router. Konfigurasi routing ini akan ditaruh ke dalam `/root/.bashrc` agar dapat dijalankan secara otomatis saat project diaktifkan. Konfigurasinya sebagai berikut:

- Aura
  ```
  route add -net 10.19.64.0 netmask 255.255.255.224 gw 10.19.128.2
  route add -net 10.19.32.0 netmask 255.255.255.252 gw 10.19.128.2
  route add -net 10.19.0.0 netmask 255.255.255.252 gw 10.19.128.2
  route add -net 10.19.8.0 netmask 255.255.248.0 gw 10.19.128.2
  route add -net 10.19.16.0 netmask 255.255.252.0 gw 10.19.128.2
  route add -net 10.19.28.0 netmask 255.255.255.252 gw 10.19.128.2
  route add -net 10.19.24.0 netmask 255.255.255.248 gw 10.19.128.2
  route add -net 10.20.128.0 netmask 255.255.255.0 gw 10.20.0.2
  route add -net 10.21.128.0 netmask 255.255.255.248 gw 10.22.0.2
  route add -net 10.21.192.0 netmask 255.255.255.252 gw 10.22.0.2
  route add -net 10.21.240.0 netmask 255.255.255.252 gw 10.22.0.2
  route add -net 10.21.248.0 netmask 255.255.255.192 gw 10.22.0.2
  route add -net 10.21.252.0 netmask 255.255.252.0 gw 10.22.0.2
  route add -net 10.21.224.0 netmask 255.255.254.0 gw 10.22.0.2
  route add -net 10.21.0.0 netmask 255.255.255.252 gw 10.22.0.2
  route add -net 10.21.48.0 netmask 255.255.255.0 gw 10.22.0.2
  route add -net 10.21.32.0 netmask 255.255.252.0 gw 10.22.0.2
  route add -net 10.21.64.0 netmask 255.255.255.252 gw 10.22.0.2
  ```

- Frieren
  ```
  route add -net 10.19.0.0 netmask 255.255.255.252 gw 10.19.32.2
  route add -net 10.19.8.0 netmask 255.255.248.0 gw 10.19.32.2\
  route add -net 10.19.16.0 netmask 255.255.252.0 gw 10.19.32.2
  route add -net 10.19.28.0 netmask 255.255.255.252 gw 10.19.32.2
  route add -net 10.19.24.0 netmask 255.255.255.248 gw 10.19.32.2
  ```
  
  - Flamme
  ```
  route add -net 10.19.8.0 netmask 255.255.248.0 gw 10.19.0.2
  route add -net 10.19.24.0 netmask 255.255.255.248 gw 10.19.28.2
  ```
    
- Eisen
  ```
  route add -net 10.21.240.0 netmask 255.255.255.252 gw 10.21.192.2
  route add -net 10.21.248.0 netmask 255.255.255.192 gw 10.21.192.2
  route add -net 10.21.252.0 netmask 255.255.252.0 gw 10.21.192.2
  route add -net 10.21.224.0 netmask 255.255.254.0 gw 10.21.192.2
  route add -net 10.21.48.0 netmask 255.255.255.0 gw 10.21.0.2
  route add -net 10.21.32.0 netmask 255.255.252.0 gw 10.21.0.2
  ```
  
- Linie
  ```
  route add -net 10.21.248.0 netmask 255.255.255.192 gw 10.21.240.2
  route add -net 10.21.252.0 netmask 255.255.252.0 gw 10.21.240.2
  ```
  
- Lawine
  ```
  route add -net 10.21.252.0 netmask 255.255.252.0 gw 10.21.248.3
  ```

## VLSM
## Topologi pada CPT
Tentukan subnet dari topologi, dengan metode VLSM.
<img width="1264" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/51597e48-f7d1-45aa-88ef-e069a1f43771">


### Rute dan Subnet Mask
Tentukan subnet mask dari masing-masing subnet, dengan jumlah host yang dibutuhkan yang tercamtum di topologi.


<img width="451" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/b7692b47-1602-4ae7-821d-da2f271f1b39">

### Konfigurasi IP
Buat perhitungan dari subnet mask dari masing-masing subnet untuk menentukan pembagian konfigurasi IP.
<img width="340" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/b55de240-c04d-4847-8bfc-aef7befe974e">

### VLSM Tree
Berdasarkan konfigurasi IP yang sudah didapatkan, gambarkan tree VLSM nya.
<img width="1260" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/c1d21c8b-1eb6-452f-a47f-a32d28bd2f4d">

### Konfigurasi di CPT
1) Subnetting
   Atur IP interface dari router yang mengarah ke client.
   (Contoh: Subnet A2, Frieren -> Switch3 -> LakeKorridor)
 <img width="524" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/374cedf3-1c9e-438c-94bf-10db33e2db1c">


   Atur IP interface dari client yang mengarah ke router. (Contoh: Subnet A2, LakeKorridor -> Switch3 -> Frieren)

<img width="522" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/a567b04b-5425-4cbe-a0dc-e7a2c0e48a3d">

  <img width="515" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/f44ba9dd-50ec-4840-b43f-ab18eff16d96">

   Atur IP interface dari router utama yang mengarah ke router subnet.
   (Contoh: Subnet A1, Aura -> Frieren)
   <img width="523" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/34ae4e98-d58c-4b84-8a70-838582da80a5">

   Atur IP interface dari router subnet yang mengarah ke router utama.
   (Contoh: Subnet A1, Frieren -> Aura)
   <img width="522" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/90753842-8164-42a8-bf77-0f7f3cbd5fdb">

   Lakukan untuk semua subnet.

2) Routing
   Atur default routing dari router subnet ke router utama.
   (Contoh: Frieren -> Aura)
   <img width="522" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/2b5de707-1929-4391-be4a-a423d4fc412a">

   Atur routing dari router utama ke subnet client.
   (Contoh: Subnet A2, Aura -> Frieren)

   <img width="522" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/a45f04c5-46cd-427f-b0e4-294c53d5ff04">

   Lakukan untuk semua subnet.
   
   
  
   
