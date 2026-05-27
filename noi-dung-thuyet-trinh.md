# Nội dung thuyết trình Steam Store

Bản này khớp với 16 slide trong `index.html`. Mỗi mục là nội dung có thể đọc khi thuyết trình.

## Slide 1

Em xin chào thầy và các bạn. Nhóm em xin trình bày đề tài phân tích và thiết kế hệ thống Steam Store. Trong bài này, nhóm không tiếp cận Steam Store như một website bán game đơn giản, mà xem đây là một hệ thống phần mềm hoàn chỉnh, có nhiều nhóm người dùng, nhiều nghiệp vụ liên kết và nhiều yêu cầu kỹ thuật quan trọng.

Điểm đặc biệt của Steam Store là sản phẩm được mua không phải hàng hóa vật lý, mà là quyền truy cập số. Vì vậy hệ thống phải xử lý chính xác từ khâu tìm kiếm game, thêm vào giỏ hàng, thanh toán, cấp license, đưa game vào thư viện, cho đến review và hoàn tiền.

Bài trình bày được chia theo vai trò của 5 thành viên. Đạt phụ trách mở đầu, tổng quan, kiến trúc và kết luận. Khoa phụ trách yêu cầu và use case. Dương phụ trách giao diện và hành trình người dùng. Khánh phụ trách các luồng nghiệp vụ bằng UML động. Đô phụ trách thiết kế lớp và dữ liệu. Mục tiêu của nhóm là trình bày không chỉ “đã vẽ sơ đồ gì”, mà còn giải thích vì sao chọn cách phân tích đó.

## Slide 2

Trước khi đi vào chi tiết, nhóm xin trình bày lộ trình của bài. Phần đầu do Đạt trình bày, tập trung vào bức tranh tổng quan: Steam Store là hệ thống gì, phạm vi phân tích của nhóm đến đâu, nhóm đã hoàn thành những sản phẩm nào và tiến độ ra sao.

Tiếp theo, Khoa trình bày yêu cầu hệ thống và use case. Đây là phần nền tảng, vì mọi mô hình phía sau đều phải xuất phát từ yêu cầu và actor. Sau đó, Dương trình bày các giao diện chính và hành trình người dùng, giúp người nghe hình dung hệ thống hoạt động dưới góc nhìn thực tế.

Phần tiếp theo do Khánh trình bày, tập trung vào UML nghiệp vụ như sequence, activity và state diagram. Những sơ đồ này giúp làm rõ thứ tự xử lý, nhánh điều kiện và trạng thái của các nghiệp vụ quan trọng. Cuối cùng, Đô trình bày thiết kế dữ liệu và lớp, còn Đạt kết luận lại bằng các điểm chính và hướng phát triển. Cách chia này giúp bài nói đi từ yêu cầu, sang hành vi, rồi đến cấu trúc hệ thống.

## Slide 3

Nhóm chọn Steam Store vì đây là một ví dụ phù hợp để phân tích trong môn kỹ thuật phần mềm. Hệ thống có nhiều actor khác nhau, gồm khách vãng lai, người dùng Steam, Steam Client, nhà phát hành, quản trị viên và cổng thanh toán. Mỗi actor có mục tiêu sử dụng và quyền thao tác khác nhau.

Ở mức nghiệp vụ, Steam Store có chuỗi xử lý rất rõ: người dùng tìm game, xem chi tiết, thêm vào giỏ hàng, thanh toán, sau đó hệ thống cấp license để game xuất hiện trong thư viện. Từ thư viện, người dùng có thể tải game, viết review hoặc gửi yêu cầu hoàn tiền.

Nhóm bắt đầu bằng sơ đồ kiến trúc tổng quan vì đây là cách nhanh nhất để đặt bối cảnh cho toàn bộ bài. Sơ đồ cho thấy hệ thống không chỉ có giao diện web, mà còn có Steam Client, API Gateway, các service nghiệp vụ, cơ sở dữ liệu, search index, CDN và cổng thanh toán. Khi có bức tranh lớn này, các sơ đồ chi tiết như use case, sequence, ERD và deployment sẽ dễ hiểu hơn.

## Slide 4

Về khối lượng công việc, nhóm đã hoàn thành ba nhóm sản phẩm chính. Nhóm thứ nhất là phân tích yêu cầu, bao gồm mô tả bài toán, bảng thuật ngữ, yêu cầu chức năng, yêu cầu phi chức năng và phân quyền theo vai trò.

Nhóm thứ hai là mô hình hóa nghiệp vụ bằng UML. Cụ thể, nhóm có use case cho người dùng và quản trị, sequence diagram cho các luồng quan trọng, activity diagram cho mua game và hoàn tiền, state diagram cho vòng đời order và refund, cùng BCE để liên kết giao diện, xử lý nghiệp vụ và dữ liệu.

