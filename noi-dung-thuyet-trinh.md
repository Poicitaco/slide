# Nội dung thuyết trình Steam Store

Bản này khớp với 16 slide trong `index.html`. Mỗi slide có lời trình bày, điểm cần nhấn và kiến thức phòng khi thầy hỏi.

## Slide 1: Slide 1 - Mở đầu - Đạt

### Lời trình bày

Em xin chào thầy và các bạn. Nhóm em xin trình bày đề tài phân tích và thiết kế hệ thống Steam Store. Trong bài này, nhóm không tiếp cận Steam Store như một website bán game đơn giản, mà xem đây là một hệ thống phần mềm hoàn chỉnh, có nhiều nhóm người dùng, nhiều nghiệp vụ liên kết và nhiều yêu cầu kỹ thuật quan trọng.

Điểm đặc biệt của Steam Store là sản phẩm được mua không phải hàng hóa vật lý, mà là quyền truy cập số. Vì vậy hệ thống phải xử lý chính xác từ khâu tìm kiếm game, thêm vào giỏ hàng, thanh toán, cấp license, đưa game vào thư viện, cho đến review và hoàn tiền.

Bài trình bày được chia theo vai trò của 5 thành viên. Đạt phụ trách mở đầu, tổng quan, kiến trúc và kết luận. Khoa phụ trách yêu cầu và use case. Dương phụ trách giao diện và hành trình người dùng. Khánh phụ trách các luồng nghiệp vụ bằng UML động. Đô phụ trách thiết kế lớp và dữ liệu.

Mục tiêu của nhóm là trình bày không chỉ đã vẽ những sơ đồ nào, mà còn giải thích vì sao nhóm chọn các sơ đồ đó, mỗi sơ đồ trả lời câu hỏi gì và liên hệ như thế nào với nghiệp vụ của Steam Store.

### Điểm cần nhấn trên slide
- Nhấn mạnh đề tài là phân tích và thiết kế, không phải xây website chạy thật.
- Giải thích khái niệm license ngay từ đầu để các phần payment, library, refund phía sau dễ hiểu.
- Nói rõ mỗi thành viên đều có phần UML riêng.

### Kiến thức phòng khi thầy hỏi
- **Vì sao chọn Steam Store?** Vì hệ thống có đủ actor, nghiệp vụ giao dịch, dữ liệu quyền sở hữu số, review, refund và yêu cầu bảo mật, phù hợp để áp dụng nhiều loại UML.
- **Có cần demo website thật không?** Không bắt buộc. Đây là báo cáo phân tích thiết kế, trọng tâm là mô hình nghiệp vụ và thiết kế hệ thống.

## Slide 2: Slide 2 - Lộ trình - Đạt

### Lời trình bày

Trước khi đi vào chi tiết, nhóm trình bày lộ trình của bài để thầy và các bạn dễ theo dõi. Phần đầu do Đạt trình bày, tập trung vào bức tranh tổng quan: Steam Store là hệ thống gì, phạm vi phân tích của nhóm đến đâu, nhóm đã hoàn thành những sản phẩm nào và tiến độ ra sao.

Tiếp theo, Khoa trình bày yêu cầu hệ thống và use case. Đây là phần nền tảng, vì mọi mô hình phía sau đều phải xuất phát từ yêu cầu và actor. Sau đó, Dương trình bày các giao diện chính và hành trình người dùng, giúp người nghe hình dung hệ thống dưới góc nhìn thực tế.

Phần tiếp theo do Khánh trình bày, tập trung vào UML nghiệp vụ như sequence, activity và state diagram. Những sơ đồ này giúp làm rõ thứ tự xử lý, nhánh điều kiện và trạng thái của các nghiệp vụ quan trọng. Cuối cùng, Đô trình bày thiết kế dữ liệu và lớp, còn Đạt kết luận bằng các điểm chính và hướng phát triển.

