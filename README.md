# 🚀 **Tutorial: Setup Self-Hosted Runner untuk GitHub Actions**

## 📝 **Prasyarat**
1. VPS atau server dengan akses SSH.
2. Repository yang sudah dibuat dan akan digunakan.

---

## 🏁 **Langkah 1: Persiapan di GitHub**

1. **Masuk ke GitHub**
   - Masuk ke akun GitHub kamu.
   - Pilih repository yang ingin kamu gunakan dengan self-hosted runner ini.
   
2. **Masuk ke Settings Repository**
   - Di halaman repository, klik **Settings**.
   - Pilih **Actions** pada sidebar kiri, lalu pilih **Runners**.

3. **Tambahkan Self-Hosted Runner**
   - Klik tombol **Add runner**.
   - Pilih **Linux** sebagai sistem operasi.
   - GitHub akan memberikan instruksi untuk menginstal dan mengonfigurasi runner di server.

---

## 🖥️ **Langkah 2: Setup Self-Hosted Runner di Server**

1. **Update Sistem**
   Sebelum mulai, pastikan sistem kamu up-to-date dan install tools yang dibutuhkan dengan menjalankan perintah berikut:
   ```bash
   sudo apt update && sudo apt upgrade -y && sudo apt install curl tar -y

## ⬇️ Langkah 3: Unduh Runner
   CONTOH: (Pakai sudo jika permission denied)
   
   mkdir actions-runner && cd actions-runner
   
   curl -o actions-runner-linux-x64-2.310.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.310.0/actions-runner-linux-x64-2.310.0.tar.gz
   
   tar xzf ./actions-runner-linux-x64-2.310.0.tar.gz

## 🔑 Langkah 4: Daftarkan Runner
    Kembali ke halaman GitHub dan salin perintah untuk mendaftarkan runner kamu. 
    Biasanya perintahnya seperti ini: ./config.sh --url https://github.com/username/repo --token YOUR_TOKEN

## ▶️ Langkah 5: Jalankan Runner
   ./run.sh (ini langsung berjalan di interface, jika di ctrl + c maka ia akan berhenti runner nya)

   disarankan menggunakan files svc.sh jika anda ingin service nya berjalan di background dan selalu hidup service runnernya :
   sudo ./svc.sh install && sudo ./svc.sh start && sudo ./svc.sh status

## 🏁 Langkah 6: Buat Workflow dan Selesai..
