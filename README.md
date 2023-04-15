# Lab5Web

### <u>Tugas Pertemuan Ke-6</u>
Hafidz Abdul Malik Arifin - 
312210205 - 
TI.21.C1

## OOP (Object-Oriented Programming) PHP
<p> OOP PHP adalah paradigma pemrograman yang berfokus pada konsep objek. Dalam OOP PHP, kita dapat membuat class, objek, properti, dan metode yang membantu dalam membuat kode yang modular, reusable, dan mudah dipelihara. Dalam OOP PHP, kita dapat menggunakan konsep pewarisan (inheritance) dan polimorfisme (polymorphism) untuk membuat kode lebih efisien dan mudah diubah. Pewarisan memungkinkan kita untuk membuat kelas baru yang mewarisi properti dan metode dari kelas yang ada sebelumnya, sementara polimorfisme memungkinkan kita untuk menggunakan metode yang sama pada objek yang berbeda dengan cara yang berbeda.</p> contoh program PHP yang menggunakan OOP adalah sebagai berikut:

```
<?php
    /** * Program sederhana pendefinisian class dan pemanggilan class. **/ 
    class Mobil { 
        private $warna; 
        private $merk; 
        private $harga; 
        public function __construct() { 
            $this->warna = "Biru"; 
            $this->merk = "BMW"; 
            $this->harga = "10000000"; 
        } 
        public function gantiWarna ($warnaBaru) { 
            $this->warna = $warnaBaru; 
        } 
        public function tampilWarna () {
            echo "Warna mobilnya : " . $this->warna; 
        } 
    } 
    // membuat objek mobil 
    $a = new Mobil(); 
    $b = new Mobil(); 
    // memanggil objek 
    echo "<b>Mobil pertama</b><br>"; 
    $a->tampilWarna(); 
    echo "<br>Mobil pertama ganti warna<br>";
    $a->gantiWarna("Merah"); 
    $a->tampilWarna(); 
    // memanggil objek 
    echo "<br><b>Mobil kedua</b><br>"; 
    $b->gantiWarna("Hijau"); 
    $b->tampilWarna(); 
?>

```

Dalam contoh di atas, kita membuat class "Mobil" dengan properti "warna", "merk", dan "harga", serta metode "tampilWarna()". Kemudian kita membuat objek dari kelas tersebut dan mengatur propertinya, dan akhirnya memanggil metodenya. Berikut tampilan dari coding tersebut:

![1](https://user-images.githubusercontent.com/113694802/232172908-dd057b59-8a48-48a8-a1ec-ac7e66a6f381.jpg)

Ini hanya contoh sederhana, namun OOP dapat digunakan untuk mengembangkan aplikasi yang lebih besar dan kompleks. OOP dapat membantu membuat kode yang lebih mudah dipahami, dipelihara, dan digunakan ulang, sehingga meningkatkan efisiensi dalam pengembangan perangkat lunak.

### Class Library
Class library merupakan pustaka kode program yang dapat digunakan bersama pada beberapa file yang berbeda (konsep modularisasi). Class library menyimpan fungsi-fungsi atau class object komponen untuk memudahkan dalam proses development aplikasi. berikut contoh pengkodean yang menggunakan class library :

```
<?php 
/** * Nama Class: Form * Deskripsi: CLass untuk membuat form inputan text sederhan **/ 
class Form { 
    private $fields = array(); 
    private $action; 
    private $submit = "Submit Form"; 
    private $jumField = 0; 
    public function __construct($action, $submit) { 
        $this->action = $action; 
        $this->submit = $submit; 
    } 
    public function displayForm() { 
        echo "<form action='".$this->action."' method='POST'>"; 
        echo '<table width="100%" border="0">'; 
        for ($j=0; $j<count($this->fields); $j++) { 
            echo "<tr><td align='right'>".$this->fields[$j]['label']."</td>";
            echo "<td><input type='text' name='".$this->fields[$j]['name']."'></td></tr>"; 
        } 
        echo "<tr><td colspan='2'>"; 
        echo "<input type='submit' value='".$this->submit."'></td></tr>"; 
        echo "</table>"; 
    } 
    public function addField($name, $label) { 
        $this->fields [$this->jumField]['name'] = $name;
        $this->fields [$this->jumField]['label'] = $label; 
        $this->jumField ++; 
    } 
} 
?>
```
selanjutnya kode tersebut, kita simpan dengan nama form.php. File tersebut tidak dapat dieksekusi langsung, karena hanya berisi deklarasi class. Untuk menggunakannya perlu dilakukan include pada file lain yang akan menjalankan dan harus dibuat instance object terlebih dulu. untuk itu, kita buat file form_input.php dengan kode sebagai berkut:

```
<?php 
    /** * Program memanfaatkan Program 10.2 untuk membuat form inputan sederhana. **/ 
    include "form.php"; 
    echo "<html><head><title>Mahasiswa</title></head><body>"; 
    $form = new Form("","Input Form"); 
    $form->addField("txtnim", "Nim"); 
    $form->addField("txtnama", "Nama"); 
    $form->addField("txtalamat", "Alamat"); 
    echo "<h3>Silahkan isi form berikut ini :</h3>"; 
    $form->displayForm(); 
    echo "</body></html>"; 
?>
```
sehingga menghasilkan tampilan sebagai berikut :

![2](https://user-images.githubusercontent.com/113694802/232172913-6dffd9b0-f1a7-4aa6-8c24-aa3b3c2ac72a.jpg)
