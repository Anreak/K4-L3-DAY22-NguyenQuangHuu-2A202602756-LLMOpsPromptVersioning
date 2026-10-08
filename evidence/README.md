# Báo cáo đánh giá và phân tích kết quả RAGAS

Tài liệu phân tích so sánh hiệu quả giữa hai phiên bản Prompt V1 và Prompt V2 trong hệ thống RAG.

## 1. Bảng so sánh chỉ số RAGAS

| Chỉ số | Prompt V1 (Strict Concise) | Prompt V2 (Detailed Explanatory) | Mục tiêu chuẩn | Đạt mục tiêu |
|---|---|---|---|---|
| Faithfulness | 0.8725 | 0.8416 | >= 0.80 | Có |
| Answer Relevancy | 0.8841 | 0.8650 | >= 0.80 | Có |
| Context Recall | 0.9800 | 0.9750 | - | Có |
| Context Precision | 0.9633 | 0.9580 | - | Có |

Note: Cả hai phiên bản đều vượt mục tiêu độ trung thực (faithfulness >= 0.8) theo yêu cầu của bài thực hành.

## 2. Phân tích so sánh V1 và V2

### Vì sao Prompt V1 có điểm Faithfulness cao hơn V2:
- Prompt V1 được thiết kế với phong cách ngắn gọn, trực diện và giới hạn chặt chẽ phạm vi thông tin trong ngữ cảnh được cung cấp (retrieved context).
- Prompt V2 yêu cầu giải thích chi tiết, mở rộng diễn giải. Trong quá trình diễn giải sâu, mô hình ngôn ngữ có xu hướng đưa thêm từ ngữ bổ trợ hoặc suy diễn ngoài văn bản gốc, làm giảm nhẹ điểm tính trung thực từ 0.8725 xuống 0.8416.
- V1 đảm bảo tính xác thực thông tin cao hơn và hạn chế hiện tượng ảo giác (hallucination) hiệu quả hơn trong các tác vụ tra cứu thông tin kỹ thuật.

### Vì sao Prompt V1 có Answer Relevancy cao hơn:
- V1 tập trung trả lời thẳng vào trọng tâm câu hỏi mà không bổ sung các thông tin râu ria, giúp vector biểu diễn ngữ nghĩa của câu trả lời khớp sát hơn với truy vấn của người dùng.

### Kết luận về định tuyến A/B:
- Prompt V1 phù hợp nhất cho môi trường hỏi đáp kỹ thuật, tra cứu nghiệp vụ yêu cầu độ chính xác tuyệt đối và tối ưu hóa chi phí token.
- Prompt V2 phù hợp hơn cho môi trường hỗ trợ đào tạo hoặc hướng dẫn người dùng mới, nơi cần diễn giải trực quan và mở rộng bối cảnh.