Nhóm thứ ba là thiết kế hệ thống, gồm kiến trúc, deployment, class design, ERD và danh sách bảng dữ liệu. Cách chia này giúp báo cáo không chỉ dừng ở việc mô tả chức năng, mà còn đi được đến cấu trúc triển khai. Các phần trong báo cáo cũng được phân công theo năng lực từng thành viên, nhưng vẫn bảo đảm mỗi bạn có phần UML liên quan đến chức năng mình phụ trách.

## Slide 5

Slide này thể hiện bảng phân chia công việc chi tiết và tiến độ hoàn thành. Điểm nhóm muốn nhấn mạnh là mỗi thành viên không chỉ phụ trách một đoạn nội dung, mà còn phải phân tích UML gắn trực tiếp với chức năng của mình.

Đạt là trưởng nhóm, phụ trách tổng quan hệ thống, phạm vi, tiến độ và phần kiến trúc triển khai. Vì vậy UML chính của Đạt là architecture diagram và deployment diagram. Khoa phụ trách yêu cầu, actor và phân quyền, nên UML chính là use case user, use case admin và ma trận truy vết từ yêu cầu sang mô hình.

Dương phụ trách giao diện và hành trình người dùng, nên phần UML liên quan là activity purchase và boundary trong mô hình BCE. Khánh phụ trách các luồng nghiệp vụ như mua game, đăng nhập, review và hoàn tiền, nên tập trung vào sequence, activity và state diagram. Đô phụ trách thiết kế lớp và dữ liệu, nên tập trung vào BCE, class design và ERD. Tất cả các đầu việc đều đã hoàn thành ở mức 100 phần trăm, bao gồm báo cáo, UML, slide và nội dung thuyết trình.

## Slide 6

Phần yêu cầu hệ thống được chia thành ba nhóm. Nhóm thứ nhất là yêu cầu chức năng dành cho người dùng, gồm đăng ký tài khoản, đăng nhập, xác thực Steam Guard, tìm kiếm game, quản lý wishlist, giỏ hàng, checkout, thư viện, review và hoàn tiền.

Nhóm thứ hai là yêu cầu dành cho phía quản trị và nhà phát hành. Publisher cần quản lý thông tin game, giá bán, media, DLC và khuyến mãi. Admin cần kiểm duyệt nội dung, hỗ trợ tài khoản và theo dõi các giao dịch bất thường.

Nhóm thứ ba là yêu cầu phi chức năng. Với Steam Store, các yếu tố quan trọng gồm hiệu năng tìm kiếm, khả năng mở rộng trong các đợt sale lớn, bảo mật tài khoản, tính sẵn sàng của checkout và toàn vẹn dữ liệu giữa thanh toán với cấp license. Nhóm chọn cách phân tích yêu cầu theo vai trò vì mỗi actor có quyền khác nhau. Cách này giúp tránh nhầm lẫn giữa khách vãng lai, người dùng đã đăng nhập, publisher, admin và hệ thống ngoài.

## Slide 7

Use case diagram giúp xác định phạm vi chức năng của hệ thống. Ở phía người dùng, nhóm chia actor thành khách vãng lai, người dùng Steam và Steam Client. Khách vãng lai có thể tìm kiếm, lọc game, xem chi tiết và đăng ký tài khoản, nhưng chưa được mua game hoặc viết review.

Người dùng Steam là actor chính. Sau khi đăng nhập, người dùng có thể quản lý wishlist, thêm game vào giỏ hàng, thanh toán, quản lý thư viện, viết review và yêu cầu hoàn tiền. Steam Client được tách thành actor riêng vì việc tải, cài đặt và cập nhật game thường diễn ra qua ứng dụng client, dựa trên license trong thư viện.

Ở phía quản trị, publisher quản lý trang game, media, DLC, giá bán và khuyến mãi. Admin phụ trách kiểm duyệt nội dung, hỗ trợ tài khoản và theo dõi giao dịch. Nhóm chọn use case ở bước này vì use case là cầu nối giữa yêu cầu và các sơ đồ động phía sau. Khi thầy nhìn use case, có thể thấy rõ hệ thống có những chức năng nào và ai là người sử dụng chức năng đó.

## Slide 8

Phần giao diện được trình bày theo các màn hình chính mà người dùng hoặc quản trị viên sẽ nhìn thấy. Với người dùng, hành trình bắt đầu từ trang chủ Store, nơi có game nổi bật, game đang sale, danh mục và thanh tìm kiếm. Sau đó người dùng chuyển sang trang tìm kiếm hoặc lọc game theo tag, giá, nền tảng, đánh giá và ngày phát hành.

