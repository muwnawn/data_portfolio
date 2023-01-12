---
title: "Sách Naked Statistics"
date: 2023-01-07
last_modified_at: 2023-01-10T11:59:26-04:00
author_profile: true
header:
  image: "/images/STATS.jpg"
  teaser: "/images/STATS.jpg"
excerpt: ""
classes: wide
toc: true
toc_icon: "heart"
published: false
---

## 1. MÔ TẢ
### 1.1. Cuốn sách này dành cho ai?
Câu chuyện đưa tớ đến với cuốn sách này bắt nguồn từ một cuộc phỏng vấn. Đây là lần đầu tớ đi phỏng vấn sau khi tốt nghiệp và sau khi kết thúc gần hơn một năm rưỡi làm việc ở Giaohangtietkiem. Vì là lần đầu nên tớ cũng giữ tâm lý thoải mái thui và gần như không chuẩn bị gì, đặc biệt là chuẩn bị cho các bài test. Và như một sinh viên đi thi lệch tủ, có bài test thật nhưng là test tư duy từ bài toán thực tế, khác hẳn với định kiến trong đầu tớ bài test phỏng vấn là test IQ. Trong đấy có một câu cho tỷ lệ người chết vì bệnh ung thư vú giữa hai nhóm người được offer khám và nhóm tiêu chuẩn, và hỏi liệu tỷ lệ đó có giúp kết luận việc offer khám có giúp giảm tỷ lệ chết vì ung thư vú không. Để trả lời câu hỏi này thì cần kiến thức về thống kê như sample size, chất lượng sample,.. Và như một lẽ dĩ nhiên, tớ không trả lời được... may sao chị phỏng vấn rất nice, từ tốn giải thích cho tớ và thậm chí chỉ tớ một vài kiến thức khác như độ lệch chuẩn, outliner,... 

Nhưng điều tớ muốn nói ở đây không phải về việc tớ fail như nào, hay những câu hỏi phỏng vấn hay ho ra sao mà là cách mà chị phỏng vấn đã định hướng tớ về bản chất của phân tích dữ liệu hay thống kê. Tớ đã bị quá ngợp bởi các công cụ, kiến thức phức tạp xa vời mà quên mất chữ "Why" đầu tiên. Tại sao mình lại cần phân tích dữ liệu? Và trước hết tớ muốn biết tại sao mình lại cần thống kê? Vì thế tớ tìm đến cuốn sách Naked Statistics: Stripping the Dread from the Data (tạm dịch bởi vốn liếng ít ỏi của tớ là Thống kê trần trụi: Đừng sợ dữ liệu nữa).

Tóm gọn lại thì, cuốn sách này dành cho những người như tớ, **những người đang muốn tiếp cận thống kê theo hướng đơn giản và đời thực hơn**. 

### 1.2. Cuốn sách này cung cấp kiến thức gì?
**Hầu hết các kiến thức quan trọng của thống kê**, bao gồm: thống kê mô tả (Descriptive Statistics), (Deceptive Description), hệ số tương quan (Correlation), xác suất cơ bản (Basic Probability), định luật giới hạn trung tâm (The Central Limit Theorem), phân tích hồi quy (Regression Analysis).

