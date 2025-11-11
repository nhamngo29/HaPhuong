Chắc chắn rồi. Dưới đây là dàn ý chi tiết cho đề tài **"Phân tích và dự đoán kết quả học tập của sinh viên"**, được xây dựng để tuân thủ nghiêm ngặt các yêu cầu trong tệp PDF dàn ý môn học của bạn.

---

### 📝 Dàn ý chi tiết đề tài: Phân tích và dự đoán kết quả học tập của sinh viên

#### 1. Tên đề tài
**Phân tích các yếu tố ảnh hưởng và Xây dựng mô hình dự đoán Kết quả học tập của sinh viên**

#### 2. Mục tiêu nghiên cứu / phân tích
* **Mục tiêu chính:** Xây dựng mô hình khai thác dữ liệu có khả năng dự đoán kết quả học tập cuối kỳ của sinh viên (ví dụ: "Đạt" hay "Không Đạt") dựa trên các yếu tố nhân khẩu học, xã hội và các thói quen học tập.
* **Mục tiêu cụ thể:**
    * Thực hiện thống kê mô tả chi tiết bộ dữ liệu (theo yêu cầu Phần 1).
    * Khám phá và trực quan hóa (bằng Python) để tìm ra các yếu tố chính có tương quan mạnh mẽ đến điểm số cuối kỳ (ví dụ: thời gian học, số buổi vắng, hoạt động ngoại khóa, thói quen sử dụng rượu bia...).
    * [cite_start]Thực hiện 2 phương pháp khai thác dữ liệu theo yêu cầu[cite: 48]:
        1.  **Phân lớp (Classification):** Dự đoán sinh viên sẽ "Đạt" hay "Không Đạt".
        2.  **Phân cụm (Clustering):** Phân nhóm các sinh viên có đặc điểm và hành vi tương đồng để xác định các "hồ sơ sinh viên" (ví dụ: nhóm chăm chỉ, nhóm rủi ro cao...).
    * [cite_start]Mô phỏng một tác vụ xử lý dữ liệu trên Hadoop[cite: 52].
    * [cite_start]Đánh giá hiệu quả và độ tin cậy của các mô hình đã xây dựng[cite: 56].

#### 3. Dữ liệu sử dụng
* [cite_start]**Nguồn dữ liệu:** "Student Performance Data Set" từ UCI Machine Learning Repository (có thể tìm thấy trên Kaggle [cite: 96]).
* **Tổng quan:** Dữ liệu chứa thông tin về kết quả học tập (môn Toán hoặc Tiếng Bồ Đào Nha) của sinh viên trung học. Dữ liệu gốc có khoảng 649 sinh viên và 33 thuộc tính.
* [cite_start]**Kiểu dữ liệu (Phân tích theo yêu cầu Phần 1 [cite: 6]):**
    * [cite_start]**Số (Numeric)[cite: 39]:** `age` (tuổi), `absences` (số buổi vắng), `G1` (điểm kỳ 1), `G2` (điểm kỳ 2), `G3` (điểm cuối kỳ). [cite_start](Sẽ tính mean, median, five-number summary... [cite: 20]).
    * [cite_start]**Nhị phân (Binary)[cite: 38]:** `schoolsup` (hỗ trợ thêm từ trường), `famsup` (hỗ trợ từ gia đình), `paid` (lớp học thêm trả phí), `activities` (tham gia ngoại khóa), `nursery` (học mẫu giáo), `higher` (muốn học cao hơn), `internet` (có Internet), `romantic` (đang hẹn hò). [cite_start](Sẽ tính tỷ lệ % và mode [cite: 12]).
    * [cite_start]**Danh nghĩa (Nominal)[cite: 37]:** `school`, `sex` (giới tính), `address` (khu vực sống U/R), `Mjob` (nghề nghiệp mẹ), `Fjob` (nghề nghiệp cha), `reason` (lý do chọn trường). [cite_start](Sẽ tính tỷ lệ % và mode [cite: 12, 16]).
    * [cite_start]**Thứ tự (Ordinal)[cite: 40]:**
        * `Medu`, `Fedu` (trình độ học vấn cha/mẹ: 0-4).
        * `traveltime` (thời gian di chuyển: 1-4).
        * `studytime` (thời gian học hàng tuần: 1-4).
        * `failures` (số lần thi rớt trước đó: 1-4).
        * `famrel`, `freetime`, `goout`, `Dalc`, `Walc`, `health` (đánh giá theo thang 1-5). [cite_start](Sẽ tính tỷ lệ % và mode [cite: 12, 18]).
* **Biến mục tiêu (Target):** `G3` (điểm cuối kỳ). Để phục vụ bài toán phân lớp, biến này sẽ được nhị phân hóa (ví dụ: tạo biến mới `Pass_Fail`, trong đó "Pass" nếu $G3 \ge 10$ và "Fail" nếu $G3 < 10$).

