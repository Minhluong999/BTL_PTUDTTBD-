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
Width: Fill parent
```
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4794a2a2-0f13-4fd8-98dc-1bbbffb2bc91" />

1.6. Block xử lý bài toán Screen2

Vào tab Blocks của Screen2.

Ta cần dùng:
```
Variables
Math
Control
Text
```
Tạo block cho nút btnSolve

Logic mô tả bằng lời:
```
Khi bấm nút Giải:
- Lấy dữ liệu từ txtA và txtB
- Chuyển sang số
- Kiểm tra các trường hợp
- Gán kết quả vào lblResult.Text
```
Block tương đương:
```
when btnSolve.Click
do
    if txtA.Text = "" or txtB.Text = ""
        set lblResult.Text to "Vui lòng nhập đầy đủ a và b"
    else
        initialize local a to txtA.Text
        initialize local b to txtB.Text

        if a = 0 and b = 0
            set lblResult.Text to "Phương trình có vô số nghiệm"
        else if a = 0 and b ≠ 0
            set lblResult.Text to "Phương trình vô nghiệm"
        else
            set lblResult.Text to join "Phương trình có nghiệm x = " (-b / a)
```
Trong MIT App Inventor, TextBox trả về kiểu text, nhưng khi dùng với block toán học, App Inventor có thể tự ép kiểu nếu nội dung là số.

Block nút quay lại
```
when btnBack.Click
do close screen
```
Hoặc:
```
when btnBack.Click
do open another screen screenName "Screen1"
```

<img width="882" height="436" alt="image" src="https://github.com/user-attachments/assets/ea9a3a79-11e3-4f5d-900c-2963451ccdda" />

1.7. Làm Screen3: WebViewer

Screen3 dùng để hiển thị web.

Trang cần mở:

https://k58kmt.tdh.io.vn?masv=K225480106044

Giao diện Screen3

Cần các thành phần:

Thành phần	Tên	Công dụng
VerticalArrangement	Layout_Web	Gom giao diện
Label	lblWebTitle	Tiêu đề
WebViewer	webViewer	Hiển thị trang web
Button	btnBack	Quay lại
Kéo thả Screen3

Vào Screen3 → Designer.

Kéo:
```
Layout → VerticalArrangement
Label
User Interface → WebViewer
Button
```
Đổi tên:
```
Label1 → lblWebTitle
WebViewer1 → webViewer
Button1 → btnBack
```
Chỉnh thuộc tính:

lblWebTitle
```
Text: WEBVIEW
FontSize: 20
FontBold: true
TextAlignment: Center
Width: Fill parent
```
webViewer
```
HomeUrl: https://k58kmt.tdh.io.vn?masv=K225480106059
Width: Fill parent
Height: Fill parent
```
btnBack
```
Text: Quay lại
Width: Fill parent
```
MIT App Inventor có tài liệu riêng về các thành phần giao diện như Label, Button, TextBox, WebViewer và cách điều khiển thuộc tính bằng block trong phần Component Documentation.

<img width="1365" height="720" alt="image" src="https://github.com/user-attachments/assets/47850d90-1c1d-440d-addc-6b9dddde57ad" />

Block Screen3

Khi mở Screen3, cho WebViewer truy cập URL.
```
when Screen3.Initialize
do call webViewer.GoToUrl
   url "https://k58kmt.tdh.io.vn?masv=K225480106059"
```
Nút quay lại:
```
when btnBack.Click
do close screen
```

<img width="674" height="292" alt="image" src="https://github.com/user-attachments/assets/903ee0d8-5cf0-4f26-b193-1539b87d4342" />

1.8. Test app MIT App Inventor

Trên thanh công cụ chọn:

Connect → AI Companion

Trên điện thoại cài app:
`
MIT AI2 Companion
`
Quét QR code để chạy thử.
<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/c2b54d26-04e6-410f-a225-d234562f83af" />
<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/8e8b4be9-7d9a-4433-87ef-d9ac960a419f" />
<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/0be8014c-4b2e-42b2-9f52-d5dd0e044480" />
<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/32d1debf-192e-434a-a56d-f5d6131d99dd" />

## PHẦN 2: ANDROID STUDIO APP1 DÙNG ASSETS
### 2.1. Ý tưởng APP1

Ta làm app tên:
`
JavaGuideAssets
`
Chức năng:

App hướng dẫn học Java cơ bản offline

Dữ liệu được chuẩn bị trước trong thư mục:
`
app/src/main/assets/
`
Dữ liệu dạng JSON:
`
lessons.json
`
App đọc file JSON từ Assets, xử lý dữ liệu và hiển thị lên màn hình.

Android xem resources là các file/tài nguyên tĩnh dùng bởi code như chuỗi giao diện, bitmap, layout, animation…; còn thư mục Assets phù hợp khi muốn đóng gói file dữ liệu nguyên bản và tự đọc bằng code.
### 2.2. Tạo project Android Studio

Mở Android Studio:
`
New Project
`
Chọn:
`
Empty Views Activity
`
Không chọn Jetpack Compose để dễ làm bằng XML + Java.

Cấu hình:
```
Name: JavaGuideAssets
Language: Java
Minimum SDK: API 23 hoặc cao hơn
```
