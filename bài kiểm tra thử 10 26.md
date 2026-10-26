

# BÀI LÀM – THI THỬ HACKATHON 02 (GAMEZONE)  
  
- **Họ tên:Nguyễn Trường Khang**  
- **Lớp:CNTT3**  
- **Link repository:**  
- **Hệ điều hành (Windows/macOS):Window**  
  
## 4.2. Thao tác CLI  
  
### Các lệnh đã chạy  
  
```shell  
pwd 
ls -Force
mv cap_nhat.txt docs/
mv .\logo_gamezone.png media/
cp "media/logo_gamezone.png" .\backup\
rm .\temp_207.tmp
cd logs
ls -Force
cd..
Get-ChildItem -Recurse -Force
  
```  
  
### Kết quả liệt kê toàn bộ dự án  
  
```text  
 Directory: D:\de-on-tap-game\starter-kit\agamezone-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/26/2026   1:29 PM                backup
d-----        10/26/2026   1:37 PM                data
d-----        10/26/2026   1:42 PM                docs
d-----        10/26/2026   1:38 PM                logs
d-----        10/26/2026   1:45 PM                media
-a----        10/26/2026   1:13 PM             70 .env
-a----        10/26/2026   1:13 PM           1437 bai_lam.md


    Directory: D:\de-on-tap-game\starter-kit\agamezone-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/26/2026   1:13 PM           8542 logo_gamezone.png


    Directory: D:\de-on-tap-game\starter-kit\agamezone-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/26/2026   1:13 PM           5814 giao_dich_thang_11.xlsx


    Directory: D:\de-on-tap-game\starter-kit\agamezone-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/26/2026   1:13 PM             61 cap_nhat.txt


    Directory: D:\de-on-tap-game\starter-kit\agamezone-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/26/2026   1:13 PM            986 game.log


    Directory: D:\de-on-tap-game\starter-kit\agamezone-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/26/2026   1:13 PM           8542 logo_gamezone.png
  
```  
  
## 4.3. Lọc log thủ công  
  
### Lệnh đã chạy  
  
```shell  
Get-Content logs/game.log | Select-String "ERROR" > logs/daily_report.txt
Get-Content logs/daily_report.txt
  
```  
  
### 2 dòng lỗi đầu tiên trong daily_report.txt  
  
```text  
2025-11-05 08:03:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:09:15 [ERROR] Mat ket noi may chu game
  
```  
  
## 4.4. README.md  
  
> Chấm trực tiếp trên `README.md` ở gốc dự án.  
  
- [ ] Heading 1  
- [ ] Mô tả in đậm + in nghiêng  
- [ ] Bảng `Thư mục | Nội dung` (≥3 dòng)  
- [ ] Code block lệnh liệt kê  
- [ ] Task list (≥2 việc, ≥1 đã xong)  
- [ ] Blockquote nhắc không upload `.env`  
  
## 4.5. Chạy script auto_report  
  
### Lệnh chạy  
  
```shell  
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\auto_report.ps1
Get-Content logs/auto_report.txt
  
```  
  
### Nội dung file logs/auto_report.txt  
  
```text  
2025-11-05 08:03:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:09:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:12:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:39:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:42:15 [ERROR] Mat ket noi may chu game
2025-11-05 08:51:15 [ERROR] Loi luu tien trinh choi

```  
  
## 4.6. Đếm số dòng lỗi  
  
### Lệnh  
  
```shell  
Get-Content logs/game.log | Select-String "ERROR" | Measure-Object | Select-Object -ExpandProperty Count  
  
```  
  
### Kết quả đếm  
  
```text  
6 
  
```  
  
## 4.7. Báo cáo tổng hợp  
  
### Các lệnh đã chạy  
  
```shell 

Get-Content logs/game.log | Select-String "WARNING" >> logs/tong_hop.txt

(Get-Content logs/game.log | Select-String "ERROR" | Measure-Object).Count >> logs/tong_hop.txt

Get-Content logs/tong_hop.txt 
  
```  
  
### Nội dung file logs/tong_hop.txt  
  
```text  
2025-11-05 08:54:15 [WARNING] May chu qua tai CPU 90%  
  
```  
  
## 4.8. Excel  
  
> Chấm trực tiếp trên file `data/giao_dich_thang_11.xlsx`.
