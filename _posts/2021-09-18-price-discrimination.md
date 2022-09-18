---
title: '[Vi] Kết hợp phân tích dữ liệu và chiến thuật phân biệt giá tối ưu doanh thu ngắn hạn cho hãng độc quyền'
date: 2021-09-18
permalink: /posts/vi/2021/09/price-discrimination-and-ds/
tags:
  - marketing
  - price discrimination
  - Vietnamese
---

![Poster](/images/post/price_discrimination.jpeg){: width="70%" }<br>
Dẫn nhập
-----
Làm sao để tối ưu doanh thu là câu hỏi muôn thuở của những nhà kinh doanh. Sự dồi dào của dữ liệu hiện nay mở ra nhiều tiềm năng cho việc khai thác và ứng dụng, nhưng thường sẽ cần kết hợp với một chiến thuật kinh doanh nào đó. Mô hình Marketing-Mix cổ điển xét đến việc tác động đến 4 nhân tố sản phẩm, giá, kênh phân phối và promotion (quảng bá và khuyến mãi). Bài này nói về ứng dụng Data analysis và chính sách phân biệt giá hoàn hảo ( perfect price discrimination - PPD ) - một chiến thuật tối ưu doanh thu kinh điển cho hãng độc quyền, nhắm vào nhân tố giá.

Nội dung
------
------
(I) Hãng độc quyền là gì?  (II) Phân biệt giá là gì? (III) Làm sao DA có thể thúc đẩy PPD? (IV) Studies liên quan? (V) Các vấn đề liên quan?

(I) Hãng độc quyền là gì?
-----
Khi đi tìm hướng tối ưu doanh thu cho các hãng (firms), người ta thấy rằng các hãng thường có đặc điểm khác nhau ở một mức độ nhất định, không có phương pháp tối ưu cho tất cả các hãng. Vì vậy, họ chia các hãng thành 4 loại tương ứng với 4 thị trường: độc quyền (monopoly), độc quyền tập đoàn (oligopoly), cạnh tranh độc quyền (monopolistic competition), cạnh tranh hoàn hảo (perfect competition). Trong đó hãng độc quyền là hãng có khả năng chi phối và thiết lập giá mà người tiêu dùng sẽ phải chấp nhận, như thị trường điện, thị trường xăng dầu. Các hãng viễn thông thường được phân loại vào nhóm độc quyền tập đoàn, tuy nhiên ở một mức độ nhất định, các hãng này cũng có khả năng thiết lập giá. <br>

![](/images/post/market_concerntration.png){: width="70%" }<br>

(II) Phân biệt giá là gì?
-----

*Ngưỡng chấp nhận chi trả - đường cầu* <br>
Mức độ nhạy cảm của mỗi người dùng với giá cùng một sản phẩm là khác nhau tại cùng một thời điểm. Với một chiếc điện thoại Iphone X, có người sẽ cho rằng mức giá 20 triệu là quá đắt, có người lại cho rằng đây là mức giá hời. Mức giá cao nhất mà một người dùng sẵn sàng chi trả để mua sản phẩm gọi là ngưỡng chấp nhận chi trả của người dùng đó (demand price). 

![](/images/post/demand_curve.png){: width="70%" }<br>

Số lượng sản phẩm mà người dùng chấp nhận mua tại mỗi mức giá gọi là đường cầu (demand curve). Tổng cộng các đường cầu cá nhân hình thành đường cầu thị trường. <br>

*Chính sách phân biệt giá là gì?* <br>
Nếu như ta biết rằng mỗi người dùng sẽ chấp nhận một mức giá khác nhau, thì ý tưởng tối ưu doanh thu tự nhiên sẽ là áp dụng các mức giá khác nhau cho người dùng. Chiến thuật này gọi là phân biệt giá. Có 3 loại phân biệt giá cổ điển là cấp 1 (hay phân biệt giá hoàn hảo), cấp 2, cấp 3. Tạm thời ta sẽ chỉ xét cấp 1.

