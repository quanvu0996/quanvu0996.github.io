---
title: '[Vi] Nghiên cứu giải mã lời nói từ tín hiệu điện não của Facebook'
date: 2022-09-10
permalink: /posts/vi/2022/09/db_research_on_decoding_speech_from_eeg/
tags:
  - EEG
  - Neural science
  - Speech decoding
  - Vietnamese
---

![Facebook research on EEG and speed](/images/post/2022_fb_research_eeg.jpeg){: width="500" }<br>
Vào cuối tháng 8 vừa rồi team AI của Facebook (Meta) đã công bố bản preprint nghiên cứu của họ về tín hiệu điện não. 

Lời nói là một hoạt động phức tạp của trí thông minh, vì vậy các nghiên cứu cách thông tin lời nói được xử lý trong não bộ thường phải được xử lý với tín hiệu điện não xâm nhập (invasive EEG), tức là phải phẫu thuật hộp sọ để đặt điện cực vào trực tiếp bộ não.Cách làm này có phần kinh dị và không thể mở rộng phổ biến đại trà. Tuy nhiên tín hiệu điện não không xâm nhập (non-invasive EEG), được đo bên ngoài da, thường rất nhiễu, yếu, lại có sự khác biệt giữa các cá nhân, thậm chí giữa các phiên thu dữ liệu của cùng một người. 
Nghiên cứu của Facebook đạt được bước tiến đáng kể giải mã lời nói từ tín hiệu non-invasive EEG. Kiến trúc mạng sử dụng wav2vec 2.0, contrastive training với hàm loss CLIP và đáng chú ý là bộ các layer CNN xếp chồng lên các Subject layers. Subject layer được mô tả là thực hiện tham số hóa các hàm trên mỗi điện cực trên không gian Fourier.
Hy vọng source code của bài báo này sẽ sớm được công bố.

Link: [https://lnkd.in/gBhVHBKj](https://lnkd.in/gBhVHBKj)