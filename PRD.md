# PRODUCT REQUIREMENTS DOCUMENT (PRD)

**Tên dự án:** Hệ thống thuyết minh tự động đa ngôn ngữ tại các nhà thi đấu TP.HCM

**Mã dự án:** CNPM-TMDNN

**Phiên bản:** 1.0

**Định hướng kỹ thuật:** Backend Development – Kiến trúc 3 lớp – CI/CD

**Thời gian dự kiến:** 21/10/2026 – 29/11/2026

---

## 1. Vấn đề (Problem Statement)

Trong bối cảnh giả định, TP.HCM được lựa chọn đăng cai Giải bóng chuyền vô địch châu Á, với bốn địa điểm tổ chức:

- Nhà thi đấu Phú Thọ.
- Nhà thi đấu Hồ Xuân Hương.
- Nhà thi đấu Rạch Miễu.
- Nhà thi đấu Nguyễn Du.

Sự kiện thu hút khán giả trong nước, khách du lịch và người hâm mộ quốc tế đến tham quan, theo dõi các trận đấu.

Tuy nhiên, sự khác biệt ngôn ngữ và việc thiếu một hệ thống giới thiệu tập trung có thể khiến khách tham quan gặp khó khăn khi tìm hiểu thông tin về các nhà thi đấu.

Do đó, cần xây dựng hệ thống thuyết minh tự động, cho phép người dùng chủ động tiếp cận thông tin bằng ngôn ngữ phù hợp.

Sau sự kiện giả định, mô hình có thể tiếp tục được sử dụng để giới thiệu các công trình thể thao và mở rộng cho những giải đấu khác.

## 2. Phương án đề xuất (Proposed Solution)

Phát triển hệ thống Backend theo kiến trúc ba lớp, cung cấp API quản lý và truy xuất nội dung thuyết minh đa ngôn ngữ.

Người dùng truy cập một website đơn giản thông qua mã QR, lựa chọn nhà thi đấu và ngôn ngữ mong muốn để xem thông tin, hình ảnh và nghe thuyết minh.

**Quy trình sử dụng:**

1. Quét mã QR bằng điện thoại.
2. Truy cập website giới thiệu bốn nhà thi đấu.
3. Lựa chọn nhà thi đấu muốn tìm hiểu.
4. Chọn ngôn ngữ thuyết minh.
5. Xem nội dung và phát audio tương ứng.

Website đóng vai trò giao diện tương tác cơ bản. Backend chịu trách nhiệm quản lý dữ liệu, cung cấp nội dung và xử lý các yêu cầu từ người dùng.

## 3. Mục tiêu (Objectives)

- Cung cấp hệ thống thuyết minh giúp khách tham quan tự tìm hiểu thông tin mà không cần nhân viên hướng dẫn trực tiếp cho các nội dung đã được số hóa.
- Giới thiệu lịch sử, kiến trúc, đặc điểm và vai trò của các nhà thi đấu tại TP.HCM.
- Hỗ trợ bốn ngôn ngữ chính: tiếng Việt, tiếng Anh, tiếng Hàn và tiếng Nhật.
- Cung cấp nội dung dưới dạng văn bản, hình ảnh và audio.
- Cho phép quản trị viên cập nhật dữ liệu mà không phải chỉnh sửa trực tiếp mã nguồn.
- Xây dựng Backend có cấu trúc rõ ràng, có kiểm thử và quy trình CI/CD.
- Tạo nền tảng để mở rộng thêm nhà thi đấu, ngôn ngữ và chức năng trong tương lai.

## 4. Đối tượng sử dụng (Target Users)

**Khán giả và người hâm mộ:** Truy cập thông tin nhà thi đấu, nghe thuyết minh và tìm hiểu các tiện ích cơ bản.

**Khách tham quan quốc tế:** Lựa chọn ngôn ngữ phù hợp để tiếp cận nội dung.

**Quản trị viên nội dung:** Quản lý thông tin nhà thi đấu, bản dịch, hình ảnh và audio thông qua các chức năng quản trị.

**Ban quản lý nhà thi đấu:** Có thể sử dụng số liệu thống kê cơ bản để đánh giá mức độ quan tâm của khách tham quan.

## 5. Yêu cầu chức năng (Functional Requirements)

### 5.1. Người dùng cuối

**FR1 – Tra cứu nhà thi đấu**

- Hiển thị danh sách bốn nhà thi đấu.
- Cho phép lựa chọn và xem thông tin chi tiết từng địa điểm.

**FR2 – Lựa chọn ngôn ngữ**

- Hỗ trợ tiếng Việt, tiếng Anh, tiếng Hàn và tiếng Nhật.
- Cho phép thay đổi ngôn ngữ trong quá trình sử dụng.
- Trả về nội dung tương ứng với ngôn ngữ được chọn.

**FR3 – Thuyết minh đa phương tiện**

- Hiển thị văn bản thuyết minh và hình ảnh.
- Cung cấp audio tương ứng với từng nhà thi đấu và ngôn ngữ.
- Cho phép người dùng phát, tạm dừng và tua audio thông qua trình phát trên website.
- Văn bản thuyết minh được hiển thị để người dùng có thể đọc cùng lúc với việc nghe.

**FR4 – Truy cập bằng mã QR**

- Cung cấp mã QR dẫn đến website.
- Người dùng sử dụng camera điện thoại để quét QR mà không cần cài đặt ứng dụng riêng.

### 5.2. Quản trị hệ thống

**FR5 – Quản lý nội dung**

- Thêm, xem, sửa và xóa thông tin nhà thi đấu.
- Quản lý văn bản thuyết minh theo từng ngôn ngữ.
- Quản lý thông tin và đường dẫn tài nguyên hình ảnh, audio.
- Hỗ trợ cập nhật nội dung thông qua API quản trị.

**FR6 – Xác thực và phân quyền**

- Xác thực người quản trị.
- Chỉ cho phép tài khoản có quyền quản trị thực hiện các thao tác thay đổi dữ liệu.
- Người dùng thông thường được truy cập nội dung công khai mà không cần đăng nhập.

**FR7 – Thống kê cơ bản**

- Ghi nhận số lượt truy cập hoặc yêu cầu phát thuyết minh.
- Thống kê theo nhà thi đấu và ngôn ngữ.
- Cung cấp dữ liệu thống kê thông qua API.

### 5.3. Chức năng mở rộng

Các chức năng không bắt buộc trong phiên bản đầu tiên:

- Nhận diện vị trí tự động qua GPS/beacon.
- Bản đồ tương tác và hướng dẫn lộ trình.
- Tour 360° và video giới thiệu.
- Chế độ hoạt động offline.
- Đánh dấu yêu thích, đánh giá và gửi phản hồi.
- Tạo audio bằng TTS hoặc dịch tự động bằng AI theo yêu cầu.
- Quản lý phiên bản bản dịch và quy trình phê duyệt nhiều bước.

## 6. Yêu cầu phi chức năng (Non-functional Requirements)

**NFR1 – Hiệu năng**

- Mục tiêu tải nội dung chính trong vòng 3 giây.
- Mục tiêu bắt đầu phát audio trong vòng 2 giây sau thao tác của người dùng.
- Các chỉ số được đánh giá trong điều kiện kiểm thử xác định, với kết nối mạng và kích thước tài nguyên phù hợp.

**NFR2 – Khả năng mở rộng**

- Cho phép bổ sung nhà thi đấu và ngôn ngữ thông qua dữ liệu hoặc cấu hình mà không phải thay đổi logic nghiệp vụ chính.
- Thiết kế cấu trúc dữ liệu phù hợp để tái sử dụng cho các địa điểm khác.

**NFR3 – Bảo mật**

- Bảo vệ API quản trị bằng cơ chế xác thực và phân quyền.
- Kiểm tra dữ liệu đầu vào và xử lý các yêu cầu không hợp lệ.
- Hạn chế thu thập thông tin cá nhân không cần thiết.
- Sử dụng kết nối an toàn khi triển khai hệ thống công khai.

**NFR4 – Tính tương thích**

- Website cơ bản có thể truy cập trên trình duyệt phổ biến của điện thoại và máy tính.
- Giao diện thích ứng với kích thước màn hình.
- Không yêu cầu người dùng cài ứng dụng riêng.

**NFR5 – Tính tiếp cận**

- Nội dung văn bản có thể đọc song song với audio.
- Giao diện sử dụng cỡ chữ dễ đọc và độ tương phản phù hợp.
- Các thao tác chọn địa điểm, chọn ngôn ngữ và phát audio phải dễ sử dụng.

**NFR6 – Đa ngôn ngữ**

- Sử dụng Unicode để lưu trữ nội dung.
- Quản lý ngôn ngữ bằng các mã chuẩn: `vi`, `en`, `ko`, `ja`.
- Đảm bảo hệ thống xử lý và hiển thị đúng ký tự đặc thù của từng ngôn ngữ.

**NFR7 – Khả năng bảo trì**

- Backend được tổ chức theo kiến trúc Controller – Service – Repository.
- Mã nguồn được quản lý bằng Git/GitHub.
- Có kiểm thử và quy trình CI/CD phục vụ tích hợp, triển khai.

## 7. Phạm vi dự án (Project Scope)

### 7.1. Trong phạm vi MVP

- Bốn nhà thi đấu tại TP.HCM.
- Bốn ngôn ngữ: Việt, Anh, Hàn, Nhật.
- Nội dung văn bản, hình ảnh và audio đã được chuẩn bị sẵn.
- QR dẫn đến website giới thiệu nhà thi đấu.
- Website người dùng ở mức cơ bản.
- API tra cứu nhà thi đấu và thuyết minh đa ngôn ngữ.
- API quản trị nội dung có xác thực và phân quyền.
- Thống kê sử dụng cơ bản.
- Backend ba lớp, kết nối cơ sở dữ liệu, kiểm thử và CI/CD.

### 7.2. Ngoài phạm vi MVP

- Đặt vé, thanh toán và kiểm soát cổng ra vào.
- Hệ thống chỉ đường đến từng ghế ngồi.
- GPS, beacon, bản đồ tương tác.
- Tour 360°, AR và trải nghiệm thực tế ảo.
- Chế độ offline đầy đủ.
- Chatbot, nhận diện giọng nói.
- Dịch tự động hoặc sinh audio trực tiếp bằng AI.
- Dashboard phân tích chuyên sâu.
- Giao diện CMS phức tạp.

### 7.3. Hướng phát triển tiếp theo

- Bổ sung tiếng Trung và tiếng Ả Rập.
- Mở rộng sang các nhà thi đấu, sân vận động khác.
- Tích hợp các tính năng định vị, trải nghiệm tương tác và AI khi có điều kiện.

## 8. Ràng buộc và giả định (Constraints & Assumptions)

- Giải bóng chuyền vô địch châu Á tại TP.HCM là bối cảnh giả định phục vụ đồ án.
- Thông tin thực tế về bốn nhà thi đấu phải được kiểm tra từ các nguồn đáng tin cậy.
- Dữ liệu giải đấu giả định phải được phân biệt với thông tin thực tế.
- Bản dịch cần được kiểm tra về nội dung, thuật ngữ và tính tự nhiên trước khi sử dụng.
- Audio có thể được chuẩn bị trước bằng công cụ phù hợp.
- Hình ảnh, audio và các tài nguyên khác phải có quyền sử dụng hợp lệ.
- Việc đặt mã QR trực tiếp tại các nhà thi đấu cần sự đồng ý của đơn vị quản lý nếu hệ thống được triển khai thực tế.
- Trong phạm vi đồ án, mã QR mẫu có thể dẫn đến website demo mà không cần triển khai tại địa điểm.
- Thời gian và nguồn lực phát triển hạn chế; dự án ưu tiên Backend và giao diện minh họa đơn giản.

## 9. Chỉ số thành công và tiêu chí nghiệm thu

### 9.1. Tiêu chí nghiệm thu MVP

- Truy xuất được thông tin của cả bốn nhà thi đấu.
- Truy xuất được văn bản và audio của bốn ngôn ngữ đã cam kết.
- Người dùng có thể truy cập website qua mã QR.
- Người dùng có thể chọn địa điểm, đổi ngôn ngữ và phát audio.
- API quản trị hỗ trợ các thao tác CRUD theo đúng quyền hạn.
- API thống kê trả về dữ liệu sử dụng cơ bản.
- Backend thể hiện rõ kiến trúc ba lớp.
- Các chức năng chính có kiểm thử và xử lý lỗi cơ bản.
- Quy trình CI/CD có thể thực hiện build, test và triển khai phiên bản demo.

### 9.2. KPI vận hành trong tương lai

Khi hệ thống được triển khai thực tế, có thể theo dõi:

- Tổng số lượt sử dụng.
- Phân bố lượt sử dụng theo nhà thi đấu.
- Tỷ lệ lựa chọn từng ngôn ngữ.
- Số lượt nghe audio.
- Mức độ hài lòng của người dùng, hướng đến CSAT từ 4/5 trở lên khi có chức năng khảo sát.
- Số lỗi nội dung hoặc bản dịch được phát hiện, xử lý.