*Phân biệt giá hoàn hảo*<br>
Ở phân biệt giá hoàn hảo, ta sẽ bán cho từng người dùng ở đúng mức giá tối đa mà người dùng chấp nhận chi trả cho mỗi sản phẩm, và từ đó doanh thu thu được sẽ là tối đa. <br>
Ví dụ, ta bán xà bông cho 2 người A và B. A sẽ mua 1 cục xà bông nếu giá cục đó dưới 10\$, sẽ mua cục thứ 2 nếu cục đó dưới 5\$ và không có nhu cầu mua cục thứ 3; B sẽ mua 1 cục xà bông nế giá cục đó dưới 5\$ và không có nhu cầu mua cục thứ 2.
* Nếu ta không áp dụng phân biệt giá, bán với giá công khai 8\$ → A sẽ mua 1 cục, B không chấp nhận mua → doanh thu = 8\$ (diện tích $S_0$).
* Nếu ta áp dụng phân biệt giá cấp 1, bán cho A với giá 10\$, B với giá 5\$ → A sẽ mua 1 cục, B sẽ mua 1 cục → doanh thu 15\$ (diện tích $S_0+ S_1+ S_2$).
* Nếu ta áp dụng phân biệt giá cấp 1, bán cho A với giá 10\$, khuyến mãi nếu mua cục thứ 2 với giá 5\$, bán cho B với giá 5\$ → A mua 2 cục, 1 cục 10\$ và 1 cục 5\$, B mua 1 cục 5\$ → tổng doanh thu tối ưu là 20\$ (diện tích $S_0 + S_1+ S_2+ S_3$).

![](/images/post/surplus.png){: width="70%" }<br>

(III) Làm sao DA có thể thúc đẩy được PPD
-----

**Hai điều kiện của PPD** <br>

Để có thể áp dụng chính sách phân biệt giá hoàn hảo, hãng cần đảm bảo được 2 điều kiện:
* C1: Có khả năng nhận diện ngưỡng chấp nhận chi trả của người dùng
* C2: Có khả năng áp dụng mức giá đó cho từng người.

C2 phụ thuộc đặc thù của hãng, trong khi C1 đòi hỏi hãng phải hiểu rất rõ người dùng và cá nhân hóa được mức giá cho họ. Đây thường là lợi thế của việc phân tích dữ liệu.Các hãng thu thập được thông tin của người dùng giả sử là một ma trận X và xây dựng dự đoán, áp dụng theo 2 hướng là:
* Phân biệt giá đến từng người dùng
* Phân biệt giá đến từng mức sản lượng.
* Phân biệt giá từng người dùng 

Ta kỳ vọng phân biệt giá tới từng người dùng và gia tăng tỷ lệ người tiêu dùng quyết định “mua” thay vì “không mua”. Phân biệt này thường áp dụng cho các mặt hàng bán 1 lần hoặc 1 sản phẩm. Mỗi người dùng sẽ có một mức giá mà cao hơn mức đó người dùng sẽ quyết định không mua, nhiệm vụ của mô hình là dự đoán được mức giá này: $P=  f(X)$ <br>
Đây là một mô hình supervise và có thể áp dụng các kỹ thuật thông thường.

*Phân biệt giá đến từng mức sản lượng* <br>
Không phải lúc nào người dùng quyết định “mua” là đã làm hài lòng nhà kinh doanh. Như ví dụ bán xà bông phía trên, ta không chỉ muốn người dùng mua, mà còn muốn người dùng mua nhiều cục xà bông. <br>
$\Rightarrow$ Ta kỳ vọng phân biệt giá tới từng mức sản lượng, để người dùng không chỉ quyết định mua mà còn mua nhiều hơn. Nhiệm vụ của mô hình là xác định được đường cầu cá nhân của từng người dùng, giả thiết đơn giản là: $Q = a*P +b$. Trong đó a đại diện cho mức độ nhạy cảm với giá của người dùng, ta kỳ vọng các dữ liệu về người dùng $X$ có thể giải thích được $a$, hay $a = f(X)$ và mô hình dự đoán sẽ có dạng: $Q = f(X)*P +b$ <br>

Hoặc ta cũng có thể sử dụng một mô hình đề xuất sau:
* B1. Ước lượng hệ số nhạy cảm với giá của người dùng đã quan sát $a = dQ/dP$, và $b = mean( Q - a*P)$
* B2. Xây dựng model dự đoán tham số đường cầu cá nhân cho tất cả người dùng $[ a,b ] = f(X)$ . Việc này có thể thực hiện đơn giản bằng một mạng Nơ-ron nhân tạo 2 notes đầu ra.
Các mô hình có thể đa dạng, tuy nhiên đầu ra ta sẽ xác định được ở mỗi mức sản lượng, thì người dùng sẽ chấp nhận trả mức giá cao nhất là bao nhiêu. <br>

