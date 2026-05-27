# N?i dung thuy?t tr?nh Steam Store

B?n n?y kh?p v?i 15 slide trong `index.html`. M?i m?c l? n?i dung c? th? ??c khi thuy?t tr?nh.

## Slide 1

Em xin chào thầy và các bạn. Nhóm em trình bày đề tài phân tích và thiết kế hệ thống Steam Store. Trong bài này, nhóm không xem Steam Store chỉ là một trang bán game, mà xem nó như một hệ thống phần mềm có nhiều nghiệp vụ liên kết với nhau.

Hệ thống có người dùng tìm kiếm game, xem chi tiết, thêm vào wishlist, mua game, thanh toán, nhận game trong thư viện, viết review và yêu cầu hoàn tiền. Ngoài ra còn có nhà phát hành quản lý game, quản trị viên kiểm duyệt và cổng thanh toán xử lý giao dịch.

Bài trình bày được chia theo vai trò của 5 thành viên. Đạt phụ trách tổng quan và kết luận. Khoa phụ trách yêu cầu và phân quyền. Dương phụ trách giao diện và hành trình người dùng. Khánh phụ trách UML nghiệp vụ. Đô phụ trách kiến trúc, dữ liệu và thiết kế kỹ thuật.

## Slide 2

Đây là lộ trình trình bày của nhóm. Phần đầu do Đạt trình bày, tập trung vào lý do chọn đề tài, phạm vi hệ thống và khối lượng công việc nhóm đã hoàn thành.

Tiếp theo, Khoa trình bày yêu cầu hệ thống. Phần này trả lời câu hỏi hệ thống cần làm gì, có những actor nào và mỗi actor được sử dụng chức năng nào. Dương trình bày giao diện và hành trình người dùng để người nghe hình dung hệ thống dưới góc nhìn thực tế.

Sau đó Khánh trình bày các UML mô tả nghiệp vụ như use case, sequence, activity và state. Cuối cùng Đô trình bày thiết kế kỹ thuật gồm kiến trúc, BCE, class diagram, ERD và deployment. Cách đi này giúp bài thuyết trình liền mạch: từ yêu cầu đến hành vi, rồi đến cấu trúc hệ thống.

## Slide 3

Nhóm chọn Steam Store vì đây là một hệ thống đủ lớn để áp dụng các kiến thức của môn kỹ thuật phần mềm. Hệ thống có nhiều vai trò khác nhau: khách vãng lai, người dùng Steam, Steam Client, nhà phát hành, quản trị viên và cổng thanh toán.

Điểm quan trọng là các nghiệp vụ trong Steam Store liên kết chặt chẽ với nhau. Người dùng tìm game, thêm vào giỏ hàng, thanh toán, sau đó hệ thống cấp license để game xuất hiện trong thư viện. Từ thư viện, người dùng có thể tải game, viết review hoặc yêu cầu hoàn tiền.

Nhóm bắt đầu bằng sơ đồ kiến trúc tổng quan để đặt bối cảnh cho toàn bộ bài. Sơ đồ này cho thấy hệ thống gồm client, API Gateway, các service nghiệp vụ, database, search index, CDN và cổng thanh toán. Khi có bức tranh tổng thể, các UML chi tiết phía sau sẽ có điểm tựa rõ ràng hơn.

## Slide 4

Khối lượng công việc của nhóm gồm ba lớp nội dung. Lớp đầu tiên là xác định yêu cầu hệ thống. Nhóm đã mô tả bài toán, xây dựng bảng thuật ngữ, xác định yêu cầu chức năng, yêu cầu phi chức năng và phân quyền theo vai trò.

Lớp thứ hai là phân tích UML. Nhóm có use case cho người dùng và quản trị, sequence diagram cho các luồng chính, activity diagram cho quy trình mua game và hoàn tiền, state diagram cho order và refund, cùng BCE để nối giao diện, điều khiển và dữ liệu.

Lớp thứ ba là thiết kế hệ thống. Nhóm đã có architecture diagram, deployment diagram, class design, ERD và danh sách bảng cơ sở dữ liệu. Cách chia này giúp từng thành viên có phần riêng nhưng vẫn nằm trong một luồng phân tích thống nhất.

## Slide 5

Phần yêu cầu hệ thống được chia thành ba nhóm. Nhóm thứ nhất là yêu cầu chức năng dành cho người dùng, gồm đăng ký, đăng nhập, Steam Guard, tìm kiếm game, wishlist, giỏ hàng, checkout, quản lý thư viện, review và hoàn tiền.

Nhóm thứ hai là chức năng quản trị. Nhà phát hành quản lý thông tin game, giá bán, media, DLC và khuyến mãi. Quản trị viên xử lý kiểm duyệt nội dung, hỗ trợ tài khoản và theo dõi giao dịch bất thường.

Nhóm thứ ba là yêu cầu phi chức năng. Với Steam Store, bảo mật tài khoản, hiệu năng tìm kiếm, khả năng mở rộng trong các đợt sale lớn và toàn vẹn giữa thanh toán với cấp license là các điểm rất quan trọng. Nhóm chọn tách yêu cầu theo vai trò vì mỗi actor có quyền thao tác khác nhau, đây là nền để xây dựng use case và phân quyền hệ thống.

