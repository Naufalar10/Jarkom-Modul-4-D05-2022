# Lapres Jarkom Modul 4 Kelompok D05 #

| Nama Praktikan  | NRP Praktikan |
| ------------- | ------------- |
| Ichlasul Hasanat  | 5025201091  |
| Haidar Fico Ramadhan Aryputra | 5025201185  |
| Naufal Ariq Putra Yosyam | 5025201112 |

# SOAL

1. Soal shift dikerjakan pada Cisco Packet Tracer dan GNS3 menggunakan metode perhitungan CLASSLESS yang berbeda. Keterangan: Bila di CPT menggunakan VLSM, maka di GNS3 menggunakan CIDR atau Sebaliknya
2. Jika tidak ada pemberitahuan revisi soal dari asisten, berarti semua soal BERSIFAT BENAR dan DAPAT DIKERJAKAN.
3. Untuk di GNS3 CLOUD merupakan NAT1 jangan sampai salah agar bisa terkoneksi internet.
4. Pembagian IP menggunakan Prefix IP yang telah ditentukan pada modul pengenalan
5. Pembagian IP dan routing harus SE-EFISIEN MUNGKIN.

![image](https://user-images.githubusercontent.com/88977654/204091879-4326a6e7-68be-4449-a910-52dd6484f5cc.png)

------

## Buat Topologi

### Menambah ethernet pada Router

Sebelum membuat topologi, kita perlu menambahkan lubang ethernet ke beberapa router. Karena sebuah router hanya memiliki 2 lubang ethernet. Router yang membutuhkan router tambahan yaitu `The Minister`, `The Order`, `The Resonance`, `The Instrument`, `The Profound`, dan `The Firefist`. Pada bagian 'physical', kami akan menambahkan modul yaitu `NM-2FE2W` karena hanya membutuhkan 2 tambahan ethernet.

![image](https://user-images.githubusercontent.com/88977654/204091760-1e09e2b8-315c-42f6-934d-012967ebcb58.png)

Namun khusus untuk `The Resonance`, router ini membutuhkan 3 lubang ethernet. Maka kami menggunakan modul `NM-4E`

![image](https://user-images.githubusercontent.com/88977654/204092182-5e1730ff-3283-416b-ba01-a2b9cb1c287d.png)

# VLSM (CPT)

## Pembagian Subnet

![image](https://user-images.githubusercontent.com/88977654/204091389-25490247-1819-4bc1-8846-ac50107c88f8.png)

## Jumlah Alamat IP

| Subnet | Jumlah IP | Netmask |
| ------------- |:-------------:| -----:|
|A1| 1001	|/22|
|A2|	2	|/30|
|A3|	251	|/24|
|A4|	2	|/30|
|A5|	51	|/26|
|A6|	2	|/30|
|A7|	2	|/30|
|A8|271	|/23|
|A9|	2	|/30|
|A10|	121	|/25|
|A11|	2	|/30|
|A12|	121	|/25|
|A13|	71	|/25|
|A14|	2	|/30|
|A15|	212	|/24|
|A16|	501	|/23|
|A17|	2	|/30|
|A18|	2	|/30|
|Total|	2618	|/20|

## Pembagian IP Berdasarkan NID

![image](https://user-images.githubusercontent.com/88977654/204091680-35d928d8-8b79-43fc-9d4d-8cdc77378682.png)

## Pembagian IP pada CPT

![image](https://user-images.githubusercontent.com/88977654/204093142-6fe35868-12ec-4feb-b50a-d6d54324347e.png)

## Routing

### The Dauntless
```
192.187.0.0/22 via 192.187.11.193
192.187.11.128/26 via 192.187.11.193
192.187.6.0/23 via 192.187.11.193
192.187.10.0/25 via 192.187.11.193
192.187.10.128/25 via 192.187.11.193
192.187.11.0/25 via 192.187.11.193
192.187.9.0/24 via 192.187.11.193
192.187.4.0/23 via 192.187.11.193
192.187.11.220/30 via 192.187.11.193
192.187.11.224/30 via 192.187.11.193
```

### The Minister
```
192.187.8.0/24 via 192.187.11.194
192.187.11.128/26 via 192.187.11.198
192.187.6.0/23 via 192.187.11.198
192.187.10.0/25 via 192.187.11.198
192.187.10.128/25 via 192.187.11.198
192.187.11.0/25 via 192.187.11.198
192.187.9.0/24 via 192.187.11.198
192.187.4.0/23 via 192.187.11.198
192.187.11.220/30 via 192.187.11.198
192.187.11.224/30 via 192.187.11.198
```

### The Order
```
192.187.8.0/24 via 192.187.11.197
192.187.0.0/22 via 192.187.11.197
192.187.6.0/23 via 192.187.11.202
192.187.10.0/25 via 192.187.11.202
192.187.10.128/25 via 192.187.11.202
192.187.11.0/25 via 192.187.11.202
192.187.9.0/24 via 192.187.11.202
192.187.4.0/23 via 192.187.11.202
192.187.11.220/30 via 192.187.11.202
192.187.11.224/30 via 192.187.11.202
```

### The Resonance
```
192.187.8.0/24 via 192.187.11.201
192.187.0.0/22 via 192.187.11.201
192.187.11.128/26 via 192.187.11.201
192.187.6.0/23 via 192.187.11.206
192.187.10.0/25 via 192.187.11.210
192.187.10.128/25 via 192.187.11.210
192.187.11.0/25 via 192.187.11.210
192.187.9.0/24 via 192.187.11.210
192.187.4.0/23 via 192.187.11.210
192.187.11.220/30 via 192.187.11.210
```

### The Magical
```
192.187.8.0/24 via 192.187.11.205
192.187.0.0/22 via 192.187.11.205
192.187.11.128/26 via 192.187.11.205
192.187.10.0/25 via 192.187.11.205
192.187.10.128/25 via 192.187.11.205
192.187.11.0/25 via 192.187.11.205
192.187.9.0/24 via 192.187.11.205
192.187.4.0/23 via 192.187.11.205
192.187.11.220/30 via 192.187.11.205
192.187.11.224/30 via 192.187.11.205
```

### The Instrument
```
192.187.8.0/24 via 192.187.11.209
192.187.0.0/22 via 192.187.11.209
192.187.11.128/26 via 192.187.11.209
192.187.6.0/23 via 192.187.11.209
192.187.11.224/30 via 192.187.11.209
192.187.10.128/25 via 192.187.11.214
192.187.11.0/25 via 192.187.11.214
192.187.9.0/24 via 192.187.11.218
192.187.4.0/23 via 192.187.11.218
192.187.11.220/30 via 192.187.11.218
```

### The Profound
```
192.187.8.0/24 via 192.187.11.213
192.187.0.0/22 via 192.187.11.213
192.187.11.128/26 via 192.187.11.213
192.187.6.0/23 via 192.187.11.213
192.187.11.224/30 via 192.187.11.213
192.187.10.0/25 via 192.187.11.213
192.187.9.0/24 via 192.187.11.213
192.187.4.0/23 via 192.187.11.213
192.187.11.220/30 via 192.187.11.213
```

### The Firefist
```
192.187.8.0/24 via 192.187.11.217
192.187.0.0/22 via 192.187.11.217
192.187.11.128/26 via 192.187.11.217
192.187.6.0/23 via 192.187.11.217
192.187.11.224/30 via 192.187.11.217
192.187.10.0/25 via 192.187.11.217
192.187.10.128/25 via 192.187.11.217
192.187.11.0/25 via 192.187.11.217
192.187.11.220/30 via 192.187.9.253
```

### The Queen
```
192.187.8.0/24 via 192.187.9.254
192.187.0.0/22 via 192.187.9.254
192.187.11.128/26 via 192.187.9.254
192.187.6.0/23 via 192.187.9.254
192.187.10.0/25 via 192.187.11.254
192.187.10.128/25 via 192.187.9.254
192.187.11.0/25 via 192.187.9.254
192.187.4.0/23 via 192.187.9.254
192.187.11.224/30 via 192.187.9.254
```

# CIDR - GNS3
## Penggabungan Subnet
Kita melakukan penggabungan subnet-subnet paling bawah dalam topologi yaitu dimulai dari subnet yang paling jauh dengan cloud/nat hingga hanya memiliki 1 subnet (induk).
![1.1](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/1.png)
![1.2](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/2.png)
![1.3](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/3.png)
![1.4](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/4.png)
![1.5](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/5.png)
![1.6](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/6.png)
![1.7](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/7.png)
![1.8](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/8.png)
![1.9](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/9.png)
![1.10](https://github.com/Naufalar10/Jarkom-Modul-4-D05-2022/blob/main/jarkom_4/10.png)