Cách chia này đi theo đúng quy trình phân tích thiết kế: từ yêu cầu, đến giao diện và hành vi nghiệp vụ, sau đó mới đến kiến trúc, lớp và dữ liệu.

### Điểm cần nhấn trên slide
- Khi nói slide này, chỉ vào từng dòng trong bảng để lớp biết ai sẽ nói phần nào.
- Làm rõ Đạt nhận phần kiến trúc/deployment để giảm tải cho Đô.

### Kiến thức phòng khi thầy hỏi
- **Vì sao không để một người nói hết UML?** Vì mỗi UML gắn với một nhóm chức năng khác nhau. Chia theo chức năng giúp từng thành viên hiểu phần mình phụ trách.
- **Thứ tự trình bày có quan trọng không?** Có. Nếu nói dữ liệu trước khi nói yêu cầu/use case thì người nghe khó hiểu vì chưa biết dữ liệu phục vụ nghiệp vụ nào.

## Slide 3: Slide 3 - Tổng quan đề tài - Đạt

### Lời trình bày

Nhóm chọn Steam Store vì đây là một ví dụ phù hợp để phân tích trong môn kỹ thuật phần mềm. Hệ thống có nhiều actor khác nhau, gồm khách vãng lai, người dùng Steam, Steam Client, nhà phát hành, quản trị viên và cổng thanh toán.

Ở mức nghiệp vụ, Steam Store có chuỗi xử lý rất rõ: người dùng tìm game, xem chi tiết, thêm vào giỏ hàng, thanh toán, sau đó hệ thống cấp license để game xuất hiện trong thư viện. Từ thư viện, người dùng có thể tải game, viết review hoặc gửi yêu cầu hoàn tiền.

Nhóm bắt đầu bằng sơ đồ kiến trúc tổng quan vì đây là cách nhanh nhất để đặt bối cảnh cho toàn bộ bài. Sơ đồ cho thấy hệ thống không chỉ có giao diện web, mà còn có Steam Client, API Gateway, các service nghiệp vụ, cơ sở dữ liệu, search index, CDN và cổng thanh toán.

Khi có bức tranh lớn này, các sơ đồ chi tiết như use case, sequence, ERD và deployment sẽ dễ hiểu hơn. Mỗi sơ đồ phía sau đều có vị trí trong kiến trúc tổng thể này.

### Điểm cần nhấn trên slide
- Click vào ảnh architecture nếu cần phóng to.
- Chỉ vào API Gateway và các service để nói hệ thống được chia theo miền nghiệp vụ.

### Kiến thức phòng khi thầy hỏi
- **API Gateway là gì?** Là cửa vào chung cho client, nhận request rồi định tuyến đến service phù hợp; có thể xử lý xác thực, logging, rate limit.
- **Vì sao có Steam Client riêng?** Vì tải/cập nhật game không chỉ diễn ra trên web mà qua ứng dụng client, dựa trên license trong thư viện.

## Slide 4: Slide 4 - Khối lượng công việc - Đạt

### Lời trình bày

Về khối lượng công việc, nhóm đã hoàn thành ba nhóm sản phẩm chính. Nhóm thứ nhất là phân tích yêu cầu, bao gồm mô tả bài toán, bảng thuật ngữ, yêu cầu chức năng, yêu cầu phi chức năng và phân quyền theo vai trò.

Nhóm thứ hai là mô hình hóa nghiệp vụ bằng UML. Cụ thể, nhóm có use case cho người dùng và quản trị, sequence diagram cho các luồng quan trọng, activity diagram cho mua game và hoàn tiền, state diagram cho vòng đời order và refund, cùng BCE để liên kết giao diện, xử lý nghiệp vụ và dữ liệu.

Nhóm thứ ba là thiết kế hệ thống, gồm kiến trúc, deployment, class design, ERD và danh sách bảng dữ liệu. Cách chia này giúp báo cáo không chỉ dừng ở việc mô tả chức năng, mà còn đi đến cấu trúc triển khai.

