## Mô Đun Kiểm Tra Điện Áp Pcbfun Pzem-004t Ac 100a Đa Năng Chuyên Dụng

```
https://shopee.vn/M%C3%B4-%C4%90un-Ki%E1%BB%83m-Tra-%C4%90i%E1%BB%87n-%C3%81p-Pcbfun-Pzem-004t-Ac-100a-%C4%90a-N%C4%83ng-Chuy%C3%AAn-D%E1%BB%A5ng-i.213820428.22248965874

https://hshop.vn/mach-do-ap-dong-cong-suat-nang-luong-ac-100a-giao-tiep-uart

https://www.mediafire.com/file/zsvhta2wzjhdi6f/%5BHshop.vn%5D+PZEM-004T+Software.zip
https://github.com/vietduino/Hshopvn_Pzem004t_V2/tree/master


https://youtu.be/ZexFCHxVj7o
https://youtu.be/hnTdq-rVSfs (vs Esp8266)

```

Thư viện
```
Thư viện SoftwareSerial.h: https://github.com/PaulStoffregen/SoftwareSerial
Thư viện: https://github.com/mandulaj/PZEM-004T-v30

```

```
#include <PZEM004Tv30.h>

PZEM004Tv30 pzem(11, 12);

void setup() {
  Serial.begin(115200);
}

void loop() {
    float voltage = pzem.voltage();
    if(voltage != NAN){
        Serial.print("Voltage: "); Serial.print(voltage); Serial.println("V");
    } else {
        Serial.println("Error reading voltage");
    }

    float current = pzem.current();
    if(current != NAN){
        Serial.print("Current: "); Serial.print(current); Serial.println("A");
    } else {
        Serial.println("Error reading current");
    }

    float power = pzem.power();
    if(current != NAN){
        Serial.print("Power: "); Serial.print(power); Serial.println("W");
    } else {
        Serial.println("Error reading power");
    }

    float energy = pzem.energy();
    if(current != NAN){
        Serial.print("Energy: "); Serial.print(energy,3); Serial.println("kWh");
    } else {
        Serial.println("Error reading energy");
    }

    float frequency = pzem.frequency();
    if(current != NAN){
        Serial.print("Frequency: "); Serial.print(frequency, 1); Serial.println("Hz");
    } else {
        Serial.println("Error reading frequency");
    }

    float pf = pzem.pf();
    if(current != NAN){
        Serial.print("PF: "); Serial.println(pf);
    } else {
        Serial.println("Error reading power factor");
    }

    Serial.println();
    delay(2000);
}

```


```
Các tính năng:

1.Chức năng đo thông số điện (điện áp, dòng điện, công suất hoạt động).

2.Nút nguồn chức năng rõ ràng.

3.Chức năng lưu trữ dữ liệu tắt nguồn (tắt trước khi tiết kiệm điện tích lũy).

4.Chức năng hiển thị PC (hiển thị điện áp, dòng điện và nguồn hoạt động).

5.Chức năng giao tiếp nối tiếp (được trang bị giao diện nối tiếp TTL, giao tiếp với bo mạch bộ điều hợp thông qua các thiết bị đầu cuối khác nhau, đọc và cài đặt các thông số).

Giới thiệu:

B. Màn hình hiển thị phía trước và các nút

Giao diện người dùng:

Cửa sổ hiển thị PC bao gồm bốn cửa sổ, được sử dụng để hiển thị các thông số về điện áp, dòng điện, công suất và công suất, như trong hình

Định dạng hiển thị:

1. Nguồn cung cấp: dải đo 0-22kW

Trong định dạng hiển thị 0-0.000-9.9999, 10 kilowatt;

Định dạng hiển thị là 10,00-22,00 ở 10-22kW.

Nguồn cung cấp: phạm vi đo 0-9999kWh:

10kwh trong định dạng hiển thị 0-0.000-9.9999;

Định dạng hiển thị 10,00-99,99 nằm trong khoảng 10-100kWh;

Các định dạng hiển thị từ 100,0 đến 999,9 nằm trong khoảng từ 100 đến 1000kWh;

1000 đến 9999kWh và định dạng hiển thị từ 1000 đến 9999 ở trên.

Điện áp: Phạm vi kiểm tra 80-260VAC:

Định dạng hiển thị 110.0 ~ 220.0.

Hiện tại: Phạm vi đo 0-100A:

Định dạng hiển thị 00.00 đến 99,99.

Chìa khóa:

Các nút tích hợp trên bảng điều khiển được sử dụng cho các chức năng phát điện rõ ràng, như trong Hình 2.

Phương pháp đặt lại nguồn: Nhấn nút ZERO trong 5 giây và sau đó nhả nút! Nhấn nút xóa một lần nữa, dữ liệu sẽ được xóa và phí thoát sẽ được xóa cho đến khi hoàn tất quá trình xóa.

Giao tiếp nối tiếp:

Mô-đun được trang bị giao diện truyền thông dữ liệu nối tiếp TTL thông qua cổng nối tiếp có thể đọc và đặt các thông số liên quan; Nhưng nếu bạn muốn sử dụng USB hoặc RS232 (chẳng hạn như máy tính) cho các thiết bị liên lạc, Bạn cần được trang bị các bảng mạch phần cứng bộ điều hợp TTL khác nhau (để giao tiếp USB và bảng điều hợp TTL sang USB; để giao tiếp với TTL RS232, cần có bảng điều hợp RS232). Các chi tiết kết nối cụ thể của bo mạch bộ điều hợp có thể được tìm thấy trên sơ đồ.

Giải thích về giao tiếp:

1. Kết nối phần cứng theo sơ đồ mạch.

2. Sau khi kết nối cáp, một lựa chọn hàng đầu là chọn cổng giao tiếp của mô-đun phần mềm PC để hỗ trợ cổng giao tiếp COM2 COM3 COM4. Thông qua Trình quản lý thiết bị, nếu bạn không cần sửa đổi cổng, không xem nó trên một số cổng.

Những vấn đề cần chú ý:

1. Mô-đun này thích hợp để sử dụng trong nhà và không sử dụng ngoài trời.

2. Tải trọng áp dụng không được vượt quá công suất định mức.

3. Việc đấu dây không được sai.

Thông số:

1. Điện áp làm việc: 80-260VAC

2. Điện áp thử nghiệm: 80-260VAC

2. Công suất định mức: 100A / 22000W

3. Tần số làm việc: 45-65Hz

4. Độ chính xác của phép đo: 1.0

Gói bao gồm:

Bảng trần mô-đun giao tiếp * 1

Mô-đun giao tiếp không có vỏ * 1 + cuộn dây đóng mở * 1

Mô-đun giao tiếp không có vỏ * 1 + cuộn dây đóng * 1

Mô-đun giao tiếp với vỏ * 1 + cuộn dây đóng mở * 1

Mô-đun giao tiếp có vỏ * 1 + cuộn dây đóng * 1
```
<img width="800" height="800" alt="image" src="https://github.com/user-attachments/assets/c3161c53-33fd-4864-b75b-42aee00fc626" />

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/ca993dae-f70a-486c-aaed-44fa150a06dd" />

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/12329a2d-57dc-43cd-b9a0-8c1c4f07abd6" />

