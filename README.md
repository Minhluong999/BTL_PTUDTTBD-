PHẦN 1: LÀM APP BẰNG MIT APP INVENTOR
1.1. Tạo project MIT App Inventor

Vào trang MIT App Inventor:
```
https://ai2.appinventor.mit.edu
```
Sau đó làm:
```
Projects → Start new project
```
Đặt tên project:
```
MobileBTL_MIT
```

<img width="1360" height="768" alt="image" src="https://github.com/user-attachments/assets/2413e895-bf2e-4ce1-818b-db194414fea0" />

1.3. Làm Screen1: About
Bố cục Screen1

Screen1 là màn hình giới thiệu bản thân và điều hướng sang 2 màn hình còn lại.

Ta cần các thành phần:

Thành phần	Tên nên đặt	Công dụng
VerticalArrangement	Layout_Main	Gom các thành phần theo chiều dọc
Label	lblTitle	Hiển thị tiêu đề
Label	lblInfo	Hiển thị thông tin cá nhân
Button	btnGoSolve	Sang màn hình giải toán
Button	btnGoWeb	Sang màn hình WebView

Kéo thả giao diện Screen1

Trong MIT App Inventor, vào tab Designer.

Từ bên trái `Palette`, kéo vào màn hình:
```
Layout → VerticalArrangement
```
Đổi thuộc tính cho VerticalArrangement:

```
Width: Fill parent
Height: Fill parent
AlignHorizontal: Center
AlignVertical: Center
BackgroundColor: White
```
Sau đó kéo các thành phần sau vào VerticalArrangement:
```
User Interface → Label
User Interface → Label
User Interface → Button
User Interface → Button
```
Đổi tên component

Ở khung Components, đổi tên:
```
Label1 → lblTitle
Label2 → lblInfo
Button1 → btnGoSolve
Button2 → btnGoWeb
```
Cách đổi tên:

Chọn component → Rename → nhập tên mới
Chỉnh thuộc tính Screen1
lblTitle
```
Text: BÀI TẬP LỚN MOBILE
FontSize: 22
FontBold: true
TextAlignment: Center
Width: Fill parent
```
lblInfo
```
Text:
Họ tên: Lăng Nguyễn Minh Lượng
Mã sinh viên: K225480106044
Lớp: K58KMT
Môn học: Phát triển ứng dụng trên thiết bị di động - TEE0419
```
```
FontSize: 16
TextAlignment: Center
Width: Fill parent
```
btnGoSolve
```
Text: Sang màn hình giải toán
Width: Fill parent
Height: Automatic
FontSize: 16
```
btnGoWeb
```
Text: Sang màn hình WebView
Width: Fill parent
Height: Automatic
FontSize: 16
```

<img width="1365" height="768" alt="image" src="https://github.com/user-attachments/assets/dd43b381-2b57-4c7c-b048-c1462fbfc43a" />
