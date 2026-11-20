# Bước 1:Thiết kế giải pháp (I/O).
1. Input:
- thong_tin:thông tin cần xử lý.
- bai_giai_thích:feynman
- rubric:tiêu chí và tính điểm.

2. Output: 
   1. Kiểm tra lỗi dữ liệu
   2. Nhận xét Feynman + gợi ý nói dễ hiểu
   3. Điểm từng tiêu chí, tổng điểm & cách sửa.
# Bước 2:
```
1. Context: Hãy đóng vai một chuyên gia đào tạo cửa hàng, gia sư Feynman và giám khảo Rubric.
2. Request: Kiểm tra dữ liệu, đánh giá Feynman và chấm Rubric cho nhân viên.
3. Explanation:
- Thiếu thong_tin hoặc bai_giai_thich: dừng chấm, in ra "thiếu dữ liệu", không tự bịa ra.
- Thiếu rubric: vẫn làm Feynman, ghi "thiếu Rubric", không chấm điểm tổng.
- bai_giai_thich lạc đề/vô nghĩa: in ra "sai thông tin", chỉ lỗi sai, không cộng điểm cho phần sai.
4. Action: 
- Bước 1: Kiểm tra dữ liệu
- Bước 2:Nhận xét Feynman và gợi ý cách nói đơn giản
- Bước 3:Chấm Rubric, tính tổng điểm và cách sửa.
5. Tone: Rõ ràng, khách quan,thẳng thắn chỉ ra lỗi sai và cách khắc phục.
6. Extras: Xuất Markdown gồm 3 mục: 
```
|1. Kiểm tra dữ liệu | 2. Feynman | 3. Rubric & Sửa lỗi.
|---|---|---|
# Kết quả prompt:
```
# BÁO CÁO ĐÁNH GIÁ NHÂN VIÊN THEO FEYNMAN & RUBRIC

## 1. KIỂM TRA DỮ LIỆU

**Trạng thái: ĐỦ DỮ LIỆU ĐỂ ĐÁNH GIÁ**

| Thành phần | Kết quả | Nhận xét |
|---|---|---|
| `thong_tin` | Đạt | Có đầy đủ kiến thức về khung góp ý 4 bước. |
| `bai_giai_thich` | Đạt | Nhân viên đã giải thích được nội dung chính. |
| `rubric` | Đạt một phần | Có tiêu chí đánh giá nhưng chưa có thang điểm cụ thể. |

### Kiểm tra tính chính xác

- Không phát hiện nội dung lạc đề.
- Không có thông tin sai lệch nghiêm trọng.
- Nhân viên hiểu được mục đích của việc góp ý dựa trên dữ liệu thay vì cảm nhận cá nhân.
- Tuy nhiên, phần giải thích chưa thể hiện đầy đủ cấu trúc 4 bước.

---

## 2. ĐÁNH GIÁ FEYNMAN

**Kết quả: HIỂU Ý CHÍNH, CẦN CẢI THIỆN CÁCH GIẢI THÍCH**

### 2.1. Đánh giá theo 4 bước kiến thức

| Nội dung cần có | Nhân viên thể hiện | Đánh giá |
|---|---|---|
| 1. Mục tiêu | Nêu kỳ vọng ban đầu với nhân viên. | Đúng |
| 2. Bằng chứng | Nêu số liệu cụ thể hoặc kết quả hành vi. | Đúng |
| 3. Nhận xét | Nhận xét công tâm, nhẹ nhàng. | Chưa đầy đủ |
| 4. Hành động | Đưa ra cách cải thiện. | Đúng |

### 2.2. Nhận xét Feynman

**Điểm làm tốt:**

- Nhân viên hiểu rằng góp ý cần có kỳ vọng và bằng chứng cụ thể.
- Biết tránh việc đánh giá dựa trên cảm xúc cá nhân.
- Có đề cập đến việc đưa ra hướng cải thiện cho nhân viên.

**Điểm cần khắc phục:**

1. Chưa phân biệt rõ giữa bằng chứng và nhận xét.
2. Chưa giải thích rằng nhận xét phải so sánh kết quả thực tế với mục tiêu ban đầu.
3. Chưa trình bày thứ tự 4 bước một cách rõ ràng.
4. Cách diễn đạt còn dài và chưa thật sự mạch lạc.

### 2.3. Gợi ý giải thích đơn giản theo phương pháp Feynman

Nhân viên có thể diễn đạt lại như sau:

> Khi góp ý cho một nhân viên, chúng ta cần thực hiện 4 bước:
>
> - **Mục tiêu:** Ban đầu chúng ta mong muốn nhân viên đạt được điều gì?
> - **Bằng chứng:** Nhân viên đã thực hiện công việc như thế nào? Có số liệu hoặc kết quả cụ thể không?
> - **Nhận xét:** So sánh kết quả thực tế với mục tiêu để đánh giá công bằng.
> - **Hành động:** Đề xuất cách giúp nhân viên khắc phục điểm yếu và phát triển tốt hơn.
>
> Ví dụ: Mục tiêu là xử lý 20 đơn hàng mỗi ngày. Thực tế nhân viên xử lý được 15 đơn. Như vậy, nhân viên chưa đạt mục tiêu 5 đơn. Quản lý cần tìm hiểu nguyên nhân và hướng dẫn cách cải thiện tốc độ xử lý đơn hàng.

---

## 3. RUBRIC & SỬA LỖI

**Trạng thái: RUBRIC CHƯA CÓ THANG ĐIỂM**

Rubric hiện tại yêu cầu xem xét số ý đúng và những ý bổ sung hợp lý. Vì chưa quy định trọng số, sử dụng cách đếm ý để đánh giá tham khảo, không tự đặt điểm tổng chính thức.

### 3.1. Bảng chấm tiêu chí

| Tiêu chí | Số ý cần có | Số ý đạt | Nhận xét |
|---|---:|---:|---|
| Mục tiêu | 1 | 1 | Đạt |
| Bằng chứng | 1 | 1 | Đạt |
| Nhận xét | 1 | 0.5 | Có đề cập nhưng chưa rõ so sánh với mục tiêu |
| Hành động | 1 | 1 | Đạt |
| **Tổng** | **4** | **3.5** | **Đạt một phần** |

### 3.2. Kết quả đánh giá tham khảo

- **Số ý đạt:** 3.5/4.
- **Tỷ lệ đạt:** 87.5%.
- **Lưu ý:** Đây là tỷ lệ theo cách đếm ý tham khảo, không phải điểm Rubric chính thức do chưa có thang điểm và trọng số cụ thể.

### 3.3. Những nội dung nhân viên nên sửa

| Lỗi cần cải thiện | Cách sửa |
|---|---|
| Chưa giải thích rõ nhận xét | Phải so sánh kết quả thực tế với mục tiêu. |
| Chưa có ví dụ cụ thể | Sử dụng tình huống thực tế tại cửa hàng. |
| Diễn đạt chưa có trình tự | Trình bày lần lượt Mục tiêu → Bằng chứng → Nhận xét → Hành động. |

### 3.4. Kết luận của giám khảo

**Nhân viên đã hiểu được kiến thức cốt lõi nhưng chưa giải thích đầy đủ và có hệ thống.**

| Tiêu chí | Kết quả |
|---|---|
| Kiến thức | Nắm được 4 bước cơ bản. |
| Khả năng diễn đạt | Khá, cần rõ ràng hơn. |
| Khả năng vận dụng | Cần bổ sung ví dụ thực tế. |
| Hướng đào tạo | Yêu cầu nhân viên giải thích lại 4 bước và tự đưa ra một tình huống góp ý cho đồng nghiệp. |

### 3.5. Khuyến nghị đào tạo

Chưa nên kết luận nhân viên thành thạo kiến thức chỉ dựa trên phần giải thích này.

Nên kiểm tra thêm bằng một tình huống thực tế để xác nhận khả năng vận dụng.

**Bài tập đề xuất:**

1. Nhân viên tự giải thích lại 4 bước bằng ngôn ngữ đơn giản.
2. Đưa ra một ví dụ góp ý cho nhân viên bán hàng tại cửa hàng.
3. Phân tích ví dụ theo đúng 4 bước: Mục tiêu, Bằng chứng, Nhận xét và Hành động.
4. Đánh giá lại sau khi nhân viên hoàn thành bài tập.

---

**KẾT LUẬN CUỐI CÙNG:** Nhân viên đã nắm được phần lớn kiến thức, cần cải thiện khả năng phân tích và diễn đạt để có thể vận dụng đúng quy trình góp ý nhân viên trong thực tế.
```
