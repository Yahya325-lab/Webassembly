# Webassembly
<br><br>
WebAssembly (wasm) format instruksi yang dirancang agar bisa menjalankan aplikasi di browser dengan performa setara dengan apllikasi aslinya. Tujuannya adalah memungkinkan developer
menjalankan kode dengan cepat di web. WebAssembly biasanya menggunakan bahasa tingkat tinggi seperti C, C++, Rust, bisa dikombinasikan juga dengan JavaScript.

Disini saya mengeksperimen membuat 1 WebAssembly bertemakan kalkulator sederhana menggunakan Html dan C.
<br><br>
# Langkah Pertama : Penginstallan 
<br><br>
Pertama clone dulu emsdk nya di terminal

![image](https://github.com/user-attachments/assets/9b7b1b70-4d3c-4892-92b4-7a5be9f29f97)

Setelah itu install ini di terminal

![image](https://github.com/user-attachments/assets/ca32993a-c1fb-48ee-aa52-0743d1a91188)

Setelah itu cek sudah terinstall apa belum

![image](https://github.com/user-attachments/assets/1095d33f-8a6c-4fbf-88fe-c09c5f6373cb)

Kalau sudah nanti muncul folder dengan nama emsdk di Vscode nya

![image](https://github.com/user-attachments/assets/6581e501-4189-480b-840d-018ab5308e8b)

Setelah itu harus di compile emcc nya, ketik ini di terminal
```bash
emcc main.c -s WASM=1 -s EXPORTED_FUNCTIONS="['_add']" -s EXPORTED_RUNTIME_METHODS='["cwrap", "ccall"]' -o main.js
```
Kalo udah di compile maka akan muncul 2 file baru, 1 file main.js dan 1 file main.wasm

![image](https://github.com/user-attachments/assets/3e3df7e4-e3b1-463c-a87e-99cd4c369fbf)
<br><br>

# Langkah Kedua : Pembuatan
<br><br>

Buat file baru di folder emsdk nya dengan nama main.c
![image](https://github.com/user-attachments/assets/e06003aa-f73c-4cfb-b2d0-66afb8879ab4)
<br><br>

Fungsi add fungsi penjumlahan biasa, sedangkan EMSCRIPTEN_ALIVE membuat fungsi tetap bisa diakses oleh JavaScript setelah di compile

<br><br>

Kemudian buat file index.html
![image](https://github.com/user-attachments/assets/93e29ce1-6926-451d-a3da-499711733fc8)

<br><br>

Di dalam html ini juga terdapat JavaScript dan CSS nya

<br><br>

# Langkah Ketiga : Hasil
<br><br>

Jalankan Html nya di web dan akan muncul hasilnya seperti ini 
![image](https://github.com/user-attachments/assets/bd24b163-ef07-4485-8298-dff4fc1e5aee)

<br><br>

Fitur di WebAssembly ini ada banyak, yaitu:
<br><br>

<br>

| Fitur                   | Letaknya                     | Penjelasan                                                   |
|------------------------|------------------------------|--------------------------------------------------------------|
|  Support multi bahasa | Fungsi C + akses dari JS      | Kombinasi C dan JavaScript                                   |
|  Performa tinggi    | WebAssembly bytecode         | Fungsi `add()` dijalankan sangat cepat lewat Wasm              |
|  Support banyak browser     | `main.wasm` dijalankan di browser | Semua browser modern bisa baca `.wasm`                        |
|  Saling bekerja sama    | `EMSCRIPTEN_KEEPALIVE`, `cwrap` | Integrasi erat Wasm dan JavaScript                    |










