# Phát Hiện Ngôn Ngữ Độc Hại và Thù Ghét Trên Sàn Thương Mại Điện Tử (Vietnamese Toxic Speech Detection in E-commerce)

Dự án này tập trung vào việc tự động phát hiện các ngôn từ thù ghét, độc hại, và xúc phạm trong các bình luận, đánh giá sản phẩm trên các Sàn Thương Mại Điện Tử (TMĐT) tại Việt Nam. 

Dự án này kế thừa và ứng dụng các phương pháp luận cùng kiến trúc mô hình từ nghiên cứu **ViHOS (Vietnamese Hate and Offensive Spans Detection)**.

> **⚠️ Cảnh báo nội dung (Disclaimer):** Dự án và tập dữ liệu đi kèm chứa các bình luận thực tế có ngôn từ thô tục, xúc phạm, thù ghét và mang tính công kích. Xin lưu ý trước khi xem xét dữ liệu.

---

## 📖 Giới thiệu (Introduction)

Cùng với sự phát triển bùng nổ của Thương mại điện tử tại Việt Nam, phần bình luận và đánh giá (reviews) đóng vai trò quan trọng trong việc quyết định mua hàng. Tuy nhiên, đây cũng là nơi thường xuyên xuất hiện các ngôn từ độc hại như:

* Khách hàng lăng mạ, chửi bới người bán hàng do trải nghiệm tồi tệ.
* Các cửa hàng đối thủ sử dụng từ ngữ thô tục, bôi nhọ để cạnh tranh không lành mạnh.
* Ngôn từ vi phạm tiêu chuẩn cộng đồng, teencode phức tạp, từ lóng mang ý nghĩa xúc phạm.

Việc kiểm duyệt thủ công hàng triệu bình luận mỗi ngày là bất khả thi. Do đó, dự án này hướng tới việc xây dựng một hệ thống phát hiện tự động, giúp quản trị viên dễ dàng lọc và xử lý các bình luận toxic, tạo ra một môi trường mua sắm văn minh hơn.

---

## 🗂️ Tập dữ liệu (Dataset)

> **💡 Lưu ý cho tác giả:** Hãy thay đổi các con số dưới đây theo dataset thực tế mà bạn đã thu thập/sử dụng.

Tập dữ liệu của chúng tôi được thu thập từ các nền tảng TMĐT phổ biến tại Việt Nam (Shopee, Lazada, Tiki...). Các bình luận được gán nhãn **[Phân loại câu (Toxic/Clean) / Hoặc gán nhãn theo Span (Đoạn text toxic) giống ViHOS]**.

**Thống kê chi tiết:**
* **Tổng số lượng bình luận:** 30000 bình luận.
* **Phân bổ:** 15000 bình luận độc hại, gây thù ghét và 15000 bình luận chuẩn mực.
* **Đặc trưng ngôn ngữ:** Chứa nhiều teencode, viết tắt chữ cái đầu, dùng ký tự đặc biệt để lách bộ lọc (ví dụ: đ*, v.l, rác rưởi,...).

**Chia tập dữ liệu (Data Split):**
* **Tập huấn luyện (Train set):** 80% tổng số bình luận.
* **Tập phát triển (Dev set):** 10% bình luận của 20% bình luận còn lại.
* **Tập kiểm thử (Test set):** 10% bình luận còn lại.

*Xem chi tiết định dạng dữ liệu trong thư mục `data/`.*

---

## ⚙️ Cài đặt và Sử dụng (Installation & Usage)

### 1. Cài đặt môi trường
Clone repository và cài đặt các thư viện cần thiết:

```bash
git clone [[https://github.com/](https://github.com/)[username-cua-ban]/[ten-repo].git](https://github.com/itphamky/ViHOS_VN)
```
### 2. Kết quả thực nghiệm
<img width="481" height="504" alt="image" src="https://github.com/user-attachments/assets/a1a322a8-b2c5-43a3-87ec-eadf210b624d" />
<img width="704" height="470" alt="image" src="https://github.com/user-attachments/assets/a933cb7b-07eb-45b4-be4f-31231894289d" />
<img width="704" height="470" alt="image" src="https://github.com/user-attachments/assets/e978647e-9497-4269-b55c-6f21ecc91041" />
<img width="704" height="470" alt="image" src="https://github.com/user-attachments/assets/55ac95c4-039b-4042-b09e-b07da4058af5" />
<img width="704" height="470" alt="image" src="https://github.com/user-attachments/assets/92755e94-89c5-444b-b2c2-3b69e529d1b1" />
<img width="790" height="590" alt="image" src="https://github.com/user-attachments/assets/c321a125-a0fa-49d2-83c0-56623ae296fe" />


### 3. 🙏 Lời cảm ơn và Trích dẫn (Acknowledgements & Citation)
Dự án này được truyền cảm hứng và tham khảo mã nguồn từ nghiên cứu ViHOS. Chúng tôi xin gửi lời cảm ơn đến nhóm tác giả của paper ViHOS: Hate Speech Spans Detection for Vietnamese.

Nếu bạn quan tâm đến phương pháp gốc về gán nhãn và trích xuất chuỗi (spans) ngôn ngữ thù ghét, vui lòng tham khảo nghiên cứu của họ:
@article{hoang2023vihos,
  title={ViHOS: Hate Speech Spans Detection for Vietnamese},
  author={Hoang, Phu Gia and Luu, Canh Duc and Tran, Khanh Quoc and Van Nguyen, Kiet and Nguyen, Ngan Luu-Thuy},
  journal={arXiv preprint arXiv:2301.10186},
  year={2023}
}