### 1.3. Đọc sách ở đâu?
Theo như tớ tìm hiểu thì sách chưa có bản tiếng việt (nên bài viết này được viết bằng tiếng việt hj). Vậy nên hãy mua sách bản tiếng anh ở nhà sách (ví dụ như tiki nè), mua bản epub trả phí hoặc tìm với keyword "Naked Statistics pdf" để được đọc online miễn phí (không có bản epub miễn phí) nha. Ví dụ một [link](https://media.oiipdf.com/pdf/9b324d85-3b79-4dc1-b7b2-898f1cc64d45.pdf).

Hoy, giờ thì đọc sách cùng tớ nhé!

## 2. KIẾN THỨC TRỌNG TÂM
Đầu tiên thì, rất khuyến khích đọc sách đầy đủ, từ đầu đầu đến cuối (và tớ sẽ làm thế, kiến thức mà, không vội được :) nhưng dưới đây tớ sẽ lược bớt và chỉ ghi lại những kiến thức quan trọng của thống kế thui. Vì tớ muốn giữ bài viết này ngắn nhất có thể, như một chiếc note cho bản thân tớ về sau xem lại hoặc cho ai đó muốn (tạm) nắm các khái niệm về thống kê nha.

### 2.1. Tổng quan về Thống kê (Statistics)
"It’s a nice tool for making a quick comparison and bring meaning to raw data"

#### Thống kê mô tả (Descriptive Statistics)
- Thống kê mô tả giúp dễ dàng tính toán một tập dữ liệu, dễ hiểu và dễ so sánh. Một ví dụ về Thống kê mô tả là GPA, chỉ số thể hiện kết quả học tập toàn khoá của sinh viên, được tính bằng cách lấy trung bình điểm của tất cả các môn trong khoá.
- Tuy nhiên, Thống kê mô tả không phản ánh đầy đủ các yếu tố đằng sau dữ liệu. Ví dụ, những sinh viên học những môn khó hơn có thể có GPA thấp hơn nhứng sinh vieen học môn dễ hơn.

#### Thống kê suy luận (Descriptive Inference)
- Thống kê suy luận là dùng những dữ liện đã biết (bằng cách lấy mẫu - sampling) để suy luận về những dữ liệu chưa biết. Ví dụ khảo sát bầu cử, thi thử,... để từ đó suy luận được kết quá bầu cử hay trình độ sinh viên của năm đó.

#### Rủi ro và các sự kiện liên quan đến xác suất khác
- Rủi ro là 1 sự kiện liên quan đến xác suất. Ví dụ về gambling, đánh bài hay cá cược, tận dụng xác suất là luôn có rủi ro bị thua bài, mất cược tuy nhiên sau mỗi lần xảy ra thì xác suất thua giảm đi và xác suất thắng tăng lên.

#### Suy đoán các mối liên hệ đằng sau dữ liệu (**re-read**)
- Quay lại câu hỏi phỏng vấn của tớ ở đầu bài viết. Tỷ lệ người chết vì ung thư vú của nhóm được khám thấp hơn nhóm không được khám thì có kết luận được rằng việc khám giúp giảm tỷ lệ tử vong không? Không, vì nhóm được khám có thể mang những đặc điểm không liên quan đến việc khám bệnh, ví dụ như nhóm này vốn đã quan tâm đến sức khoẻ nên có thể không cần khám ung thư vú thì nhóm này vốn đã có tỷ lệ tử vong thấp hơn rùi. Vì vậy, ngoài tử vong về ung thư vú cần xét thêm cả tỷ lệ tủ vong vì các bệnh khác nữa. 
- Nhưng làm sao để biết được những mối liên hệ này? DA cần có business sense để phán đoán và dùng statistics là công cụ hỗ trợ để đưa ra kết luận có ý nghĩa nè.

#### Hạn chế của thống kê
- Về cách định nghĩa: Thống kê có thể chỉ ra cầu thủ tốt nhất, tuy nhiên không có định nghĩa thống nhất về sự tốt nhất này. Dẫn đến kết quả thống kê có thể không được công nhận.
- Về dữ liệu: Dữ liệu có thể bị hạn chế dựa trên phương thức thu thập và độ lớn của mẫu (do hạn chế về tài chính, để thu được dữ liệu như ý muốn có thể đắt đỏ)

### 2.2. Thống kê mô tả (Descriptive Statistics)
- mean: giá trị trung bình của tập dữ liệu. 
  - Ví dụ, một nhóm 5 người có thu nhập 10 triệu/ tháng có thu nhập trung bình là 10 triệu/ tháng.
- outlier: giá trị ngoại lai có thể khiến mean mất ý nghĩa. 
  - Ví dụ, nhóm nạp thêm 1 thành viên có thu nhập 100 triệu/ tháng dẫn đến thu nhập trung bình là 25 triệu/tháng. Nếu chỉ xét giá trị mean có thể bị kết luận rằng nhóm này bao gồm những người có thu nhập trung bình-cao, tuy nhiên thực chất bao gồm những người có thu nhập trung bình-thấp và chỉ duy nhất 1 người thu nhập cao đột biến.
- median: giá trị trung vị, số nằm ở giữa trong một danh sách các số được sắp xếp theo thứ tự. Với tập dữ liệu có outliers, median được sử dụng thay mean. 
  - Ví dụ, median của nhóm trước và sau khi thêm thành viên vẫn là 10 triệu/ tháng.
- frequency distrubution (theo %)
- quartiles, percentiles: phân vị, tương tự như median nhưng thay vì chia đôi thì chia 4 hoặc 100 điểm của tập dữ liệu, giúp 1 giá trị trở nên có ý nghĩa hơn trong tập dữ liệu. 
  - Ví dụ, sinh viên thi đại học đạt điểm 8/10, giá trị khi đứng 1 mình không mang nhiều ý nghĩa, không biết sinh viên này có đỗ đại học hay không. Nếu biết thêm 8 là phân vị 90 (90th percentiles) , tức là sinh viên này có điểm cao hơn 90% số sinh viên còn lại, thì khả năng đỗ đại học cao. Ngược lại nếu đề thi năm đó dễ, 8 chỉ là phân vị 40 thì khả năng đỗ của sinh viên này không cao.
- standard deviation: độ lệch chuẩn, đo _độ phân tán_ của dữ liệu so với giá trị trung bình mean. 
  - Ví dụ, 2 nhóm cùng thu nhập trung bình 25 triệu/ tháng có thể là 1 nhóm gồm 6 người cùng thu nhập hoặc 1 nhóm khác có rải thu nhập từ 1 triệu, 5, 10, 24, 50 đến 60 triệu/ tháng. Nhóm thứ 2 có độ lệch chuẩn lớn hơn nhóm 1.
  - Một ứng dụng khác của độ lệch chuẩn trong y tế. Ví dụ, một người đi khám có nồng độ oxy trong máu là 93%, thấp hơn nồng độ trung bình là 95% khiến người đó có thể hiểu rằng mình đang có vấn đề về sức khoẻ. Tuy nhiên, giá trị trung bình này được tính từ một tập giá trị cao hoặc thấp hơn 95% và độ lệch chuẩn của giá trị trung bình này là 5%, tức giá trị 93% của người này là giá trị thông thường, không có nguy hiểm.
- variance: phương sai, có ý nghĩa tương tự độ lệch chuẩn và có giá trị là căn bậc hai của độ lệch chuẩn.
- normal distribution: 





### 2.3. Sự mô tả đánh lừa (Deceptive Description)
### 2.4.
### 2.5.







(còn tiếp)

<!-- ## 3. HYPOTHESIS TESTING FOR ONE SAMPLE
### 3.1. Some term
- Confidence Intervals:
<p align = 'center'>
  <img src = "https://conversionsciences.com/wp-content/uploads/2016/09/confidence-interval-example.webp">
<p/>
- Margin of Errors:
<p align = 'center'>
  <img src = "https://conversionsciences.com/wp-content/uploads/2016/09/confidence-interval-example.webp">
<p/>
- Regression toward the mean is “the phenomenon that if a variable is extreme on its first measurement, it will tend to be closer to the average on its second measurement.” This ensures that as we continue increasing the sample size and the length of observation, the mean of our observations will get closer and closer to the true mean of the population.
- Null Hypothesis (Ho): a baseline assumption that there is no relationship between two data sets. When a statistical hypothesis test is run, the results either disprove the null hypothesis or they fail to disprove the null hypothesis.
    - Example: When taking AB test, we automatically assume Variation B is NOT a meaningful improvement over Variation A. That is our null hypothesis. Either we disprove it by showing that Variation B’s conversion rate is a statistically significant improvement over Variation A, or we fail to disprove it.
- Statistical Significance: when the p-value < the significance level
    - p-value is the probability of obtaining at least as extreme results given that the null hypothesis is true.
    - significance level (alpha) is the probability of rejecting the null hypothesis given that it is true.
     
### 3.2. Steps
- Step 1. Set up the hypotheses and check conditions
    - Hypothesis Test for One-Sample Proportion
    - Hypothesis Testing for One-Sample Mean
- Step 2. Decide on the significance level, alpha
- Step 3. Calculate the test statistic
Hypothesis Test for One-Sample Proportion
Hypothesis Testing for One-Sample Mean
- Step 4. Calculate probability value (p-value)
    - Hypothesis Test for One-Sample Proportion
    - Hypothesis Testing for One-Sample Mean
Z-table for Proportion
T-table for Mean
- Step 5. Make a decision about the null hypothesis

## 3. SOURCES
1. [STAT 500: Applied Statistics](https://online.stat.psu.edu/stat500/)
2. [A/B Testing Statistics](https://conversionsciences.com/ab-testing-statistics/#:~:text=An%20AB%20test%20is%20an,statistically%20significant%20relationship%20or%20not)
 -->