Điểm cần nhấn mạnh là các sản phẩm không tách rời. Yêu cầu dẫn đến use case. Use case dẫn đến sequence và activity. Class và ERD được xây dựa trên các thực thể xuất hiện trong nghiệp vụ.

### Điểm cần nhấn trên slide
- Nói rõ đây là phần tổng hợp công việc đã đạt được.
- Bảng dưới cho thấy mảng nào gắn với thành viên nào.

### Kiến thức phòng khi thầy hỏi
- **Báo cáo đã đủ UML chưa?** Đủ các nhóm chính: use case, sequence, activity, state, BCE/class, ERD, deployment. Mỗi loại phục vụ một mục đích khác nhau.
- **Tại sao cần ma trận truy vết?** Để chứng minh yêu cầu không bị bỏ sót và mỗi mô hình đều xuất phát từ yêu cầu cụ thể.

## Slide 5: Slide 5 - Phân công chi tiết - Đạt

### Lời trình bày

Slide này thể hiện bảng phân chia công việc chi tiết và tiến độ hoàn thành. Điểm nhóm muốn nhấn mạnh là mỗi thành viên không chỉ phụ trách một đoạn nội dung, mà còn phải phân tích UML gắn trực tiếp với chức năng của mình.

Đạt là trưởng nhóm, phụ trách tổng quan hệ thống, phạm vi, tiến độ và phần kiến trúc triển khai. Vì vậy UML chính của Đạt là architecture diagram và deployment diagram. Khoa phụ trách yêu cầu, actor và phân quyền, nên UML chính là use case user, use case admin và ma trận truy vết từ yêu cầu sang mô hình.

Dương phụ trách giao diện và hành trình người dùng, nên phần UML liên quan là activity purchase và boundary trong mô hình BCE. Khánh phụ trách các luồng nghiệp vụ như mua game, đăng nhập, review và hoàn tiền, nên tập trung vào sequence, activity và state diagram.

Đô phụ trách thiết kế lớp và dữ liệu, nên tập trung vào BCE, class design và ERD. Tất cả các đầu việc đều đã hoàn thành ở mức 100 phần trăm, bao gồm báo cáo, UML, slide và nội dung thuyết trình.

### Điểm cần nhấn trên slide
- Nếu thầy hỏi ai làm gì, đọc đúng bảng này.
- Nói rõ Đô đã được giảm phần kiến trúc/deployment; Đạt nhận phần đó.

### Kiến thức phòng khi thầy hỏi
- **Dương có phân tích UML không?** Có. Dương liên hệ giao diện với activity purchase và Boundary trong BCE.
- **Đô có bị nặng không?** Không. Phần kiến trúc/deployment đã chuyển sang Đạt; Đô tập trung vào BCE, Class Design và ERD.

## Slide 6: Slide 6 - Yêu cầu hệ thống - Khoa

### Lời trình bày

Phần yêu cầu hệ thống được chia thành ba nhóm. Nhóm thứ nhất là yêu cầu chức năng dành cho người dùng, gồm đăng ký tài khoản, đăng nhập, xác thực Steam Guard, tìm kiếm game, quản lý wishlist, giỏ hàng, checkout, thư viện, review và hoàn tiền.

Nhóm thứ hai là yêu cầu dành cho phía quản trị và nhà phát hành. Publisher cần quản lý thông tin game, giá bán, media, DLC và khuyến mãi. Admin cần kiểm duyệt nội dung, hỗ trợ tài khoản và theo dõi các giao dịch bất thường.

Nhóm thứ ba là yêu cầu phi chức năng. Với Steam Store, các yếu tố quan trọng gồm hiệu năng tìm kiếm, khả năng mở rộng trong các đợt sale lớn, bảo mật tài khoản, tính sẵn sàng của checkout và toàn vẹn dữ liệu giữa thanh toán với cấp license.

Nhóm chọn cách phân tích yêu cầu theo vai trò vì mỗi actor có quyền khác nhau. Cách này giúp tránh nhầm lẫn giữa khách vãng lai, người dùng đã đăng nhập, publisher, admin và hệ thống ngoài.

