# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini
1. Devops merupakan pihak yang menengahi antara tim Developer dan Operations yang memiliki peran untuk menciptakan workflow yang lebih lancar dan efisien antara apa yang dikerjakan oleh Software Development dengan IT Operations.
2. Insfrastruktur adalah kumpulan komponen seperti Hardware, Software, OS, data storage, Sistem Operasi yang diperlukan untuk membangun serta menjalankan aplikasi dalam suatu organisasi
3. Server adalah suatu sistem komputer yang menyediakan sumber daya untuk penyimpanan data, meskipun demikian server juga dapat di kembangkan kebutuhannya untuk banyak client mulai dari untuk email, DNS, hingga website. Contoh layanan web server yang umum digunakan Apache atau Nginx. Contoh implementasinya adalah hosting web.
4. Server dibutuhkan dalam tahap pengembangan suatu software karena selain memastikan sistem tetap online dan berperan untuk melayani klien nantinya. Server juga memberikan kekuatan pemrosesan tinggi dengan spesifikasi RAM dan CPU yang lebih baik
5. - Virtualiasi adalah teknologi yang dapat digunakan untuk menciptakan versi virtual dari suatu teknologi yang berbentu fisik seperti server, penyimpanan, jaringan, dan mesin fisik lainnya.
- Container adalah software yang digunakan untuk mempermudah pengembangan aplikasi dengan cara mengemas kode serta semua dependensinya dan mengisolasi suatu aplikasi secara virtual sehingga aplikasi dapat berjalan dengan cepat dan andal dari suatu lingkungan komputasi ke lingkungan komputasi lainnya.
6. Selain karena kelebihan containernya itu sendiri seperti Penskalaan sistem & pendistribusian software yang lebih cepat serta fleksibilitas dalam mengoperasikan aplikasi dalam container. Container populer karena berbagai faktor lain seperti, mulia jatuhnya mesin virtual.
7. Orkestrasi container adalah proses untuk mengelola penerapan, integrasi, penskalaan, dan siklus hidup perangkat lunak dan aplikasi dalam container di lingkungan yang kompleks dan dinamis. Sebagai alat otomatisasi, ia menganalisis, mengatur, dan mengintegrasikan aplikasi dan layanan di tingkat operasi dasar.

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

