# Product ROI Dashboard v2 — MindMesh

**Product:** MindMesh — AI Research Assistant cho sinh viên và nghiên cứu sinh  
---

## Part A — Adoption Context

### A.1 Thách Thức Nhóm Chọn

| Trường | Trả lời |
|---|---|
| Thách thức áp dụng AI | Người dùng cần lọc và chọn paper đáng đọc trong literature review, nhưng nếu AI summary sai hoặc không grounded vào nguồn thì người dùng có thể chọn sai paper. |
| Tình huống xuất phát từ ai / ở đâu? | Sinh viên năm cuối, sinh viên cao học và nghiên cứu sinh đang làm assignment, thesis, proposal hoặc literature review theo deadline. |
| Dấu hiệu bị kẹt | Người dùng mất nhiều giờ để skim paper, query nhiều lần nhưng vẫn chưa chắc paper nào đáng đọc; một số người tin summary quá nhanh mà không kiểm chứng nguồn. |
| Vì sao thách thức này đáng giải quyết? | Nếu làm tốt, MindMesh giảm thời gian sàng lọc paper và giúp người dùng ra quyết định đọc sâu tốt hơn; nếu làm sai, sản phẩm tạo hallucination, overtrust và claim marketing vượt quá evidence. |

### A.2 Sản Phẩm / Công Cụ AI

| Trường | Trả lời |
|---|---|
| Tên sản phẩm / công cụ AI | MindMesh — AI Research Assistant |
| Người dùng chính | Sinh viên đại học năm cuối, nghiên cứu sinh, junior researcher |
| Bối cảnh sử dụng | Người dùng nhập research topic/query, nhận danh sách paper liên quan, đọc summary có citation, shortlist paper và phản hồi useful/not useful. |
| Mục tiêu kinh doanh / học tập / vận hành | Giúp người dùng chọn được ít nhất 1 paper đáng đọc trong session đầu; tăng retention 7 ngày; giảm rework do chọn paper sai; tạo trust bằng citation và audit trail. |
| Không nằm trong phạm vi | Không thay thế việc đọc paper gốc; không đưa kết luận học thuật cuối cùng; không tự viết literature review hoàn chỉnh; không khuyến nghị dùng summary làm citation thay paper gốc. |

### A.3 2-4 Quy Trình Chính

| # | Tên quy trình | Vai trò AI | Điểm người kiểm tra | Khi AI sai thì xử lý thế nào? |
|---|---|---|---|---|
| 1 | Query paper + rank relevance | Search, classify topic, rerank paper theo relevance, metadata và tín hiệu chất lượng | Người dùng xem top results, title, abstract, citation/source và chọn paper để mở sâu | Cho phép reject result, ghi lý do "irrelevant/low quality/duplicate", đưa vào relevance review set |
| 2 | Summarize single paper | Parse PDF/abstract, tạo summary theo cấu trúc: main idea, method, result, limitation, why it matters | Người dùng mở citation trace và đối chiếu claim quan trọng với đoạn paper gốc | Nếu citation thiếu hoặc parsing quality thấp, chuyển sang abstract-only summary, gắn warning và đưa vào hallucination QA sample |
| 3 | Shortlist paper for reading decision | Recommend paper nên đọc sâu hơn dựa trên query, summary và metadata | Người dùng quyết định keep/skip và có thể sửa lý do chọn | Nếu user report paper không phù hợp, log decision error và yêu cầu người dùng kiểm tra paper gốc trước khi dùng |

### A.4 Chẩn Đoán Nhanh ADKAR

| Stage | Câu hỏi | Nhận định nhóm |
|---|---|---|
| Awareness | Người dùng có biết AI này giúp gì không? | Có, họ hiểu MindMesh giúp lọc và hiểu nhanh paper. Tuy nhiên cần nói rõ là "hỗ trợ quyết định paper nào nên đọc sâu", không phải "đọc thay". |
| Desire | Người dùng có muốn dùng không? | Có, vì pain point lớn và có deadline. Pilot trước ghi nhận khoảng 45% đạt aha moment và khoảng 30% quay lại trong 7 ngày. |
| Knowledge | Người dùng có biết dùng đúng không? | Chưa ổn định. Người mới làm research dễ tin summary hoặc accept paper vì không biết đánh giá output. |
| Ability | Người dùng có đủ access, thời gian, kỹ năng không? | Tương đối đủ, nhưng cần citation trace rõ, warning khi PDF parse kém và UI giúp kiểm chứng nguồn nhanh. |
| Reinforcement | Có cơ chế khiến họ quay lại dùng không? | Có thể có nếu shortlist thật sự hữu ích qua nhiều assignment/topic, nhưng cần đo weekly repeat theo task thật, không chỉ login. |