#### 4. Công cụ và Thuật toán dự kiến
* [cite_start]**Ngôn ngữ & Thư viện (bắt buộc dùng Python [cite: 44-47]):**
    * **Python:** Ngôn ngữ lập trình chính.
    * **Pandas & Numpy:** Dùng cho tiền xử lý, làm sạch và tổng hợp dữ liệu.
    * **Matplotlib & Seaborn:** Dùng để trực quan hóa dữ liệu (vẽ Boxplot, Histogram, Scatter plot...).
    * **Scikit-learn:** Dùng để triển khai các thuật toán khai thác dữ liệu và đánh giá mô hình.
* **Công cụ Big Data:**
    * [cite_start]**Hadoop:** Dùng để mô phỏng tác vụ xử lý[cite: 50].
* [cite_start]**Thuật toán (chọn 2 phương pháp theo yêu cầu [cite: 48]):**
    1.  **Phân lớp (Classification):** Cây quyết định (Decision Tree) hoặc Random Forest (để dự đoán `Pass_Fail`).
    2.  **Phân cụm (Clustering):** K-Means (để phân nhóm sinh viên).

#### 5. Các bước thực hiện (Bám sát 4 phần của dàn ý PDF)

##### Phần 1: Giới thiệu CSDL
* [cite_start]Trình bày tổng quan về bộ dữ liệu "Student Performance"[cite: 4].
* [cite_start]Lập bảng mô tả chi tiết 33 thuộc tính: tên field, ý nghĩa, số giá trị null, số giá trị unique, kiểu dữ liệu [cite: 6-11].
* Tính toán thống kê mô tả:
    * [cite_start]Với các thuộc tính số (`age`, `absences`, `G1`, `G2`, `G3`): Tính mean, median, mode, min, max, five-number summary[cite: 20, 21].
    * [cite_start]Với các thuộc tính nhị phân/danh nghĩa/thứ tự (`sex`, `studytime`, `internet`...): Lập bảng tần suất, tính tỷ lệ % và tìm mode[cite: 12].
* [cite_start]Trình bày quá trình tiền xử lý[cite: 22]:
    * Tạo biến mục tiêu `Pass_Fail` từ `G3`.
    * Xử lý giá trị khuyết thiếu (nếu có).
    * Chuyển đổi các biến danh nghĩa sang dạng số (One-Hot Encoding) nếu cần cho mô hình.

##### [cite_start]Phần 2: Phân tích và Khai thác (Sử dụng Python [cite: 44-47])
* **2.1. Tìm hiểu dữ liệu (Thống kê thủ công/Trực quan):**
    * Chọn 3 thuộc tính: `G3`, `studytime`, `absences`.
    * [cite_start]Vẽ **Boxplot** cho `G3` và `absences` (để xem phân bố và outliers)[cite: 28].
    * [cite_start]Vẽ **Quantile-Quantile Plot** cho `G1` và `G2` (xem 2 biến điểm có phân phối tương đồng không)[cite: 29].
    * [cite_start]Vẽ **Histogram** cho `G3` (xem phân bố điểm) và `studytime`[cite: 30].
    * [cite_start]Vẽ **Scatter plot** cho `studytime` và `G3` (xem thời gian học ảnh hưởng điểm số)[cite: 31].
    * [cite_start]Nhóm dữ liệu theo thuộc tính danh nghĩa `sex` (giới tính)[cite: 32]:
        * [cite_start]Vẽ **Boxplot** của `G3` cho 2 nhóm "Male" và "Female"[cite: 33].
        * [cite_start]Vẽ **Histogram** của `absences` cho 2 nhóm "Male" và "Female"[cite: 34].
    * [cite_start]Đo lường sự tương đồng[cite: 35]:
        * [cite_start]Chọn 4 thuộc tính: `Mjob` (danh nghĩa), `internet` (nhị phân), `age` (số), `studytime` (thứ tự) [cite: 36-40].
        * [cite_start]Chọn 4 dòng dữ liệu (4 sinh viên)[cite: 41].
        * Tính **Ma trận tương quan** (Pearson) cho các thuộc tính số.
        * Tính **Độ đo Cosin** cho 4 vector sinh viên đã chọn.
        * [cite_start]So sánh kết quả[cite: 43].
* **2.2 - 2.4. Tiền xử lý, Tổng hợp, Trực quan hóa (bằng Python):**
    * Sử dụng Pandas để chuẩn hóa dữ liệu số (ví dụ: StandardScaler).
    * Sử dụng Seaborn để vẽ heatmap cho ma trận tương quan của tất cả các biến số.
* **2.5. [cite_start]Thực hiện khai thác (bằng Python)[cite: 47]:**
    * **Phương pháp 1: Phân lớp (Classification)**
        * Sử dụng `scikit-learn` để chia dữ liệu (train/test split).
        * Huấn luyện mô hình Cây quyết định (Decision Tree) để dự đoán biến `Pass_Fail` dựa trên các yếu tố (ví dụ: `studytime`, `failures`, `Medu`, `goout`, `absences`).
    * **Phương pháp 2: Phân cụm (Clustering)**
        * Sử dụng `scikit-learn` và thuật toán K-Means.
        * Chọn các biến đầu vào (ví dụ: `studytime`, `absences`, `Walc`, `freetime`) để phân sinh viên thành K cụm (ví dụ: K=3).
        * Phân tích đặc điểm của từng cụm (ví dụ: Cụm 1: chăm học, ít vắng; Cụm 2: lười học, vắng nhiều...).

