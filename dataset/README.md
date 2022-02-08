
## quá trình thu thập dữ liệu
Dữ liệu thô gồm các video nhóm bọn em thu thập thủ công từ youtube, từ các kênh của fifa, từ các kênh của các đội bóng, câu lạc bộ.

Sau khi có dữ liệu thô là các video toàn bộ trận đấu (full match), nhóm chúng em tiến hành chia ra xem và tách ra những đoạn (tầm 5-10s) được xem là diễn biến chính (như đã được đề cập ở trước). Nhưng trong khi tách thì bọn em nhận ra được là các đoạn mà bọn em quan tâm (diễn biến chính) của 1 video 90 phút hơn là rất ít. Ban đầu, chúng em tách được 1396 video non-highlight (không phải diễn biến chính) và 81 video highlight (diễn biến chính). Chính sự chênh lệch data giữa hai class quá lớn đã dẫn đến overfiting cho model. Vì vậy chúng em tiến hành thu thập thêm các video highlight ở youtube, sau đó định vị chính xác và cắt nhỏ ra từng video có độ dài 5-10s để bổ sung vào tập highlight, tránh bị chênh lệch dữ liệu dẫn đến việc đào tạo không đem lại hiệu quả cao.

## khó khăn khi thu thập dữ liệu:
•	Việc thu thập các video highlight tốn rất nhiều thời gian, phải xem những video dài chi tiết, sau đó mới có thể tìm ra được những đoạn nhỏ (Trung bình 1 video hơn 100p chỉ tìm được khoảng 2-3p highlight).

•Việc thu thập data highlight phải đa dạng ở nhiều góc độ.

•	Các video thu thập phải chọn lọc kỹ lưỡng, tránh các video có gắn quảng cáo ở màn hình.

## Quá trình tạo video tóm tắt:

Từ một video đầu vào, nhóm sẽ tiến hành chia nhỏ thành từng đoạn có độ dài từ 5 đến 7 giây (và 1 bộ sẽ luôn luôn là 10s) và xem thử đoạn đó có phải là đoạn diễn biến chính (highlight)
mà nhóm quan tâm hay không, nếu có, video sẽ được gán nhãn là "1", ngược lại, video sẽ mang nhãn "0"

![alt text](https://github.com/minz1337/CS114.M11/blob/main/images/qua_trinh_tao_video_tom_tat.png)

## Quá trình phân loại dựa trên dataset

Sau khi có video, nhóm sẽ tiến hành phân loại dựa theo sơ đồ sau:

![alt text](https://github.com/minz1337/CS114.M11/blob/main/images/Qua_trinh_phan_loai.png)

- Link to dataset: https://drive.google.com/drive/folders/1_LJ7WGDTrdK_mm7s1fu3mC75EWabQDuK?usp=sharing
     - /AudioBaseData : Bộ dataset dùng cho phương pháp sử dụng Audio
     - /LogoBaseData : Bộ dataset dùng cho phương pháp sử dụng ảnh logo
     - /result/stft_output_2/highlight_labeled: Kết quả nhóm gán nhãn highlight bằng tay
     - /result/stft_output_2 : Kết quả sử dụng phương pháp audio để tóm tắt trận đấu
     - /save model : Lưu trữ kết quả train của các model
