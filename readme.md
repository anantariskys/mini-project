# Hands on GIT

## Scenario 1

dimulai dengan membuat Git repository di komputer lokal, kemudian kita membuat struktur foldernya sebagai berikut:

```path
📁mini-project
   📄index.html
```

masuk ke folder tersebut lalu jalankan perintah 'git init' pada terminal terlebih dahulu.

Lalu kita mengisi file `index.html` dengan code:

```html
<html>
  <head>
    <title>BCC mini project</title>
  </head>
  <body></body>
</html>
```

lakukan commit dengan pesan "Init" dengan terlebih dahulu melakukan staging kemudian commit:

```bash
git add .
git commit -m "Init"

```

Kemudian kita membuat file berikutnya yaitu `test.html` dengan isi:

```html
<html>
  <head>
    <title>Test Page</title>
  </head>
  <body></body>
</html>
```

Namun kita tidak ingin file `test.html` di-commit di Git, karena file itu hanya sample page percobaan pribadi. Akhirnya kita harus mendaftarkannya ke file `.gitignore`.

Lalu kita membuat folder di repository untuk menampung semua halaman dari aplikasi **mini-project** bernama `pages`.

Selanjutnya kita menambahkan beberapa file disana yaitu `homepage.html`, `article.html`.

**Lakukan Commit**. commit ini sudah termasuk dengan file `.gitignore`.

Akhirnya strukture file dari aplikasi yang kita buat akan menjadi seperti ini:

```path
📁mini-project
   📁.git
   📁pages
      📄homepage.html
      📄article.html
   📄index.html
   📄test.hmtl
   📄.gitignore
```

Kemudian kita mulai bekerja pada file `📄homepage.html` dengan menambahkan beberapa elemen pada file tersebut, yaitu:

```html
<html>
  <head>
    <title>Homepage</title>
  </head>
  <body>
    <div>
      <h1>section one</h1>
    </div>

    <div>
      <h1>section two</h1>
    </div>
  </body>
</html>
```

Dan beberapa list judul artikel pada file `article.html` yaitu:

```html
<html>
<head>
    <title>Article Page</title>
</head>
<body>
    <ul>
        <li>article one</li>
        <li>article two</li>
    <ul>
</body>
</html>
```

Selanjutnya, kita membuat commit untuk file `📄homepage.html` saja. Dicommit berikutnya untuk file `article.html`

## Scenario 2

membuat branch baru bernama `feature/dashboard` Kemudian branch utama, pindah ke branch `feature/dashboard`

```bash
git branch feature/dashboard
git checkout feature/dashboard
```

Tambahkan file `dashboard.html` di folder pages.

Sehingga struktur folder di branch `feature/dashboard` akan terlihat seperti ini:

```path
📁mini-project
   📁.git
   📁pages
      📄homepage.html
      📄article.html
      📄dashboard.html
   📄index.html
   📄test.hmtl
   📄.gitignore
```

Selanjutnya, kita menambahkan file dashboard.html dengan code:

```html
<html>
<head>
    <title>Dashboard Page</title>
</head>
<body>
    <div>Chart1<div>
    <div>Chart2<div>
</body>
</html>
```

**Lakukan Commit**

## Scenario 3

kembali ke branch utama yaitu `master`. Lalu kita lanjutkan untuk mengerjakan file `homepage.html` dan menambahkan footer ke file tersebut:

```html
<html>
  <head>
    <title>Homepage</title>
  </head>
  <body>
    <div>
      <h1>section one</h1>
    </div>

    <div>
      <h1>section two</h1>
    </div>

    <footer>create by me</footer>
  </body>
</html>
```

**Lakukan Commit**

## Scenario 4

dari branch `master` kita pindah ke branch `feature/dashboard`.

Lalu kita menambahkan code di file `dashborad.html` untuk menyelesaikannya:

```html
<html>
<head>
    <title>Dashboard Page</title>
</head>
<body>
    <div>
        <canvas id="chart1"></canvas>
    <div>
    <div>
        <canvas id="chart2"></canvas>
    <div>
</body>
</html>
```

**Lakukan Commit**

Karena pekerjaan di branch tersebut telah selesai, maka kita melakukan penggabungan dari branch `feature/dashboard` ke branch `master`

```bash
git checkout master
git merge feature/dashboard
```

Setelah branch digabungkan, edit file `article.html`. di sini kita tambahkan judul artikel:

```html
<html>
<head>
    <title>Article Page</title>
</head>
<body>
    <ul>
        <li>article one</li>
        <li>article two</li>
        <li>article three</li>
    <ul>
</body>
</html>
```

Setelah menambahkan pertanyaan tersebut, kita **Lakukan Commit** dengan pesan

Di commit kita selanjutnya menambahkan total 20 artikel:

```html
<html>
<head>
    <title>Article Page</title>
</head>
<body>
    <ul>
        <li>article one</li>
        <li>article two</li>
        <li>article three</li>
        <li>article four</li>
        ...
        <li>article twenty</li>
    <ul>
</body>
</html>
```

**Lakukan Commit** 

ternyata artikel yang diminta tidak sampai 20 melainkan hanya 5 saja. Akhirnya, di commit berikutnya kita **menghapus semua soal** tersebut dan menggantinya menjadi hanya 5 artikel dengan terlebih dahulu melakukan reset:

```html
<html>
<head>
    <title>Article Page</title>
</head>
<body>
    <ul>
        <li>article one</li>
        <li>article two</li>
        <li>article three</li>
        <li>article four</li>
        <li>article five</li>
    <ul>
</body>
</html>
```
**Lakukan Commit**