##### Phần 3: Giới thiệu về HADOOP
* [cite_start]Giới thiệu tổng quan về Hadoop, HDFS, và MapReduce[cite: 50].
* Trình bày (có thể chụp ảnh màn hình) các bước cài đặt Hadoop (ví dụ: trên máy ảo hoặc Docker).
* [cite_start]Mô phỏng[cite: 52]: Viết một chương trình MapReduce đơn giản (bằng Python) và mô phỏng việc chạy nó trên Hadoop, ví dụ: "Đếm số lượng sinh viên Đạt/Không Đạt theo từng khu vực sống (`address`)".

##### Phần 4: Đánh giá các mẫu kết quả
* [cite_start]**Đánh giá mô hình Phân lớp (chọn 2)[cite: 65]:**
    1.  [cite_start]**Số liệu để đánh giá hiệu suất phân loại (Metrics)**[cite: 66]: Sử dụng Ma trận nhầm lẫn (Confusion Matrix), tính các độ đo Accuracy, Precision, Recall, và F1-Score.
    2.  [cite_start]**Xác thực chéo (Cross-Validation)**[cite: 69]: Sử dụng K-Fold Cross-Validation (ví dụ K=10) để đánh giá độ ổn định và tin cậy của mô hình, thay vì chỉ dùng 1 lần train/test split.
* [cite_start]**Đánh giá mô hình Phân cụm (bắt buộc 2 phương pháp)[cite: 74]:**
    1.  [cite_start]**Phương pháp không giám sát (Unsupervised)**[cite: 76]: Sử dụng chỉ số Silhouette (Silhouette Score) để đo lường mức độ tách biệt và cô đọng của các cụm đã tạo.
    2.  [cite_start]**Phương pháp giám sát (Supervised)**[cite: 75]: (Dùng để kiểm chứng) So sánh các nhãn cụm (từ K-Means) với nhãn thực tế `Pass_Fail` (ví dụ: dùng Adjusted Rand Index) để xem các cụm K-Means có vô tình tìm ra được nhóm sinh viên "Đạt" và "Không Đạt" hay không.

#### 6. Kết quả mong đợi
* Một mô hình Cây quyết định có khả năng dự đoán sinh viên "Không Đạt" với độ chính xác (hoặc F1-score) định lượng được (ví dụ: F1-score > 70%).
* Một biểu đồ trực quan hóa Cây quyết định, chỉ ra các "luật" quan trọng nhất để dự đoán (ví dụ: NẾU `failures > 2` VÀ `studytime = 1` THÌ dự đoán `Fail`).
* Xác định được 3-4 hồ sơ sinh viên điển hình từ kết quả phân cụm (ví dụ: Cụm 1: "Nhóm rủi ro cao", Cụm 2: "Nhóm cân bằng", Cụm 3: "Nhóm chăm chỉ").
* [cite_start]Báo cáo hoàn chỉnh tuân thủ các quy định trình bày (font, lề,...) [cite: 81-84].



### **BÁO CÁO ĐỀ TÀI CÁ NHÂN: MÔN KHAI THÁC DỮ LIỆU LỚN**

**ĐỀ TÀI: PHÂN TÍCH CÁC YẾU TỐ ẢNH HƯỞNG VÀ XÂY DỰNG MÔ HÌNH DỰ ĐOÁN KẾT QUẢ HỌC TẬP CỦA SINH VIÊN**

-----

### **Phần 1: Giới thiệu về CSDL sử dụng cho đề tài**

#### 1.1. [cite\_start]Tổng quan về CSDL [cite: 4]

Đề tài này sử dụng bộ dữ liệu **"Student Performance"** (Kết quả học tập của Sinh viên) từ kho lưu trữ UCI Machine Learning, được thu thập tại Bồ Đào Nha.

  * **Vấn đề dữ liệu:** Dữ liệu mô tả các yếu tố nhân khẩu học, xã hội (gia đình, bạn bè), thói quen (học tập, sử dụng rượu bia) và kết quả học tập (điểm kỳ 1, kỳ 2, và điểm cuối kỳ) của sinh viên.
  * [cite\_start]**Nguồn thu thập:** Dữ liệu được thu thập qua bảng hỏi và hồ sơ nhà trường[cite: 96].
  * **Số lượng Records:** *[Sau khi chạy mã, bạn điền vào. [cite\_start]Ví dụ: Dữ liệu gốc gồm 649 records].* [cite: 5]
  * **Số lượng Fields:** *[Ví dụ: 33 thuộc tính (fields)].*

<!-- end list -->

