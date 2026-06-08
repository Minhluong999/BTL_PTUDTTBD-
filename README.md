## PHẦN 1: LÀM APP BẰNG MIT APP INVENTOR
### 1.1. Tạo project MIT App Inventor

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

# PHẦN 2: ANDROID STUDIO APP1 - SỬ DỤNG DỮ LIỆU TRONG ASSETS

## 2.1. AndroidManifest.xml

AndroidManifest.xml là file cấu hình trung tâm của ứng dụng Android.

Chức năng:

- Khai báo Activity.
- Khai báo quyền truy cập.
- Khai báo theme.
- Khai báo màn hình khởi động.

Ví dụ:

```xml
<activity
    android:name=".MainActivity"
    android:exported="true">

    <intent-filter>
        <action android:name="android.intent.action.MAIN"/>
        <category android:name="android.intent.category.LAUNCHER"/>
    </intent-filter>

</activity>
```

### Khai báo quyền

Ví dụ ứng dụng cần Internet:

```xml
<uses-permission
    android:name="android.permission.INTERNET"/>
```

### Check quyền bằng Java

```java
if (checkSelfPermission(
        Manifest.permission.CAMERA)
        != PackageManager.PERMISSION_GRANTED) {

    requestPermissions(
            new String[]{
                    Manifest.permission.CAMERA
            },
            100);
}
```

Ý nghĩa:

- checkSelfPermission(): kiểm tra quyền.
- requestPermissions(): yêu cầu người dùng cấp quyền.


---

## 2.2. Vòng đời Activity

| Hàm | Ý nghĩa |
|------|----------|
| onCreate() | Tạo Activity |
| onStart() | Bắt đầu hiển thị |
| onResume() | Người dùng tương tác |
| onPause() | Tạm dừng |
| onStop() | Ẩn khỏi màn hình |
| onDestroy() | Hủy Activity |

### Vì sao Android tự sinh onCreate()?

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}
```

Dùng để:

- Gắn giao diện XML.
- Khởi tạo View.
- Đọc dữ liệu ban đầu.

---

## 2.3. Giao diện XML

Android mô tả giao diện bằng file XML trong:

```text
res/layout
```

Ví dụ:

```xml
<LinearLayout
    android:orientation="vertical">

    <TextView/>

    <Button/>

</LinearLayout>
```

### LinearLayout

```xml
android:orientation="vertical"
```

Các đối tượng nằm theo chiều dọc.

```xml
android:orientation="horizontal"
```

Các đối tượng nằm theo chiều ngang.

### Gravity

```xml
android:gravity="center"
```

Căn giữa nội dung.

   
---

## 2.4. Resource và Strings

Không nên hardcode:

```java
txtTitle.setText("Hướng dẫn Java");
```

Nên lưu trong:

```text
res/values/strings.xml
```

Ví dụ:

```xml
<string name="app_title">
    Hướng dẫn học Java cơ bản
</string>
```

Tham chiếu:

XML:

```xml
@string/app_title
```

Java:

```java
R.string.app_title
```

Ưu điểm:

- Dễ sửa đổi.
- Hỗ trợ đa ngôn ngữ.
- Hỗ trợ Theme.
- Tránh lặp dữ liệu.

Android tự động lấy resource theo:

- Language
- Location
- Theme

Ví dụ:

```text
values/
values-en/
values-night/
```

---

## 2.5. Code tương tác với Layout

```java
TextView txtContent =
        findViewById(R.id.txtContent);
```

Hiển thị dữ liệu:

```java
txtContent.setText(
        getString(R.string.app_title)
);
```

Sử dụng getString() thay vì text hardcode để hỗ trợ Language và Theme.

---

## 2.6. Event (Sự kiện)

### Cách 1: setOnClickListener

```java
btnReload.setOnClickListener(v -> {
    loadData();
});
```

### Cách 2: android:onClick

XML:

```xml
<Button
    android:onClick="reloadData"/>
```

Java:

```java
public void reloadData(View view){
    loadData();
}
```

Để xử lý event:

- Layout khai báo Button.
- Java viết hàm xử lý tương ứng.

---

## 2.7. Sử dụng Assets

Assets là thư mục chứa các file đi kèm ứng dụng.

Ví dụ:

```text
assets/
├── lessons.json
├── guide.html
├── image.png
```

Khi build APK:

```text
Assets
↓
Đóng gói vào APK
↓
Có thể sử dụng Offline
```

### Truy cập file Assets

```java
InputStream inputStream =
        getAssets().open("lessons.json");
```

Lợi ích:

- Không cần Internet.
- Dữ liệu luôn có sẵn.
- Truy cập nhanh.

**CHÈN ẢNH: Thư mục Assets**

---

## 2.8. APP1 – Java Learning Offline

### Ý tưởng

Xây dựng ứng dụng học Java Offline sử dụng dữ liệu chuẩn bị trước trong Assets.

Các chức năng:

- Hiển thị danh sách bài học.
- Tìm kiếm bài học.
- Xem chi tiết bài học.
- Đánh dấu bài đã học.
- Lưu tiến độ học bằng SharedPreferences.
- Hoạt động hoàn toàn Offline.

### Dữ liệu sử dụng

File:

```text
assets/lessons.json
```

Định dạng:

```json
[
  {
    "title":"Bài 1",
    "level":"Cơ bản",
    "content":"..."
  }
]
```

### Đặc thù dữ liệu

```text
JSON Array
    └── JSON Object
```

Mỗi bài học gồm:

- title
- level
- content

### Thuật toán xử lý

```text
Đọc lessons.json
↓
Chuyển thành JSONArray
↓
Duyệt từng bài học
↓
Tạo danh sách Lesson
↓
Hiển thị lên ListView
↓
Hiển thị chi tiết bằng TextView
```

### Đối tượng hiển thị

- ListView: hiển thị danh sách bài học.
- TextView: hiển thị nội dung.
- EditText: tìm kiếm.
- ScrollView: hỗ trợ cuộn.
- SharedPreferences: lưu trạng thái đã học.

<img width="1347" height="709" alt="image" src="https://github.com/user-attachments/assets/d7800cdd-0154-460e-909b-c8d001dfe098" />

Kết quả chạy trên điện thoại

<img width="320" height="595" alt="image" src="https://github.com/user-attachments/assets/fb5046ba-f3d7-4db5-9d10-f6215c9cc7ad" />

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/d9a0f53c-2b41-45da-8977-d7e6be86e49a" />

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/d1a114ab-a307-489a-9ada-3bc01f7b9f67" />


