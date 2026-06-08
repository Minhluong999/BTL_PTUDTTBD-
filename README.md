# BÀI TẬP LỚN MÔN PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG - TEE0419

## Thông tin sinh viên

- Họ và tên: **Lăng Nguyễn Minh Lượng**
- Mã sinh viên: **K225480106044**

---

# 1. ỨNG DỤNG MIT APP INVENTOR

## 1.1. Mục tiêu

Phần này xây dựng một ứng dụng bằng MIT App Inventor, tập trung vào quy trình tạo phần mềm bằng phương pháp kéo thả giao diện và lập trình bằng block.

Ứng dụng gồm 3 Screen:

- **Screen1**: giới thiệu thông tin cá nhân và có nút chuyển sang hai màn hình còn lại.
- **Screen2**: giải bài toán đơn giản.
- **Screen3**: dùng WebViewer để hiển thị một trang web có sẵn.

---

## 1.2. Tạo project MIT App Inventor

Truy cập MIT App Inventor:

```text
https://ai2.appinventor.mit.edu
```

Tạo project mới:

```text
Projects → Start new project
```

Tên project:

```text
MobileBTL_MIT
```

<img width="1360" height="768" alt="image" src="https://github.com/user-attachments/assets/2413e895-bf2e-4ce1-818b-db194414fea0" />

---

## 1.3. Thanh công cụ và quy trình thiết kế trong MIT App Inventor

MIT App Inventor có các khu vực chính:

| Khu vực | Chức năng |
|---|---|
| Palette | Chứa các thành phần giao diện như Label, Button, TextBox, WebViewer |
| Viewer | Khu vực mô phỏng màn hình điện thoại để kéo thả giao diện |
| Components | Danh sách các thành phần đã dùng trong Screen |
| Properties | Thay đổi thuộc tính của component |
| Blocks | Lập trình logic bằng các khối lệnh kéo thả |
| Media/Assets | Quản lý file hình ảnh, âm thanh hoặc dữ liệu đi kèm |

Quy trình thiết kế giao diện gồm: kéo component từ **Palette** vào **Viewer**, chọn component trong **Components**, sau đó chỉnh thuộc tính trong **Properties** như `Text`, `Width`, `Height`, `FontSize`, `TextAlignment`, `BackgroundColor`.

Block trong MIT App Inventor là các khối lệnh trực quan. Người dùng ghép các block lại với nhau để tạo luồng xử lý thay vì viết code bằng ngôn ngữ lập trình truyền thống.

Ưu điểm của block:

- Dễ học, phù hợp người mới bắt đầu.
- Không cần nhớ cú pháp code.
- Ít gặp lỗi cú pháp.
- Dễ quan sát luồng xử lý.

Nhược điểm:

- Khi ứng dụng lớn, block dễ rối.
- Khả năng tùy biến hạn chế hơn viết code Java/Kotlin.
- Khó tối ưu với các ứng dụng phức tạp.

**Backpack** là công cụ dùng để sao chép và tái sử dụng block. Có thể kéo block vào Backpack rồi lấy ra dùng lại ở Screen khác hoặc project khác.

---

## 1.4. Screen1 - About

Screen1 dùng để giới thiệu thông tin sinh viên và điều hướng sang Screen2, Screen3.

Các thành phần sử dụng:

| Thành phần | Tên đặt | Công dụng |
|---|---|---|
| VerticalArrangement | Layout_Main | Gom các thành phần theo chiều dọc |
| Label | lblTitle | Hiển thị tiêu đề |
| Label | lblInfo | Hiển thị thông tin cá nhân |
| Button | btnGoSolve | Chuyển sang Screen2 |
| Button | btnGoWeb | Chuyển sang Screen3 |

Thuộc tính chính:

```text
lblTitle.Text: BÀI TẬP LỚN MOBILE
lblInfo.Text: Họ tên, mã sinh viên, lớp, môn học
btnGoSolve.Text: Sang màn hình giải toán
btnGoWeb.Text: Sang màn hình WebView
```

