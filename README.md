BÁO CÁO KIỂM THỬ API
Tên dự án: Test Collection of APIs
Công cụ kiểm thử: Postman
API sử dụng: DummyJSON
Ngày kiểm thử: 27/05/2026
Người kiểm thử: Nguyễn Phương Ngân
1.	MỤC TIÊU KIỂM THỬ
Sử dụng công cụ Postman để kiểm thử API thực tế, kiểm tra khả năng gửi request và nhận response từ server thông qua các phương thức HTTP. Đồng thời làm quen với việc đọc dữ liệu JSON và xử lý lỗi API.
2.	MÔI TRƯỜNG KIỂM THỬ
•	Hệ điều hành: Windows
•	Công cụ kiểm thử: Postman
•	Kết nối Internet
•	API sử dụng:
o	https://dummyjson.com/users
o	https://dummyjson.com/products
3.	PHƯƠNG PHÁP KIỂM THỬ
Trong bài thực hành này, phương pháp kiểm thử thủ công được sử dụng thông qua công cụ Postman để gửi request API và kiểm tra phản hồi từ server.
Quá trình kiểm thử được thực hiện theo các bước sau:
•	Mở phần mềm Postman và tạo mới các HTTP Request.
•	Chọn phương thức HTTP phù hợp cho từng kịch bản kiểm thử.
•	Nhập URL API cần kiểm thử.
•	Gửi request từ Postman đến server bằng nút “Send”.
•	Quan sát phản hồi trả về từ API bao gồm:
o	Mã trạng thái HTTP (200 OK, 404 Not Found,…)
o	Dữ liệu JSON trả về
o	Thời gian phản hồi
o	Dung lượng dữ liệu phản hồi
•	So sánh kết quả thực tế với kết quả mong đợi để đánh giá trạng thái thành công hoặc thất bại của từng kịch bản kiểm thử.
•	Chụp ảnh màn hình kết quả thực hiện để lưu làm minh chứng cho báo cáo.
Ngoài ra, bài kiểm thử còn thực hiện kiểm tra trường hợp lỗi bằng cách sử dụng endpoint không tồn tại nhằm đánh giá khả năng xử lý lỗi của API khi nhận request sai đường dẫn.
Thông qua quá trình kiểm thử, người thực hiện có thể hiểu rõ hơn về:
•	Cách hoạt động của API
•	Cách gửi request bằng Postman
•	Cách đọc dữ liệu JSON
•	Ý nghĩa của các mã phản hồi HTTP
•	Cách phát hiện và xử lý lỗi API trong quá trình kiểm thử phần mềm.
4.	KỊCH BẢN KIỂM THỬ
Kịch bản kiểm thử lần 1
	Tên kịch bản:
Kiểm thử API lấy danh sách người dùng
	Mục đích:
Kiểm tra khả năng hoạt động của API và phần mềm Postman khi gửi request GET đến server. Đồng thời kiểm tra khả năng phản hồi dữ liệu người dùng dưới dạng JSON.
	Phương thức HTTP:
GET
	URL:
https://dummyjson.com/users
	Các bước thực hiện:
•	Mở phần mềm Postman.
•	Tạo một HTTP Request mới.
•	Chọn phương thức GET.
•	Nhập URL: https://dummyjson.com/users
•	Nhấn nút “Send” để gửi request đến server.
•	Quan sát kết quả phản hồi trả về.
	Kết quả mong đợi:
•	API hoạt động bình thường.
•	Server trả về mã phản hồi HTTP 200 OK.
•	Dữ liệu trả về ở định dạng JSON.
•	Danh sách người dùng được hiển thị đầy đủ.
	Kết quả thực tế:
•	API phản hồi thành công.
•	Server trả về mã trạng thái 200 OK.
•	Dữ liệu JSON chứa thông tin người dùng được hiển thị đầy đủ.
	Trạng thái: Thành công
	Hình ảnh kết quả:
	
 
	Kết quả kiểm thử chi tiết:
{
"users": [
{
"id": 1,
"firstName": "Emily",
"lastName": "Johnson",
"email": "emily.johnson@x.dummyjson.com"
}
]
}
Kịch bản kiểm thử lần 2
	Tên kịch bản:
Kiểm thử API với endpoint không tồn tại
	Mục đích:
Kiểm tra khả năng xử lý lỗi của API khi người dùng gửi request đến một endpoint sai hoặc không tồn tại trên server.
	Phương thức HTTP:
GET
	URL:
https://dummyjson.com/abcdef
	Các bước thực hiện:
•	Mở Postman.
•	Tạo request mới bằng phương thức GET.
•	Nhập URL sai: https://dummyjson.com/abcdef
•	Nhấn “Send”.
•	Quan sát phản hồi từ server.
	Kết quả mong đợi:
•	Server phát hiện endpoint không hợp lệ.
•	API trả về mã lỗi HTTP 404 Not Found.
•	Hệ thống thông báo lỗi rõ ràng.
	Kết quả thực tế:
•	Server trả về lỗi 404 Not Found.
•	API không tìm thấy endpoint được yêu cầu.
•	Dữ liệu phản hồi hiển thị thông báo lỗi.
	Trạng thái: Không thành công
	Hình ảnh kết quả:

 
	Kết quả kiểm thử chi tiết:
{
"message": "Not Found"
}
Kịch bản kiểm thử lần 3
	Tên kịch bản:
