# copy url service backend

1. buka berkas application -> models -> Record_model.php
2. set value untuk variable base_uri dengan url deployed service backend
3. deploy ke app engine dengan nama service frontend: gcloud app deploy
4. Dapatkan link dan copy url hasil deploy: gcloud app browse -s <nama_service>
5. buka berkas application -> config -> config.php
6. hapus tanda "#" dan set value variable $config['base_url'] dengan url deployed service frontend sebelumnya
7. deploy ke app engine dengan nama service frontend: gcloud app deploy
8. Dapatkan link dan copy url hasil deploy: gcloud app browse -s <nama_service>

# deploy aplikasi frontend ke app engine dengan service "frontend"

untuk membuat service tertentu, dalam hal ini "frontend", pertama kita harus buat kondisi service "default" dulu dengan cara melakukan comment pada baris kode "service: frontend", setelah itu baru bisa buat service lainnya sesuai dengan kebutuhan.

1. Buka cloud shell terminal GCP
2. Lakukan clone: git clone https://github.com/twentiecker/menjadi-google-cloud-engineer.git
3. Masuk ke folder profile-app: cd menjadi-google-cloud-engineer/submission2/money-tracker
4. Deploy ke app engine: gcloud app deploy
5. Dapatkan link dan copy url hasil deploy: gcloud app browse
6. buka app.yaml hapus tanda "#" pada baris kode "service: frontend"
7. Deploy ke app engine: gcloud app deploy
8. Dapatkan link dan copy url hasil deploy: gcloud app browse -s <nama_service>
