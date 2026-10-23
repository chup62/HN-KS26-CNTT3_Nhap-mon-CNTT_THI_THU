# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên:** Nguyen Trung Thanh
- **Lớp:** CNTT-3
- **Link repository:** 
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
Get-ChildItem -Force
Move-Item nhap_hang.txt docs
Move-Item logo_van_phong_pham.png media
Copy-Item media\logo_van_phong_pham.png backup
Remove-Item *.tmp
cd logs
Get-ChildItem
cd ..
Get-ChildItem -Recurse -Force
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text


    Directory: C:\Users\OS\Downloads\starter-kit\starter-kit\van-phong-pham-website


Mode                 LastWriteTime         Length Name                                                                                                                         
----                 -------------         ------ ----                                                                                                                         
d-----        10/23/2026   6:09 PM                backup                                                                                                                       
d-----        10/23/2026   6:08 PM                data                                                                                                                         
d-----        10/23/2026   6:09 PM                docs                                                                                                                         
d-----        10/23/2026   6:11 PM                logs                                                                                                                         
d-----        10/23/2026   6:09 PM                media                                                                                                                        
------        10/19/2026   9:41 AM             78 .env                                                                                                                         
-a----        10/23/2026   6:10 PM            256 auto_report.ps1                                                                                                              
-a----        10/19/2026  10:00 AM           2253 bai_lam.md                                                                                                                   
-a----        10/23/2026   6:13 PM            723 README.md                                                                                                                    


    Directory: C:\Users\OS\Downloads\starter-kit\starter-kit\van-phong-pham-website\backup


Mode                 LastWriteTime         Length Name                                                                                                                         
----                 -------------         ------ ----                                                                                                                         
-a----        10/19/2026   9:41 AM           6053 logo_van_phong_pham.png                                                                                                      


    Directory: C:\Users\OS\Downloads\starter-kit\starter-kit\van-phong-pham-website\data


Mode                 LastWriteTime         Length Name                                                                                                                         
----                 -------------         ------ ----                                                                                                                         
-a----        10/19/2026   9:41 AM           6105 don_ban_thang_10.xlsx                                                                                                        


    Directory: C:\Users\OS\Downloads\starter-kit\starter-kit\van-phong-pham-website\docs


Mode                 LastWriteTime         Length Name                                                                                                                         
----                 -------------         ------ ----                                                                                                                         
-a----        10/19/2026   9:41 AM             51 nhap_hang.txt                                                                                                                


    Directory: C:\Users\OS\Downloads\starter-kit\starter-kit\van-phong-pham-website\logs


Mode                 LastWriteTime         Length Name                                                                                                                         
----                 -------------         ------ ----                                                                                                                         
-a----        10/23/2026   6:11 PM            710 auto_report.txt                                                                                                              
-a----        10/23/2026   6:09 PM            668 daily_report.txt                                                                                                             
-a----        10/19/2026   9:41 AM           1053 shop.log                                                                                                                     
-a----        10/23/2026   6:11 PM            406 tong_hop.txt                                                                                                                 


    Directory: C:\Users\OS\Downloads\starter-kit\starter-kit\van-phong-pham-website\media


Mode                 LastWriteTime         Length Name                                                                                                                         
----                 -------------         ------ ----                                                                                                                         
-a----        10/19/2026   9:41 AM           6053 logo_van_phong_pham.png                                                                                                      




```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
Get-Content logs\shop.log | Select-String "ERROR" > logs\daily_report.txt
Get-Content logs\daily_report.txt
Get-Content logs\daily_report.txt -TotalCount 2
```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và *in nghiêng*
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
.\auto_report.ps1
```

### Nội dung file logs/auto_report.txt

```text
=== BAO CAO LOI ===

2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:33:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:39:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:42:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 09:12:28 [ERROR] Thanh toan bi tu choi
```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
Get-Content logs\shop.log | Select-String "ERROR" | Measure-Object
```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
Count : 6
```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
"=== TONG HOP LOG ===" > logs\tong_hop.txt
Get-Content logs\shop.log | Select-String "WARNING" >> logs\tong_hop.txt
(Get-Content logs\shop.log | Select-String "ERROR" | Measure-Object).Count >> logs\tong_hop.txt
Get-Content logs\tong_hop.txt
```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===

2025-10-28 08:51:28 [WARNING] Thoi gian tai trang cham
2025-10-28 08:54:28 [WARNING] Anh san pham dung luong lon
2025-10-28 08:57:28 [WARNING] Thoi gian tai trang cham

6
```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.