```python
# Mã lệnh Python để tải và kiểm tra tổng quan dữ liệu
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Giả sử bạn tải file "student-por.csv" (môn Tiếng Bồ Đào Nha) về cùng thư mục
try:
    df = pd.read_csv('student-por.csv', sep=';')
except FileNotFoundError:
    print("Vui lòng tải file 'student-por.csv' từ UCI/Kaggle vào thư mục.")
    # df = pd.DataFrame() # Tạo dataframe rỗng để tránh lỗi

print("--- Thông tin tổng quan CSDL ---")
print(df.info())
print(f"\nKích thước CSDL: {df.shape[0]} records và {df.shape[1]} fields.")
```

#### 1.2. [cite\_start]Giới thiệu từng thuộc tính (Field) [cite: 6]

Dưới đây là phân tích một số thuộc tính quan trọng:

**1. [cite\_start]Thuộc tính `G3` (Điểm cuối kỳ) - Dạng số (Numeric) [cite: 20, 39]**

  * [cite\_start]**Ý nghĩa:** Điểm số cuối kỳ của sinh viên (thang điểm 0-20)[cite: 8].
  * **Giá trị Null:** *[Kết quả từ df['G3'].isnull().sum()]*.
  * **Giá trị Unique:** *[Kết quả từ df['G3'].nunique()]*.
  * **Thống kê mô tả (Mean, Median, Mode, Five-number summary):**
      * *Mean: [kết quả]*
      * *Median: [kết quả]*
      * *Mode: [kết quả]*
      * *Min: [kết quả]*
      * *25% (Q1): [kết quả]*
      * *50% (Median): [kết quả]*
      * *75% (Q3): [kết quả]*
      * *Max: [kết quả]*

<!-- end list -->

```python
# Mã lệnh Python để lấy thống kê thuộc tính SỐ
print("\n--- Phân tích thuộc tính SỐ: G3 (Điểm cuối kỳ) ---")
print(df['G3'].describe())
print(f"Mode (Yếu vị): {df['G3'].mode()[0]}")
```

**2. [cite\_start]Thuộc tính `sex` (Giới tính) - Dạng danh nghĩa / nhị phân [cite: 16, 37, 38]**

  * [cite\_start]**Ý nghĩa:** Giới tính của sinh viên[cite: 8].
  * **Giá trị Null:** *[Kết quả từ df['sex'].isnull().sum()]*.
  * **Giá trị Unique:** *[Kết quả từ df['sex'].nunique()]*.
  * [cite\_start]**Phân bố giá trị:** [cite: 12]

| Tên giá trị | Số lượng | Tỷ lệ |
| :--- | :--- | :--- |
| *[F]* | *[kết quả]* | *[kết quả %]* |
| *[M]* | *[kết quả]* | *[kết quả %]* |

  * [cite\_start]**Mode:** *[F hoặc M, giá trị có tỷ lệ cao nhất]*[cite: 13].

<!-- end list -->

```python
# Mã lệnh Python để lấy thống kê thuộc tính DANH NGHĨA
print("\n--- Phân tích thuộc tính DANH NGHĨA: sex (Giới tính) ---")
print(df['sex'].value_counts())
print(df['sex'].value_counts(normalize=True) * 100)
```

**3. [cite\_start]Thuộc tính `studytime` (Thời gian học) - Dạng thứ tự (Ordinal) [cite: 18, 40]**

  * [cite\_start]**Ý nghĩa:** Thời gian học hàng tuần (1: \<2h, 2: 2-5h, 3: 5-10h, 4: \>10h)[cite: 8].
  * **Giá trị Null:** *[kết quả]*.
  * **Giá trị Unique:** *[kết quả]*.
  * [cite\_start]**Phân bố giá trị:** [cite: 12]

| Tên giá trị | Ý nghĩa | Số lượng | Tỷ lệ |
| :--- | :--- | :--- | :--- |
| *[1]* | *[\<2 giờ]* | *[kết quả]* | *[kết quả %]* |
| *[2]* | *[2-5 giờ]* | *[kết quả]* | *[kết quả %]* |
| *[3]* | *[5-10 giờ]*| *[kết quả]* | *[kết quả %]* |
| *[4]* | *[\>10 giờ]*| *[kết quả]* | *[kết quả %]* |

  * [cite\_start]**Mode:** *[Giá trị có tỷ lệ cao nhất, ví dụ: 2]*[cite: 13].

<!-- end list -->

```python
# Mã lệnh Python để lấy thống kê thuộc tính THỨ TỰ
print("\n--- Phân tích thuộc tính THỨ TỰ: studytime (Thời gian học) ---")
print(df['studytime'].value_counts().sort_index())
```

#### 1.3. [cite\_start]Tiền xử lý dữ liệu [cite: 22, 44]

1.  **Kiểm tra dữ liệu khuyết thiếu (Missing Data):**
      * *Sau khi chạy mã, phát hiện [số lượng] giá trị null. [Mô tả cách xử lý, ví dụ: Bộ dữ liệu này may mắn không có giá trị null nào].*
