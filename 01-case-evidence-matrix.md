## A. Case Evidence Matrix — cá nhân

### Case 1:
| Trường | Trả lời |
|---|---|
| **Case** | Case 1 — Hallucination do model đã từng “biết” paper trước đó |
| **AI được dùng trong workflow nào?** | User query → retrieve paper → parse PDF/abstract → LLM summarize → user đọc summary → quyết định giữ/bỏ paper |
| **Người dùng chính là ai?** | Sinh viên năm cuối, nghiên cứu sinh |
| **Họ đo metric gì?** | • % summary được user giữ lại <br> • Time-to-first-useful-paper <br> • Satisfaction với summary |
| **Metric đó thuộc layer nào?** | • Time-to-first-useful-paper → Activation / Value <br> • Satisfaction → Trust <br> • % summary dùng → Engagement |
| **Metric đó chứng minh được gì?** | • User thấy workflow nhanh hơn <br> • Summary đủ readable để hỗ trợ skim paper |
| **Metric đó chưa chứng minh được gì?** | • Summary có thực sự đọc từ paper user upload không <br> • Model có đang “nhớ lại” kiến thức cũ từ pretraining thay vì grounded vào tài liệu hiện tại không <br> • Factual accuracy thực sự của summary |
| **Thiếu metric nào?** | • Citation trace rate (mỗi claim có trace về đoạn paper không) <br> • Grounding score (% claim có evidence trong PDF) <br> • Hallucination rate qua manual review |
| **Rủi ro lớn nhất** | Model thấy paper quen → thay vì đọc tài liệu thật, nó “đoán” lại nội dung từ pretraining hoặc latent memory. Dẫn đến summary nghe hợp lý nhưng lệch chi tiết, đặc biệt ở method/result mới. User khó phát hiện vì output rất tự tin. |
| **Bài học cho dashboard nhóm** | Không đo mỗi satisfaction. Cần đo grounded quality: <br> • % claim traceable về source <br> • confidence theo parsing quality <br> • % summary bị report sai/hallucination |

### Case 2
| Trường | Trả lời |
|---|---|
| **Case** | Case 2 — Workflow sử dụng khó khiến metric bị hiểu sai |
| **AI được dùng trong workflow nào?** | Search → rank → summary → user shortlist paper → mở source |
| **Người dùng chính là ai?** | Sinh viên mới làm literature review lần đầu |
| **Họ đo metric gì?** | • ≥50% paper được giữ lại <br> • % summary không cần đọc lại paper <br> • Session completion |
| **Metric đó thuộc layer nào?** | • % paper giữ lại → Engagement / Value <br> • Không đọc lại paper → Trust (nhưng lệch hướng) <br> • Session completion → Activation |
| **Metric đó chứng minh được gì?** | • User có sử dụng tool <br> • Có shortlist paper ở mức nào đó |
| **Metric đó chưa chứng minh được gì?** | • User có chọn đúng paper không <br> • Paper đó có thực sự được cite vào literature review không <br> • Workflow research có tốt hơn không |
| **Thiếu metric nào?** | • Shortlisted paper citation rate (% paper cuối cùng được cite thật) <br> • Query refinement count (user phải sửa query bao nhiêu lần) <br> • Paper usefulness score sau 1 tuần |
| **Rủi ro lớn nhất** | User mới chưa biết đọc paper → không biết đánh giá output đúng/sai. Nếu metric chỉ đo accept rate hoặc satisfaction thì team dễ hiểu nhầm rằng AI tốt, trong khi user chỉ “đành giữ đại” vì không biết chọn gì hơn. |
| **Bài học cho dashboard nhóm** | Metric có thể kéo hành vi sai. Ví dụ: optimize “không cần đọc paper nữa” sẽ khuyến khích overtrust AI. Nên chuyển sang đo decision quality thay vì usage quantity. |