![IMG_3530](https://github.com/user-attachments/assets/26ae161e-ed72-477c-b3af-8f632040d076)

<img width="613" height="1079" alt="image" src="https://github.com/user-attachments/assets/5e115563-717b-4c8e-805f-a589c217d2f4" /> 
<img width="645" height="1079" alt="image" src="https://github.com/user-attachments/assets/36e59a5e-cceb-4fb9-b7ba-9068cef55b71" />

https://youtu.be/hnTdq-rVSfs  

<img width="645" height="1079" alt="image" src="https://github.com/user-attachments/assets/dccd614f-cb4e-43d8-b145-faa7ee8aa3a2" />



Code RX-TX

![IMG_3529](https://github.com/user-attachments/assets/27524712-1686-4a93-8079-c76b86b8af22)

Baud rate 9600, 8 data bits, 1 stop bit, no parity

```
0x000 Voltage value
0x001 Current value low 16 bits
0x002 Current value high 16 bits
0x003 Power value low 16 bits
0x004 Power value high
0x005 Energy value low
0x006 Energy value high
0x007 Frequency value
0x008 Power factor value
0x009 Alarm stauts
(0xFFFF is alarm, 0x0000 is not alarm)


CRC check code 0xHH and 0xLL
Voltage is 0x0898, coverted decimal is 2220, display 220.0V
Current is 0x00003E8, cenvertd to decimal is 1000, display 1.000A
Power is 0x00000898 cenverted to decimal is 2200 display 220.0W
Energy is 0x00000000 cenverted to decimal is 0, display 0Wh
Frequency is 0x01F4, converted to decimal is 500, display 50.0Hz
Power factor is 0x0064, ceonveted to decimal is 100, display 1.00


0x03 Read Holding Register
0x04 Read Input Register
0x06 Write Single Register0x41 Calibration
0x42 Reset energy




0x41 function code is only for internal use (address can be only 0xF8), used for factory calibration and return to factory maintenance occasions, after the function code to increase 16-bit password, the default password is 0x3721


Slave Address + 0x04 + Register Address High Byte + Register Address Low Bute + Number of Registers High Bute + Number Of Registers Low Bute + CRC Check High Bute + CRC Check Low byte.

Correct Reply" Slave Address + 0x04 + Number Of Bytes + Register 1 Data High Byte + Register 1 Data Low Byte +..+ CRC Check High Byte + CRC Check Low Byte

Register adderss
0x0001 Power alarm threshold   1LSB correspond to 1W
0x0002 Modbus-RTU address The ran ger is 0x00001~0x00F7


TTL to USB cable

PZEM-004T w


```