<img width="1365" height="768" alt="image" src="https://github.com/user-attachments/assets/dd43b381-2b57-4c7c-b048-c1462fbfc43a" />

Tạo thêm hai Screen:

```text
Screen2
Screen3
```

Block chuyển màn hình:

```text
when btnGoSolve.Click
do open another screen screenName "Screen2"

when btnGoWeb.Click
do open another screen screenName "Screen3"
```

<img width="479" height="287" alt="image" src="https://github.com/user-attachments/assets/e7ee4fb3-a158-4797-b070-203f3acc8fa0" />

---

## 1.5. Screen2 - Giải phương trình bậc nhất

Bài toán được chọn:

```text
Giải phương trình ax + b = 0
```

Các trường hợp xử lý:

```text
Nếu a = 0 và b = 0 → phương trình có vô số nghiệm
Nếu a = 0 và b ≠ 0 → phương trình vô nghiệm
Nếu a ≠ 0 → nghiệm x = -b / a
```

Các thành phần sử dụng:

| Thành phần | Tên đặt | Công dụng |
|---|---|---|
| VerticalArrangement | Layout_Solve | Gom giao diện theo chiều dọc |
| Label | lblSolveTitle | Tiêu đề |
| TextBox | txtA | Nhập hệ số a |
| TextBox | txtB | Nhập hệ số b |
| Button | btnSolve | Nút giải phương trình |
| Label | lblResult | Hiển thị kết quả |
| Button | btnBack | Quay lại Screen1 |

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/4794a2a2-0f13-4fd8-98dc-1bbbffb2bc91" />

Block xử lý bài toán:

```text
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

Block quay lại:

```text
when btnBack.Click
do close screen
```

<img width="882" height="436" alt="image" src="https://github.com/user-attachments/assets/ea9a3a79-11e3-4f5d-900c-2963451ccdda" />

---

## 1.6. Screen3 - WebViewer

Screen3 sử dụng WebViewer để mở trang web của giảng viên theo mã sinh viên.

URL sử dụng:

```text
https://k58kmt.tdh.io.vn?masv=K225480106044
```

Các thành phần sử dụng:

| Thành phần | Tên đặt | Công dụng |
|---|---|---|
| VerticalArrangement | Layout_Web | Gom giao diện |
| Label | lblWebTitle | Tiêu đề |
| WebViewer | webViewer | Hiển thị trang web |
| Button | btnBack | Quay lại |

<img width="1365" height="720" alt="image" src="https://github.com/user-attachments/assets/47850d90-1c1d-440d-addc-6b9dddde57ad" />

Block Screen3:

```text
when Screen3.Initialize
do call webViewer.GoToUrl
   url "https://k58kmt.tdh.io.vn?masv=K225480106044"

