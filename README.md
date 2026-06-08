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

Tạo thêm `Screen2` và `Screen3`

Trên thanh trên cùng:
`
Add Screen
`
Tạo:
```
Screen2
Screen3
```
1.4. Lập trình block chuyển màn hình Screen1

Vào tab `Blocks` của `Screen1`.

Block cho nút sang Screen2

Tạo block:
```
when btnGoSolve.Click
do open another screen screenName "Screen2"
```
Ý nghĩa:
```
Khi người dùng bấm nút btnGoSolve, app sẽ mở màn hình Screen2.
```
Block cho nút sang Screen3

Tạo block:
```
when btnGoWeb.Click
do open another screen screenName "Screen3"
```
Ý nghĩa:
```
Khi người dùng bấm nút btnGoWeb, app sẽ mở màn hình Screen3.
```
<img width="479" height="287" alt="image" src="https://github.com/user-attachments/assets/e7ee4fb3-a158-4797-b070-203f3acc8fa0" />

1.5. Làm Screen2: Giải phương trình bậc nhất

Bài toán:
`
Giải phương trình ax + b = 0
`
Cách xử lý:

```
Nếu a = 0 và b = 0 → phương trình vô số nghiệm
Nếu a = 0 và b ≠ 0 → phương trình vô nghiệm
Nếu a ≠ 0 → nghiệm x = -b / a
```
Giao diện Screen2

Cần các thành phần:

Thành phần	Tên	Công dụng
VerticalArrangement	Layout_Solve	Gom giao diện theo chiều dọc
Label	lblSolveTitle	Tiêu đề
TextBox	txtA	Nhập hệ số a
TextBox	txtB	Nhập hệ số b
Button	btnSolve	Nút giải
Label	lblResult	Hiển thị kết quả
Button	btnBack	Quay lại Screen1
Kéo thả Screen2

Vào Screen2 → Designer.

Kéo:
```
Layout → VerticalArrangement
```
Đổi thuộc tính:
```
Width: Fill parent
Height: Fill parent
AlignHorizontal: Center
AlignVertical: Center
```
Kéo tiếp:
```
Label
TextBox
TextBox
Button
Label
Button
```
Đổi tên:
```
Label1 → lblSolveTitle
TextBox1 → txtA
TextBox2 → txtB
Button1 → btnSolve
Label2 → lblResult
Button2 → btnBack
```
Chỉnh thuộc tính Screen2
lblSolveTitle
```
Text: GIẢI PHƯƠNG TRÌNH ax + b = 0
FontSize: 20
FontBold: true
TextAlignment: Center
Width: Fill parent
```
txtA
```
Hint: Nhập hệ số a
NumbersOnly: true
Width: Fill parent
```
txtB
```
Hint: Nhập hệ số b
NumbersOnly: true
Width: Fill parent
```
btnSolve
```
Text: Giải phương trình
Width: Fill parent
```
lblResult
```
Text: Kết quả sẽ hiển thị ở đây
FontSize: 16
Width: Fill parent
TextAlignment: Center
```
btnBack
```
Text: Quay lại màn hình chính
Width: Fill parent```