**Triển khai phân biệt giá**<br>
Vấn đề còn lại là làm sao để thuyết phục người dùng phân mức giá cao là họ không bị hớ. Hành vi của người dùng tự nhiên khi không áp dụng phân biệt giá và khi áp dụng là có thể khác nhau. Nếu người dùng biết rằng người khác có thể mua với mức giá thấp hơn thì hành vi của họ có thể thay đổi và hàm cầu cũng thay đổi. <br>
Một số giải pháp có thể là: <br>
* Đặt giá niêm yết cao và đặt mức khuyến mãi cho từng người dùng hoặc từng mức sản lượng sao cho mức giá sau khi trừ đi khuyến mãi đúng bằng “ngưỡng chấp nhận chi trả tự nhiên”.
* Chia thành các nhãn sản phẩm đặc biệt cho từng người dùng, mà đặc tính sản phẩm về cơ bản là như nhau nhưng có mức giá khác nhau.

Dù áp dụng theo hình thức nào thì người dùng luôn phải bị động và không thể kỳ vọng hoặc tác động để thay đổi chính sách giá áp dụng cho mình, nếu không kỳ vọng và ngưỡng chấp nhận chi trả của người dùng sẽ thay đổi theo hướng giảm.

(IV) Studies liên quan
-----

Thường các hãng không công bố lợi ích của chính sách phân biệt giá do liên quan đến vấn đề pháp lý (xem phần V) và tránh ảnh hưởng đến tâm lý người dùng. Tuy nhiên một số nghiên cứu cho thấy PPD kết hợp với big data có tiềm năng lớn gia tăng lợi nhuận cho các hãng. Shiller (2014) sử dụng mô phỏng cho thấy PPD khi sử dụng dữ liệu trình duyệt web cho tiềm năng gia tăng lợi nhuận là 12.2% cao hơn so với PPD sử dụng dữ liệu demographic (0.8%). Nghiên cứu của Baker, Kiewell and Winkler cho thấy nếu các hãng có thể gia tăng 1% giá mà không làm ảnh hưởng đến sản lượng thì sẽ làm gia tăng 8.7% lợi nhuận hoạt động và khoảng 30% mức giá mà các hãng đưa ra là chưa tối ưu.

(V) Các vấn đề liên quan
-----

*Thặng dư tiêu dùng*<br>
Giả sử bạn kỳ vọng một sản phẩm có giá 10\$, tuy nhiên khi mua, bạn phát hiện giá sản phẩm chỉ có 5\$ => phần chênh lệch $10-5 = 5$ được gọi là thặng dư tiêu dùng. Khi các hãng phân biệt giá và áp dụng mức giá cho người dùng tại ngưỡng chấp nhận chi trả, thì thặng dư tiêu dùng =0. Điều này được cho là làm thiệt hại cho người tiêu dùng.

*Vấn đề pháp lý* <br>
Nhằm hạn chế ảnh hưởng của các chính sách phân biệt giá đến người tiêu dùng, EU và Mỹ đều có những điều khoản hạn chế các chính sách phân biệt giá của các hãng (xem thêm [3], [5] ).
Gia tăng doanh thu dài hạn
Mặc dù tiềm năng trong việc gia tăng doanh thu ngắn hạn, các chính sách phân biệt giá có thể ảnh hưởng đến mức trung thành của khách hàng. Thường các chính sách này sẽ cần đi kèm với các giải pháp cải thiện mức độ hài lòng người dùng. Và các giải pháp cải tiến chất lượng sản phẩm, dịch vụ vẫn là nhân tố cốt lõi để có thể gia tăng doanh thu dài hạn.


REFERENCES
-----

[1] Big data and first-degree price discrimination, https://www.bruegel.org/blog-post/big-data-and-first-degree-price-discrimination

[2]Using big data to make better pricing decisions, https://www.mckinsey.com/business-functions/marketing-and-sales/our-insights/using-big-data-to-make-better-pricing-decisions?utm_source=Bruegel+Updates&utm_campaign=656e7da39b-Blogs+review+11%2F02%2F2017&utm_medium=email&utm_term=0_eb026b984a-656e7da39b-278510293

[3] Birget, David, Big Data and Price Discrimination (June 1, 2017). Available at SSRN: https://ssrn.com/abstract=3096457 or http://dx.doi.org/10.2139/ssrn.3096457

[4] Liu, Yi & Yildirim, Pinar & Zhang, Z.. (2019). Artificial Intelligence and Price Discrimination. https://www.researchgate.net/publication/337856177_Artificial_Intelligence_and_Price_Discrimination

[5] AI-facilitated price discrimination and the EU acquis communautaire: will the law cope with a pricing revolution?
, https://www.academia.edu/35823318/AI-facilitated_price_discrimination_and_the_EU_acquis_communautaire_will_the_law_cope_with_a_pricing_revolution