when btnBack.Click
do close screen
```

<img width="674" height="292" alt="image" src="https://github.com/user-attachments/assets/903ee0d8-5cf0-4f26-b193-1539b87d4342" />

---

## 1.7. Test ứng dụng MIT App Inventor

Sử dụng MIT AI2 Companion để quét mã QR và chạy thử ứng dụng trên điện thoại.

Các chức năng đã kiểm thử:

- Screen1 hiển thị thông tin sinh viên.
- Chuyển từ Screen1 sang Screen2.
- Screen2 giải phương trình bậc nhất.
- Chuyển từ Screen1 sang Screen3.
- Screen3 mở trang web bằng WebViewer.

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/c2b54d26-04e6-410f-a225-d234562f83af" />

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/8e8b4be9-7d9a-4433-87ef-d9ac960a419f" />

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/0be8014c-4b2e-42b2-9f52-d5dd0e044480" />

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/32d1debf-192e-434a-a56d-f5d6131d99dd" />

---

# 2. ANDROID STUDIO APP1 - ỨNG DỤNG DỮ LIỆU TRONG ASSETS

## 2.1. Mục tiêu APP1

APP1 sử dụng cơ chế dữ liệu chuẩn bị trước trong thư mục **Assets**. Ứng dụng được xây dựng bằng Android Studio, ngôn ngữ Java.

Vấn đề đặt ra:

```text
Xây dựng ứng dụng học Java Offline.
Dữ liệu bài học có sẵn trong app.
Người dùng có thể xem bài học, tìm kiếm và đánh dấu bài đã học mà không cần Internet.
```

---

## 2.2. AndroidManifest.xml

`AndroidManifest.xml` là file cấu hình trung tâm của ứng dụng Android.

Chức năng:

- Khai báo Activity.
- Khai báo quyền truy cập.
- Khai báo theme.
- Khai báo màn hình khởi động.

Ví dụ khai báo Activity chính:

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

Ví dụ khai báo quyền Internet:

```xml
<uses-permission android:name="android.permission.INTERNET"/>
```

Kiểm tra quyền bằng Java:

```java
if (checkSelfPermission(Manifest.permission.CAMERA)
        != PackageManager.PERMISSION_GRANTED) {

    requestPermissions(
            new String[]{Manifest.permission.CAMERA},
            100);
}
```

Ý nghĩa:

- `checkSelfPermission()` kiểm tra quyền đã được cấp hay chưa.
- `requestPermissions()` yêu cầu người dùng cấp quyền khi chạy app.

---

## 2.3. Vòng đời Activity

Các hàm vòng đời chính:

| Hàm | Ý nghĩa |
|---|---|
| onCreate() | Activity được tạo |
| onStart() | Activity bắt đầu hiển thị |
| onResume() | Activity sẵn sàng tương tác |
| onPause() | Activity tạm dừng |
| onStop() | Activity bị ẩn |
| onDestroy() | Activity bị hủy |

Khi tạo project, Android Studio tự sinh hàm `onCreate()` vì đây là nơi khởi tạo Activity ban đầu.

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}
```

Trong `onCreate()` thường thực hiện:

- Gắn giao diện XML bằng `setContentView()`.
- Ánh xạ View bằng `findViewById()`.
- Khởi tạo dữ liệu.
- Gắn sự kiện cho Button.

---

## 2.4. Giao diện XML và Resource

Giao diện Android được mô tả bằng file XML trong thư mục:

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

`LinearLayout` là đối tượng chứa các View con. Thuộc tính `orientation` quy định cách sắp xếp:

```xml
android:orientation="vertical"
```

Các đối tượng con nằm theo chiều dọc.

```xml
android:orientation="horizontal"
```

Các đối tượng con nằm theo chiều ngang.

Thuộc tính `gravity` dùng để căn chỉnh nội dung:

```xml
android:gravity="center"
```

---

## 2.5. Tránh hardcode bằng strings.xml

Không nên viết trực tiếp:

```java
txtTitle.setText("Hướng dẫn Java");
```

Nên lưu trong:

```text
res/values/strings.xml
```

Ví dụ:

```xml
<string name="app_title">Hướng dẫn học Java cơ bản</string>
```

Tham chiếu trong XML:

```xml
@string/app_title
```

Tham chiếu trong Java:

```java
R.string.app_title
```

Ưu điểm:

- Dễ sửa đổi.
- Hỗ trợ đa ngôn ngữ.
- Hỗ trợ theme.
- Tránh lặp nội dung.

Android có thể tự chọn resource phù hợp theo:

```text
Language
Location
Theme
```

Ví dụ:

```text
values/
values-en/
values-night/
```

Nhờ đó ứng dụng có thể thay đổi ngôn ngữ và giao diện sáng/tối theo thiết lập của người dùng.

---

## 2.6. Code tương tác với Layout và Event

Ánh xạ View:

```java
TextView txtContent = findViewById(R.id.txtContent);
```

Hiển thị dữ liệu:

```java
txtContent.setText(getString(R.string.app_title));
```

Sự kiện người dùng có thể xử lý bằng hai cách.

Cách 1: `setOnClickListener`

```java
btnReload.setOnClickListener(v -> {
    loadData();
});
```

Cách 2: khai báo `android:onClick` trong XML:

```xml
<Button
    android:onClick="reloadData"/>
```

Trong Java:

```java
public void reloadData(View view) {
    loadData();
}
```

---

## 2.7. Sử dụng Assets

`Assets` là thư mục chứa các file đi kèm ứng dụng như JSON, HTML, hình ảnh, âm thanh.

Ví dụ:

```text
assets/
├── lessons.json
├── guide.html
└── image.png
```

Khi biên dịch APK, các file trong Assets được đóng gói vào app và có thể sử dụng offline.

Cú pháp truy cập file:

```java
InputStream inputStream = getAssets().open("lessons.json");
```

Lợi ích:

- Không cần Internet.
- Dữ liệu có sẵn trong app.
- Truy cập nhanh.
- Phù hợp ứng dụng học tập hoặc tra cứu offline.

---

## 2.8. APP1 - Java Learning Offline

APP1 được xây dựng dưới dạng ứng dụng học Java Offline.

Dữ liệu lưu trong file:

```text
assets/lessons.json
```

Định dạng dữ liệu:

```json
[
  {
    "title": "Bài 1",
    "level": "Cơ bản",
    "content": "..."
  }
]
```

Đặc thù dữ liệu:

```text
JSON Array
    └── JSON Object
```

Mỗi bài học gồm:

- `title`: tên bài học.
- `level`: cấp độ bài học.
- `content`: nội dung bài học.

Thuật toán xử lý:

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

Đối tượng hiển thị:

- `ListView`: hiển thị danh sách bài học.
- `TextView`: hiển thị nội dung chi tiết.
- `EditText`: tìm kiếm bài học.
- `ScrollView`: hỗ trợ cuộn nội dung.
- `SharedPreferences`: lưu trạng thái đã học.

<img width="1347" height="709" alt="image" src="https://github.com/user-attachments/assets/d7800cdd-0154-460e-909b-c8d001dfe098" />

Kết quả chạy trên điện thoại:

<img width="320" height="595" alt="image" src="https://github.com/user-attachments/assets/fb5046ba-f3d7-4db5-9d10-f6215c9cc7ad" />

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/d9a0f53c-2b41-45da-8977-d7e6be86e49a" />

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/d1a114ab-a307-489a-9ada-3bc01f7b9f67" />

---

# 3. ANDROID STUDIO APP2 - ỨNG DỤNG 3 ACTIVITY

## 3.1. Mục tiêu APP2

APP2 được xây dựng bằng Android Studio, sử dụng Java và XML Layout. Ứng dụng có chức năng tương đương với app MIT App Inventor.

Ứng dụng gồm 3 Activity:

- **MainActivity**: màn hình About, hiển thị thông tin sinh viên và nút chuyển sang hai Activity còn lại.
- **SolveActivity**: giải bài toán đơn giản và gửi kết quả lên API.
- **WebActivity**: sử dụng WebView để mở trang web theo mã sinh viên.

---

## 3.2. Cấu trúc APP2

Tên project:

```text
MobileBTLAndroid
```

Package:

```text
com.example.mobilebtlandroid
```

Cấu trúc chính:

```text
app/
├── manifests/
│   └── AndroidManifest.xml
├── java/
│   └── com.example.mobilebtlandroid/
│       ├── MainActivity.java
│       ├── SolveActivity.java
│       └── WebActivity.java
└── res/
    ├── layout/
    │   ├── activity_main.xml
    │   ├── activity_solve.xml
    │   └── activity_web.xml
    └── values/
        └── strings.xml
```

<img width="1341" height="702" alt="image" src="https://github.com/user-attachments/assets/8ea5e196-f6ad-4147-bfe6-17003e50ba03" />