### Điểm cần nhấn trên slide
- Giải thích khác nhau giữa yêu cầu chức năng và phi chức năng.
- Nhấn mạnh bảo mật và toàn vẹn dữ liệu vì đây là điểm dễ bị hỏi.

### Kiến thức phòng khi thầy hỏi
- **FR và NFR khác gì?** FR là chức năng hệ thống phải làm; NFR là chất lượng hệ thống phải đạt, như bảo mật, hiệu năng, mở rộng.
- **Yêu cầu quan trọng nhất là gì?** Thanh toán thành công phải cấp đúng license; thanh toán thất bại không được cấp game.

## Slide 7: Slide 7 - Actor và Use Case - Khoa

### Lời trình bày

Use case diagram giúp xác định phạm vi chức năng của hệ thống. Ở phía người dùng, nhóm chia actor thành khách vãng lai, người dùng Steam và Steam Client. Khách vãng lai có thể tìm kiếm, lọc game, xem chi tiết và đăng ký tài khoản, nhưng chưa được mua game hoặc viết review.

Người dùng Steam là actor chính. Sau khi đăng nhập, người dùng có thể quản lý wishlist, thêm game vào giỏ hàng, thanh toán, quản lý thư viện, viết review và yêu cầu hoàn tiền. Steam Client được tách thành actor riêng vì việc tải, cài đặt và cập nhật game thường diễn ra qua ứng dụng client, dựa trên license trong thư viện.

Ở phía quản trị, publisher quản lý trang game, media, DLC, giá bán và khuyến mãi. Admin phụ trách kiểm duyệt nội dung, hỗ trợ tài khoản và theo dõi giao dịch. Nhóm chọn use case ở bước này vì use case là cầu nối giữa yêu cầu và các sơ đồ động phía sau.

Khi nhìn vào use case, có thể trả lời hai câu hỏi: ai dùng hệ thống và họ dùng chức năng nào. Sau khi trả lời được hai câu hỏi đó, nhóm mới đi tiếp sang sequence, activity và thiết kế dữ liệu.

### Điểm cần nhấn trên slide
- Click phóng to use case khi cần giải thích.
- Chỉ rõ khách vãng lai khác người dùng đã đăng nhập ở quyền mua/review/refund.

### Kiến thức phòng khi thầy hỏi
- **Include và extend là gì?** Include là chức năng luôn được dùng kèm; extend là hành vi mở rộng chỉ xảy ra trong điều kiện nhất định.
- **Vì sao Steam Client là actor?** Vì client tương tác với hệ thống để tải/cập nhật game dựa trên license, không phải chỉ là giao diện web.

## Slide 8: Slide 8 - Giao diện chính - Dương

### Lời trình bày

Phần giao diện được trình bày theo các màn hình chính mà người dùng hoặc quản trị viên sẽ nhìn thấy. Với người dùng, hành trình bắt đầu từ trang chủ Store, nơi có game nổi bật, game đang sale, danh mục và thanh tìm kiếm.

Sau đó người dùng chuyển sang trang tìm kiếm hoặc lọc game theo tag, giá, nền tảng, đánh giá và ngày phát hành. Trang chi tiết game cung cấp trailer, hình ảnh, mô tả, giá, DLC, review và cấu hình yêu cầu.

Nếu quan tâm, người dùng có thể thêm game vào wishlist hoặc giỏ hàng. Khi mua, người dùng đi qua checkout, chọn phương thức thanh toán và xác nhận đơn hàng. Sau khi thanh toán thành công, game xuất hiện trong thư viện.

Ngoài ra còn có màn hình review, refund, Publisher Dashboard và Admin Dashboard. Về mặt UML, các màn hình này tương ứng với lớp Boundary trong mô hình BCE. Boundary là nơi tiếp nhận tương tác từ người dùng trước khi chuyển sang lớp Control xử lý nghiệp vụ.

