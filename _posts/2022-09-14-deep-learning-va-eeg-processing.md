---
title: '[Vi] Deep learning và xử lý tín hiệu điện não'
date: 2022-09-14
permalink: /posts/vi/2022/09/deep-learning-va-eeg-processing/
tags:
  - EEG
  - Neuroscience
  - Deep learning
  - Vietnamese
---

Deep learning (DL), ngành khoa học dựa trên ý tưởng cách hoạt động của bộ não. 
Kể từ khi Hinton tuyên bố mình hiểu cách não bộ hoạt động, cùng với sự ra đời của deep learning, các ngành khoa học liên quan đã thay đổi cách tiếp cận của mình rất đáng kể. Năm 2012, mạng AlexNet, phát triển bởi các học trò của Hinton, đạt kết quả SOTA trong xử lý ảnh. Kể từ đó các phương pháp trích xuất đặc trưng ảnh truyền thống dần chìm vào quên lãng. Ngày nay khi nói đến xử lý ảnh, người ta nghĩ ngay đến mạng deep learning kích thước lớn với các lớp CNN xếp chồng. 


Cho đến năm 2016, Deep learning đã rất phát triển, chinh phục nhiều lĩnh vực và trở nên nổi tiếng nhờ sự kiện AlphaGo đánh bại con người trong trò chơi cờ vây. Tuy nhiên, nó vẫn là một thuật ngữ xa lạ với những người làm khoa học thần kinh, thứ mà DL vốn muốn mô phỏng. Giao diện não - máy tính (Brain-computer interfaces, BCI) là một lĩnh vực hứa hẹn của neural science và cũng là tên một bộ sách rất toàn diện về xử lý tín hiệu não bộ cũng như đưa chúng vào ứng dụng. Hai bộ sách BCI tập 1 và tập 2 được WILEY phát hành năm 2016, dành ra 4 chương nói về xử lý dữ liệu điện não, 1 chương nói về ứng dụng machine learning. Tuy nhiên cả 2 bộ đều không có từ nào nhắc đến DL. 

DL dần trở nên phát triển trong nghiên cứu điện não một cách nhanh chóng những năm sau đó. Năm 2017, Akara et al. giới thiệu DeepSleepNet chứng minh rằng dù không sử dụng bất kỳ tiền xử lý dữ liệu thủ công, xử lý tín hiệu hay kiến thức chuyên ngành về giấc ngủ nào, các model học máy vẫn có thể đạt được độ chính xác tương đương với những model được xây dựng bởi chuyên gia. Model của họ thuần túy sử dụng các layer CNN, RNN. Các phương pháp kết hợp giữa xử lý tín hiệu và DL cũng được quan tâm. Năm 2020 Nicolas et al. giới thiệu kiến trúc Recurrent Event Detector (RED) với 2 phiên bản RED-time và RED-CWT. RED-Time sử dụng các layer CNN với kennels nhỏ để trích xuất đặc trưng địa phương và đưa vào Bidirectional LSTM để học diễn biến thời gian. RED-CWT có kiến trúc tương tự nhưng thêm ở đầu vào một layer Continuous Wavelet Transform để trích xuất thông tin time-frequency. Hiệu quả thí nghiệm của 2 model này cơ bản là tương đương nhau. 

Cũng như xử lý ảnh, các model sử dụng DL mới loại bỏ dần sự cần thiết của kiến thức chuyên ngành. Nếu như năm 2020 nhóm nghiên cứu của đại học Zurich (Skorucak et al.) vẫn sử dụng các kiến thức chuyên môn về sóng não như sóng alpha, beta và phát hiện tỷ lệ theta/alpha là đặc trưng vàng cho việc dự đoán ngủ gật (micro sleeps). Thì cũng nhóm nghiên cứu này đến năm 2021 đã công bố một nghiên cứu mới, chỉ sử dụng các kỹ thuật CNN, kết nối phần dư,... các kỹ thuật thuần túy của DL và cho kết quả vượt trội hơn nhiều. 

Năm 2021 nhóm nghiên cứu của Facebook (Chehab, Defossez et al.) cũng công bố một nghiên cứu trong việc học đặc trưng của tín hiệu MEG. Tất cả những gì họ dùng là các layer LSTM kẹp giữa các layer CNN và CNN transpose. Nâng cấp nghiên cứu này, Defossez et al. mới đây đã công bố nghiên cứu của họ sử dụng DL ta đã tiến rất gần tới việc hiểu được bộ não phản ánh tiếng nói như thế nào.

Cuối cùng, năm 2021, WILEY cũng đã đăng Call for Book Chapter với tiêu đề mới cho tập 3 của bộ sách BCI: Using Deep Learning Applications. Trong tương lai, những nhà nghiên cứu về BCI và khoa học thần kinh có thể sẽ phải có hiểu biết nhiều hơn về deep learning, thậm chí còn nhiều hơn cả giải phẫu hay sinh học.

REFERENCES
-----

Maureen Clerc, Laurent Bougrain, Fabien Lotte (2016), Brain–Computer Interfaces 1: Foundations and Methods, Print ISBN:9781848218260, Online ISBN:9781119144977, DOI:10.1002/9781119144977

Maureen Clerc, Laurent Bougrain, Fabien Lotte (2016), Brain-Computer Interfaces 2: Technology and Applications, ISBN: 978-1-848-21963-2

Supratak, Akara & Dong, Hao & Wu, Chao & Guo, Yike. (2017). DeepSleepNet: a Model for Automatic Sleep Stage Scoring based on Raw Single-Channel EEG. IEEE Transactions on Neural Systems and Rehabilitation Engineering. PP. 10.1109/TNSRE.2017.2721116. 

Tapia-Rivas, Nicolás & Estevez, Pablo. (2020). RED: Deep Recurrent Neural Networks for Sleep EEG Event Detection. 	arXiv:2005.07795 

Jelena Skorucak, Anneke Hertig-Godeschalk, David R Schreier, Alexander Malafeev, Johannes Mathis, Peter Achermann, Automatic detection of microsleep episodes with feature-based machine learning, Sleep, Volume 43, Issue 1, January 2020, zsz225, https://doi.org/10.1093/sleep/zsz225

Malafeev A, Hertig-Godeschalk A, Schreier DR, Skorucak J, Mathis J and Achermann P (2021) Automatic Detection of Microsleep Episodes With Deep Learning. Front. Neurosci. 15:564098. doi: 10.3389/fnins.2021.564098

Chehab, Omar & Defossez, Alexandre & Loiseau, Jean-Christophe & Gramfort, Alexandre & King, Jean-Rémi. (2021). Deep Recurrent Encoder: A scalable end-to-end network to model brain signals. 

Défossez, Alexandre & Caucheteux, Charlotte & Rapin, Jérémy & Kabeli, Ori & King, Jean-Rémi. (2022). Decoding speech from non-invasive brain recordings. 

Wiley-BCI-2021: Brain-Computer Interface: Using Deep Learning Applications, Call for Book Chapter - Scrivener Publishing - WILEY, https://easychair.org/cfp/WILEY-BCI2021