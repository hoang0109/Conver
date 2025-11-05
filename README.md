# Question Converter & Exam Mixer

## 👤 About
- Developer: Lê Huy Hoàng
- Email: hoang0109@gmail.com

# Question Converter GUI - Giao diện chuyển đổi câu hỏi



Công cụ chuyển đổi câu hỏi trắc nghiệm và tạo đề thi ngẫu nhiên với giao diện đồ họa (GUI).## Mô tả

Giao diện GUI hiện đại để chuyển đổi định dạng câu hỏi từ văn bản thành bảng có cấu trúc theo format JSON.

## 📋 Mục lục

## Tính năng chính

- [Tính năng](#tính-năng)

- [Yêu cầu hệ thống](#yêu-cầu-hệ-thống)### 🖥️ **Giao diện 2 panel:**

- [Cài đặt](#cài-đặt)- **Panel trái**: Bảng hiển thị với 2 cột theo cấu trúc JSON:

- [Cách sử dụng](#cách-sử-dụng)  ```

  - [Tab 1: Chuyển đổi câu hỏi](#tab-1-chuyển-đổi-câu-hỏi)  | Cột 1        | Cột 2                    |

  - [Tab 2: Trộn đề thi](#tab-2-trộn-đề-thi)  |--------------|--------------------------|

- [Định dạng file](#định-dạng-file)  | Câu 0.1      | Nội dung câu hỏi...      |

- [Các chức năng nâng cao](#các-chức-năng-nâng-cao)  |    A)        | Đáp án A                 |

- [Xử lý lỗi](#xử-lý-lỗi)  |    B)        | Đáp án B                 |

- [FAQ](#faq)  |    C)        | Đáp án C                 |

  |    D)        | Đáp án D                 |

---  |    Đáp án    | D                        |

  ```

## ✨ Tính năng

- **Panel phải**: Hiển thị nội dung file gốc với syntax highlighting:

### Tab "Chuyển đổi câu hỏi"  - Câu hỏi được tô màu xanh đậm

- ✅ **Import đa định dạng**: Hỗ trợ `.txt`, `.docx`, `.xml`  - Đáp án đúng được tô màu xanh lá đậm

- ✅ **Export đa định dạng**: `.docx`, `.txt`, `.xml`, `.json`  - Vùng được chọn tô màu vàng

- ✅ **Quản lý nhóm câu hỏi**: Phân loại câu hỏi theo nhóm chủ đề

- ✅ **Kiểm tra chất lượng**: Phát hiện lỗi định dạng, câu trùng, thiếu đáp án### 🎯 **Tính năng đồng bộ:**

- ✅ **Xem và sửa lỗi**: Nhấp đúp vào lỗi để xem vị trí trong file gốc- Khi click vào bất kỳ hàng nào ở bảng trái → Panel phải tự động focus và highlight màu vàng

- ✅ **Tự động sửa số câu**: Phát hiện và sửa câu hỏi đánh số sai (VD: 226a → 227)- Scroll tự động đến vị trí câu hỏi được chọn

- ✅ **Export theo nhóm**: Xuất mỗi nhóm thành file Word riêng hoặc gộp thành 1 file- Status bar hiển thị thông tin chi tiết



### Tab "Trộn đề thi"### 📁 **Xử lý file và xuất dữ liệu:**

- 🎲 **Tạo đề thi ngẫu nhiên**: Tự động tạo nhiều đề thi khác nhau- **Import**: Hỗ trợ nhiều định dạng file:

- 📊 **Phân bổ cân bằng**: Lấy câu hỏi đều từ các nhóm  - `.doc/.docx` - Microsoft Word

- 📝 **Định dạng chuẩn**: File Word với câu hỏi + bảng đáp án ở cuối  - `.txt` - Text file (hỗ trợ tag `<Gr>` và `<CH>`)

- 🔄 **Không trùng lặp**: Mỗi câu chỉ xuất hiện 1 lần trong mỗi đề  - `.xml` - XML file với cấu trúc linh hoạt

- Tự động phát hiện định dạng và parse nội dung

---- Tự động phân tích cấu trúc câu hỏi với error detection

- Hỗ trợ nhận dạng nhóm câu hỏi với tag `<Gr>` và `<CH>`

## 💻 Yêu cầu hệ thống

- **Export**: Xuất kết quả ra nhiều định dạng:

- **Python**: 3.8 trở lên  - **Word (.docx)** - Bảng 2 cột với format đẹp

- **Hệ điều hành**: Windows, macOS, Linux  - **JSON** - Cấu trúc chuẩn theo schema

- **Thư viện Python**:  - **TXT** - File text với format rõ ràng, đánh dấu đáp án đúng

  - `tkinter` (có sẵn trong Python)  - **XML** - Cấu trúc phân cấp với group và question elements

  - `python-docx`

```json

---{

  "title": "Trắc nghiệm Tin học cơ bản",

## 🚀 Cài đặt  "questions": [

    {

### Bước 1: Clone repository      "id": "0.1",

      "question_text": "Nội dung câu hỏi",

```bash      "options": [

git clone https://github.com/your-username/question-converter.git        {"key": "A", "text": "Đáp án A"},

cd question-converter        {"key": "B", "text": "Đáp án B"},

```        {"key": "C", "text": "Đáp án C"},

        {"key": "D", "text": "Đáp án D"}

### Bước 2: Tạo môi trường ảo (khuyến nghị)      ],

      "correct_answer_key": "D"

**Windows:**    }

```bash  ]

python -m venv .venv}

.venv\Scripts\activate```

```

## Cách sử dụng

**macOS/Linux:**

```bash### 1. Chạy chương trình:

python3 -m venv .venv```bash

source .venv/bin/activatepython question_converter_gui.py

``````



### Bước 3: Cài đặt thư viện### 2. Sử dụng toolbar:

- **📁 Mở File**: Chọn file .doc/.docx chứa câu hỏi

```bash- **🔄 Refresh**: Làm mới dữ liệu

pip install python-docx- **💾 Xuất Word**: Lưu kết quả ra file Word

```

### 3. Làm việc với dữ liệu:

### Bước 4: Chạy chương trình- Click vào bất kỳ câu hỏi nào trong bảng trái

- Panel phải sẽ tự động highlight và cuộn đến vị trí tương ứng

```bash- Kiểm tra và xác nhận đáp án đúng

python question_converter_gui.py

```### 4. Xuất kết quả:

- Click "💾 Xuất Word"

---- Chọn vị trí lưu file

- File Word sẽ chứa bảng có cấu trúc đầy đủ

## 📖 Cách sử dụng

## Định dạng file input được hỗ trợ

## Tab 1: Chuyển đổi câu hỏi

```

### 1. Import file câu hỏiCâu 1. Nội dung câu hỏi ở đây?

A. Đáp án A

#### **Cách 1: Sử dụng Menu**B. Đáp án B  

1. Click **File** → **Mở file** (hoặc **Ctrl+O**)C. Đáp án C

2. Chọn file: `.txt`, `.docx`, hoặc `.xml`*D. Đáp án D (đáp án đúng có dấu *)

3. Dữ liệu sẽ hiển thị:

   - **Panel trái**: Danh sách câu hỏi và đáp ánCâu 2. Câu hỏi tiếp theo?

   - **Panel phải**: Nội dung file gốc với số dòng*A. Đáp án đúng

B. Đáp án B

#### **Cách 2: Sử dụng Toolbar**C. Đáp án C

- Click nút **📂 Mở file** trên thanh công cụD. Đáp án D

```

### 2. Xem và kiểm tra câu hỏi

## Tính năng nâng cao

- **Xem chi tiết câu hỏi**: Click vào câu hỏi trong bảng

- **Xem vị trí trong file gốc**: Double-click vào câu hỏi### Hỗ trợ nhiều định dạng file:

- **Copy/Paste**: 

  - Right-click → Copy/Paste#### 1. **File TXT** (.txt)

  - Hoặc dùng **Ctrl+C** / **Ctrl+V**- Format đơn giản, dễ chỉnh sửa

- Hỗ trợ tag nhóm: `<Gr>` và `<CH>...</CH>`

### 3. Kiểm tra lỗi- Ví dụ:

```

Click **🔍 Kiểm tra chất lượng** để phát hiện:<Gr> CÂU HỎI VỀ HỆ ĐIỀU HÀNH



| Loại lỗi | Mô tả |<CH>

|-----------|-------|Câu 1: Hệ điều hành nào là mã nguồn mở?

| **Thiếu tag** | Câu hỏi không có `<CH>` hoặc `</CH>` |A. Windows

| **Thiếu đáp án** | Câu hỏi không có đủ các đáp án A, B, C, D |B. macOS

| **Thiếu đáp án đúng** | Không có đáp án nào có dấu `*` |*C. Linux

| **Đáp án trùng** | Hai đáp án có cùng ký tự (VD: 2 đáp án A) |D. iOS

| **Câu hỏi trùng** | Hai câu có cùng số thứ tự |</CH>

| **Sai thứ tự** | Câu hỏi không theo thứ tự tăng dần |```



**Sửa lỗi:**#### 2. **File XML** (.xml)

- Double-click vào lỗi trong cửa sổ "Lỗi phân tích"- Cấu trúc phân cấp rõ ràng

- Sửa trực tiếp trong panel phải- Hỗ trợ nhiều schema khác nhau

- Tự động nhận dạng group và question tags

- Ví dụ:

### 4. Export file```xml

<?xml version="1.0" encoding="utf-8"?>

#### **Export tất cả vào 1 file**<document>

1. Click **💾 Xuất Word** (hoặc **File** → **Xuất ra file Word**)  <group name="CÂU HỎI VỀ HỆ ĐIỀU HÀNH">

2. Nếu có nhóm câu hỏi:    <question>

   - **YES**: Xuất mỗi nhóm thành file riêng      <text>Câu 1: Hệ điều hành nào là mã nguồn mở?</text>

   - **NO**: Xuất tất cả vào 1 file      <answer>A. Windows</answer>

3. Chọn vị trí lưu file      <answer>*C. Linux</answer>

    </question>

#### **Export theo nhóm riêng**  </group>

1. Click **Export** → **Xuất theo nhóm (Word)**</document>

2. Chọn thư mục lưu```

3. Kết quả: `Group_TenNhom.docx` cho mỗi nhóm

#### 3. **File Word** (.doc/.docx)

#### **Export định dạng khác**- Hỗ trợ đọc file Word tiêu chuẩn

- **TXT**: **📝 Xuất TXT** hoặc **Export** → **Xuất ra TXT**- Giữ nguyên format gốc

- **XML**: **📋 Xuất XML** hoặc **Export** → **Xuất ra XML**

- **JSON**: **Export** → **Xuất ra JSON**### Nhận dạng nhóm câu hỏi:

- Tag `<Gr>` để đánh dấu tên nhóm

---- Tag `<CH>...</CH>` để đánh dấu block câu hỏi

- Hiển thị nhóm với header màu xanh lá trong bảng

## Tab 2: Trộn đề thi- Xuất file giữ nguyên cấu trúc nhóm



### 1. Chuẩn bị dữ liệu### Syntax Highlighting:

- Câu hỏi: màu xanh đậm

- Đầu tiên, load file câu hỏi ở **Tab "Chuyển đổi câu hỏi"**- Đáp án đúng: màu xanh lá đậm  

- Chuyển sang **Tab "Trộn đề thi"**- Vùng được chọn: màu vàng

- Thông tin sẽ tự động hiển thị:

  - Tổng số câu hỏi### Responsive Design:

  - Số nhóm- Tự động điều chỉnh kích thước cột

  - Chi tiết từng nhóm- Scrollbar cho cả 2 panel

- Tooltip và status bar thông tin

### 2. Cấu hình đề thi

### Error Handling:

**Nhập thông số:**- Kiểm tra định dạng file

- **Số đề cần tạo**: VD: 5, 10, 20- Thông báo lỗi chi tiết

- **Số câu mỗi đề**: VD: 20, 30, 50- Fallback với dữ liệu mẫu



**Lưu ý:**## Yêu cầu hệ thống

- Số câu phải ≤ tổng số câu có sẵn- Python 3.7+

- Nếu số câu < số nhóm: Chọn ngẫu nhiên một số nhóm- Thư viện: tkinter, python-docx

- Nếu số câu ≥ số nhóm: Lấy ít nhất 1 câu/nhóm, phần còn lại phân đều- Windows/Linux/MacOS



### 3. Tạo đề thi## Demo

Chương trình đã tích hợp sẵn dữ liệu mẫu để test ngay khi khởi động.

1. Click **🎲 Tạo đề thi**

2. Chọn thư mục lưu các đề---

3. Chờ chương trình tạo đề**Phát triển bởi**: Question Converter Team  

4. Kết quả: **Phiên bản**: 1.0  

   - `De_thi_01.docx`**Ngày**: November 2025
   - `De_thi_02.docx`
   - `De_thi_03.docx`
   - ...

### 4. Cấu trúc file đề thi

Mỗi file Word bao gồm:

```
ĐỀ THI SỐ XX

Câu 1. Nội dung câu hỏi...
   A. Đáp án A
   B. Đáp án B
   C. Đáp án C
   D. Đáp án D

Câu 2. Nội dung câu hỏi...
   ...

[Ngắt trang]

ĐÁP ÁN

┌──────────┬────────┐
│ Câu hỏi  │ Đáp án │
├──────────┼────────┤
│ Câu 1    │   B    │
│ Câu 2    │   A    │
│ ...      │  ...   │
└──────────┴────────┘
```

---

## 📄 Định dạng file

### Định dạng TXT/Import

```
<Gr> Tên nhóm câu hỏi
<CH>
Câu 1. Nội dung câu hỏi?
A. Đáp án A
*B. Đáp án đúng (có dấu *)
C. Đáp án C
D. Đáp án D
</CH>
<CH>
Câu 2. Nội dung câu hỏi khác?
*A. Đáp án đúng
B. Đáp án B
C. Đáp án C
D. Đáp án D
</CH>
</Gr>

<Gr> Nhóm khác
<CH>
Câu 3. ...
</CH>
</Gr>
```

### Quy tắc định dạng

| Thành phần | Quy tắc |
|------------|---------|
| **Nhóm** | `<Gr>` + Tên nhóm ở đầu, `</Gr>` ở cuối |
| **Câu hỏi** | Bắt đầu bằng `<CH>`, kết thúc bằng `</CH>` |
| **Số câu** | `Câu X.` (X là số) |
| **Đáp án** | `A.`, `B.`, `C.`, `D.` + nội dung |
| **Đáp án đúng** | Thêm dấu `*` phía trước (VD: `*A.`) |

### Lưu ý quan trọng

- ✅ Mỗi câu hỏi phải có đủ 4 đáp án (A, B, C, D)
- ✅ Phải có duy nhất 1 đáp án đúng (có dấu `*`)
- ✅ Nhóm có thể có hoặc không (tùy chọn)
- ✅ Thứ tự câu hỏi nên tăng dần
- ⚠️ Không để 2 đáp án trên cùng 1 dòng

---

## 🔧 Các chức năng nâng cao

### 1. Tự động sửa số câu

**Vấn đề:** File có câu `226a` do chèn thủ công

**Giải pháp:**
1. Click **View** → **Sửa số câu tự động**
2. Chương trình tự động:
   - Phát hiện `226a` → Đổi thành `227`
   - Tăng các câu sau lên 1 (`227` → `228`, `228` → `229`, ...)

### 2. Export với đánh số theo nhóm

Khi xuất **tất cả vào 1 file Word** có nhiều nhóm:

- **Nhóm 1**: Câu 0.1, 0.2, 0.3, ...
- **Nhóm 2**: Câu 1.1, 1.2, 1.3, ...
- **Nhóm 3**: Câu 2.1, 2.2, 2.3, ...

**Cách bật:**
- Khi xuất Word, chọn **NO** (xuất tất cả vào 1 file)
- Chương trình tự động áp dụng nếu phát hiện nhiều nhóm

### 3. Refresh dữ liệu

Sau khi sửa file gốc:
1. Click **🔄 Refresh** (hoặc **View** → **Refresh**)
2. Dữ liệu sẽ được phân tích lại

---

## ⚠️ Xử lý lỗi

### Lỗi thường gặp

#### 1. "Không thể mở file"
**Nguyên nhân:** File đang được mở bởi chương trình khác

**Giải pháp:** Đóng file trong Word/Excel, thử lại

#### 2. "Không đủ câu hỏi"
**Nguyên nhân:** Số câu yêu cầu > số câu có sẵn

**Giải pháp:** Giảm số câu mỗi đề hoặc tăng số câu trong file gốc

#### 3. "Phát hiện lỗi phân tích"
**Nguyên nhân:** File không đúng định dạng

**Giải pháp:**
- Click đúp vào lỗi để xem vị trí
- Sửa theo đúng định dạng (xem mục [Định dạng file](#định-dạng-file))
- Click **🔄 Refresh**

#### 4. "Không có dữ liệu để xuất"
**Nguyên nhân:** Chưa load file hoặc file không có câu hỏi hợp lệ

**Giải pháp:** Load file ở tab "Chuyển đổi câu hỏi" trước

---

## ❓ FAQ

### Q1: Tôi có thể sử dụng file Word (.doc) cũ không?
**A:** Có, nhưng khuyến nghị chuyển sang `.docx` hoặc `.txt` để đảm bảo tương thích.

### Q2: Làm sao để tạo file test nhanh?
**A:** 
1. Chạy chương trình (đã có dữ liệu mẫu)
2. Export ra TXT
3. Chỉnh sửa và sử dụng

### Q3: Có giới hạn số lượng câu hỏi không?
**A:** Không có giới hạn, nhưng:
- File quá lớn (>10,000 câu) có thể chậm
- Khuyến nghị chia nhỏ thành nhiều file

### Q4: Đề thi có thể trùng nhau không?
**A:** Có thể (do random), nhưng:
- Mỗi câu trong 1 đề không trùng nhau
- Xác suất trùng hoàn toàn rất thấp

### Q5: Tôi có thể thêm nhiều hơn 4 đáp án không?
**A:** Hiện tại chỉ hỗ trợ A, B, C, D. Để thêm E, F cần sửa code.

### Q6: Làm sao để backup dữ liệu?
**A:** Export ra XML hoặc JSON để lưu trữ lâu dài.

### Q7: Chương trình có chạy trên Mac/Linux không?
**A:** Có, Python và tkinter hỗ trợ đa nền tảng.

### Q8: Tôi có thể tùy chỉnh giao diện không?
**A:** Có thể sửa code trong file `question_converter_gui.py`.

---

## 📦 Cấu trúc thư mục

```
question-converter/
├── question_converter_gui.py   # File chương trình chính
├── test_exam_mixer.txt          # File test với 25 câu, 5 nhóm
├── README.md                    # File hướng dẫn này
├── .venv/                       # Môi trường ảo (nếu có)
└── requirements.txt             # Danh sách thư viện (tùy chọn)
```

---

## 🎯 Ví dụ nhanh

### Tạo đề thi trong 3 bước

```bash
# 1. Chạy chương trình
python question_converter_gui.py

# 2. Load file test
# File → Mở file → Chọn test_exam_mixer.txt

# 3. Chuyển sang tab "Trộn đề thi"
# Nhập: 5 đề, mỗi đề 10 câu
# Click "Tạo đề thi"
```

### Chuyển đổi file nhanh

```bash
# 1. Load file câu hỏi (.txt, .docx, .xml)
# 2. Kiểm tra lỗi (nếu có)
# 3. Export sang định dạng mong muốn
```

---

## 🤝 Đóng góp

Mọi đóng góp đều được chào đón! Vui lòng:
1. Fork repository
2. Tạo branch mới (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Mở Pull Request

---

## 📝 License

Dự án này được phát hành dưới giấy phép MIT.

---

## 📧 Liên hệ

Nếu có câu hỏi hoặc gặp vấn đề, vui lòng mở Issue trên GitHub.

---

## 🎉 Lời cảm ơn

Cảm ơn bạn đã sử dụng Question Converter & Exam Mixer!

**Chúc bạn tạo đề thi thành công!** 🚀