### Điểm cần nhấn trên slide
- Không cần mở web Steam thật. Chỉ cần trình bày theo các màn hình trên slide.
- Nhấn mạnh giao diện là Boundary, không phải phần xử lý nghiệp vụ chính.

### Kiến thức phòng khi thầy hỏi
- **Có cần demo web thật không?** Không. Phần này mô tả giao diện cần có trong thiết kế hệ thống, không phải demo sản phẩm chạy thật.
- **Boundary trong BCE là gì?** Là lớp giao tiếp với người dùng hoặc hệ thống ngoài, ví dụ màn hình login, cart, checkout.

## Slide 9: Slide 9 - Hành trình người dùng - Dương

### Lời trình bày

Hành trình mua game giúp nối phần giao diện với nghiệp vụ phía sau. Bước đầu tiên, người dùng vào trang chủ hoặc trang tìm kiếm để tìm game phù hợp. Sau đó người dùng mở trang chi tiết để xem thông tin, giá, review và yêu cầu cấu hình.

Nếu muốn mua, người dùng thêm game vào giỏ hàng và chuyển sang checkout. Ở bước checkout, hệ thống cần hiển thị danh sách game, giá tại thời điểm mua và tổng tiền. Khi thanh toán thành công, hệ thống cấp license và game xuất hiện trong thư viện người dùng.

Hành trình này liên hệ trực tiếp với ba nhóm mô hình. Use case cho biết người dùng được thực hiện chức năng nào. Activity diagram mô tả quy trình và các nhánh thành công hoặc thất bại. ERD cho thấy dữ liệu được tạo ra theo thứ tự: cart item, order, payment, license và library.

Vì vậy phần giao diện không tách rời phần kỹ thuật, mà là điểm bắt đầu của toàn bộ chuỗi nghiệp vụ.

### Điểm cần nhấn trên slide
- Nói theo 6 bước trên slide, không lan sang phần kỹ thuật quá sâu.
- Chốt bằng câu: giao diện dẫn sang activity và dữ liệu.

### Kiến thức phòng khi thầy hỏi
- **Vì sao phải lưu snapshot giá?** Để lịch sử đơn hàng không bị thay đổi nếu giá game thay đổi sau khi người dùng mua.
- **Hành trình này liên quan ERD thế nào?** Mỗi bước tạo hoặc dùng dữ liệu: cart item, order, payment, license, library.

## Slide 10: Slide 10 - UML nghiệp vụ - Khánh

### Lời trình bày

Ở phần UML nghiệp vụ, nhóm dùng nhiều loại sơ đồ vì một nghiệp vụ phức tạp không thể mô tả đầy đủ bằng một sơ đồ duy nhất. Use case trả lời câu hỏi ai sử dụng hệ thống và sử dụng chức năng nào. Sequence diagram trả lời câu hỏi các thành phần gọi nhau theo thứ tự nào.

Activity diagram tập trung vào quy trình và các nhánh điều kiện. Ví dụ khi mua game, thanh toán có thể thành công hoặc thất bại. Khi hoàn tiền, yêu cầu có thể bị từ chối, được duyệt tự động hoặc chuyển sang admin xem xét.

State diagram mô tả vòng đời trạng thái của các đối tượng như order và refund. Nhóm dùng state diagram cho hai đối tượng này vì chúng có nhiều trạng thái trung gian và có thể đi qua nhánh lỗi.

Nhóm chọn cách kết hợp nhiều UML để nhìn nghiệp vụ từ nhiều góc. Use case giúp xác định phạm vi. Sequence giúp kiểm soát thứ tự xử lý. Activity giúp thấy rẽ nhánh. State giúp tránh bỏ sót trạng thái.

### Điểm cần nhấn trên slide
- Không cần giải thích tất cả UML quá dài; tập trung từng loại trả lời câu hỏi gì.
- Nhấn mạnh lý do dùng nhiều UML là để tránh bỏ sót nghiệp vụ.

