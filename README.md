Bài 6 : Thiết lập môi trường làm việc cho hệ thống Smart-Farm trên SoC

- **Bước 1:** Từ thư mục Home (`~`), tạo thư mục `smart-farm` chứa `bin`, `config`, `data` bằng **1 dòng lệnh** PowerShell.

- NewItem -Itemtype directory -Force -Path "Home\smart-farm\bin". "Home\smart-farm\config" , "Home\smart-farm\data"
- 

- **Bước 2:** Tạo file ẩn `.env` trong `config` để chứa mật khẩu cảm biến. Giải thích tại sao `Get-ChildItem` thông thường không nhìn thấy file `.env` *?*

- Lý do là Get-ChildItem đọc được file .env; mặc định nó chỉ không hiển thị file có thuộc tính Hidden trong danh sách

- lệnh ta có : NewItem -Itemtype File -Path "Home\smart-farm\config\.env"
- 

- - **Bước 3:** Sao chép file mẫu `template.ps1` từ thư mục `Public` vào `bin` và đổi tên thành `pump_control.ps1` chỉ trong **1 lệnh duy nhất**
 
  _ Copy-Item "$env:PUBLIC\template.ps1" -Destination "Home\smart-farm\bin\pump_control.ps1"
  

  - **Bước 4:** Dùng lệnh liệt kê để kiểm tra lại toàn bộ cấu trúc thư mục `smart-farm` vừa tạo, xác nhận đủ 3 thư mục con và các file đã đúng vị trí
 
  - Get-ChildItem "Home\smart-farm" -Force -Recurse
 

**Bước cuối **

Nếu chương trình bị lỗi cần chậy bằng quyền quản lý (Access denied)


ta dùng lệnh sau : Star-Process powershell -Verb Runas