2.  **Tạo biến mục tiêu (Target Variable):**
      * Để phục vụ bài toán Phân lớp, chúng ta chuyển đổi biến số `G3` (0-20) thành biến nhị phân `Pass_Fail`.
      * Quy tắc: $G3 \ge 10$ là "Pass" (Đạt, gán bằng 1), $G3 < 10$ là "Fail" (Không Đạt, gán bằng 0).

<!-- end list -->

```python
# Mã lệnh Python để tiền xử lý
print(f"\nTổng giá trị Null trong CSDL: {df.isnull().sum().sum()}")

# 1. Tạo biến mục tiêu 'Pass_Fail'
df['Pass_Fail'] = (df['G3'] >= 10).astype(int)

print("\nPhân bố biến mục tiêu 'Pass_Fail':")
print(df['Pass_Fail'].value_counts(normalize=True) * 100)
```

-----

### [cite\_start]**Phần 2: Phân tích – thống kê và Khai thác dữ liệu (Dùng Python)** [cite: 44-47]

#### 2.1. Tìm hiểu dữ liệu (Trực quan hóa)

**2.1.1. [cite\_start]Phân tích thuộc tính độc lập [cite: 25]**

  * [cite\_start]**Biểu đồ Boxplot của `G3` (Điểm cuối kỳ)[cite: 28]:**
      * *Nhận xét: [Ví dụ: Điểm số phân bố chủ yếu từ 10 đến 13. Median là 11. Có một số outliers (ngoại lệ) đạt điểm 0].*

<!-- end list -->

```python
# Mã lệnh vẽ Boxplot
plt.figure(figsize=(8, 4))
sns.boxplot(x=df['G3'])
plt.title('Biểu đồ Boxplot cho Điểm cuối kỳ (G3)')
plt.xlabel('Điểm số')
plt.show()
```

  * [cite\_start]**Biểu đồ Histogram của `absences` (Số buổi vắng)[cite: 30]:**
      * *Nhận xét: [Ví dụ: Dữ liệu bị lệch phải nghiêm trọng. Đa số sinh viên vắng từ 0-2 buổi. Rất ít sinh viên vắng nhiều].*

<!-- end list -->

```python
# Mã lệnh vẽ Histogram
plt.figure(figsize=(8, 4))
sns.histplot(df['absences'], bins=20, kde=True)
plt.title('Phân bố số buổi vắng (absences)')
plt.xlabel('Số buổi vắng')
plt.ylabel('Tần suất')
plt.show()
```

  * [cite\_start]**Biểu đồ Scatter plot giữa `studytime` và `G3`[cite: 31]:**
      * *Nhận xét: [Ví dụ: Biểu đồ cho thấy xu hướng không rõ ràng, nhưng có vẻ những sinh viên học nhiều (studytime=3, 4) có xu hướng đạt điểm G3 cao hơn].*

<!-- end list -->

```python
# Mã lệnh vẽ Scatter plot
plt.figure(figsize=(8, 4))
sns.scatterplot(x='studytime', y='G3', data=df, alpha=0.6)
plt.title('Tương quan giữa Thời gian học và Điểm cuối kỳ')
plt.xlabel('Thời gian học (1-4)')
plt.ylabel('Điểm cuối kỳ (G3)')
plt.show()
```

**2.1.2. [cite\_start]Phân tích theo nhóm (Nhóm theo `sex` - Giới tính) [cite: 32]**

  * [cite\_start]**Boxplot của `G3` theo `sex`[cite: 33]:**
      * *Nhận xét: [Ví dụ: Nữ sinh (F) có điểm trung vị (median) cao hơn Nam sinh (M) một chút. Phân bố điểm của Nữ sinh cũng tập trung hơn].*

<!-- end list -->

```python
# Mã lệnh vẽ Boxplot theo nhóm
plt.figure(figsize=(8, 4))
sns.boxplot(x='sex', y='G3', data=df)
plt.title('So sánh điểm G3 theo Giới tính')
plt.xlabel('Giới tính (F=Nữ, M=Nam)')
plt.ylabel('Điểm cuối kỳ (G3)')
plt.show()
```

#### 2.2. [cite\_start]Đo lường sự tương đồng (Ma trận tương quan) [cite: 35]

[cite\_start]Chúng ta sẽ tính **Ma trận tương quan Pearson** cho các thuộc tính dạng số [cite: 39] (`age`, `absences`, `G1`, `G2`, `G3`) để xem mức độ tương quan tuyến tính giữa chúng.

  * *Nhận xét Ma trận (Heatmap):*
      * *`G1` và `G2` có tương quan dương rất mạnh với `G3` (khoảng 0.9), điều này là hiển nhiên.*
      * *`failures` (số lần rớt) có tương quan âm mạnh với `G3` (khoảng -0.3).*
      * *`Medu` và `Fedu` (học vấn cha mẹ) có tương quan dương yếu với `G3` (khoảng 0.2).*

