# Panduan Penggunaan GIT

## Table Of Content

[TOC]

------

Tutorial cara menggunakan git baik github, bitbucket, gitlab dan lain-lainya.

## Buat Akun dan Repository Baru.

1. Silahkan daftar ke http://bitbucket.org/ atau http://github.com dan git lainnya.

2. *Create new repositories* klik lambang + pada kiri menu halaman bitbucket anda.

   ![Pilih +](https://cdn-images-1.medium.com/max/800/1*qs6YWxA5EX2OYZlbRP99aw.png)

   ​

3. Selanjutnya pilih **repository**.

   ![Pilih Repository](https://cdn-images-1.medium.com/max/800/1*YDxy7rcGRDlW2ZlZwcrhQg.png)

   ​

4. Pilih **create a new repository** dan isi dengan nama repository anda.

   ![Create new repository](https://www.dropbox.com/s/o83kfszp92ok8ci/create_new_repo.PNG?raw=1)

   ```markdown
   Input nama repository anda (contoh:md_tutorial_karyaone), lalu centang private apabila ingin hanya anda yang bisa melihat repository ini
   ```

   ​

5. Selamat repositories anda berhasil dibuat abaikan create file README.md dan Commit pertama akan terlihat.

6. Selesai





## SYNC Data BitBucket

Selanjutnya lakukan clone kedalam folder yang anda inginkan pada pc anda masing-masing dengan perintah sebagai berikut.

### Clone

1. Buka folder untuk kita melakukan clone

2. Jika kamu sudah menginstall GitBash tinggak klik kanan **GitBash Here** pada folder, jika belum anda bisa melakukan **path secara menual melalui cmd** ke dalam *folder anda*.

   ![GitBash Here](https://www.dropbox.com/s/x5byhwpwu74r63l/gitbashere.jpg?raw=1)

   ​

3. Salin dahulu url git yang ingin kamu sync atau clone dan ketik command berikut diikuti dengan link repositories anda pada bitbucket yang telah anda buat.

   > Copy Link Repositories yang telah kita buat seperti gambar dibawah ini :

   ![Copy Link Repositories](https://www.dropbox.com/s/y680lgi2v9h5etc/copy_md_link.PNG?raw=1)

   ​

   > Selanjutnya jalankan GitBash atau CMD yang sudah berada pada folder yang anda inginkan dan jalankan perintah clone pada CMD seperti gambar berikut ini :

   ![CMD Clone](https://www.dropbox.com/s/51foz3ydbyy11bd/cmd_clone.PNG?raw=1)

   Otomatis akan terbuat folder baru sesuai dengan nama repositories kamu pada bitbucket ke folder yang kamu inginkan.

   ​

4. Selesai data repositories kamu telah diclone kedalam pc kamu.

   ​

   > Dengan konsep clone repositories ini otomatis akan tergenerate *git init origin* pada folder yang telah kita clone dengan begitu kita **tidak perlu** melakukan setting git ini dan git remote add origin master https://kangyasin@bitbucket.org/kangyasin/md_tutorial_karyaone.git



Konsep Tanpa Clone Menyusul ya kawan :smile:



### Push dan Pull

Ada 2 perintah dasar git yang akan kita lakukan, dimana perintah ini yang paling umum dan paling utama, yaitu push untuk menambahkan project, pull untuk mengambil project.



**Sebelum melakukan push dan pull jalankan perintah add**

```
git add *
```

**Selanjutnya lakukan perintah commit**

```markdown
git commit -m "Initial Comment" 
["initial comment"] bisa disesuaikan dengan info update masing-masing
```

**Lakukan push**

```markdown
git push -u origin master
lalu akan diminta [password] bitbucket untuk pertama kali saja
```



![Success](https://www.dropbox.com/s/8jz5qo70qwkw7wo/git_commit_success.PNG?raw=1)



> untuk memastikan data yang kita push masuk kedalam account bitbucket kita langsung cek dan login melalui browser akan terlihat commit terbaru disisi kanan halaman repositories kita pada bitbucket.



![Update Complete](https://www.dropbox.com/s/u9imfqnagrem5y5/update_complete.PNG?raw=1)



**Untuk perintah Pull**

```markdown
git pull origin master
```



## Membuat branch baru

### Apa itu Branch

Jika anda melakukan branch maka anda pada dasarnya membuat **suatu cabang dari repository anda**. Jika anda membuat perubahan dan melakukan commit pada cabang ini maka ini hanya terjadi pada cabang tersebut dan tidak akan berdampak pada cabang utama maupun cabang-cabang  lain yang mungkin ada. Disamping itu cabang ini nantinya bisa digabung **(=merge)** dengan cabang-cabang yang lain atau disatukan kembali dengan cabang utama.



### Cara Membuat Branch Baru

Jalan CMD pada directory git anda pada pc dan jalankan perintah berikut ini.

```markdown
git branch "namabranch"
```

```markdown
git checkout "namabranch"
```



**Note : Ubah namabranch sesuai dengan apa yang kamu ingin gunakan dan tanpa tanda petik**

# Pemakaian Git sehari-hari

Kita akan mengulas secara singkat perintah-perintah yang sering kita gunakan dalam Git. Tapi sebelum mulai, perlu kita pahami beberapa istilah sebagai berikut :

- diff : perbedaan antara satu file dengan file lainbiasanya diff dilakukan terhadap satu file yang sudah berubah isinya

- changeset : kumpulan diff

- working folder : folder kerja kita, berisi file yang (mungkin) sudah berubah sejak commit terakhir

- staging : tempat persiapan changeset yang akan dicommit

- commit : snapshot dari posisi folder dan file pada waktu tertentu

- tip : commit paling ujung

- head : nama lain tip

- branch : head yang diberi nama

- HEAD : head yang sedang aktif

- merge : menggabungkan lebih dari satu commit

  ​

## Membuat Repository

Untuk bisa mulai bekerja, kita harus memiliki repository dulu. Ada dua kemungkinan, kita membuat repository baru, atau kita membuat clone dari repository yang sudah ada.

| Keterangan                                     | Perintah                    |
| ---------------------------------------------- | --------------------------- |
| membuat repository baru                        | git init                    |
| membuat repository baru di folder project-baru | git init project-baru       |
| membuat repository untuk dishare               | git init –bare project-baru |
| copy repository lain                           | git clone repo-url          |

pilihan format URL

file:///path/ke/repo : clone dari folder lokal

/path/ke/repo : clone dari folder lokal, menggunakan hard link

http://server/path/ke/repo : clone melalui protokol http

username@server:path/ke/repo : clone melalui protokol ssh



## Bekerja paralel menggunakan branch

Branch memungkinkan kita bekerja secara paralel, misalnya ada tim yang menambah fitur, dan ada tim yang melakukan bug fix.

| Keterangan                                                | Perintah                                  |
| --------------------------------------------------------- | ----------------------------------------- |
| membuat branch baru                                       | git branch namabranch                     |
| pindah ke branch tersebut                                 | git checkout namabranch                   |
| bikin branch sambil pindah                                | git checkout -b namabranch                |
| membuat tracking branch untuk branch bugfix di origin     | git checkout –track origin/bugfix         |
| membuat tracking branch dengan nama berbeda dengan remote | git checkout -b myfix origin/bugfix       |
| membandingkan branch satu dengan lainnya                  | git diff master..fitur-xx                 |
| membandingkan branch dengan titik awal branch tersebut    | git diff master…fitur-xx                  |
| menggabungkan branch satu dengan lainnya                  | git checkout branch-tujuan                |
|                                                           | git merge branch-yang-mau-diambil         |
| Mengedit konflik :                                        |                                           |
| - edit konfliknya                                         | git add namafile-yang-konflik             |
| - remove markernya                                        | git commit -m “merge fitur-xxx ke master” |
| membatalkan merge yang konflik                            | git reset –hard                           |



## Bekerja dengan remote

Interaksi dengan remote repository

| Keterangan                                                   | Perintah                                                  |
| ------------------------------------------------------------ | --------------------------------------------------------- |
| mendaftarkan remote repository                               | git remote add namaremote url                             |
| melihat daftar remote repository                             | git remote -v                                             |
| menghapus remote repository                                  | git remote rm namaremote                                  |
| mengambil perubahan di remote                                | git remote update                                         |
| mengambil perubahan di satu remote saja                      | git remote update namaremote                              |
| mengambil perubahan di remote, hapus branch di lokal yang sudah tidak ada di remote | git remote update –prune                                  |
| mengambil perubahan sesuai refspec yang sudah dikonfigurasi  | git fetch namaremote                                      |
| mengambil perubahan kemudian dimerge ke branch lokal yang sesuai | pull = fetch + merge                                      |
|                                                              | git pull namaremote                                       |
| mengirim perubahan di lokal ke remote                        | git push nama-remote nama-branch-lokal:nama-branch-remote |
| mengirim perubahan di lokal ke remote, semua branch yang namanya bersesuaian akan dikirim | git push nama-remote                                      |
| mengirim perubahan di branch lokal yang sedang aktif ke branch di remote dengan nama yang sama | git push nama-remote HEAD                                 |
| menghapus branch di remote                                   | git push nama-remote :nama-branch-remote                  |

Demikianlah perintah-perintah Git yang kita gunakan sehari-hari. Melengkapi daftar perintah di atas, diagram berikut dapat membantu pemahaman kita tentang konsep dan operasi di Git.



[^-]: KangYasin :grinning:

