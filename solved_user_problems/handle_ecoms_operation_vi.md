# Chia Sẻ Kinh Nghiệm: Nguyễn Hoàng Quân

**Vai trò**: Kỹ sư phần mềm  
**Số năm kinh nghiệm**: 5+ năm  
**Lĩnh vực liên quan**: Thương mại điện tử, Logistics, Tài chính

## Mục lục
1. [Giới thiệu](#giới-thiệu)
2. [Bối cảnh và nền tảng](#bối-cảnh-và-nền-tảng)
3. [Vấn đề gặp phải](#vấn-đề-gặp-phải)
4. [Giải pháp và cách tiếp cận](#giải-pháp-và-cách-tiếp-cận)
5. [Kết quả và tác động](#kết-quả-và-tác-động)
6. [Bài học kinh nghiệm](#bài-học-kinh-nghiệm)
7. [Kết luận](#kết-luận)

## Giới thiệu
Trong tài liệu này, tôi sẽ chia sẻ kinh nghiệm làm việc trên một giải pháp tự động hóa cho một công ty chăm sóc cá nhân hàng đầu tại Việt Nam, tập trung vào những thách thức trong việc đồng bộ hóa dữ liệu tồn kho và đơn hàng trên nhiều nền tảng thương mại điện tử và hệ thống ERP.

## Bối cảnh và nền tảng

**Tên dự án**: Tự động hóa hỗ trợ quản lý các nền tảng thương mại điện tử.
**Quy mô nhóm**: 1 người.
**Thời gian**: 1 tháng.

Tôi chịu trách nhiệm phát triển một giải pháp tự động hóa cho một công ty chăm sóc cá nhân hàng đầu tại Việt Nam để quản lý hoạt động trên năm trang web thương mại điện tử (sử dụng trang web của bên thứ ba) và đồng bộ hóa chúng với hệ thống ERP của khách hàng. Yêu cầu chính là đảm bảo giao tiếp liền mạch và đồng bộ hóa dữ liệu giữa các nền tảng thương mại điện tử và hệ thống ERP, đặc biệt là về quản lý tồn kho và xử lý đơn hàng.

Quy trình làm việc hàng ngày bao gồm:
* Nhiều SKU trên mỗi trang web: Mỗi SKU thuộc về hai kho hàng.
* Tải lên tồn kho hàng ngày: Vào 6 giờ sáng, khách hàng tải dữ liệu tồn kho vào thư mục FSTP được chia sẻ.
* Quy trình thủ công: Người phụ trách (PIC) phải tải xuống dữ liệu tồn kho, tổng hợp và nhập thủ công vào tất cả năm trang web thương mại điện tử để đảm bảo cập nhật tồn kho vào đầu ngày.
* Đối chiếu: Sau khi cập nhật tồn kho, PIC tạo báo cáo đối chiếu so sánh mức tồn kho trên trang web với tệp tồn kho đầu vào và gửi báo cáo cho Tổng Giám đốc của khách hàng.
* Báo cáo đơn hàng: Vào 12 giờ trưa, PIC tạo thủ công báo cáo đơn hàng dưới định dạng .xlsx cho mỗi trang web thương mại điện tử và gửi qua email. Hệ thống ERP của khách hàng xử lý các báo cáo này để cập nhật trạng thái đơn hàng.

## Vấn đề gặp phải

Những thách thức chính gặp phải trong quy trình thủ công này là:

* Lỗi con người: PIC đôi khi bỏ sót các nhiệm vụ quan trọng như tải lên dữ liệu tồn kho, gửi báo cáo đối chiếu hoặc tạo báo cáo đơn hàng. Điều này dẫn đến sự khác biệt về mức tồn kho hoặc bỏ sót đơn hàng, ảnh hưởng trực tiếp đến hoạt động kinh doanh.

* Khả năng mở rộng: Khi khách hàng cân nhắc mở rộng hoạt động (thêm nhiều trang web hoặc kho hàng), quy trình thủ công ngày càng tốn thời gian và dễ xảy ra lỗi. Việc mở rộng quy mô bằng phương pháp hiện tại sẽ làm tăng đáng kể khối lượng công việc và đòi hỏi nguồn lực đáng kể để duy trì độ chính xác.

=> Vì vậy, giá trị tôi cần mang lại là:

* Giảm lỗi con người
* Tăng hiệu quả hoạt động: giải phóng PIC khỏi công việc hàng ngày, cho họ thời gian để làm những việc thú vị khác.
* Cải thiện khả năng mở rộng: Khách hàng sẽ có cái nhìn sâu sắc hơn để mở rộng kinh doanh, không lo lắng về nền tảng hoặc kho hàng.

## Giải pháp và cách tiếp cận

Để tập trung và quản lý dữ liệu, tôi đã tạo một nền tảng nội bộ thu thập tất cả thông tin sản phẩm và đơn hàng từ các nền tảng thương mại điện tử.
Nền tảng này sử dụng các API tương ứng để kéo dữ liệu, đảm bảo rằng chúng tôi có cái nhìn nhất quán, cập nhật về mức tồn kho sản phẩm và trạng thái đơn hàng trên tất cả các trang web.
Nền tảng này đóng vai trò là nguồn thông tin đáng tin cậy duy nhất, cho phép chúng tôi không chỉ theo dõi thông tin tồn kho và đơn hàng một cách đáng tin cậy hơn mà còn tự động hóa các quy trình tiếp theo như đối chiếu và báo cáo.

![pulling-ecom-information](https://github.com/quan-nh2/experience-sharing/blob/main/public/images/ecoms_auto_flow.png)

1. Một công việc nền để tự động hóa cập nhật tồn kho:
* Tạo một công việc nền tự động tải xuống dữ liệu tồn kho từ thư mục FSTP mỗi ngày vào 6 giờ sáng. Công việc nền sẽ tổng hợp thông tin tồn kho và đẩy cập nhật đến tất cả 5 trang web thương mại điện tử thông qua các API tương ứng của họ.

2. Một công việc nền để tự động tạo báo cáo đối chiếu:
* Với tất cả dữ liệu được tập trung trên nền tảng nội bộ, tôi đã tự động hóa quy trình đối chiếu. Nền tảng so sánh dữ liệu tồn kho trên các trang web với các tệp tồn kho đầu vào, đảm bảo tính nhất quán. Báo cáo đối chiếu sau đó được tạo tự động bằng Google Sheets API và gửi đến Tổng Giám đốc của khách hàng qua email.

3. Một công việc nền để tạo báo cáo đơn hàng tự động và gửi email:
* Sử dụng dữ liệu đơn hàng tập trung của nền tảng nội bộ, tôi đã tự động hóa việc tạo báo cáo đơn hàng .xlsx cho mỗi trang web thương mại điện tử. Các báo cáo được tạo vào 12 giờ trưa mỗi ngày và tự động gửi email đến hệ thống ERP của khách hàng, đảm bảo xử lý đơn hàng kịp thời và chính xác mà không cần sự can thiệp của con người.

### Đánh đổi của giải pháp:
Thời gian phát triển ban đầu để xây dựng nền tảng nội bộ dài hơn so với việc chỉ tự động hóa các quy trình thủ công hiện có, nhưng nó cung cấp một giải pháp có thể mở rộng và tập trung giảm thiểu lỗi trong tương lai và cho phép mở rộng dễ dàng.

## Kết quả và tác động
Giải pháp tự động hóa mang lại một số lợi ích chính:
* Giảm 99% lỗi thủ công: Tự động hóa loại bỏ lỗi con người liên quan đến cập nhật tồn kho thủ công và báo cáo đơn hàng.
* Tăng hiệu quả: Các nhiệm vụ trước đây đòi hỏi nhiều giờ mỗi ngày được hoàn thành tự động trong vòng chưa đầy 30 phút.
* Khả năng mở rộng: Giải pháp được thiết kế để mở rộng dễ dàng, cho phép khách hàng thêm nhiều trang web và kho hàng mà không làm tăng đáng kể khối lượng công việc.
* Cải thiện độ chính xác: Báo cáo đối chiếu hàng ngày đảm bảo dữ liệu tồn kho trên tất cả các nền tảng luôn được cập nhật, giảm thiểu sự khác biệt.
Phản hồi của khách hàng rất tích cực, vì giải pháp cho phép doanh nghiệp hợp lý hóa hoạt động của họ, giải phóng nguồn lực cho các nhiệm vụ quan trọng khác.
* Khi hệ thống tự động đi vào hoạt động, khách hàng nhanh chóng nhận ra hiệu quả của nó và yêu cầu các tính năng bổ sung để nâng cao hơn nữa hoạt động của họ (và có một khoản thưởng nhỏ cho tôi :)).

## Bài học kinh nghiệm
* Tự động hóa là chìa khóa: Bằng cách tự động hóa các nhiệm vụ thủ công lặp đi lặp lại, chúng tôi đã cải thiện đáng kể hiệu quả và độ chính xác của các quy trình kinh doanh. Kinh nghiệm này củng cố tầm quan trọng của việc tìm đúng công cụ để hợp lý hóa hoạt động.
* Phức tạp trong tích hợp: Làm việc với nhiều nền tảng thương mại điện tử và API của họ đã đưa ra những thách thức về tính nhất quán của dữ liệu và giao tiếp giữa các hệ thống, đòi hỏi lập kế hoạch cẩn thận.
* Khả năng mở rộng: Thiết kế hệ thống với khả năng mở rộng trong tương lai là rất quan trọng, đặc biệt là đối với các doanh nghiệp đang phát triển. Xây dựng một kiến trúc linh hoạt ngay từ đầu đảm bảo giải pháp có thể đáp ứng sự phát triển trong tương lai.

## Kết luận

Dự án này là một trải nghiệm bổ ích trong việc tự động hóa quy trình làm việc phức tạp cho các doanh nghiệp thương mại điện tử. Giải pháp không chỉ giải quyết các điểm đau tức thời của lỗi thủ công và khả năng mở rộng mà còn đặt nền móng cho sự phát triển trong tương lai. Tôi mong muốn áp dụng các chiến lược tự động hóa tương tự trong các dự án tương lai để tối ưu hóa hoạt động kinh doanh.