Trang chi tiết game cung cấp trailer, hình ảnh, mô tả, giá, DLC, review và cấu hình yêu cầu. Nếu quan tâm, người dùng có thể thêm game vào wishlist hoặc giỏ hàng. Khi mua, người dùng đi qua checkout, chọn phương thức thanh toán và xác nhận đơn hàng. Sau khi thanh toán thành công, game xuất hiện trong thư viện.

Ngoài ra còn có màn hình review, refund, Publisher Dashboard và Admin Dashboard. Về mặt UML, các màn hình này tương ứng với lớp Boundary trong mô hình BCE. Boundary là nơi tiếp nhận tương tác từ người dùng trước khi chuyển sang lớp Control xử lý nghiệp vụ.

## Slide 9

Hành trình mua game giúp nối phần giao diện với nghiệp vụ phía sau. Bước đầu tiên, người dùng vào trang chủ hoặc trang tìm kiếm để tìm game phù hợp. Sau đó người dùng mở trang chi tiết để xem thông tin, giá, review và yêu cầu cấu hình.

Nếu muốn mua, người dùng thêm game vào giỏ hàng và chuyển sang checkout. Ở bước checkout, hệ thống cần hiển thị danh sách game, giá tại thời điểm mua và tổng tiền. Khi thanh toán thành công, hệ thống cấp license và game xuất hiện trong thư viện người dùng.

Hành trình này liên hệ trực tiếp với ba nhóm mô hình. Use case cho biết người dùng được thực hiện chức năng nào. Activity diagram mô tả quy trình và các nhánh thành công hoặc thất bại. ERD cho thấy dữ liệu được tạo ra theo thứ tự: cart item, order, payment, license và library. Vì vậy phần giao diện không tách rời phần kỹ thuật, mà là điểm bắt đầu của toàn bộ chuỗi nghiệp vụ.

## Slide 10

Ở phần UML nghiệp vụ, nhóm dùng nhiều loại sơ đồ vì một nghiệp vụ phức tạp không thể mô tả đầy đủ bằng một sơ đồ duy nhất. Use case trả lời câu hỏi ai sử dụng hệ thống và sử dụng chức năng nào. Sequence diagram trả lời câu hỏi các thành phần gọi nhau theo thứ tự nào.

Activity diagram tập trung vào quy trình và các nhánh điều kiện. Ví dụ khi mua game, thanh toán có thể thành công hoặc thất bại. Khi hoàn tiền, yêu cầu có thể bị từ chối, được duyệt tự động hoặc chuyển sang admin xem xét. State diagram mô tả vòng đời trạng thái của các đối tượng như order và refund.

Nhóm chọn cách kết hợp nhiều UML để nhìn nghiệp vụ từ nhiều góc. Use case giúp xác định phạm vi. Sequence giúp kiểm soát thứ tự xử lý. Activity giúp thấy rẽ nhánh. State giúp tránh bỏ sót trạng thái. Đây là cách phân tích phù hợp với các nghiệp vụ nhạy cảm như thanh toán và hoàn tiền.

## Slide 11

Quy trình mua game là luồng nghiệp vụ tiêu biểu nhất của Steam Store. Người dùng bắt đầu bằng việc checkout từ giỏ hàng. Cart Service trả danh sách game trong giỏ và giá tại thời điểm mua. Việc lưu snapshot giá rất quan trọng vì giá game có thể thay đổi do sale hoặc theo khu vực.

Sau đó Order Service tạo đơn hàng tạm và gửi yêu cầu sang Payment Gateway. Nếu thanh toán thất bại, hệ thống không được cấp game mà chỉ thông báo lỗi để người dùng thử lại. Nếu thanh toán thành công, Order Service gọi Library Service để tạo license cho từng game, rồi game xuất hiện trong thư viện.

Điểm cốt lõi của luồng này là toàn vẹn giao dịch. Hệ thống phải tránh hai lỗi nghiêm trọng: người dùng bị trừ tiền nhưng không nhận game, hoặc chưa thanh toán mà vẫn có game trong thư viện. Vì vậy nhóm dùng sequence purchase để mô tả thứ tự gọi service, activity purchase để mô tả nhánh thành công/thất bại và state order để kiểm soát trạng thái đơn hàng.

## Slide 12

Ngoài mua game, nhóm phân tích thêm các luồng đăng nhập, review và hoàn tiền vì đây là các nghiệp vụ ảnh hưởng trực tiếp đến bảo mật, chất lượng nội dung và quyền sở hữu số.

Luồng đăng nhập có Steam Guard thể hiện yêu cầu bảo mật tài khoản. Account Service kiểm tra thông tin đăng nhập, sau đó Steam Guard xác thực bổ sung nếu thiết bị hoặc vị trí đăng nhập cần kiểm tra. Luồng review thể hiện việc kiểm soát đánh giá: người dùng chỉ được review khi có license hợp lệ trong thư viện, giúp hạn chế review giả.

