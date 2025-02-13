#!/usr/bin/env expect

set timeout -1

# Install dos2unix
spawn bash -c "apt update && apt install dos2unix -y"
expect eof

# Download install.sh
spawn bash -c "wget -O install.sh https://raw.githubusercontent.com/QwesHX/folderr/refs/heads/main/install.sh"
expect eof
spawn chmod +x install.sh
expect eof
spawn dos2unix install.sh
expect eof

# Jalankan install.sh
spawn ./install.sh

# Tunggu teks tertentu sebelum mengirim input
expect "PILIH OPSI (1-16):"  
send "11\r"

expect "replace app/Console/Kernel.php? \[y\]es, \[n\]o, \[A\]ll, \[N\]one, \[r\]ename:"  
send "A\r"

expect "Would you like to put your application into maintenance while Blueprint is installing? (Y/n)"  
send "y\r"

expect eof

# Download ulang install.sh dan jalankan lagi dengan input tambahan
spawn bash -c "wget -O install.sh https://raw.githubusercontent.com/QwesHX/folderr/refs/heads/main/install.sh"
expect eof
spawn ./install.sh

expect "PILIH OPSI (1-16):"  
send "2\r"

expect -re "(press enter to continue)"  
send "\r"

expect -re "(press enter to continue)"  
send "\r"

spawn echo "Proses Sudah Selesai"
expect eof

interact