## Slide 6

Use case diagram thể hiện actor nào tương tác với hệ thống và họ được sử dụng chức năng nào. Khách vãng lai có thể tìm kiếm, lọc game, xem chi tiết và đăng ký tài khoản. Đây là nhóm chưa đăng nhập nên không được mua game, review hoặc quản lý wishlist.

Người dùng Steam là actor chính của hệ thống. Sau khi đăng nhập, người dùng có thể quản lý wishlist, giỏ hàng, thanh toán, thư viện, viết review và yêu cầu hoàn tiền. Steam Client được tách thành actor riêng vì việc tải và cập nhật game diễn ra qua ứng dụng client dựa trên license trong thư viện.

Phía quản trị có publisher và admin. Publisher quản lý trang game, giá, media và khuyến mãi. Admin kiểm duyệt nội dung, hỗ trợ tài khoản và theo dõi giao dịch. Use case được dùng ở bước này vì nó giúp chốt phạm vi trước khi đi vào sequence, activity và thiết kế dữ liệu.

## Slide 7

Phần giao diện được trình bày theo các màn hình chính của Steam Store. Người dùng bắt đầu từ trang chủ Store, nơi hiển thị game nổi bật, game đang sale, danh mục và thanh tìm kiếm. Sau đó người dùng đi tới trang tìm kiếm hoặc lọc game theo tag, giá, nền tảng, đánh giá và ngày phát hành.

Trang chi tiết game cung cấp trailer, hình ảnh, mô tả, giá, DLC, review và cấu hình yêu cầu. Khi quyết định mua, người dùng sử dụng wishlist, giỏ hàng và checkout. Sau khi thanh toán thành công, game xuất hiện trong thư viện.

Ngoài ra còn có review, refund, Publisher Dashboard và Admin Dashboard. Trong mô hình BCE, các màn hình này tương ứng với lớp Boundary, tức là lớp tiếp nhận tương tác từ người dùng trước khi chuyển sang Control xử lý nghiệp vụ.

## Slide 8

Hành trình người dùng được mô tả từ lúc bắt đầu tìm game đến khi game xuất hiện trong thư viện. Người dùng có thể bắt đầu ở trang chủ hoặc trang tìm kiếm. Khi tìm được game phù hợp, người dùng mở trang chi tiết để xem thông tin, giá, review và yêu cầu cấu hình.

Sau đó người dùng thêm game vào wishlist hoặc giỏ hàng. Nếu mua ngay, người dùng chuyển sang checkout, chọn phương thức thanh toán và xác nhận đơn hàng. Khi thanh toán thành công, hệ thống cấp license và game xuất hiện trong thư viện.

Hành trình này liên hệ trực tiếp với use case và activity diagram. Use case cho biết người dùng được làm gì, activity diagram cho biết quy trình rẽ nhánh như thế nào, còn ERD cho thấy dữ liệu giỏ hàng, order, payment, license và library được tạo ra theo thứ tự nào.

## Slide 9

Phần UML nghiệp vụ giải thích cách hệ thống hoạt động. Use case diagram cho biết actor nào dùng chức năng nào. Tuy nhiên use case chưa cho biết thứ tự xử lý bên trong, vì vậy nhóm dùng sequence diagram.

Sequence diagram mô tả các thành phần gọi nhau theo thời gian. Ví dụ trong luồng mua game, Web UI gọi Cart Service, Order Service, Payment Gateway và Library Service. Activity diagram mô tả quy trình có rẽ nhánh, chẳng hạn thanh toán thành công hoặc thất bại, refund được duyệt tự động hoặc cần admin xem xét.

State diagram được dùng cho order và refund vì hai đối tượng này có vòng đời rõ ràng. Nhóm dùng nhiều loại UML vì mỗi sơ đồ trả lời một câu hỏi khác nhau. Cách này giúp nghiệp vụ được phân tích đầy đủ hơn và tránh bỏ sót trạng thái lỗi.

## Slide 10

Quy trình mua game là luồng nghiệp vụ quan trọng nhất. Người dùng bắt đầu bằng checkout từ giỏ hàng. Hệ thống lấy danh sách game và lưu snapshot giá để bảo đảm lịch sử giao dịch không bị thay đổi nếu giá game thay đổi sau đó.

Order Service tạo đơn hàng tạm và gửi yêu cầu sang Payment Gateway. Nếu thanh toán thất bại, hệ thống không cấp game mà chỉ thông báo lỗi. Nếu thanh toán thành công, Order Service gọi Library Service để tạo license cho từng game, sau đó game xuất hiện trong thư viện.

Điểm quan trọng là toàn vẹn giao dịch. Hệ thống phải tránh hai lỗi: người dùng bị trừ tiền nhưng không nhận game, hoặc chưa thanh toán mà vẫn được cấp game. Vì vậy sequence purchase, activity purchase và state order được dùng để kiểm soát thứ tự xử lý và trạng thái đơn hàng.

