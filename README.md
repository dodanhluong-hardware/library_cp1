ESP32 AUDIO DSP BOARD
=====================

Giới thiệu
----------
Đây là mạch DSP audio sử dụng vi điều khiển ESP32 làm bộ xử lý chính.
Mạch được thiết kế để xử lý âm thanh đa kênh với các tính năng DSP,
hỗ trợ micro, Bluetooth audio, điều khiển qua web và giao diện người dùng
bằng OLED + encoder.

Hệ thống sử dụng codec audio rời với ADC PCM1808 và DAC CS4344,
cho phép xử lý 4 kênh audio gồm 2 kênh toàn dải và 2 kênh subwoofer.

Hình ảnh
--------
Ảnh thực tế mạch:

![ESP32 Audio DSP Board](IMG_20260301_163539.jpg)

Sơ đồ mạch (Version 1):

![Schematic Version 1](Documents/Schematic/Version%201.png)

Sơ đồ mạch (Version 2):

![Schematic Version 2](Documents/Schematic/Version%202.png)

Phần cứng
---------
Vi điều khiển
- ESP32 (module chính)

Audio Codec
- 2 x PCM1808 ADC (Audio Input)
- 2 x CS4344 DAC (Audio Output)

Số kênh audio
- 4 kênh xử lý
  + 2 kênh full-range
  + 2 kênh subwoofer

Đầu vào audio
-------------
- 1 x AUX input (line level)
- 2 x microphone dynamic

Microphone được khuếch đại qua op-amp để đạt mức tín hiệu phù hợp
cho việc lấy mẫu bởi ADC.

Đầu ra audio
------------
- 2 kênh toàn dải (Full Range)
- 2 kênh Subwoofer

Bảo vệ loa
----------
- Chân MUTE chống hiện tượng bụp loa khi bật hoặc tắt nguồn.

Nguồn cấp
---------
- Dải điện áp đầu vào: 8V - 36V DC
- Có đo và hiển thị điện áp nguồn trên màn hình OLED.

Giao diện người dùng
--------------------
- Màn hình OLED hiển thị trạng thái hệ thống
- Encoder EC11 để điều khiển menu
- Hiệu ứng hiển thị nháy theo nhạc trên OLED
- Hiển thị chữ chạy (scroll text)

Kết nối
-------
Bluetooth
- Hỗ trợ Bluetooth Audio Sink để nhận nhạc không dây.

WiFi
- Có giao diện DSP webserver chạy trực tiếp trên ESP32
- Web interface được lưu trong bộ nhớ ESP32

Chế độ WiFi
- STA mode (kết nối router)
- Có thể nhập SSID và password
- Nếu kết nối thất bại 3 lần sẽ tự động chuyển sang AP mode.

DSP Web Interface
-----------------
Giao diện điều khiển DSP có thể truy cập bằng trình duyệt web.

Demo interface:
https://dodanhluong-hardware.github.io/DSP-Interface/dsp.html

Web interface này cho phép điều chỉnh:
- EQ
- Gain
- Crossover
- Delay
- Micro effects
- Các thông số DSP khác

Tính năng DSP
--------------

Full-range channel
- EQ 6 band cho mỗi kênh
- Gain độc lập từng kênh
- Dynamic Loudness (bù bass tự động)

Subwoofer channel
- Gain
- Delay line để chỉnh phase
- Đảo pha
- Điều chỉnh tần số cắt

Xử lý Micro
-----------
Mỗi micro có điều chỉnh riêng:
- Bass
- Mid
- Treble
- Gain

Hiệu ứng Micro
--------------

Reverb
- Level
- Pre-delay
- Decay
- Room size
- Damping
- Mix

Echo
- Level
- Repeat
- Mix
- Delay

Chống hú micro
--------------
Áp dụng phương pháp dịch tần (frequency shifting)
trong dải 0 - 20Hz để giảm hiện tượng feedback.

Cài đặt hệ thống
----------------
- Điều chỉnh tốc độ chữ chạy trên màn hình OLED
- Điều chỉnh thời gian trễ phát nhạc khi khởi động

Ứng dụng
--------
- Loa karaoke
- DSP cho ampli
- Hệ thống loa sub + full
- Mixer mini có hiệu ứng

Tác giả
-------
Thiết kế và phát triển bởi:
Do Danh Luong

GitHub
------
https://github.com/dodanhluong-hardware

License
-------
Open hardware / open source project.