## Scenario 5

Setelah mengerjakan cukup banyak feature, kita sadar bahwa halaman materi di file `homepage.html` masih cukup banyak yang harus dikerjakan. Namun deadline aplikasi ini untuk release sudah semakin dekat. maka dari itu, kita akan bekerja sama dengan **John**

akan tetapi, dikarenakan kebutuhan artikel ternyata 20, kita melakukan **reset** ke commit tempat kita menambahkan 20 artikel tadi.

Setelah melakukan revert, maka artikel sudah kita _rollback_ sehingga tidak perlu menulis ulang sebanyak 20 artikel.

```bash
git reset --hard <commitID_target>
```

## Scenario 6

Karena kita akan bekerja sama dengan John, kita perlu memindahkan local repository kita ke remote repository agar john bisa mengakses source code kita. Hubungkan local repository dengan remote repository dengan menggunakan github.

Sekarang **John** akan melakukan cloning dan membuat branch baru bernama `feature/homepage-from-john`. Lalu ia pindah ke branch tersebut dan menambahkan beberapa materi pada file `homepage.html` yaitu:

```html
<html>
  <head>
    <title>Homepage</title>
  </head>
  <body>
    <div>
      <h1>section one</h1>
    </div>

    <div>
      <h1>section two</h1>
    </div>

    <div>
      <h1>section three</h1>
    </div>

    <div>
      <h1>section four</h1>
    </div>

    <footer>create by me</footer>
  </body>
</html>
```

**Lakukan Commit** dan tidak lupa melakukan push beserta membuat Pull Request dari perubahan yang telah dilakukan, dengan judul PR: **add section three and four in homepage**.

## Scenario 7

Kembali lagi ke sudut pandang kita yang akan mengerjakan materi di branch `master`. Kita menambahkan konten di file `homepage.html` yaitu:

```html
<html>
  <head>
    <title>Homepage</title>
  </head>
  <body>
    <div>
      <h1>section one</h1>
    </div>

    <div>
      <h1>section two</h1>
    </div>

    <div>
      <h1>QnA section</h1>
    </div>

    <footer>create by me</footer>
  </body>
</html>
```

**Lakukan Commit**  dan tidak lupa melakukan push ke branch master di repo github yang sudah kita buat.

## Scenario 8

Setelah kita berkolaborasi dengan branch yang berbeda, **John** mengkonfirmasi bahwa materi yang sudah dibuatnya telah selesai dan siap untuk digabungkan dengan perubahan yang kita buat. Namun setelah kita check PR nya, ternyata terjadi conflict antara branch `master` dengan `feature/homepage-from-john`.

Jadi kita bisa pindah ke branch `feature/homepage-from-john` dan melakukan merge dari sana ke branch `master` untuk menyelesaikan conflict yang terjadi.

Terlihat bahwa, ada beberapa conflict yang terjadi. Kita harus memilih kedua perubahan tersebut karena kita melakukan perubahan pada file yang sama, untuk berkolaborasi.

Setelah memilih kedua perubahan, lalu kita lakukan commit dengan pesan "Merge branch 'master' into feature/homepage-from-john" dan tidak lupa melakukan push.

Maka sekarang terlihat bahwa PR **John** sudah tidak terjadi conflict dan bisa digabungkan dengan menekan tombol "Merge pull request".

Setelah dilakukan penggabungan branch, maka kita bisa menghapus branch `feature/homepage-from-john` untuk menandakan bahwa pekerjaan di branch tersebut telah selesai.

melakukan update di _local repository_ kita dengan melakukan penarikan _(**pull**)_ perubahan yang ada di remote.

## Scenario 9

Setelah pekerjaan selesai, John kembali ditugaskan untuk membuat feature login page dan kita diberikan tugas untuk membuat profile page. Pekerjaan dilakukan masing-masing dan dihubungkan dengan github.
Sebelum melakukan pekerjaannya, dibuat branch masing-masing agar tidak saling mengganggu pekerjaan dan meningkatkan kolaborasi. Kita membuat branch `feature/profile` dan john melakukan pekerjaannya di branch `feature/login-from-john`

Kita akan membuat file baru bernama `profile.html` didalam folder pages yang berisi kode sebagai berikut:

```html
<html>
  <head>
    <title>Profile</title>
  </head>
  <body>
    <div>
      <h1>Ahmad Faiz</h1>
    </div>

    <div>
      <h1>Nomor Handphone: +62812xxxxxxxx</h1>
    </div>
  </body>
</html>
```

Sedangkan John akan membuat file bernama `login.html` di dalam folder pages yang berisi kode sebagai berikut:

```html
<html>
  <head>
    <title>Login Page</title>
  </head>
  <body>
    <form action="" method="post">
      <label for="username">Username</label>
      <input type="text" name="username" id="username" />

      <label for="password">Password</label>
      <input type="password" name="password" id="password" />
    </form>
  </body>
</html>
```

Ternyata john sudah menyelesaikan pekerjaannya terlebih dahulu dan pekerjaannya sudah tergabung dengan main branch yaitu `master`. Kita akan menggunakan strategy yang berbeda dengan merge, yaitu rebase karena selain ingin melakukan keep upstream dengan main branch, kita juga ingin membuat commit history tetap clean, yaitu menggabungkan commit sama seperti merge tetapi tanpa membuat commit baru. Kita akan melakukan rebase dari branch `feature/profile` dengan branch `master`

```bash
git pull origin master --rebase
```

Saat ini seharusnya branch `feature/profile` sudah merupakan branch yang up-to-date dengan branch `master`