## Slide 11

Ngoài mua game, nhóm phân tích thêm các luồng quan trọng khác. Luồng đăng nhập có Steam Guard thể hiện yêu cầu bảo mật tài khoản. Account Service kiểm tra thông tin đăng nhập, sau đó Steam Guard xác thực bổ sung nếu thiết bị hoặc vị trí đăng nhập cần kiểm tra.

Luồng viết review thể hiện việc kiểm soát chất lượng đánh giá. Người dùng chỉ được review khi đã sở hữu game hoặc có license hợp lệ trong thư viện. Điều này giúp hạn chế review giả và spam.

Luồng hoàn tiền thể hiện vòng đời nghiệp vụ phức tạp. Refund có thể bị từ chối, được duyệt tự động hoặc chuyển sang admin xem xét. Khi hoàn tiền được chấp nhận, hệ thống phải hoàn tiền và thu hồi license. Vì vậy nhóm dùng cả activity refund và state refund để mô tả rẽ nhánh và trạng thái.

## Slide 12

Kiến trúc hệ thống được tách theo miền nghiệp vụ. Phía ngoài là Web Frontend và Steam Client. Hai thành phần này không gọi trực tiếp vào từng service, mà đi qua API Gateway. Gateway là cửa vào chung, giúp định tuyến request và hỗ trợ xác thực.

Các service phía sau gồm Account, Catalog, Cart, Order, Library, Review, Publisher và Notification. Mỗi service phụ trách một miền nghiệp vụ riêng. Catalog tập trung vào game và tìm kiếm. Order xử lý đơn hàng và thanh toán. Library quản lý license. Review xử lý đánh giá. Publisher phục vụ nhà phát hành.

Nhóm chọn hướng tách service vì Steam Store có nhiều nghiệp vụ với đặc điểm khác nhau. Trong đợt sale lớn, catalog và search cần mở rộng mạnh. Trong khi đó order và payment cần chính xác giao dịch. Tách theo miền nghiệp vụ giúp hệ thống dễ mở rộng, dễ bảo trì và giảm ảnh hưởng khi một service gặp lỗi.

## Slide 13

ERD thể hiện các thực thể chính và quan hệ dữ liệu trong hệ thống. User có nhiều order, review, wishlist và một library. Game thuộc publisher và có thể xuất hiện trong wishlist item, cart item, review và license.

Điểm quan trọng là quan hệ giữa Library, License và Game. Library là thư viện của người dùng, còn License là quyền truy cập cụ thể đến một game. Điều này phản ánh đúng nghiệp vụ của Steam Store: sau khi thanh toán thành công, người dùng nhận quyền truy cập số thay vì nhận sản phẩm vật lý.

RefundRequest gắn với order và user. Khi hoàn tiền được duyệt, hệ thống cập nhật trạng thái refund, cập nhật order và thu hồi license. Nhờ đó dữ liệu có thể truy vết từ người dùng, đơn hàng, thanh toán đến quyền truy cập game.

## Slide 14

BCE giúp nối phần giao diện với phần thiết kế lớp. Boundary là lớp nhận tương tác từ người dùng, ví dụ StorePageBoundary, CartBoundary và LoginBoundary. Các lớp này không xử lý nghiệp vụ sâu mà chuyển yêu cầu sang lớp Control.

Control là lớp điều phối nghiệp vụ. CatalogController xử lý tìm kiếm và lọc game. OrderController xử lý tạo đơn hàng và xác nhận thanh toán. AccountController xử lý đăng nhập và Steam Guard. RefundController xử lý yêu cầu hoàn tiền.

Entity là các đối tượng dữ liệu cốt lõi như User, Game, Cart, Order, Payment, License, Review và RefundRequest. Class design tiếp tục làm rõ thuộc tính và phương thức của các lớp này. Nhóm chọn BCE vì nó giúp chuyển từ use case sang thiết kế lớp một cách rõ ràng: giao diện nhận yêu cầu, control xử lý, entity lưu dữ liệu.

## Slide 15

Để kết luận, nhóm đã hoàn thành bộ mô hình phân tích và thiết kế cho Steam Store. Kết quả gồm mô tả bài toán, yêu cầu chức năng, yêu cầu phi chức năng, phân quyền actor, giao diện chính, use case diagram, sequence diagram, activity diagram, state diagram, BCE, class design, ERD và deployment diagram.

Điểm quan trọng là các mô hình không đứng riêng lẻ. Yêu cầu dẫn đến use case. Use case dẫn đến sequence và activity. State diagram kiểm soát vòng đời order và refund. BCE và class diagram mô tả cách tổ chức lớp. ERD mô tả dữ liệu. Deployment diagram mô tả triển khai hệ thống.

Hướng phát triển tiếp theo là xây dựng prototype giao diện chi tiết hơn, đặc tả API, bổ sung test case cho các nghiệp vụ nhạy cảm như thanh toán và hoàn tiền, đồng thời mô phỏng database. Nhóm em xin cảm ơn thầy và các bạn đã lắng nghe, và sẵn sàng nhận câu hỏi hoặc góp ý.
