Some image of esp32 s3 


esp32-s3-super-mini
https://www.espboards.dev/esp32/esp32-s3-super-mini/
```
platformio.ini

[env:esp32-s3-super-mini]
platform  = espressif32
board     = esp32-s3-devkitm-1
framework = arduino

; Exact hardware config for ESP32-S3 Super Mini
board_build.mcu        = esp32s3
board_build.f_cpu      = 240000000L
board_build.flash_size = 4MB
board_build.flash_mode = qio
board_upload.flash_size = 4MB
```
