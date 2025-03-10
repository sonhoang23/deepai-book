---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.12
    jupytext_version: 1.8.2
kernelspec:
  display_name: Python 3
  name: python3
---

+++ {"id": "vDhf13ApiSAZ"}

# 4. Bias (_độ chệch_) và variance (_độ biến động_)

Năng lực của những mô hình phân loại và dự báo trong học có giám sát của machine learning thường được thể hiện qua hai khía cạnh bias và variance. Hiểu được chính xác ý nghĩa của hai khái niệm này chúng ta sẽ biết cách tạo ra những mô hình chính xác và phòng tránh các hiện tượng overfitting (mô hình _quá khớp_) và underfitting (mô hình _khớp kém_).

Vậy thì bias và variance trong machine learning có nghĩa là gì?

**Bias** có nghĩa là **độ chệch** giữa giá trị dự báo của một mô hình machine learning so với ground truth. Độ chệch lớn thì dẫn tới các dự báo của mô hình bị sai lệch. Thông thường những mô hình **quá đơn giản** được huấn luyện trên những bộ dữ liệu có kích thước lớn sẽ không học được các biểu diễn dữ liệu một cách đủ phức tạp nên thường xảy ra hiện tượng bị chệch. Vì vậy trong tình huống này chúng ta thường sử dụng mô hình **phức tạp hơn** để tận dụng khả năng biểu diễn tốt của chúng trên những tập dữ liệu kích thước lớn. Tuy nhiên một mô hình quá phức tạp cũng có khả năng xảy ra hiện tượng variance.

**Variance** là hiện tượng mô hình của bạn dự báo **thiếu ổn định** thể hiện qua ra giá trị dự báo **dao động** xung quanh giá trị ground truth. Những lớp mô hình phức tạp được huấn luyện trên tập huấn luyện nhỏ thường xảy ra hiện tượng variance và dẫn tới việc học giả mạo thông qua bắt chước dữ liệu hơn là học qui luật tổng quát. Vì vậy đối với dữ liệu mà chúng chưa được học như trên tập kiểm tra thì không được biểu diễn chính xác trong khi tập huấn luyện thì khớp tốt.

Giữa bias và variance có một sự đánh đổi qua lại trong quá trình chúng ta xây dựng và huấn luyện mô hình machine learning. Để hình dung rõ hơn về sự đánh đổi này chúng ta cùng lấy ví dụ như bên dưới.

+++ {"id": "Tgdi_h3HQlGV"}