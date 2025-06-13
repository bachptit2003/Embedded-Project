BeagleBone Black Environmental Monitoring System
🌱 Giới thiệu
Đây là dự án Hệ thống đo đạc nhiệt độ, độ ẩm và môi trường sử dụng BeagleBone Black (BBB). Dự án được xây dựng với mục tiêu:

Thu thập dữ liệu từ các cảm biến (DHT11/DHT22, BH1750, GPIO)

Gửi dữ liệu lên web server thông qua MQTT

Tự động khởi động hệ thống qua các script init khi BBB bật nguồn

⚙️ Công nghệ & Công cụ
Buildroot: Dùng để build kernel, root filesystem và các gói phần mềm

Linux Kernel: Tích hợp các driver tự phát triển cho cảm biến

MQTT: Giao thức truyền dữ liệu lên server (ví dụ: Mosquitto broker)

Script khởi động tự động: Được viết bằng Bash/C để đảm bảo hệ thống tự chạy khi boot

📂 Cấu trúc dự án



![image](https://github.com/user-attachments/assets/4b229ba9-faa6-43ee-ac97-52a5082c0d46)


🚀 Cách build hệ thống
1️⃣ Clone repository về:

bash
Sao chép
Chỉnh sửa
git clone <URL_REPO>
cd <REPO>
2️⃣ Cấu hình buildroot:

bash
Sao chép
Chỉnh sửa
make menuconfig
Kích hoạt các driver trong menuconfig qua config.in

3️⃣ Build image:

bash
Sao chép
Chỉnh sửa
make
4️⃣ Nạp image vào BeagleBone Black và khởi động.

🌐 Truyền dữ liệu
Hệ thống sau khi chạy sẽ:

✅ Đọc dữ liệu từ cảm biến

✅ Gửi dữ liệu qua MQTT broker

✅ Broker chuyển dữ liệu lên web hoặc các hệ thống backend

🛠 Script khởi động
Hệ thống tích hợp:

script auto service init.sh

script auto service init.c

Các script này sẽ tự động chạy chương trình chính khi BeagleBone Black khởi động.

📌 Yêu cầu phần cứng
BeagleBone Black

Cảm biến DHT11 hoặc DHT22

Cảm biến BH1750

Module MQTT broker (server có thể là Mosquitto)

📌 Yêu cầu phần mềm
Buildroot

MQTT Broker (Mosquitto / HiveMQ / EMQX)

💡 Tính năng nổi bật
Buildroot build toàn bộ hệ điều hành tối giản cho BBB

Tích hợp driver tự viết cho các cảm biến

Hỗ trợ auto start bằng script

Gửi dữ liệu realtime qua MQTT

📄 Bản quyền
Dự án thuộc sở hữu của Nhóm 9 - Hệ điều hành nhúng. Chỉ sử dụng cho mục đích học tập và nghiên cứu.
