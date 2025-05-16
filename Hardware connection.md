Raspberry Pi4 giao tiếp với Arduino Uno thông qua cổng Serial (Uart),là một kết nối điểm-điểm giữa các thiết bị, cho phép chúng truyền thông tin với nhau
Để cài đặt Arduino IDE trên Raspberry Pi, nhập lệnh vào terminal:
Sudo apt-get update
Sudo apt-get install arduino
Nạp code băng tải vào arduino bằng cách cắm dây nạp vào máy tính, sau khi nạp xong rút dây nạp ra khỏi máy tính cắm vào raspberry
Trên Raspberry sẽ tiến hành tìm cổng serial của raspberry bằng cách nhập dòng lệnh trên terminal : ls /dev/tty*. Cổng serial của arduino thường có dạng "/dev/ttyACMx" hoặc "/dev/ttyUSBx"







Import serial
ser = serial.Serial('/dev/ttyACM1', 9600, timeout=1) 
ser.reset_input_buffer()

Đoạn lệnh import serial được sử dụng để đưa module serial vào chương trình, cung cấp cho chúng ta các công cụ để kết nối và giao tiếp với các thiết bị serial, cung cấp cho chúng ta các lớp để quản lý các thiết bị serial, gửi và nhận dữ liệu.
Khởi tạo một kết nối serial tới thiết bị có tên đường dẫn là "/dev/ttyACM1“, với tốc độ baud rate là 9600 bps và timeout là 1 giây.
Hàm ser.reset_input_buffer() xóa bộ đệm đầu vào của cổng serial trước khi bắt đầu đọc dữ liệu mới