### Kiến thức phòng khi thầy hỏi
- **Sequence khác activity thế nào?** Sequence nhấn mạnh thứ tự gọi giữa đối tượng/service; activity nhấn mạnh luồng công việc và rẽ nhánh.
- **State diagram dùng khi nào?** Khi đối tượng có vòng đời trạng thái rõ, ví dụ order hoặc refund.

## Slide 11: Slide 11 - Quy trình mua game - Khánh

### Lời trình bày

Quy trình mua game là luồng nghiệp vụ tiêu biểu nhất của Steam Store. Người dùng bắt đầu bằng việc checkout từ giỏ hàng. Cart Service trả danh sách game trong giỏ và giá tại thời điểm mua.

Việc lưu snapshot giá rất quan trọng vì giá game có thể thay đổi do sale hoặc theo khu vực. Nếu không lưu snapshot, lịch sử đơn hàng có thể bị sai khi giá game thay đổi sau khi người dùng đã mua.

Sau đó Order Service tạo đơn hàng tạm và gửi yêu cầu sang Payment Gateway. Nếu thanh toán thất bại, hệ thống không được cấp game mà chỉ thông báo lỗi để người dùng thử lại. Nếu thanh toán thành công, Order Service gọi Library Service để tạo license cho từng game, rồi game xuất hiện trong thư viện.

Điểm cốt lõi của luồng này là toàn vẹn giao dịch. Hệ thống phải tránh hai lỗi nghiêm trọng: người dùng bị trừ tiền nhưng không nhận game, hoặc chưa thanh toán mà vẫn có game trong thư viện. Vì vậy nhóm dùng sequence purchase, activity purchase và state order để kiểm soát thứ tự xử lý và trạng thái đơn hàng.

### Điểm cần nhấn trên slide
- Click phóng to sequence purchase nếu cần chỉ rõ Order Service, Payment Gateway, Library Service.
- Nhấn mạnh quy tắc: chưa thanh toán thành công thì chưa cấp license.

### Kiến thức phòng khi thầy hỏi
- **Idempotency là gì?** Là cơ chế để một yêu cầu lặp lại nhiều lần vẫn chỉ tạo một kết quả, tránh thanh toán/cấp license trùng.
- **Vì sao không cấp license trước rồi thanh toán sau?** Vì sẽ tạo rủi ro người dùng có game khi giao dịch chưa thành công.

## Slide 12: Slide 12 - Đăng nhập, review, refund - Khánh

### Lời trình bày

Ngoài mua game, nhóm phân tích thêm các luồng đăng nhập, review và hoàn tiền vì đây là các nghiệp vụ ảnh hưởng trực tiếp đến bảo mật, chất lượng nội dung và quyền sở hữu số.

Luồng đăng nhập có Steam Guard thể hiện yêu cầu bảo mật tài khoản. Account Service kiểm tra thông tin đăng nhập, sau đó Steam Guard xác thực bổ sung nếu thiết bị hoặc vị trí đăng nhập cần kiểm tra.

Luồng review thể hiện việc kiểm soát đánh giá: người dùng chỉ được review khi có license hợp lệ trong thư viện, giúp hạn chế review giả. Đây là lý do Review Service phải kiểm tra với Library Service trước khi lưu review.

Luồng hoàn tiền phức tạp hơn vì có nhiều trạng thái. Refund có thể bị từ chối, được duyệt tự động hoặc chuyển sang admin duyệt thủ công. Nếu hoàn tiền được chấp nhận, hệ thống phải gọi cổng thanh toán và thu hồi license. Vì vậy nhóm dùng cả activity refund và state refund để mô tả đầy đủ quy trình và vòng đời trạng thái.

### Điểm cần nhấn trên slide
- Click phóng to state refund hoặc activity refund để nói về các trạng thái.
- Nhấn mạnh refund phải đi kèm thu hồi license.

