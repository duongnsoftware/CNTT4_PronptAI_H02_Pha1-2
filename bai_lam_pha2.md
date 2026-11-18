# bai_lam_pha2

# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 01
- **Họ tên: Nguyễn Hải Dương**
- **Lớp: CNTT4**
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.
> 

## 4.2. Trích xuất tin nhắn đặt tour ra JSON

**KET QUA AI**

```
[
{
"ma_tour": "SP2N",
"ngay_khoi_hanh": "2026-12-20",
"nguoi_lon": 2,
"tre_em": 1,
"loai_phong": "doi",
"ghi_chu": null
},
{
"ma_tour": "PQ4N",
"ngay_khoi_hanh": "2027-01-05",
"nguoi_lon": 3,
"tre_em": 0,
"loai_phong": null,
"ghi_chu": "Một người ăn chay"
},
{
"ma_tour": "DL3N",
"ngay_khoi_hanh": null,
"nguoi_lon": 4,
"tre_em": 0,
"loai_phong": "doi",
"ghi_chu": "ông nội đi xe lăn"
}
]
```

**Link trò chuyện:** [https://share.gemini.google/IVGGo3vRjE4Q](https://share.gemini.google/IVGGo3vRjE4Q)

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```
1. **Tiền người lớn:**
Đoàn đăng ký tour DL3N (3.200.000 đồng/người lớn) với số lượng 5 người lớn:

$$5 \times 3.200.000 = 16.000.000 \text{ đồng}$$

2. **Tiền trẻ em:**

* 2 trẻ em (8 tuổi và 10 tuổi) nằm trong độ tuổi từ 5 đến 11 tuổi nên tính 70% giá người lớn:

$$2 \times (3.200.000 \times 70\%) = 2 \times 2.240.000 = 4.480.000 \text{ đồng}$$

* 1 bé 3 tuổi (dưới 5 tuổi) được miễn phí:

$$1 \times 0 = 0 \text{ đồng}$$

* Tổng tiền trẻ em:

$$4.480.000 + 0 = 4.480.000 \text{ đồng}$$

3. **Tiền tour:**
Tổng tiền tour trước khi giảm giá bao gồm tiền người lớn và tiền trẻ em:

$$16.000.000 + 4.480.000 = 20.480.000 \text{ đồng}$$

4. **Giảm giá đoàn:**
Vì đoàn có 5 người lớn (đạt điều kiện từ 5 người lớn trở lên) nên được giảm 5% trên tổng tiền tour:

$$20.480.000 \times 5\% = 1.024.000 \text{ đồng}$$

Tiền tour sau khi giảm giá là:

$$20.480.000 - 1.024.000 = 19.456.000 \text{ đồng}$$

5. **Phụ thu:**
Có 1 người lớn ở phòng đơn (phí phụ thu 800.000 đồng/người và không áp dụng giảm giá):

$$1 \times 800.000 = 800.000 \text{ đồng}$$

6. **Tổng tiền:**
Tổng số tiền khách hàng cần thanh toán là:

$$19.456.000 + 800.000 = 20.256.000 \text{ đồng}$$

[RESULT: 20.256.000 đồng]
```

**Link trò chuyện:** [https://share.gemini.google/U1Vxc4CQ2BD6](https://share.gemini.google/U1Vxc4CQ2BD6)

### b) Kiểm tra kết quả AI

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```
{"loai_su_co": "khach_san", "so_khach": 2, "so_dem_bi_anh_huong": 2, "tom_tat": "Khách bị chuyển từ khách sạn 4 sao sang 3 sao ẩm mốc trong 2 đêm đầu tour Phú Quốc."}
```

**Link trò chuyện:** [https://share.gemini.google/3dRSH9Aqkf7I](https://share.gemini.google/3dRSH9Aqkf7I)

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50% - tối đa 5,0 điểm)** | **0 / 5,0** | **1. Sai giá tour:** *"Tour Sa Pa 2N1Đ bên em giá 2.200.000đ/người lớn"* — Báo sai giá chuẩn của công ty (2.400.000 đồng/người lớn).<br>

<br>

<br>**2. Sai chính sách huỷ:** *"Anh huỷ trước 3 ngày thì được hoàn tiền đầy đủ nha anh."* — Thông tin chuẩn quy định huỷ trước từ 7 ngày trở lên mới hoàn 100%, từ 3 đến 6 ngày chỉ hoàn 50%, dưới 3 ngày không hoàn tiền. | *"Tour Sa Pa 2N1Đ bên em có giá 2.400.000 đồng/người lớn. Về chính sách huỷ tour, nếu anh huỷ trước ngày khởi hành từ 7 ngày trở lên sẽ được hoàn 100%, huỷ trước từ 3 đến 6 ngày hoàn 50%, và huỷ dưới 3 ngày sẽ không hoàn tiền ạ."* |
| **Đầy đủ (30% - tối đa 3,0 điểm)** | **1,5 / 3,0** | **Thiếu bước khai thác thông tin & chốt đơn:** *"Anh cần gì cứ nhắn em nhé!"* — Đã trả lời 2 ý hỏi về giá và chính sách huỷ (dù sai nội dung), nhưng thiếu phần mời khách cung cấp ngày đi dự kiến và số lượng khách để hỗ trợ đặt tour. | *"Anh dự kiến khởi hành vào ngày nào và đoàn mình có bao nhiêu khách ạ? Anh cho em xin thông tin để em kiểm tra chỗ và hỗ trợ đặt tour cho mình nhé!"* |
| **Giọng điệu (20% - tối đa 2,0 điểm)** | **1,0 / 2,0** | **Dùng từ ngữ suồng sã, thiếu chuyên nghiệp:** *"đi rất vui luôn ạ"*, *"nha anh"*, *"nhắn em nhé!"* — Văn phong mang tính trò chuyện cá nhân, thiếu sự chỉn chu cần thiết trong tư vấn dịch vụ khách hàng. | *"Chào anh ạ! Em xin gửi anh thông tin chi tiết về tour Sa Pa 2N1Đ bên em..."* và kết thúc bằng *"Nếu cần hỗ trợ thêm thông tin, anh vui lòng phản hồi lại giúp em nhé ạ!"* |
| **TỔNG ĐIỂM** | **2,5 / 10** | Nhân viên mắc lỗi nghiêm trọng khi cung cấp sai hoàn toàn thông tin cốt lõi (giá và điều kiện hoàn huỷ), thiếu lời kêu gọi hành động (CTA) để chốt lịch và sử dụng văn phong còn suồng sã. | **Bản sửa hoàn chỉnh:** *"Dạ chào anh ạ! Em xin gửi anh thông tin chi tiết về tour Sa Pa 2N1Đ bên em: giá tour là 2.400.000 đồng/người lớn. Về chính sách huỷ tour, bên em hoàn 100% nếu anh báo huỷ trước ngày khởi hành từ 7 ngày trở lên, hoàn 50% nếu báo trước từ 3 đến 6 ngày, và không hoàn tiền nếu báo dưới 3 ngày. Anh dự kiến đi vào ngày nào và đoàn mình có bao nhiêu người ạ? Anh gửi thông tin để em kiểm tra lịch và hỗ trợ đặt tour cho mình nhé ạ!"* |
```

**Link trò chuyện:** [https://share.gemini.google/rvB7S4VC0cce](https://share.gemini.google/rvB7S4VC0cce)