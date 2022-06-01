## Nama     : Revano Arya Saputra
## NIM      : 312010461
## Kelas    : TI.20.A.1
## Matkul   : Pemograman Web

## Pertemuan 11 Lab 10 Web <b>

Di pertemuan 11 ini kita akan mempelajari PHP OOP

## Langkah - langkah Praktikum <b>

## 1. Menjalankan XAMPP SERVER <b>

![1](https://user-images.githubusercontent.com/101621068/170504646-4af9a3e7-e82f-4c8f-9ea6-713828e95607.png)

## 2. Buat Folder Baru Bernama lab10_php_oop <b>

![2](https://user-images.githubusercontent.com/101621068/170504903-e4a4199d-63ea-4938-8fff-4ea0e4716e1c.png)

Setelah membuat file, lalu jalankan dengan mengakses URL :
http://localhost/lab10_php_oop/mobil.php

## 3. Membuat File Baru Bernama mobil.php <b>
Menggunakan Class dan Pemanggilan Class

Code :
```php
<?php
/**
* Program sederhana pendefinisian class dan pemanggilan class.
**/

class Mobil
{
    private $warna;
    private $merk;
    private $harga;

    public function __construct()
    {
    $this->warna = "Biru";
    $this->merk = "BMW";
    $this->harga = "10000000";
    }

    public function gantiWarna ($warnaBaru)
    {
        $this->warna = $warnaBaru;
    }

    public function tampilWarna ()
    {
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

Berikut hasil Outputnya :

![3](https://user-images.githubusercontent.com/101621068/170505578-ed34f0e2-230f-4004-980a-ce18c6d41bb2.png)

## 4. Membuat File Baru Bernama form.php <b>

Code :
```php
<?php
/**
* Nama Class: Form
* Deskripsi: CLass untuk membuat form inputan text sederhana
**/

class Form
{
    private $fields = array();
    private $action;
    private $submit = "Submit Form";
    private $jumField = 0;

    public function __construct($action, $submit)
    {
        $this->action = $action;
        $this->submit = $submit;
    }
    
    public function displayForm()
    {
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

    public function addField($name, $label)
    {
        $this->fields [$this->jumField]['name'] = $name;
        $this->fields [$this->jumField]['label'] = $label;
        $this->jumField ++;
    }
}

?>
```

## 5. Buat File Baru Bernama form_input.php <b>

Membuat metode input dengan iclude untuk target halaman

Code :
```php
<?php
/**
* Program memanfaatkan Program 10.2 untuk membuat form inputan sederhana.
**/

include "form.php";

echo "<html><head><title>Mahasiswa</title></head><body>";
$form = new Form("","Input Form");
$form->addField("txtnim", " <b> Nim : </b> ");
$form->addField("txtnama", " <b> Nama : </b> ");
$form->addField("txtalamat", "<b> Alamat :</b>");
echo "<h3>Silahkan isi form berikut ini :</h3>";
$form->displayForm();
echo "</body></html>";

?>
```

Berikut hasil Output nya :

![4](https://user-images.githubusercontent.com/101621068/170508521-1e5f9b7a-0829-4589-8e92-2b2be7bd151c.png)

# TERIMAKASIH <b>
