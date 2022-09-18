---
title: 'Nghiên cứu giải mã lời nói từ tín hiệu điện não của Facebook'
date: 2021-08-28
permalink: /posts/2021/08/chien-thuat-choi-bac-luon-thang/
tags:
  - probability
  - gambling
  - game theory
---

![Facebook research on EEG and speed](/images/post/2022_fb_research_eeg.jpeg)
Facebook's research on decoding speech from EEG (English below)

Nghiên cứu giải mã lời nói từ tín hiệu điện não của Facebook
Vào cuối tháng 8 vừa rồi team AI của Facebook (Meta) đã công bố bản preprint nghiên cứu của họ về tín hiệu điện não. 
Lời nói là một hoạt động phức tạp của trí thông minh, vì vậy các nghiên cứu cách thông tin lời nói được xử lý trong não bộ thường phải được xử lý với tín hiệu điện não xâm nhập (invasive EEG), tức là phải phẫu thuật hộp sọ để đặt điện cực vào trực tiếp bộ não.Cách làm này có phần kinh dị và không thể mở rộng phổ biến đại trà. Tuy nhiên tín hiệu điện não không xâm nhập (non-invasive EEG), được đo bên ngoài da, thường rất nhiễu, yếu, lại có sự khác biệt giữa các cá nhân, thậm chí giữa các phiên thu dữ liệu của cùng một người. 
Nghiên cứu của Facebook đạt được bước tiến đáng kể giải mã lời nói từ tín hiệu non-invasive EEG. Kiến trúc mạng sử dụng wav2vec 2.0, contrastive training với hàm loss CLIP và đáng chú ý là bộ các layer CNN xếp chồng lên các Subject layers. Subject layer được mô tả là thực hiện tham số hóa các hàm trên mỗi điện cực trên không gian Fourier.
Hy vọng source code của bài báo này sẽ sớm được công bố.

Link: [https://lnkd.in/gBhVHBKj](https://lnkd.in/gBhVHBKj)


At the end of August, Facebook/Meta's AI team published a preprint of their research on brain electrical signals (electroencephalogram-EEG).
Speech is a complex activity of intelligence, so studies of how speech is processed in the brain often has to be worked with invasive EEG signals. Skull surgery is needed to place electrodes directly into the brain. This method is somewhat horrible and cannot be widely spread. However, non-invasive EEG signals, measured in the scalp, are often very noisy and weak, and there are differences between individuals, even between sessions of the same person. .
Facebook's research takes a significant step forward in decoding speech from non-invasive EEG signals. The network architecture uses wav2vec 2.0, contrastive training with the CLIP loss function, and notably a set of CNN layers superimposed on Subject layers. The subject layer is described as performing per-electrode parameterization on Fourier space.
Hopefully the source code of this article will be published soon.

Link: [https://lnkd.in/gBhVHBKj](https://lnkd.in/gBhVHBKj)