**Barrier chính:** Knowledge + Ability. Người dùng muốn dùng AI, nhưng chưa luôn biết khi nào nên tin summary, khi nào phải mở paper gốc và khi nào cần report lỗi.

### A.5 3 Tactic Áp Dụng

| Tactic | Nhắm vào barrier nào? | Áp dụng cho quy trình nào? | Người phụ trách | Khi nào hoàn thành? |
|---|---|---|---|---|
| Citation-first summary: mỗi claim quan trọng phải có link/đoạn nguồn | Knowledge, Trust | Summarize single paper, shortlist decision | Product Owner + ML Engineer | Trước pilot v2 |
| Confidence + parsing quality warning: cảnh báo khi PDF parse kém hoặc citation coverage thấp | Ability, Trust | Summarize single paper | ML Engineer + QA Lead | Tuần 1 của pilot v2 |
| Shortlist reason chips: user chọn lý do keep/skip paper | Knowledge, Reinforcement | Shortlist paper for reading decision | Product Owner | Trước pilot v2 |

---

## Part B — ROI Dashboard

### B.1 Chỉ Số Toàn Sản Phẩm

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % user chọn được ít nhất 1 paper "đáng đọc" trong session đầu | 45% pilot nội bộ | 60% trong pilot v2 | Product event log + post-session survey | Product Owner | User có thể chọn đại vì không biết đánh giá paper | Chỉ tính active khi paper được mở source/citation hoặc được giữ sau review cuối session |
| Retention / Value | % user quay lại dùng cho topic/assignment khác trong 7 ngày | 30% | 40% | Auth log + project/topic log | Growth Owner | Retention có thể do deadline, không phải do value | Tách cohort theo assignment deadline và đo repeat trên task mới |
| Trust / Quality | Grounded claim rate: % claim quan trọng trong summary có citation trace đúng | Chưa có benchmark chính thức | >=85% trên QA sample 30 paper/tuần | QA review sheet + citation trace log | QA Lead | Sample nhỏ hoặc dễ quá sẽ làm đẹp chỉ số | Stratified sample theo field, PDF complexity và paper length |
| Value | Time-to-first-useful-paper | Claim cũ: ~3 giờ thủ công; chưa có user study thật | <=15 phút trong controlled pilot, không dùng làm marketing claim nếu chưa đủ sample | Screen/session timing + survey | Product Owner | Tốc độ nhanh có thể đổi lấy chất lượng kém | Chỉ đạt target nếu grounded claim rate >=85% và repeat inquiry/report lỗi không tăng |

### B.2 Chỉ Số Theo Từng Quy Trình

#### Quy trình 1 — Query Paper + Rank Relevance

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % query trả về >=5 paper có metadata đầy đủ | Chưa đo chính thức | >=90% query hợp lệ | Search/retrieval log | ML Engineer | Metadata đầy đủ không có nghĩa là paper liên quan | Ghép với relevance acceptance và reject reason |
| Engagement | % user mở ít nhất 2 paper từ top 10 results | Chưa đo | >=55% session | Product event log | Product Analyst | User mở nhiều vì kết quả nhiễu | Theo dõi thêm query refinement count và reject rate |
| Productivity | Median time từ query đến paper đầu tiên được mở source | Chưa đo; mục tiêu OKR <=15 phút đến paper hữu ích | <=5 phút đến paper đầu tiên, <=15 phút đến paper hữu ích | Session timing | Product Owner | Tối ưu tốc độ có thể đẩy paper kém lên top | Điều kiện pass: top-10 relevance QA score >=4/5 |
| Quality | Top-10 relevance QA score | Chưa có benchmark | >=4/5 trên sample hàng tuần | Manual QA + user reject reason | QA Lead | QA nội bộ có thể không giống nhu cầu user | Kết hợp expert review và user usefulness score sau 1 tuần |
| Trust | Query refinement count trước khi có paper hữu ích | Chưa đo | Median <=2 lần sửa query | Query log + session outcome | Product Analyst | User mới không biết sửa query nên count thấp giả tạo | Thêm "no useful result" button để không ép user refine |
| Value | % shortlisted paper từ top 10 được cite/đọc sâu trong 7 ngày | Chưa đo | >=35% | User follow-up survey + project save log | Research Advisor | User có thể không quay lại cập nhật | Gửi follow-up survey nhẹ và cho user mark "used in work" |