### Kiến thức phòng khi thầy hỏi
- **Vì sao review phải kiểm tra library?** Để bảo đảm chỉ người có quyền sở hữu/truy cập game mới được review.
- **Refund thất bại thì sao?** State refund có nhánh Failed và có thể quay lại ManualReview để xử lý lại.

## Slide 13: Slide 13 - Kiến trúc hệ thống - Đạt

### Lời trình bày

Phần kiến trúc hệ thống do Đạt trình bày để giảm tải cho Đô và để trưởng nhóm kết nối phần nghiệp vụ với phần kỹ thuật. Kiến trúc được tách theo miền nghiệp vụ. Phía ngoài là Web Frontend và Steam Client. Hai thành phần này đi qua API Gateway thay vì gọi trực tiếp từng service.

API Gateway đóng vai trò cửa vào chung, giúp định tuyến request, hỗ trợ xác thực và che bớt độ phức tạp của backend. Các service phía sau gồm Account, Catalog, Cart, Order, Library, Review, Publisher và Notification. Mỗi service phụ trách một miền nghiệp vụ riêng.

Lý do chọn hướng tách service là vì từng miền có yêu cầu khác nhau. Catalog cần tìm kiếm nhanh và cache tốt. Order và Payment cần độ chính xác cao. Library cần quản lý license ổn định. Review cần kiểm tra quyền sở hữu và kiểm duyệt nội dung.

Deployment diagram cho thấy hệ thống còn cần database, search index, CDN, event queue và cổng thanh toán để vận hành ở quy mô lớn. Đây là thiết kế phù hợp với hệ thống có nhiều nội dung media, nhiều giao dịch và nhiều người dùng đồng thời.

### Điểm cần nhấn trên slide
- Click phóng to deployment để nhìn rõ Browser, Steam Client, API Gateway, DB, Search Index, Queue, Payment Gateway.
- Nói rõ tách service là lựa chọn thiết kế, không nhất thiết nhóm phải xây microservice thật.

### Kiến thức phòng khi thầy hỏi
- **Microservice có bắt buộc không?** Không. Đây là mô hình thiết kế phù hợp với hệ thống lớn; triển khai thật có thể bắt đầu bằng modular monolith rồi tách service sau.
- **CDN dùng để làm gì?** Phục vụ static assets, media, ảnh/trailer game nhanh hơn và giảm tải backend.

## Slide 14: Slide 14 - ERD - Đô

### Lời trình bày

Phần dữ liệu tập trung vào ERD. ERD thể hiện các thực thể chính và quan hệ giữa chúng. User có thể có nhiều order, review, wishlist và một library. Game thuộc publisher và có thể xuất hiện trong wishlist item, cart item, review và license.

Điểm quan trọng nhất là quan hệ giữa Library, License và Game. Library là thư viện của người dùng, còn License là quyền truy cập cụ thể đến một game. Người dùng không sở hữu game chỉ vì có order. Người dùng chỉ có quyền truy cập khi payment thành công và license được cấp vào library.

Thiết kế này cũng hỗ trợ hoàn tiền. RefundRequest gắn với order và user. Nếu hoàn tiền được duyệt, hệ thống cập nhật trạng thái refund, cập nhật order và thu hồi license tương ứng.

Nhờ đó dữ liệu có thể truy vết từ người dùng, đơn hàng, thanh toán đến quyền truy cập game. Đây là điểm quan trọng trong hệ thống bán sản phẩm số, vì quyền truy cập phải đi đúng với trạng thái thanh toán.

### Điểm cần nhấn trên slide
- Click phóng to ERD để chỉ User, Order, Payment, Library, License, Game, RefundRequest.
- Nói rõ license là thực thể trung tâm giữa payment và library.

### Kiến thức phòng khi thầy hỏi
- **Vì sao cần bảng licenses?** Vì order chỉ ghi nhận giao dịch; license mới biểu diễn quyền truy cập game trong thư viện.
- **Refund liên quan ERD thế nào?** RefundRequest gắn với order/user; khi duyệt phải cập nhật refund/order và thu hồi license.

