# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
   - DevOps merupakan gabungan kata dari Development Operations yang memudahkan sekaligus mempercepat dalam melakukan siklus pengembangan dan pengiriman pada perangkat lunak.
2. Apa yang anda ketahui tentang Infrastructure?
   -infrastructure merupakan sebuah gabungan komponen hardware, sodtware, dan network yang mana ini dipergunakan utuk mengembangkan, menguji, mengoperasikan, memantau dan mendukung layanan IT adapun infrastructure yang berkaitan dengan cloud yaitu IaaS( infrastructure as a Service)
   
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
   -server merupakan sebuah sistem perangkat lunak(software) maupun perangkat keras(hardware yang menyediakan layanan atau sumber daya tertentu kepada perangkat lain atau disebut client dalam sebuah jaringan. seperti contoh Web Server yang berfungsi menyediakan konten web ke browser pengguna(HTTP/HTTPS) contoh implementasi nya seperti NGINX atau APACHE.
   
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
   - alasan mengapa server dibutuhkan dalam pengembangan software untuk tempat menjalankan aplikasi karena server menyediakan lingkungan operasi seperti node.js, python, java dll agar software dapat dijalankan secara konsisten. server juga digunakan untuk menjalankan build pipeline seperti kompilasi, unit test, dan integrasi tes contohnya seperti github actions dipakai untuk CI/CD build pipeline otomatis setiap ada commit baru
     
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
   -virtualisasi merupakan proses membuat versi virtual dari sumber daya fisik seperti server, storage, atau jaringan yang menggunakan hypervisor(VMware, VirtualBox), sedangkan container merupakan sebuah virtualisasi tingkat sistem operasi yang memunginkan aplikasi dan semuaa depedensinya dikemas dalam satu unit yang ringan dan dapat dijalankan dimana saja. simpel nya container dapat dijalankan dalam 1 OS host/ lebih portable sedangkan virtualisasi menjalankan OS berbeda di satu mesin.
   
6. Mengapa teknology container saat ini sangat populer?
   -dikarenakan mampu menyederhanakan, mempercepat, dan menstandarisasi cara aplikasi dibangun, diuji, dan dijalankan dalam skenario DevOps dan CI/CD
7. Apa yang anda ketahui tentang Orchestration Container System?
   -container orchestration adalah proses mengatur dan mengelola container secara otomatis, termasuk bagaimana container dijalankan, dijadwalkan, diatur skalanya, dan dipantau, dalam lingkungan yang kompleks dan dinamis.

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

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