Luồng hoàn tiền phức tạp hơn vì có nhiều trạng thái. Refund có thể bị từ chối, được duyệt tự động hoặc chuyển sang admin duyệt thủ công. Nếu hoàn tiền được chấp nhận, hệ thống phải gọi cổng thanh toán và thu hồi license. Vì vậy nhóm dùng cả activity refund và state refund để mô tả đầy đủ quy trình và vòng đời trạng thái.

## Slide 13

Phần kiến trúc hệ thống do Đạt trình bày để giảm tải cho Đô và để trưởng nhóm kết nối phần nghiệp vụ với phần kỹ thuật. Kiến trúc được tách theo miền nghiệp vụ. Phía ngoài là Web Frontend và Steam Client. Hai thành phần này đi qua API Gateway thay vì gọi trực tiếp từng service.

API Gateway đóng vai trò cửa vào chung, giúp định tuyến request, hỗ trợ xác thực và che bớt độ phức tạp của backend. Các service phía sau gồm Account, Catalog, Cart, Order, Library, Review, Publisher và Notification. Mỗi service phụ trách một miền nghiệp vụ riêng.

Lý do chọn hướng tách service là vì từng miền có yêu cầu khác nhau. Catalog cần tìm kiếm nhanh và cache tốt. Order và Payment cần độ chính xác cao. Library cần quản lý license ổn định. Review cần kiểm tra quyền sở hữu và kiểm duyệt nội dung. Deployment diagram cho thấy hệ thống còn cần database, search index, CDN, event queue và cổng thanh toán để vận hành ở quy mô lớn.

## Slide 14

Phần dữ liệu tập trung vào ERD. ERD thể hiện các thực thể chính và quan hệ giữa chúng. User có thể có nhiều order, review, wishlist và một library. Game thuộc publisher và có thể xuất hiện trong wishlist item, cart item, review và license.

Điểm quan trọng nhất là quan hệ giữa Library, License và Game. Library là thư viện của người dùng, còn License là quyền truy cập cụ thể đến một game. Người dùng không sở hữu game chỉ vì có order. Người dùng chỉ có quyền truy cập khi payment thành công và license được cấp vào library.

Thiết kế này cũng hỗ trợ hoàn tiền. RefundRequest gắn với order và user. Nếu hoàn tiền được duyệt, hệ thống cập nhật trạng thái refund, cập nhật order và thu hồi license tương ứng. Nhờ đó dữ liệu có thể truy vết từ người dùng, đơn hàng, thanh toán đến quyền truy cập game.

## Slide 15

BCE và class design giúp chuyển từ phân tích nghiệp vụ sang thiết kế lớp. Trong BCE, Boundary là lớp giao tiếp với người dùng, ví dụ StorePageBoundary, CartBoundary và LoginBoundary. Boundary không xử lý nghiệp vụ sâu mà chuyển yêu cầu sang lớp Control.

Control là lớp điều phối nghiệp vụ. CatalogController xử lý tìm kiếm và lọc game. OrderController xử lý tạo đơn hàng và xác nhận thanh toán. AccountController xử lý đăng nhập và Steam Guard. RefundController xử lý yêu cầu hoàn tiền.

Entity là các đối tượng dữ liệu cốt lõi như User, Game, Cart, Order, Payment, License, Review và RefundRequest. Class design làm rõ thuộc tính và phương thức của các lớp này. Nhóm chọn BCE vì nó giúp tổ chức hệ thống rõ ràng: giao diện nhận yêu cầu, control xử lý nghiệp vụ, entity lưu dữ liệu. Cách này cũng giúp việc chuyển sang thiết kế code sau này dễ hơn.

## Slide 16

Để kết luận, nhóm đã hoàn thành bộ mô hình phân tích và thiết kế cho Steam Store. Kết quả gồm mô tả bài toán, yêu cầu chức năng, yêu cầu phi chức năng, phân quyền actor, giao diện chính, use case diagram, sequence diagram, activity diagram, state diagram, BCE, class design, ERD và deployment diagram.

Điểm quan trọng là các mô hình liên kết với nhau theo một chuỗi logic. Yêu cầu dẫn đến use case. Use case dẫn đến sequence và activity. State diagram kiểm soát vòng đời order và refund. BCE và class diagram mô tả tổ chức lớp. ERD mô tả dữ liệu. Deployment diagram mô tả cách triển khai hệ thống.

Hướng phát triển tiếp theo là xây dựng prototype giao diện chi tiết hơn, đặc tả API, bổ sung test case cho thanh toán và hoàn tiền, đồng thời mô phỏng database. Nhóm em xin cảm ơn thầy và các bạn đã lắng nghe, và sẵn sàng nhận câu hỏi hoặc góp ý.