---

## 3.3. AndroidManifest.xml của APP2

APP2 cần quyền Internet để gọi API và mở WebView:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

Khai báo 3 Activity:

```xml
<activity android:name=".WebActivity" android:exported="false" />

<activity android:name=".SolveActivity" android:exported="false" />

<activity
    android:name=".MainActivity"
    android:exported="true">

    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>

</activity>
```

Ý nghĩa:

- `MainActivity` là màn hình chạy đầu tiên.
- `SolveActivity` là màn hình giải toán.
- `WebActivity` là màn hình WebView.
- Quyền `INTERNET` cho phép app gửi dữ liệu lên API và truy cập website.

---

## 3.4. MainActivity - Màn hình About

File sử dụng:

```text
MainActivity.java
activity_main.xml
```

Chức năng:

- Hiển thị thông tin sinh viên.
- Có nút mở `SolveActivity`.
- Có nút mở `WebActivity`.

Code chuyển Activity:

```java
btnGoSolve.setOnClickListener(v -> {
    Intent intent = new Intent(MainActivity.this, SolveActivity.class);
    startActivity(intent);
});

btnGoWeb.setOnClickListener(v -> {
    Intent intent = new Intent(MainActivity.this, WebActivity.class);
    startActivity(intent);
});
```

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/794030e3-e67c-4604-be33-db9bafecc2cb" />

---

## 3.5. SolveActivity - Giải phương trình và gửi API

Bài toán được chọn:

```text
Giải phương trình bậc nhất: ax + b = 0
```

Cách xử lý:

```text
Nếu a = 0 và b = 0  → phương trình có vô số nghiệm
Nếu a = 0 và b ≠ 0  → phương trình vô nghiệm
Nếu a ≠ 0           → nghiệm x = -b / a
```

Công thức:

```text
x = -b / a
```

Giao diện gồm:

- Ô nhập hệ số `a`.
- Ô nhập hệ số `b`.
- Nút giải phương trình và gửi API.
- Vùng hiển thị kết quả.
- Nút quay lại.

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/430e1074-3a1e-4225-b8df-14c5509d9d46" />

Code xử lý chính:

```java
double a = Double.parseDouble(strA);
double b = Double.parseDouble(strB);

String ketLuan;
double nghiem = 0;

if (a == 0 && b == 0) {
    ketLuan = "Phương trình có vô số nghiệm";
} else if (a == 0) {
    ketLuan = "Phương trình vô nghiệm";
} else {
    nghiem = -b / a;
    ketLuan = "Phương trình có nghiệm x = " + nghiem;
}
```

Ví dụ:

```text
a = 1
b = 2
```

Kết quả:

```text
x = -2
```

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/1ae25f3f-1d35-4749-8d3b-17cbdec5fd44" />

---

## 3.6. Gửi dữ liệu lên API

Sau khi giải xong, ứng dụng gửi dữ liệu lên API:

```text
https://k58kmt.tdh.io.vn/api/
```

Dữ liệu gửi lên:

```json
{
  "app_by": "K225480106044",
  "input": {
    "a": 1,
    "b": 2,
    "c": 0,
    "name": "hello tắc kè"
  },
  "output": {
    "ketluan": "Phương trình có nghiệm x = -2.0",
    "abc": "xyz",
    "nghiem": -2.0
  }
}
```

Code tạo JSON:

```java
JSONObject input = new JSONObject();
input.put("a", a);
input.put("b", b);
input.put("c", 0);
input.put("name", "hello tắc kè");

JSONObject output = new JSONObject();
output.put("ketluan", ketLuan);
output.put("abc", "xyz");
output.put("nghiem", nghiem);

JSONObject data = new JSONObject();
data.put("app_by", STUDENT_ID);
data.put("input", input);
data.put("output", output);
```

Code gửi API:

```java
URL url = new URL(API_URL);
HttpURLConnection conn = (HttpURLConnection) url.openConnection();

conn.setRequestMethod("POST");
conn.setRequestProperty("Content-Type", "application/json; charset=UTF-8");
conn.setRequestProperty("Accept", "application/json");
conn.setDoOutput(true);

OutputStream os = conn.getOutputStream();
os.write(data.toString().getBytes(StandardCharsets.UTF_8));
os.close();
```

API trả về dạng:

```json
{
  "ok": 1,
  "stt": 1234
}
```

Kết quả thực tế đã gửi thành công lên hệ thống của giảng viên.

<img width="271" height="600" alt="image" src="https://github.com/user-attachments/assets/61fdc32d-702d-4174-99f6-a2a88795b6c0" />

<img width="1360" height="768" alt="image" src="https://github.com/user-attachments/assets/b9ede0a8-b96a-46a1-b2ff-a74954fd94f4" />

---

## 3.7. WebActivity - WebView

File sử dụng:

```text
WebActivity.java
activity_web.xml
```

Chức năng:

- Mở trang web của giảng viên bằng WebView.
- Truyền mã sinh viên qua tham số `masv`.

URL sử dụng:

```text
https://k58kmt.tdh.io.vn/?masv=K225480106044
```

Code WebView:

```java
WebSettings settings = webView.getSettings();
settings.setJavaScriptEnabled(true);
settings.setDomStorageEnabled(true);

webView.setWebViewClient(new WebViewClient());

String url = "https://k58kmt.tdh.io.vn/?masv=" + STUDENT_ID;
webView.loadUrl(url);
```

Ý nghĩa:

- `WebView` hiển thị trang web trực tiếp trong ứng dụng.
- `setJavaScriptEnabled(true)` cho phép trang web chạy JavaScript.
- `setWebViewClient()` giúp trang web mở trong app thay vì mở trình duyệt ngoài.
- Tham số `masv` giúp server nhận biết mã sinh viên truy cập.

<img width="1260" height="2800" alt="image" src="https://github.com/user-attachments/assets/c21b5627-98f6-4d8a-bc90-a94d7fe06f06" />

Kết quả WebView trả về thông tin sinh viên theo mã đã truyền:

<img width="1366" height="604" alt="image" src="https://github.com/user-attachments/assets/26ea9fce-338a-49ae-9aa4-3d635ed98488" />

---

## 3.8. So sánh APP2 với MIT App Inventor

| MIT App Inventor | Android Studio APP2 |
|---|---|
| Screen1 About | MainActivity |
| Screen2 giải toán | SolveActivity |
| Screen3 WebViewer | WebActivity |
| Block xử lý sự kiện | Java event listener |
| WebViewer | WebView |
| Kéo thả giao diện | XML Layout |

APP2 có chức năng tương đương MIT App Inventor nhưng được xây dựng bằng Java và XML, giúp kiểm soát logic chương trình rõ hơn.

---

## 3.9. Kết quả APP2

APP2 đã hoàn thành:

- Có 3 Activity.
- MainActivity hiển thị About và chuyển màn hình.
- SolveActivity giải phương trình `ax + b = 0`.
- Sau khi giải, app gửi JSON lên API.
- Nhận phản hồi từ API dạng `{ok, stt}`.
- WebActivity mở WebView đúng URL theo mã sinh viên.
- App build và chạy thành công trên thiết bị Android.

---

# KẾT LUẬN

Bài tập đã triển khai hai hướng phát triển ứng dụng di động:

- MIT App Inventor: tạo ứng dụng bằng kéo thả giao diện và lập trình block.
- Android Studio: xây dựng ứng dụng bằng Java, XML Layout, Assets, API và WebView.

Qua quá trình thực hiện, sinh viên nắm được cách tổ chức giao diện, xử lý sự kiện, sử dụng dữ liệu offline, chuyển màn hình, gọi API và hiển thị nội dung web trong ứng dụng Android.
