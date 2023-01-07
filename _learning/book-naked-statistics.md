---
title: "Sách Naked Statistics"
date: 2023-01-07
<!-- last_modified_at: 2022-12-26T11:59:26-04:00 -->
author_profile: true
header:
  image: "/images/STATS.jpg"
  teaser: "/images/STATS.jpg"
excerpt: ""
classes: wide
toc: true
toc_icon: "heart"
published: true
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

### 2.1. Thống kê (Statistics)
"It’s a nice tool for making a quick comparison"

<!-- ### 2.2. Thống kê mô tả (Descriptive Statistics) -->

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
