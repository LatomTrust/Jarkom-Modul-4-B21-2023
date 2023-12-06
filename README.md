# Jarkom-Modul-4-B21-2023

# Anggota Kelompok

| **No** | **Nama**                         | **NRP**    |
| ------ | -------------------------------- | ---------- |
| 1      |Anneu Tsabita Putri               | 5025211026 |
| 2      | Cavel Ferrari                    | 5025211198 |

## Topologi
<img width="759" alt="image" src="https://github.com/LatomTrust/Jarkom-Modul-4-B21-2023/assets/91776952/4236613b-43ce-491f-9a7f-7722f55ca87f">

## VLSM
## Topologi CPT
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
   
   
  
   