#### Quy trình 2 — Summarize Single Paper

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % opened paper có summary generate thành công | Chưa đo | >=90% với paper parse được | Summary service log | ML Engineer | Success kỹ thuật có thể che summary sai | Ghép với citation coverage và QA pass rate |
| Engagement | % summary được user mở citation trace ít nhất 1 lần | Chưa đo | >=50% summary trong pilot v2 | UI event log | Product Owner | User không mở citation có thể do UI khó thấy | Đưa citation trace vào mặc định, không giấu sau thao tác phụ |
| Productivity | Median summary generation time | Chưa đo | <=30 giây cho abstract/PDF text bình thường | LLM + parser latency log | ML Engineer | Nhanh nhưng parse thiếu bảng/equation | Hiển thị parsing quality score trước summary |
| Quality | Hallucination/report error rate trên summary | Chưa có benchmark; risk register xem hallucination là risk cao | <=5% summary bị report lỗi nghiêm trọng | Report button + QA review | QA Lead | User không report vì không phát hiện lỗi | Weekly expert review 20-30 paper, không chỉ dựa vào user report |
| Trust | Citation coverage: % sentence/claim quan trọng có source trace | Chưa đo | >=85% | Citation trace log + QA sample | QA Lead | Citation có thể đúng đoạn nhưng claim diễn giải sai | QA review kiểm tra cả trace và entailment |
| Value | % summary được đánh giá "đúng và hữu ích" >=3/4 | OKR cũ: >=75% | >=80%, chỉ tính khi citation coverage đạt target | Post-summary rating | Product Owner | Satisfaction dễ bị overtrust | Rating kèm câu hỏi "Bạn đã kiểm chứng citation chưa?" |

#### Quy trình 3 — Shortlist Paper For Reading Decision

| Layer | Metric | Baseline | Target | Data source | Owner | Red-team risk | Fix |
|---|---|---:|---:|---|---|---|---|
| Activation | % session có ít nhất 1 paper được keep/skip có lý do | Chưa đo | >=60% session | Shortlist event log | Product Analyst | Keep/skip có thể là click tùy tiện | Bắt buộc chọn reason nhẹ: relevant/method/useful/irrelevant/duplicate |
| Engagement | % user quay lại shortlist trong 7 ngày và chỉnh sửa quyết định | Chưa đo | >=25% active users | Project list history | Growth Owner | Sửa nhiều có thể do chất lượng ban đầu kém | Tách edit positive (add note) và edit negative (remove wrong paper) |
| Productivity | Time từ query đầu tiên đến shortlist 3 paper | Chưa đo | <=20 phút trong controlled pilot | Session timing | Product Owner | Shortlist nhanh không đảm bảo đúng | Ghép với paper usefulness score sau 1 tuần |
| Quality | Shortlisted paper usefulness score sau 1 tuần | Chưa đo | >=3.5/5 | Follow-up survey + project log | Research Advisor | User quên đánh giá hoặc bias vì đã chọn rồi | Sample follow-up bắt buộc với cohort pilot nhỏ |
| Trust | Override/remove rate sau khi user đọc paper gốc | Chưa đo | <=20% paper bị remove vì summary/ranking misleading | Project edit log + remove reason | QA Lead | Remove thấp có thể do user không đọc sâu | Chỉ tính với paper có source-open event |
| Value | % user đạt "first useful paper" trong <=15 phút | OKR: >=50% user chọn >=1 paper trong <=15 phút | >=60%, với QA quality pass | Event log + survey | Product Owner | Có thể biến thành vanity metric nếu chỉ đo chọn paper | Chỉ tính paper được user đánh giá useful hoặc còn trong shortlist sau 7 ngày |

---

## Part C — Dashboard Mock

```text
┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ PRODUCT HEALTH                       │ │ WORKFLOW 1: SEARCH / RANK            │
│ Metric: First useful paper <=15 min  │ │ Metric: Top-10 relevance QA score    │
│ Current: 45% pilot / Target: 60%     │ │ Current: N/A / Target: >=4/5         │
│ Status: AMBER                        │ │ Status: AMBER                        │
│ Action if red: split by query type   │ │ Action if red: tune rerank + filters │
└──────────────────────────────────────┘ └──────────────────────────────────────┘

┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ WORKFLOW 2: SUMMARY QUALITY          │ │ TRUST / GROUNDEDNESS                 │
│ Metric: Hallucination report rate    │ │ Metric: Grounded claim rate          │
│ Current: N/A / Target: <=5%          │ │ Current: N/A / Target: >=85%         │
│ Status: RED until benchmark exists   │ │ Status: RED until QA sample exists   │
│ Action if red: citation-first + QA   │ │ Action if red: abstract-only fallback│
└──────────────────────────────────────┘ └──────────────────────────────────────┘

┌──────────────────────────────────────┐ ┌──────────────────────────────────────┐
│ VALUE / RETENTION                    │ │ DECISION                             │
│ Metric: 7-day return on new task     │ │ Continue / Pivot / Kill: PIVOT       │
│ Current: 30% / Target: 40%           │ │ Metric mạnh nhất: useful paper <=15m │
│ Status: AMBER                        │ │ Before scale: QA + citation benchmark│
│ Action if red: improve shortlist UX  │ │ Owner: Product Owner + QA Lead       │
└──────────────────────────────────────┘ └──────────────────────────────────────┘
```