<!-- end list -->

```python
# Mã lệnh vẽ Ma trận tương quan
# Chọn các cột số quan trọng
numeric_cols = ['age', 'Medu', 'Fedu', 'studytime', 'failures', 'famrel', 
                'freetime', 'goout', 'Dalc', 'Walc', 'health', 'absences', 'G1', 'G2', 'G3']
corr_matrix = df[numeric_cols].corr()

plt.figure(figsize=(12, 10))
sns.heatmap(corr_matrix, annot=True, fmt='.2f', cmap='coolwarm')
plt.title('Ma trận tương quan giữa các thuộc tính số')
plt.show()
```

#### 2.3. [cite\_start]Thực hiện khai thác dữ liệu (Dùng Python) [cite: 47, 49]

**Phương pháp 1: Phân lớp (Classification) - Cây quyết định**

  * **Mục tiêu:** Dự đoán sinh viên sẽ "Pass" (1) hay "Fail" (0) dựa trên các yếu tố *không phải là điểm số* (ví dụ: `studytime`, `failures`, `goout`, `internet`, `sex`...).
  * **Thuật toán:** Cây quyết định (Decision Tree Classifier).

<!-- end list -->

```python
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.preprocessing import LabelEncoder

# 1. Chuẩn bị dữ liệu cho mô hình Phân lớp
# Lựa chọn các thuộc tính để dự đoán
features = ['sex', 'age', 'address', 'famsize', 'Medu', 'Fedu', 'studytime', 
            'failures', 'schoolsup', 'famsup', 'paid', 'activities', 'internet',
            'romantic', 'goout', 'Dalc', 'Walc', 'absences']
target = 'Pass_Fail'

# 2. Mã hóa các biến danh nghĩa (nếu có)
df_model = df[features + [target]].copy()
# Biến nhị phân (Yes/No)
binary_cols = ['schoolsup', 'famsup', 'paid', 'activities', 'internet', 'romantic']
for col in binary_cols:
    df_model[col] = df_model[col].map({'yes': 1, 'no': 0})
    
# Biến danh nghĩa (F/M, U/R, ...)
le = LabelEncoder()
df_model['sex'] = le.fit_transform(df_model['sex'])
df_model['address'] = le.fit_transform(df_model['address'])
df_model['famsize'] = le.fit_transform(df_model['famsize'])

# Xử lý các giá trị Null (nếu có)
df_model.fillna(0, inplace=True) # Đơn giản là điền 0, có thể chọn phương pháp khác

# 3. Chia dữ liệu
X = df_model[features]
y = df_model[target]
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# 4. Huấn luyện mô hình
tree_model = DecisionTreeClassifier(max_depth=5, random_state=42)
tree_model.fit(X_train, y_train)

print(f"Huấn luyện mô hình Cây quyết định thành công!")
```

**Phương pháp 2: Phân cụm (Clustering) - K-Means**

  * **Mục tiêu:** Phân nhóm các sinh viên có đặc điểm hành vi và thói quen tương đồng.
  * **Thuật toán:** K-Means.

<!-- end list -->

```python
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

# 1. Chuẩn bị dữ liệu cho mô hình Phân cụm
# Chọn các thuộc tính hành vi để phân cụm
cluster_features = ['studytime', 'failures', 'goout', 'Dalc', 'Walc', 'absences', 'health']
X_cluster = df[cluster_features].copy()

# 2. Chuẩn hóa dữ liệu (K-Means rất nhạy với thang đo)
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X_cluster)

# 3. Huấn luyện mô hình (Giả sử chọn K=3 cụm)
kmeans_model = KMeans(n_clusters=3, random_state=42, n_init=10)
df['Cluster'] = kmeans_model.fit_predict(X_scaled)

print(f"Phân cụm K-Means thành công!")

# 4. Phân tích các cụm
print("\n--- Đặc điểm trung bình của 3 cụm sinh viên ---")
cluster_analysis = df.groupby('Cluster')[cluster_features + ['G3']].mean()
print(cluster_analysis)
```

  * *Phân tích kết quả K-Means:*
      * *Cụm 0: [Ví dụ: Gồm các sinh viên "Rủi ro cao": học ít (studytime thấp), rớt nhiều (failures cao), đi chơi nhiều (goout cao), điểm G3 trung bình thấp nhất].*
      * *Cụm 1: [Ví dụ: Gồm các sinh viên "Cân bằng": các chỉ số ở mức trung bình, điểm G3 trung bình].*
      * *Cụm 2: [Ví dụ: Gồm các sinh viên "Chăm chỉ": học nhiều (studytime cao), ít rớt (failures thấp), ít đi chơi (goout thấp), điểm G3 trung bình cao nhất].*

-----

### [cite\_start]**Phần 3: Giới thiệu về HADOOP** [cite: 50]

#### 3.1. Giới thiệu HADOOP