Các KPI vận hành không được xem là số liệu đã đạt trong giai đoạn đồ án thử nghiệm.

## 10. Rủi ro và giải pháp tháo gỡ

| Rủi ro | Giải pháp dự kiến |
|---|---|
| Bản dịch sai hoặc thiếu tự nhiên | Đối chiếu nội dung, kiểm tra thủ công và nhờ người có năng lực ngôn ngữ rà soát khi có thể |
| Mạng yếu tại nhà thi đấu | Tối ưu dung lượng hình ảnh, audio và tài nguyên web; nghiên cứu offline cache ở giai đoạn sau |
| GPS kém chính xác trong nhà | Sử dụng QR làm phương thức truy cập chính, không phụ thuộc định vị GPS |
| Thiếu tư liệu hoặc vi phạm bản quyền | Ưu tiên ảnh tự chụp, tài nguyên được cấp phép hoặc có sự đồng ý |
| API hoặc cơ sở dữ liệu gặp lỗi | Kiểm thử từng chức năng, kiểm tra dữ liệu đầu vào và xử lý ngoại lệ |
| Lỗi trong quá trình triển khai | Thiết lập CI/CD, kiểm tra bản build và chuẩn bị phương án demo dự phòng |
| Chậm tiến độ | Giới hạn phạm vi MVP, ưu tiên chức năng cốt lõi và dành tuần cuối dự trữ |
| Không đủ nội dung cho bốn ngôn ngữ | Chuẩn bị dữ liệu và bản dịch sớm, kiểm tra độ đầy đủ trước khi nghiệm thu |

## 11. Lộ trình thực hiện (Project Roadmap)

### Giai đoạn 1 – Khởi động và thiết kế

**21/10 – 25/10/2026**

- Hoàn thiện PRD.
- Thu thập và xác minh dữ liệu bốn nhà thi đấu.
- Xác định phạm vi MVP.
- Thiết kế Use Case và ERD.
- Chuẩn bị cấu trúc dữ liệu và phác thảo giao diện nếu cần.

**Kết quả mong đợi:** Tài liệu yêu cầu và dữ liệu ban đầu đủ rõ để bắt đầu lập trình.

### Giai đoạn 2 – Phát triển Backend MVP

**26/10 – 22/11/2026**

**Tuần 1 (26/10 – 01/11):**
- Thiết kế và kết nối cơ sở dữ liệu.
- Xây dựng các thành phần Backend ba lớp.
- Triển khai API quản lý nhà thi đấu và CRUD cơ bản.

**Tuần 2 (02/11 – 08/11):**
- Xây dựng chức năng truy xuất nội dung đa ngôn ngữ.
- Tích hợp dữ liệu văn bản, hình ảnh và audio.
- Kiểm thử các API chính.

**Tuần 3 (09/11 – 15/11):**
- Hoàn thiện luồng thuyết minh.
- Tích hợp website demo và mã QR.
- Xây dựng chức năng quản trị, bảo mật cần thiết và CI cơ bản.
- Hoàn thành bản MVP có thể trình diễn.

**Tuần 4 (16/11 – 22/11):**
- Hoàn thiện thống kê cơ bản.
- Kiểm thử, xử lý lỗi.
- Hoàn thiện CI/CD và triển khai ứng dụng.
- Chuẩn bị tài liệu, demo và nội dung bảo vệ.

### Giai đoạn 3 – Dự trữ và nghiệm thu

**23/11 – 29/11/2026**

- Kiểm tra toàn bộ chức năng.
- Sửa các lỗi phát sinh.
- Hoàn thiện báo cáo và tài liệu kỹ thuật.
- Luyện trình bày và chuẩn bị bảo vệ đồ án.

Tuần cuối đóng vai trò dự trữ. Phiên bản có thể trình diễn cần được chuẩn bị từ giai đoạn trước để tránh phụ thuộc hoàn toàn vào tuần này.

---

**Kết luận:** Dự án hướng tới xây dựng một Backend thuyết minh tự động đa ngôn ngữ có tính ứng dụng, dễ quản lý và mở rộng, sử dụng mô hình bốn nhà thi đấu tại TP.HCM trong bối cảnh giải bóng chuyền quốc tế giả định. Phiên bản đầu tiên ưu tiên khả năng hoạt động ổn định, kiến trúc rõ ràng và đáp ứng yêu cầu kỹ thuật của đồ án Công nghệ phần mềm.