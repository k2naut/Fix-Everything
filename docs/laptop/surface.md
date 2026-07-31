# Microsoft Surface Inspection Checklist

> Version: 1.0

---

# 1. Machine Information

## Mục đích

Xác định đúng model và cấu hình.

## Thực hiện

Settings → System → About

hoặc

```powershell
systeminfo
```

hoặc

```powershell
wmic computersystem get model
```

## Đánh giá

✅ Đúng model quảng cáo

✅ CPU đúng

✅ RAM đúng

✅ Windows bản quyền

---

# 2. Serial Number

## Thực hiện

```cmd
wmic bios get serialnumber
```

hoặc

```powershell
Get-CimInstance Win32_BIOS
```

## Đánh giá

✅ Có Serial

✅ Không bị Unknown

---

# 3. SSD

## Thực hiện

PowerShell

```powershell
Get-PhysicalDisk
```

Xem SMART

CrystalDiskInfo

## Đánh giá

| Tiêu chí | PASS |
|----------|------|
| Health | >95% |
| Temperature | <45°C |
| Bad Sector | 0 |
| Interface | NVMe |

---

# 4. Battery

## Sinh Battery Report

```cmd
powercfg /batteryreport
```

Mở

```
battery-report.html
```

Quan sát

```
DESIGN CAPACITY

FULL CHARGE CAPACITY

CYCLE COUNT
```

## Đánh giá

Health

```
>95%
```

Excellent

```
90-95%
```

Very Good

```
85-90%
```

Good

```
80-85%
```

Accept

```
<80%
```

Replace

Cycle Count

```
<200
```

Excellent

```
200~400
```

Good

```
>600
```

Consider Replace

---

# 5. RAM

## Thực hiện

```powershell
wmic memorychip
```

hoặc

Task Manager

## Đánh giá

✅ Đúng dung lượng

✅ Đúng bus

---

# 6. CPU

## Thực hiện

CPU-Z

hoặc

```powershell
wmic cpu get name
```

Stress Test

CPU-Z Bench

Cinebench

## Đánh giá

✅ Turbo hoạt động

✅ Không tụt xung

✅ Không quá 95°C

---

# 7. Display

## Dead Pixel

Mở

https://lcdtech.info/en/tests/dead.pixel.htm

Kiểm tra

- White
- Black
- Red
- Green
- Blue

## PASS

✅ Không điểm chết

---

# 8. Touch

Mở

Paint

Vẽ kín toàn màn hình.

## PASS

Không đứt nét.

---

# 9. Surface Pen

- Pair Bluetooth

- Viết

- Eraser

- Pressure

PASS

Tất cả hoạt động.

---

# 10. Speaker

Mở YouTube

Left / Right Test

PASS

Không rè

Không lệch

---

# 11. Camera

Windows Camera

Kiểm tra

Front

Rear

Windows Hello

PASS

Ảnh rõ

Không lỗi

---

# 12. Keyboard

Keyboard Tester

https://keyboard-test.space/

PASS

Toàn bộ phím hoạt động.

---

# 13. Touchpad

- Left Click

- Right Click

- Scroll

- Zoom

PASS

Hoạt động bình thường.

---

# 14. USB

USB-A

Copy file 5GB

USB-C

Copy file

Display

Charge

PASS

Không ngắt kết nối.

---

# 15. WiFi

Speedtest

Ping

Bluetooth

Pair tai nghe

PASS

Không rớt mạng.

---

# 16. Temperature

HWiNFO

Idle

<55°C

Load

<90°C

PASS

Không throttle.

---

# 17. Fan

Stress 10 phút

PASS

Không kêu

Không rung

---

# 18. Charger

Kiểm tra

Sạc

Đèn LED

Nhiệt

PASS

Không nóng bất thường.

---

# 19. Exterior

Kiểm tra

- Móp

- Cong

- Trầy

- Hở màn

- Bung pin

PASS

Ngoại hình >90%.

---

# 20. Final

| Item | PASS | FAIL |
|------|------|------|
| Exterior | | |
| Screen | | |
| Touch | | |
| SSD | | |
| Battery | | |
| CPU | | |
| Camera | | |
| Speaker | | |
| USB | | |
| WiFi | | |

Overall

⭐⭐⭐⭐⭐
