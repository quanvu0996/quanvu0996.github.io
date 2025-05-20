---
title: '[Vi] Tập 2: Tín hiệu chồng chập '
date: 2023-05-31
permalink: /posts/vi/2023/05/combined_signals/
tags:
  - EEG
  - Neuroscience
  - English
---

![Poster](/images/post/2023_EEG_signals.jpeg){: width="800" }<br>
**Tín hiệu chồng chập** <br>
Đặt một chiếc micro trong phòng, bạn bắt đầu hát và hy vọng chiếc micro sẽ thu được chất giọng trong trẻo của mình. Thực tế không dễ dàng như vậy. Khi nghe lại đoạn âm thanh, bạn có thể sẽ nghe thấy tiếng ồn của xe cộ xung quanh, tiếng quạt, tiếng bước đi,...bên cạnh giọng hát của mình. Tín hiệu EEG cũng vậy, đặc biệt với non-invasive EEG. Với các điện cực nhạy và bộ khuếch đại, các tín hiệu dù nhỏ của nhiều nguồn khác nhau sẽ đều được ghi lại. Tín hiệu thu được thường là chồng chập của: tín hiệu EEG từ nhiều vùng khác nhau của não bộ (chứ không chỉ vùng não gần với điện cực nhất), tín hiệu của mắt (eye movement artifact), tín hiệu cơ (muscle/myogenic artifact), điện tim (ECG), nhiễu,...
Các mục dưới đây mô tả một số thành phần quan trọng.

**EEG combination**<br>
![EEG combination](/images/post/2023_eeg_combination.png){: width="300" } <br>

Bản chất của EEG là các luồng điện được sinh ra bởi sự đồng bộ phóng điện của một nhóm nơ-ron dạng kim tự tháp.Các xung điện này lan đi và nhanh chóng bị suy yếu do điện trở của não, hộp sọ và da đầu. Dù vậy, tại mỗi điện cực đều có sự tiếp nhận các xung điện từ các vùng xung quanh. Tùy thuộc mức độ đồng bộ và quy mô của hoạt động trên vùng não, mức độ ảnh hưởng và lan rộng của một sóng sẽ có quy mô khác nhau.

**Eye artifact**<br>

![EOG](/images/post/2023_eye_artifact_0.png){: width="300" } <br>
*Eye artifact in eye blink (A.B) and gaze (C, D), Neto et al. 2015* <br>

Cử động mắt thường là các dao động với tần số chậm hơn đáng kể so với EEG, biên độ lớn và ảnh hưởng chủ yếu đến các khu vực phía trước trán (fronto). Các ảnh hưởng này là do trong nhãn cầu, giác mạch mang điện tích dương và võng mạc mang điện tích âm. 

![EOG](/images/post/2023_eye_artifact_1.png){: width="300" } <br>
*Source: https://www.youtube.com/watch?v=-71ppPF02qw* <br>

Khi chớp mắt, hiện tượng Bell xu hướng tự nhiên của mắt là sẽ chếch giác mạc lên trên, làm cho các điện cực EEG trên da đầu gần với mắt trở nên dương hơn. Càng xa vùng trán, mức độ dương hơn càng yếu đi và tương ứng tín hiệu cử động mắt cũng yếu đi.

![EOG](/images/post/2023_eye_artifact_3.png){: width="300" } <br>
*Source: https://www.youtube.com/watch?v=-71ppPF02qw* <br>

Tương tự, chuyển động mắt sang trái hoặc sang phải cũng gây ra các cảm ứng ngược chiều giữa các điện cực F7, F8 và cả Fp1-Fpz, Fp2-Fpz.

![EOG](/images/post/2023_eye_artifact_3.png){: width="300" } <br>
*Source: https://www.youtube.com/watch?v=-71ppPF02qw* <br>

**Muscle artifact**<br>
Khi thu dữ liệu trên một người thức, thường sẽ thu được cả các tín hiệu từ cơ mặt, cổ, hàm, cơ dưới da đầu. Các tín hiệu này thường có tần số cao 50-150Hz và biên độ lớn. Thường sẽ lấn át tín hiệu EEG.

![EOG](/images/post/2023_emg.png){: width="300" } <br>
*Burhan et al. 2017*<br>

**Nhiễu**<br>
Có nhiều nguồn nhiễu có thể ảnh hưởng đến tín hiệu EEG thu được:
Powerline noise: nhiễu do dòng điện xoay chiều dân dụng. Khi ở gần hoặc chạm tay vào các thiết bị điện dân dụng như máy giặt, tủ lạnh, tivi, hoặc chạm vào laptop đang cắm sạc khi chân tiếp đất,... sẽ làm tăng cường độ nhiễu của nguồn điện dân dụng lên cao
Nhiễu do bộ khuếch đại: bộ khuếch đại tăng cường tín hiệu của các nhiễu nhỏ và có thể làm biên độ của chúng trở nên lớn hơn, trở thành một nguồn nhiễu của dữ liệu thu được. Đặc biệt khi tín hiệu chập chờn không ổn định do tiếp xúc của điện cực với da đầu kém.
Nhiễu do ma sát của điện cực với da đầu: ma sát sẽ sinh ra điện, đặc biệt với các điện cực khô và hình thành các nhiễu.

**Các phương pháp tách các thành phần của tín hiệu**<br>
Có nhiều phương pháp và cách tiếp cận để tách tín hiệu chồng chập thành các tín hiệu thành phần, từ đó phân tích và hiểu rõ hơn hoạt động của não bộ cũng như các hiện tượng quan sát được. Có thể kể đến: Principal Component Analysis (PCA), Sparse Component Analysis (SCA), Nonnegative Matrix Factorization (NMF), Signal filters, Fourier,..

**ICA - Independent Component Analysis**<br>
ICA là một trong các phương pháp để tách các nguồn signal hình thành. Được áp dụng khi tín hiệu thu được gồm nhiều kênh. Số components tối đa có thể tách được của ICA tương ứng với số kênh dữ liệu có được. 
Ví dụ sau sử dụng dữ liệu của 9 kênh lắp bao phủ da đầu và dùng ICA tách thành các thành phần tương ứng. Có thể quan sát được những thành phần có ý nghĩa như: tín hiệu cử động mắt (IC1, IC3), hoạt động sóng theta (IC4, IC7), alpha (IC5, IC8), điện tim ECG (IC12), và thành phần cơ (IC55).

![ICA](/images/post/2023_ICA.png){: width="300" } <br>

Dù cũng có những hạn chế nhất định, tuy nhiên các thành phần thu được từ ICA cho phép phân tích một cách rất hiệu quả tín hiệu điện não.



REFERENCES
-----

EEGLAB introduction part 3: Source resolved EEG brain dynamics, https://www.youtube.com/watch?v=MzJTZuyznQ4

Background on Independent Component Analysis applied to EEG, https://eeglab.org/tutorials/ConceptsGuide/ICA_background.html

Neto, Emanuel & Allen, Elena & Aurlien, Harald & Ph.D, Helge & Eichele, Tom. (2015). EEG Spectral Features Discriminate between Alzheimer’s and Vascular Dementia. Frontiers in neurology. 6. 25. 10.3389/fneur.2015.00025. 

Burhan, N., Kasno, M.‘., Ghazali, R., Jali, M.H., & Said, M.R. (2017). Discrete Wavelet Transform Approach on the Electromyography Signal Processing during Rehabilitation Exercise.
