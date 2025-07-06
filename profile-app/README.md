# struktur project

1. folder images berisi asset yang akan diupload ke dalam bucket
2. folder profile-app beris file app.yaml, index.html, dan style.css yang akan di deploy ke app engine

# membuat app engine

1. buka consol GCP
2. ketik app engine di search bar, pilih app engine
3. pilih create application
4. region: asia-southeast2
5. service account: App Engine default service account
6. pilih next

# upload image ke bucket

1. download semua file yang ada di folder images
2. ketik bucket di search bar, pilih buckets (cloud storage)
3. pilih bucket yang sudah tersedia role di iam (hip-graph-465112-d1.appspot.com).
4. setelah masuk ke bucketnya, pilih menu upload > upload files dan pilih semua file yang sudah didownload dari folder images sbelumnya
5. untuk masing2 file yang berhasil diupload di bucket, pilih titik tiga di ujung kanan, pilih edit access, pilih add entry
6. pada dropdown entity baru pilih public, kemudian save.
7. lakukan edit access untuk semua file yang ada di bucket
8. setelah semua sudah dibuat public, pilih titik tiga di ujung kanan, pilih copy public url, kemudian masukkan dalam file inde.html untuk setiap image yang bersesuaian

# tambah role Storage Object Admin

1. Ketik iam di search bar, pilih iam (iam & admin)
2. Pada kolom principal cari nama akun yang mirip seperti nama bucket (hip-graph-465112-d1)
3. Pilih icon pencil di ujung kanan
4. Pilih add another role
5. Ketik Storage Object Admin pada kotak filter, pilih Storage Object Admin
6. Pilih save

# deploy app ke app engine

1. Buka cloud shell terminal GCP
2. Lakukan clone: git clone https://github.com/twentiecker/menjadi-google-cloud-engineer.git
3. Masuk ke folder profile-app: cd menjadi-google-cloud-engineer/profile-app
4. Deploy ke app engine: gcloud app deploy
5. Dapatkan link dan buka website hasil deploy: gcloud app browse
