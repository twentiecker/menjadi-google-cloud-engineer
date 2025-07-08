# melakukan konfigurasi serviceaccountkey.json

1. ketik service account di search bar, pilih service accounts (iam & admin)
2. pilih create service account, beri nama bebas dan id akan menyesuaikan by default, create and continue
3. berikan role Storage Object Admin, kemudian pilih continue
4. pilih done
5. pilih nama service account yang sudah dibuat
6. pilih tab keys
7. Klik "Add Key" > "Create new key"
8. Pilih format JSON
9. Klik Create → File akan otomatis diunduh
10. buka file yang berhasil diunduh, copy isinya dan paste di berkas serviceaccountkey.json

# membuat bucket

1. ketik bucket di search bar, pilih buckets (cloud storage)
2. pilih create
3. beri nama, kemudian continue
4. pilih region asia-southeast2 (jakarta), kemudian continue
5. biarkan default, kemudian pilih continue
6. uncheck "Enforce public access prevention on this bucket", pilih fine-grained, kemudian continue
7. pilih create

# menyalin project id dan nama bucket

1. ketik bucket di search bar, pilih buckets (cloud storage), copy nama bucket
2. buka berkas modules -> imgUpload.js, paste nama bucket di variabel bucketName
3. ketik dashboard di search bar, pilih dashboards (cloud overview)
4. copy project id, paste di variable projectId

# membuat cloud sql

1. ketik sql di search bar, pilih Cloud SQL (Managed MySQL, PostgreSQL, SQL Server)
2. pilih create instance
3. pilih choose mysql
4. Cloud SQL Edition: Enterprise
5. Edition Preset: Development
6. Database version: versi database yang digunakan, pilih MySQL 5.7.
7. Instance ID: identitas berupa nama instance yang bersifat permanen, silakan isi sesuai keinginan Anda.
8. Password: password yang berfungsi untuk mengakses server SQL Anda, isi sesuai keinginan Anda.
9. Region: lokasi region yang akan menyimpan data Anda, pilih asia-southeast2.
10. Zonal availability: Ketersediaan dari Cloud SQL instance Anda, satu zone atau beberapa zone. Untuk saat ini, pilih Single zone saja.
11. Kemudian, klik panah pada "Show Configuration Options".
12. Machine configuration: Tipe mesin yang akan menjalankan Cloud SQL instance Anda, silakan pilih machine type Shared core dengan opsi 1 vCPU, 0.614 GB.
13. Storage: Jenis penyimpanan yang akan menjalankan Cloud SQL instance Anda, pilih Storage type HDD dan Storage capacity 10 GB.
14. Connections: Pengaturan koneksi terhadap database instance Anda, untuk saat ini biarkan sesuai default.
15. pilih Create Instance
16. Setelah Cloud SQL instance siap, silakan masuk ke menu Connections yang ada di sebelah kiri. Pada Authorized networks, klik tombol Add Network
17. isi Name dengan Public dan isi Network dengan range 0.0.0.0/0. Kemudian, klik Done
18. pilih save

# melakukan konfigurasi pada backend

1. buka berkas routes -> record.js
2. sesuaikan konfigurasi database pada variabel host, database, dan password

# terhubung dengan cloud sql instance

1. buka cloud shell
2. update system dengan menjalankan kode sudo apt-get update
3. install mysql-client dengan menjalankan kode sudo apt-get install mysql-client
4. terhubung dengan sql dengan menjalankan kode mysql -h <ippublic_mysql> -u root -p
5. masukkan password mysql
6. buat database dengan menjalankan kode create database <nama_database>;
7. gunakan database dengan menjalankank kode use <nama_database>;
8. buat tabel dan skema dengan menjalankan kode yang ada pada berkas create_table.sql

# membuat app engine

1. ketik app engine di search bar, pilih app engine (managed app platform)
2. pilih create application
3. pilih region asia-southeast2 (jakarta)
4. pilih service account yang sudah dibuat sebelumnya (bukan default service account)
5. pilih next

# deploy aplikas backend ke app engine

1. Buka cloud shell terminal GCP
2. Lakukan clone: git clone https://github.com/twentiecker/menjadi-google-cloud-engineer.git
3. Masuk ke folder profile-app: cd menjadi-google-cloud-engineer/money-tracker-api
4. Deploy ke app engine: gcloud app deploy
5. Dapatkan link dan buka website hasil deploy: gcloud app browse