**Logic khi chỉ số đỏ:**

| Ô đỏ | Hành động |
|---|---|
| Product Health đỏ | Không scale acquisition; phân tích cohort theo field, query type và experience level. |
| Search/Rank đỏ | Sửa reranking, lọc duplicate/low relevance, review top-10 sample hàng tuần. |
| Summary Quality đỏ | Freeze prompt rollout, bắt buộc citation-first summary, tăng expert QA sample. |
| Groundedness đỏ | Chuyển summary rủi ro sang abstract-only, cảnh báo parsing thấp và không dùng claim marketing "source-grounded". |
| Value/Retention đỏ | Kiểm tra paper usefulness sau 7 ngày, không tối ưu DAU/prompt count. |
| Decision đỏ | Pivot scope về search + single-paper summary, hoãn cross-paper synthesis. |

---

## Part D — Decision Memo

# Decision Memo — MindMesh

1. Nhóm khuyến nghị: **pivot with guardrails**. Tiếp tục phát triển MindMesh, nhưng không scale rộng và chưa mở rộng sang Cross Paper Synthesizer cho đến khi Search/Rank và Single Paper Summary đạt benchmark grounded quality.

2. Chỉ số mạnh nhất để bảo vệ quyết định là: **% user đạt first useful paper trong <=15 phút, chỉ được tính khi paper còn trong shortlist sau 7 ngày hoặc được đánh giá useful**. Đây là evidence tốt hơn login/prompt count vì nó đo outcome thật của workflow literature review: người dùng có tìm được paper đáng đọc hay không.

3. Metric hoặc giả định nhóm đã sửa sau red-team là:  
   **V1:** Dùng "prompt count/user/week", "% summary được user giữ lại" và claim "giảm từ 3 giờ xuống 15 phút" để chứng minh adoption/value.  
   **V2:** Đổi thành "first useful paper <=15 phút + paper còn trong shortlist sau 7 ngày", "grounded claim rate >=85%" và "hallucination/report error rate <=5%". V1 yếu vì đo activity và satisfaction dễ bị overtrust; V2 tốt hơn vì gắn tốc độ với chất lượng, citation và outcome sau khi người dùng có thời gian kiểm chứng.

4. Trước khi scale, nhóm phải:
   1. Build benchmark QA 30 paper/tuần cho relevance, grounded claim rate và hallucination — QA Lead + Research Advisor, hoàn thành trước pilot v2.
   2. Thêm citation trace, parsing quality warning và abstract-only fallback — ML Engineer, hoàn thành trong tuần 1 pilot v2.
   3. Tách marketing claim khỏi goal metric: không dùng claim "3 giờ xuống 15 phút" public cho đến khi có controlled pilot đủ sample — Product Owner, hoàn thành trước khi update landing/pitch deck.

---

## Red-team và sửa v2

### Nhóm mình bị red-team

| Red-team risk | Metric / giả định bị chất vấn | Nhóm sửa gì ở v2? |
|---|---|---|
| CFO | "User chọn paper" chưa chứng minh ROI/value nếu paper đó không được dùng thật | Thêm follow-up sau 7 ngày: paper còn trong shortlist, được đọc sâu hoặc được cite/use trong assignment |
| User | Satisfaction cao có thể là overtrust vì user mới không biết summary sai | Thêm grounded claim rate, citation trace, warning khi parsing thấp và expert QA sample |
| Risk | AI hallucinate nhưng output nghe tự tin, dễ làm người dùng chọn sai paper | Thêm hallucination/report error rate, rollback prompt/ranking khi trust giảm, abstract-only fallback |
| Workflow Owner | Data source quá chung chung như "analytics" hoặc "survey" | Ghi rõ event log, QA review sheet, citation trace log, issue tracker, post-session/follow-up survey |

### Ít nhất 2 thay đổi cụ thể từ v1 sang v2

| # | V1 có vấn đề gì? | V2 sửa thành gì? | Vì sao sửa này tốt hơn? |
|---|---|---|---|
| 1 | Đo "prompt count/user/week" như engagement | Đo "% user quay lại dùng cho topic/assignment khác trong 7 ngày" | Đo task thật và retention theo nhu cầu học tập, không khuyến khích spam prompt |
| 2 | Đo "% summary được user giữ lại" | Đo "grounded claim rate", "citation coverage" và "hallucination/report error rate" | Kiểm tra factual quality và source-grounding, không dựa hoàn toàn vào cảm giác của user |
| 3 | Dùng claim "3 giờ xuống 15 phút" như evidence marketing | Giữ "<=15 phút đến first useful paper" là goal nội bộ, chỉ pass nếu quality/trust ổn | Tránh marketing claim vượt evidence và không đánh đổi tốc độ lấy sai sót |


