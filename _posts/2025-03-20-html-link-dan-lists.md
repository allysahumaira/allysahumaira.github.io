---
layout: post
title: "HTML link dan lists"
---

penjelasan tentang link dan list pada HTML

![HTML link dan lists](/assets/images/html.link&lists.jpg)

Dalam HTML, link dan list adalah dua elemen dasar yang sangat penting untuk membangun dan mengorganisasi konten di halaman web. Berikut adalah penjelasan umum mengenai keduanya:

### **1. Linked List dalam Konteks Pengembangan Web**
Apa Itu Linked List?
Linked List adalah struktur data yang terdiri dari elemen-elemen yang disebut node. Setiap node menyimpan dua bagian penting:

#### **1.1. Data**
Menyimpan nilai atau informasi yang ingin disimpan dalam node.

#### **1.2. Pointer/Reference**
Menyimpan referensi atau alamat memori dari node berikutnya dalam list (untuk singly linked list), atau bisa juga menyimpan referensi ke node sebelumnya dan node berikutnya (pada doubly linked list).

Keunikan utama dari linked list adalah bahwa elemen-elemen tersebut tidak perlu disimpan secara berurutan di memori. Sebagai contoh, dalam array data disimpan dalam blok memori yang berurutan, sedangkan dalam linked list, data di-link-kan melalui pointer.

#### **1.3. Jenis-jenis Linked List**
Singly Linked List: Setiap node hanya menyimpan pointer ke node berikutnya.

#### **1.4. Doubly Linked List**
Setiap node menyimpan dua pointer, satu ke node berikutnya dan satu lagi ke node sebelumnya.

#### **1.5. Circular Linked List**
Node terakhir mengarah kembali ke node pertama, membentuk siklus.

**Kapan Linked List Digunakan dalam Web Development?**
 
Pada pengembangan aplikasi web, linked list mungkin tidak sering digunakan secara langsung, tetapi konsep ini sangat berguna dalam hal:

* Pengelolaan Data Dinamis: Misalnya dalam aplikasi yang membutuhkan pengelolaan data yang sering berubah atau di-update (seperti daftar komentar pada situs web atau forum).

* Manajemen Memori: Karena linked list tidak memerlukan penyimpanan berurutan seperti array, struktur ini bisa lebih efisien dalam situasi tertentu.

* Penyusunan Antrian atau Stack: Linked list bisa digunakan untuk implementasi queue (antrian) atau stack (tumpukan), yang mungkin digunakan dalam pengolahan data pada aplikasi web.

Contoh Implementasi Linked List di JavaScript
Misalnya, kita membuat sebuah Singly Linked List untuk mengelola daftar tugas di aplikasi web:

javascript
Copy
class Node {
    constructor(data) {
        this.data = data;
        this.next = null; // Pointer ke node berikutnya
    }
}

class LinkedList {
    constructor() {
        this.head = null; // Menyimpan node pertama
    }

    // Menambahkan node baru di akhir linked list
    add(data) {
        const newNode = new Node(data);
        if (!this.head) {
            this.head = newNode;
        } else {
            let current = this.head;
            while (current.next) {
                current = current.next; // Menelusuri hingga node terakhir
            }
            current.next = newNode;
        }
    }

    // Menampilkan semua data di linked list
    display() {
        let current = this.head;
        while (current) {
            console.log(current.data);
            current = current.next;
        }
    }
}

const taskList = new LinkedList();
taskList.add("Tugas 1");
taskList.add("Tugas 2");
taskList.add("Tugas 3");

taskList.display(); // Menampilkan semua tugas
Dalam contoh di atas, kita memiliki tugas yang disusun dalam linked list, dan kita bisa menambah atau menghapus tugas dengan lebih efisien pada posisi tertentu, tanpa perlu memindahkan elemen lain.

### **2. List dalam Pengembangan Web**
Apa Itu List?
Dalam konteks pengembangan web, istilah list biasanya mengacu pada jenis struktur data yang menyimpan koleksi elemen dalam urutan tertentu. List ini bisa berupa struktur data yang lebih sederhana seperti array atau lebih kompleks seperti linked list.

Ada beberapa jenis list yang sering digunakan dalam pengembangan web:

#### **2.1. Array/List dalam JavaScript**

Array di JavaScript adalah jenis list yang paling umum. Array menyimpan elemen dalam urutan tertentu dan memungkinkan akses cepat ke elemen berdasarkan indeks.

List di JavaScript seringkali digunakan untuk menyimpan data seperti daftar nama produk, komentar pengguna, atau item dalam sebuah menu dinamis.

Contoh penggunaan array/list di JavaScript:

javascript
Copy
let products = ["Laptop", "Smartphone", "Tablet"];
console.log(products[0]); // Output: Laptop
console.log(products.length); // Output: 3
Array vs Linked List:

Array memiliki akses indeks langsung yang cepat (O(1) waktu akses).

Linked List membutuhkan waktu linear (O(n)) untuk mengakses elemen tertentu, karena kita perlu menelusuri dari node pertama hingga node yang dicari.

#### **2.2. Penggunaan List dalam Web Development**
Data Dinamis: List sering digunakan dalam pengelolaan data dinamis yang bisa berubah, seperti daftar komentar pada halaman web, item dalam keranjang belanja, atau data yang disimpan di server yang dikirim melalui AJAX atau API.

#### **2.3. Interaksi Pengguna**
List sering kali digunakan untuk menyimpan dan menampilkan data yang berhubungan dengan interaksi pengguna, seperti formulir yang berisi daftar pilihan atau pengaturan aplikasi.

Contoh penggunaan list dalam pengembangan web (JavaScript):

javascript
Copy
// Daftar komentar pada halaman web
let comments = ["Great post!", "Very informative.", "Thanks for sharing!"];

// Menambahkan komentar baru
comments.push("Interesting perspective!");

// Menampilkan komentar
comments.forEach(comment => {
    console.log(comment);
});
List dalam HTML
Dalam HTML, kita bisa menggunakan elemen-elemen seperti <ul>, <ol>, dan <li> untuk membuat list yang tampil di halaman web:

html
Copy
<ul>
    <li>Laptop</li>
    <li>Smartphone</li>
    <li>Tablet</li>
</ul>