Hadoop là một framework mã nguồn mở được thiết kế để lưu trữ và xử lý các tập dữ liệu cực lớn (Big Data) một cách phân tán trên các cụm máy tính thông thường (commodity hardware). Kiến trúc cốt lõi của Hadoop gồm 2 thành phần chính:

1.  **HDFS (Hadoop Distributed File System):** Hệ thống tệp tin phân tán, chịu trách nhiệm lưu trữ dữ liệu. Nó chia các tệp lớn thành các khối (blocks) và sao chép (replicate) chúng trên nhiều máy chủ (nodes) để đảm bảo tính chịu lỗi (fault-tolerance).
2.  **MapReduce:** Là mô hình lập trình và xử lý dữ liệu. Một tác vụ MapReduce được chia làm hai giai đoạn:
      * **Map:** Xử lý và chuyển đổi dữ liệu đầu vào thành các cặp (key, value) trung gian.
      * **Reduce:** Tổng hợp (aggregate) các giá trị trung gian có cùng key để cho ra kết quả cuối cùng.

#### 3.2. [cite\_start]Cài đặt HADOOP [cite: 51]

*Việc cài đặt Hadoop đầy đủ (multi-node cluster) khá phức tạp. Trong phạm vi đề tài, em sử dụng phương pháp cài đặt đơn giản (standalone) hoặc (pseudo-distributed) trên một máy ảo (VM) Ubuntu hoặc qua Docker để mô phỏng môi trường Hadoop.*
*(Bạn có thể chụp ảnh màn hình quá trình cài đặt hoặc cấu hình file .xml nếu cần)*

#### 3.3. [cite\_start]Mô phỏng chương trình trên HADOOP [cite: 52]

Để mô phỏng, chúng ta sử dụng `Hadoop Streaming`, cho phép chạy các script (như Python) làm tác vụ MapReduce.

**Bài toán:** Đếm số lượng sinh viên "Pass" và "Fail" (biến `Pass_Fail` đã tạo) theo khu vực sống (`address` - U: Đô thị, R: Nông thôn).

**`mapper.py` (Script Python):**

```python
#!/usr/bin/env python
import sys

# Bỏ qua dòng header
sys.stdin.readline()

for line in sys.stdin:
    line = line.strip()
    # Dữ liệu CSV dùng dấu ';'
    parts = line.split(';')
    
    # Giả định: 'address' là cột thứ 4 (index 3)
    # 'Pass_Fail' là cột cuối cùng (index -1)
    # CẦN KIỂM TRA LẠI INDEX CỘT TRONG FILE CSV CỦA BẠN
    
    # Để an toàn, chúng ta lấy dữ liệu từ file đã xử lý ở Phần 2
    # Giả sử file 'processed_student.csv' có 2 cột 'address' và 'Pass_Fail'
    
    # Ví dụ với file gốc 'student-por.csv':
    try:
        address = parts[3].strip('"') # Cột 'address'
        G3 = int(parts[-3].strip('"')) # Cột 'G3'
        
        # Tạo biến Pass_Fail
        pass_fail = 1 if G3 >= 10 else 0
        
        # Tạo key là (address, pass_fail)
        key = f"{address}_{pass_fail}"
        
        # Output: key <tab> 1
        print(f"{key}\t1")
    except Exception as e:
        continue
```

**`reducer.py` (Script Python):**

```python
#!/usr/bin/env python
import sys

current_key = None
current_count = 0

for line in sys.stdin:
    line = line.strip()
    key, count = line.split('\t', 1)
    
    try:
        count = int(count)
    except ValueError:
        continue
        
    if current_key == key:
        current_count += count
    else:
        if current_key:
            # In ra kết quả của key trước đó
            print(f"{current_key}\t{current_count}")
        current_key = key
        current_count = count

# In ra kết quả của key cuối cùng
if current_key:
    print(f"{current_key}\t{current_count}")
```

**Lệnh mô phỏng (chạy trên Terminal/Shell):**

```bash
# Giả sử 2 file mapper.py và reducer.py đã được cấp quyền thực thi (chmod +x)
cat student-por.csv | python mapper.py | sort -k1,1 | python reducer.py
```

**Kết quả mô phỏng (ví dụ):**

  * *R\_0 50*
  * *R\_1 135*
  * *U\_0 98*
  * *U\_1 366*
    *(Ý nghĩa: Nông thôn (R) có 50 Fail, 135 Pass. Đô thị (U) có 98 Fail, 366 Pass)*

-----

### [cite\_start]**Phần 4: Đánh giá các mẫu kết quả thu được** [cite: 55]

#### 4.1. [cite\_start]Đánh giá mô hình Phân lớp (Cây quyết định) [cite: 65]

Chúng ta sử dụng 2 phương pháp đánh giá:

**1. [cite\_start]Số liệu để đánh giá hiệu suất phân loại (Metrics) [cite: 66]**
Chúng ta sẽ đánh giá trên tập `X_test` và `y_test`.

  * **Confusion Matrix (Ma trận nhầm lẫn):**
      * *TN (True Negative): [kết quả]*
      * *FP (False Positive): [kết quả]*
      * *FN (False Negative): [kết quả]*
      * *TP (True Positive): [kết quả]*
  * **Accuracy (Độ chính xác tổng thể):** *[Ví dụ: 85%]*
  * **Precision (Độ chuẩn xác - cho lớp "Fail"):** *[Ví dụ: 0.75]*
  * **Recall (Độ nhạy - cho lớp "Fail"):** *[Ví dụ: 0.60]*
  * **F1-Score (cho lớp "Fail"):** *[Ví dụ: 0.67]*
  * *Nhận xét: [Ví dụ: Mô hình có độ chính xác tổng thể khá cao (85%). Tuy nhiên, khả năng dự đoán sinh viên "Fail" (Recall) chỉ ở mức 60%, nghĩa là mô hình bỏ lỡ 40% số sinh viên "Fail" thực tế].*

**2. [cite\_start]Xác thực chéo (Cross-Validation) [cite: 69]**
Để đánh giá độ ổn định của mô hình, chúng ta dùng K-Fold Cross-Validation (K=10).

  * *Kết quả Accuracy qua 10-fold: [Ví dụ: [0.82, 0.85, 0.81, 0.88, 0.84, 0.85, 0.83, 0.86, 0.80, 0.87]]*
  * **Mean Accuracy (Trung bình):** *[Ví dụ: 0.841]*
  * **Standard Deviation (Độ lệch chuẩn):** *[Ví dụ: 0.025]*
  * *Nhận xét: [Ví dụ: Độ chính xác trung bình là 84.1% với độ lệch chuẩn thấp (0.025), cho thấy mô hình hoạt động ổn định và kết quả 85% trên không phải là do may mắn].*

<!-- end list -->

```python
# Mã lệnh Python để đánh giá Phân lớp
from sklearn.metrics import classification_report, confusion_matrix
from sklearn.model_selection import cross_val_score

# 1. Đánh giá trên tập Test
y_pred = tree_model.predict(X_test)

print("\n--- [Phần 4.1] Đánh giá mô hình Phân lớp ---")
print("1. Ma trận nhầm lẫn (Confusion Matrix):")
print(confusion_matrix(y_test, y_pred))

print("\n2. Báo cáo phân loại (Classification Report):")
print(classification_report(y_test, y_pred, target_names=['Fail (0)', 'Pass (1)']))

# 3. Đánh giá bằng Cross-Validation (trên toàn bộ dữ liệu X, y)
scores = cross_val_score(tree_model, X, y, cv=10, scoring='accuracy')
print(f"\n3. Xác thực chéo (10-Fold) Accuracy: {scores.mean():.3f} +/- {scores.std():.3f}")
```

#### [cite\_start]4.2. Đánh giá mô hình Phân cụm (K-Means) [cite: 74]

**1. [cite\_start]Phương pháp không giám sát (Unsupervised) [cite: 76]**

  * **Chỉ số Silhouette (Silhouette Score):** Đo lường mức độ rõ ràng và tách biệt của các cụm. Giá trị càng gần 1 càng tốt.
  * *Kết quả Silhouette Score (với K=3): [Ví dụ: 0.18]*
  * *Nhận xét: [Ví dụ: Chỉ số Silhouette khá thấp (0.18). Điều này cho thấy các cụm không được phân tách rõ ràng, các sinh viên có hành vi khá tương đồng nhau hoặc các cụm bị chồng lấn].*

<!-- end list -->

```python
# Mã lệnh Python để đánh giá Phân cụm
from sklearn.metrics import silhouette_score

print("\n--- [Phần 4.2] Đánh giá mô hình Phân cụm ---")
# 1. Phương pháp không giám sát
score = silhouette_score(X_scaled, kmeans_model.labels_)
print(f"1. Chỉ số Silhouette Score (K=3): {score:.3f}")
```

**2. [cite\_start]Phương pháp giám sát (Supervised) (Dùng để kiểm chứng) [cite: 75]**
Chúng ta so sánh nhãn cụm (0, 1, 2) với nhãn thực tế `Pass_Fail` (0, 1) để xem 3 cụm tìm được có tương ứng với kết quả học tập không.

  * *Phân tích (từ bảng `cluster_analysis` ở Phần 2):*
      * *Cụm 0 (Rủi ro cao) có điểm G3 trung bình: [Ví dụ: 8.5] (Fail)*
      * *Cụm 1 (Cân bằng) có điểm G3 trung bình: [Ví dụ: 11.2] (Pass)*
      * *Cụm 2 (Chăm chỉ) có điểm G3 trung bình: [Ví dụ: 13.8] (Pass)*
  * *Nhận xét: [Ví dụ: Thuật toán K-Means đã phân tách khá tốt. Cụm 0 gần như tương ứng với nhóm "Fail", trong khi Cụm 1 và 2 tương ứng với nhóm "Pass". Điều này chứng minh rằng các hành vi (học, chơi, vắng) có liên quan trực tiếp đến kết quả học tập].*