Kiểm thử API lấy danh sách sản phẩm
	Mục đích:
Kiểm tra khả năng phản hồi dữ liệu sản phẩm từ API và kiểm tra tính ổn định của server khi xử lý request GET.
	Phương thức HTTP:
GET
	URL:
https://dummyjson.com/products
	Các bước thực hiện:
•	Mở Postman.
•	Tạo request mới.
•	Chọn phương thức GET.
•	Nhập URL: https://dummyjson.com/products
•	Nhấn nút “Send”.
•	Theo dõi kết quả phản hồi trả về.
	Kết quả mong đợi:
•	API trả về danh sách sản phẩm thành công.
•	Mã trạng thái phản hồi là 200 OK.
•	Dữ liệu trả về đúng định dạng JSON.
	Kết quả thực tế:
•	API phản hồi thành công.
•	Dữ liệu sản phẩm được hiển thị đầy đủ.
•	Server trả về mã phản hồi 200 OK.
	Trạng thái: Thành công
	Hình ảnh kết quả:

 
	Kết quả kiểm thử chi tiết:
{
"products": [
{
"id": 1,
"title": "Essence Mascara Lash Princess",
"price": 9.99
}
]
}
5.	KẾT QUẢ KIỂM THỬ
Sau quá trình thực hiện kiểm thử API bằng công cụ Postman, các kịch bản kiểm thử đã được tiến hành thành công theo đúng yêu cầu đề bài. Người thực hiện đã kiểm tra khả năng phản hồi của API thông qua nhiều trường hợp khác nhau bao gồm request thành công và request lỗi.
Tổng cộng đã thực hiện 3 kịch bản kiểm thử với các kết quả như sau:
•	Kịch bản kiểm thử lấy danh sách người dùng:
Thành công. API phản hồi đúng dữ liệu JSON và trả về mã trạng thái HTTP 200 OK. 
•	Kịch bản kiểm thử với endpoint không tồn tại:
Thất bại theo mong đợi. API trả về mã lỗi HTTP 404 Not Found khi gửi request sai URL. 
•	Kịch bản kiểm thử lấy danh sách sản phẩm:
Thành công. API trả về dữ liệu sản phẩm đầy đủ với mã phản hồi HTTP 200 OK. 
Tổng hợp kết quả kiểm thử:
•	Tổng số kịch bản kiểm thử: 3 
•	Số kịch bản thành công: 2 
•	Số kịch bản thất bại: 1 
•	Tỉ lệ thành công: 66% 
Qua kết quả trên có thể nhận thấy:
•	API hoạt động ổn định trong các trường hợp request hợp lệ. 
•	Server xử lý và phản hồi dữ liệu nhanh chóng. 
•	Hệ thống có khả năng xử lý lỗi khi người dùng gửi sai endpoint. 
•	Công cụ Postman hỗ trợ hiệu quả trong việc kiểm tra API và theo dõi phản hồi từ server. 
Việc kiểm thử giúp người thực hiện hiểu rõ hơn về:
•	Cách hoạt động của API 
•	Các phương thức HTTP 
•	Mã trạng thái phản hồi HTTP 
•	Dữ liệu JSON 
•	Quy trình kiểm thử API trong thực tế. 
6.	PHÁT HIỆN LỖI
Trong quá trình kiểm thử API bằng Postman, một lỗi đã được phát hiện khi gửi request đến endpoint không tồn tại trên server.
Thông tin lỗi:
•	ID lỗi: 404 Not Found 
•	Tên lỗi:
Endpoint không tồn tại 
•	Mô tả lỗi:
Khi gửi request GET đến URL:
https://dummyjson.com/abcdef
server không thể tìm thấy endpoint tương ứng nên trả về mã lỗi HTTP 404 Not Found.
•	Nguyên nhân:
Người dùng nhập sai endpoint hoặc endpoint đó không tồn tại trên hệ thống API. 
•	Kết quả phản hồi thực tế: 
{
"message": "Not Found"
}
•	Mức độ ảnh hưởng:
Thấp 
•	Ảnh hưởng của lỗi:
Request không thể thực hiện thành công và dữ liệu yêu cầu không được trả về từ server. 
•	Cách phát hiện lỗi:
Quan sát mã phản hồi HTTP trong Postman và nội dung dữ liệu JSON trả về sau khi gửi request. 
•	Đề xuất hướng xử lý: 
o	Kiểm tra chính xác endpoint trước khi gửi request. 
o	Đối chiếu URL với tài liệu API. 
o	Kiểm tra phương thức HTTP phù hợp. 
o	Đảm bảo server và endpoint đang hoạt động bình thường. 
•	Kết luận:
Đây là lỗi phổ biến trong quá trình kiểm thử API và giúp người thực hiện hiểu rõ hơn về cách xử lý phản hồi lỗi từ server khi gửi request không hợp lệ. 
7.	KẾT LUẬN
Qua quá trình thực hành kiểm thử API bằng Postman, em đã hiểu cách gửi request API, kiểm tra mã phản hồi HTTP, đọc dữ liệu JSON trả về và xử lý lỗi API. Đồng thời biết cách sử dụng GitHub để lưu trữ báo cáo và kết quả kiểm thử.