## Slide 15: Slide 15 - BCE và Class Design - Đô

### Lời trình bày

BCE và class design giúp chuyển từ phân tích nghiệp vụ sang thiết kế lớp. Trong BCE, Boundary là lớp giao tiếp với người dùng, ví dụ StorePageBoundary, CartBoundary và LoginBoundary. Boundary không xử lý nghiệp vụ sâu mà chuyển yêu cầu sang lớp Control.

Control là lớp điều phối nghiệp vụ. CatalogController xử lý tìm kiếm và lọc game. OrderController xử lý tạo đơn hàng và xác nhận thanh toán. AccountController xử lý đăng nhập và Steam Guard. RefundController xử lý yêu cầu hoàn tiền.

Entity là các đối tượng dữ liệu cốt lõi như User, Game, Cart, Order, Payment, License, Review và RefundRequest. Class design làm rõ thuộc tính và phương thức của các lớp này.

Nhóm chọn BCE vì nó giúp tổ chức hệ thống rõ ràng: giao diện nhận yêu cầu, control xử lý nghiệp vụ, entity lưu dữ liệu. Cách này cũng giúp việc chuyển sang thiết kế code sau này dễ hơn, vì mỗi lớp có trách nhiệm rõ ràng.

### Điểm cần nhấn trên slide
- Click phóng to BCE hoặc class design nếu cần.
- Chốt bằng mô hình 3 lớp: Boundary - Control - Entity.

### Kiến thức phòng khi thầy hỏi
- **BCE khác MVC không?** BCE là mô hình phân tích hướng đối tượng; Boundary gần View/API, Control gần Controller/Service, Entity gần Model/Domain.
- **Vì sao không để Boundary xử lý nghiệp vụ?** Để tránh giao diện phụ thuộc nghiệp vụ sâu; nghiệp vụ nên nằm ở Control/Service để dễ bảo trì.

## Slide 16: Slide 16 - Kết luận - Đạt

### Lời trình bày

Để kết luận, nhóm đã hoàn thành bộ mô hình phân tích và thiết kế cho Steam Store. Kết quả gồm mô tả bài toán, yêu cầu chức năng, yêu cầu phi chức năng, phân quyền actor, giao diện chính, use case diagram, sequence diagram, activity diagram, state diagram, BCE, class design, ERD và deployment diagram.

Điểm quan trọng là các mô hình liên kết với nhau theo một chuỗi logic. Yêu cầu dẫn đến use case. Use case dẫn đến sequence và activity. State diagram kiểm soát vòng đời order và refund. BCE và class diagram mô tả tổ chức lớp. ERD mô tả dữ liệu. Deployment diagram mô tả cách triển khai hệ thống.

Thông điệp chính của nhóm là: với Steam Store, thiết kế đúng không chỉ là vẽ đủ sơ đồ, mà là bảo đảm thanh toán đúng, cấp license đúng, hoàn tiền đúng và dữ liệu truy vết được.

Hướng phát triển tiếp theo là xây dựng prototype giao diện chi tiết hơn, đặc tả API, bổ sung test case cho thanh toán và hoàn tiền, đồng thời mô phỏng database. Nhóm em xin cảm ơn thầy và các bạn đã lắng nghe, và sẵn sàng nhận câu hỏi hoặc góp ý.

### Điểm cần nhấn trên slide
- Kết luận ngắn, không mở thêm ý mới quá nhiều.
- Nếu còn thời gian, nhắc lại license là điểm cốt lõi của hệ thống.

### Kiến thức phòng khi thầy hỏi
- **Điểm mạnh nhất của báo cáo là gì?** Các UML liên kết được với nhau, không vẽ rời rạc; nghiệp vụ thanh toán-license-refund được kiểm soát rõ.
- **Hướng phát triển thực tế là gì?** Prototype UI, API spec, test case, mô phỏng database và có thể triển khai bản demo nhỏ.
