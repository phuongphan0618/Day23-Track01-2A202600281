# Ngày 23 — Change Management & AI Adoption

> **Version:** `claude-v1` · **Last sync:** 2026-05-11 · **Spec:** [SKELETON-v3-codex.md](../../SKELETON-v3-codex.md) v4

> AI lan rất nhanh khi nó gây wow. AI chỉ được adopt thật khi nó trở thành cách làm việc mặc định.
>
> Hôm nay học cách diagnose tại sao AI projects stall — dùng AI Adoption Stack, ADKAR, metric ladder, 25 tactics — và build **Product ROI Dashboard** cụ thể cho **1 product** thật của team với **2-4 core workflows extracted**, đi qua loop **Build → Present → Red-Team → Revise** (09:00-13:00).

---

## Tổng quan buổi học (v4 iterative loop)

```text
v4 5-BLOCK FLOW — 240 min, 09:00-13:00 absolute
┌─────────────────────────────────────────────────────────────────────────────┐
│ Block 1 — Lecture (09:00-10:00, 60')                                         │
│   Wow≠Adoption + Metrics ladder + Measurement Trap + Gartner Lite + ADKAR    │
│   + 25 tactics overview (Slides #1-22, 4 polls/cold-calls)                   │
│ Block 2 — Case study + present (10:00-11:00, 60')                            │
│   30 min group research → 25 min present round → 5 min synthesis             │
│   Cases: Nansen / Stripe / MS / DWP-GDS / Klarna / IBM Watson / KPMG / JPM   │
│ Block 3 — Product ROI Dashboard v1 build (11:00-12:00, 60')                  │
│   Phase 0 (10') Pick 1 product + extract 2-4 core workflows on whiteboard    │
│   Phase 1 (20') Part A Adoption Context                                      │
│   Phase 2 (25') Part B v1 cols 1-6 (B.1 product-level + B.2 per-workflow)    │
│   Phase 3 (5')  Part C dashboard mock                                        │
│ Block 4 — Red-team round (12:00-12:30, 30')                                  │
│   Present v1 + cross-team attack 4 roles CFO/User/Risk/Workflow              │
│   → fill Part B col 7 Red-team risk                                          │
│ Block 5 — Revise + submit (12:30-13:00, 30')                                 │
│   Phase 1 (20') Col 8 Fix + ≥2 mandatory changes                             │
│   Phase 2 (5')  Part D Decision Memo                                         │
│   Phase 3 (5')  Push repo cá nhân + share link Discord #day23-submissions    │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Lecture (Block 1, 09:00-10:00)** dạy framework cô đọng: AI adoption journey + AI Adoption Stack + Gartner-Lite + ADKAR + Metrics ladder + Measurement Trap + 25 tactics. 4 polls/cold-calls duy trì interaction.

**Lab (Block 2-5, 10:00-13:00)** áp dụng lên 1 **product** thật từ project của team — extract **2-4 core workflows** quan trọng nhất → **Product ROI Dashboard** Parts A-D. Metrics tracked at both product-level + per-workflow. Students BUILD v1, GET ATTACKED in Block 4 red-team, REVISE v2 in Block 5 với ≥2 mandatory changes.

---

## Big idea

> AI adoption không phải là công ty có dùng AI chưa. AI adoption là khi một capability mới vượt qua đủ ngưỡng về maturity, task fit, workflow fit, trust, human behavior, budget ownership và value measurement để trở thành **operating model**.

**Slogan ngày:**
> "Wow creates diffusion. Workflow creates adoption."

WARNING: "Diffusion is not Normalization" = teaching synthesis dựa trên Rogers + NPT, KHÔNG phải direct quote.

---

## Agenda (v4 Block 1-5, 09:00-13:00 absolute)

| Clock | Block | Nội dung | Slides | Hình thức | Deliverable |
|-----|-------|----------|--------|-----------|-------------|
| **09:00-10:00** | **Block 1** — Lecture (60') | Wow≠Adoption + AI Adoption Stack + Gartner Lite + Mollick + ADKAR + Metrics + Measurement Trap + 25 tactics | #1–22 | Lecture + 4 polls/cold-calls | |
| **10:00-11:00** | **Block 2** — Case study + present (60') | 30' group research (8 case packets) + 25' present round 3-5 nhóm + 5' instructor synthesis | (slide #23 intro) | Case method + group present | Case Evidence Matrix (cá nhân) |
| **11:00-12:00** | **Block 3** — Product ROI Dashboard v1 build (60') | **Phase 0** (11:00-11:10, 10') pick product + extract 2-4 workflows · **Phase 1** (11:10-11:30, 20') Part A · **Phase 2** (11:30-11:55, 25') Part B v1 cols 1-6 · **Phase 3** (11:55-12:00, 5') Part C mock | (Lab brief) | Group lab build | Parts A + B v1 + C draft |
| **12:00-12:30** | **Block 4** — Red-team round (30') | 10' present v1 + 20' cross-team attack 4 roles fill col 7 Red-team risk | | Adversarial peer-review | Red-team risk col filled |
| **12:30-13:00** | **Block 5** — Revise + submit (30') | **Phase 1** (12:30-12:50, 20') Col 8 Fix + ≥2 changes · **Phase 2** (12:50-12:55, 5') Part D · **Phase 3** (12:55-13:00, 5') push repo cá nhân + share link Discord | | Group revise + submit | **Product ROI Dashboard Parts A-D** |
| **24h sau** | Reflect cá nhân deadline | | | Cá nhân | **Reflect cá nhân 150-200 từ** |

**Tổng:** 240 phút (4h budget locked) — 60+60+60+30+30 = 240'.

---

## Hoạt động chính

### 1. Case Evidence Matrix (Block 2, cá nhân fill, group consolidate)

Mỗi nhóm được assign 1 case (Nansen / Stripe / Morgan Stanley / DWP-GDS / Klarna / IBM Watson / KPMG / JPMorgan). Fill 8-field matrix:

> Case / Metric shown / Metric layer / What this proves / What this does NOT prove / Missing metric / Biggest risk / Lesson for our dashboard

Template: [`02-templates/00-case-evidence-matrix.md`](02-templates/00-case-evidence-matrix.md). **Nộp via repo cá nhân `Day23-Track01-<MãHọcViên>` — file `01-case-evidence-matrix.md`** (xem §Hướng dẫn nộp bài).

### 2. Product ROI Dashboard (Block 3-5, nhóm — chính)

Group artifact Parts A-D. Áp dụng lên **1 product** CỤ THỂ với **2-4 core workflows** extracted:
- **Part A** Adoption Context (product name + user/team + **2-4 core workflows** mỗi workflow có AI role + human review + failure path + product-level ADKAR barrier + 3 product-level tactics)
- **Part B** Product ROI Dashboard 8 cols — B.1 product-level (2-3 metrics) + B.2 per-workflow (6-layer metric tree per workflow)
- **Part C** Dashboard mock 4-6 tiles (top tile product-level, remaining per-workflow)
- **Part D** Decision Memo 4 q's (incl. "metric replaced after red-team")

**Xem template:** [`01-worksheet.md`](01-worksheet.md) + [`Day23-Lab-Assignment.md`](Day23-Lab-Assignment.md). **Nộp via repo cá nhân — file `03-product-roi-dashboard.md`** (mỗi thành viên copy file group vào repo cá nhân, push trước 13:00). Share link repo lên Discord `#day23-submissions`.

### 3. Red-Team round (Block 4, nhóm attack)

Cross-team attack: mỗi nhóm được assign 1 attack role (CFO / User / Risk / Workflow owner), pitch v1 (2 min), bị attack (20 min), fill col 7 Red-team risk on attacked team's artifact. Template: [`02-templates/05-red-team-template.md`](02-templates/05-red-team-template.md). Discord: `#red-team-risks`.

### 4. Reflect cá nhân (24h sau Block 5, cá nhân)

150-200 từ: **"1 metric tôi sẽ replace + tại sao"** (canonical prompt — pick 1 metric trong dashboard nhóm, giải thích cơ chế vanity / cheat, đề xuất prevention concrete, cite 1 case làm evidence; focus vào red-team learning, không phải workflow scaling).

---

## Deliverables (v4)

| # | Deliverable | Loại | Deadline | Nộp ở đâu |
|---|-------------|------|----------|------------|
| 1 | **Ghi chú thách thức áp dụng AI** + Case Evidence Matrix | Cá nhân | 09:25 | Repo cá nhân: `01-case-evidence-matrix.md` |
| 2 | **Bảng so sánh case thành công/thất bại** | Nhóm (mỗi thành viên copy) | 10:40 | Repo cá nhân: `02-case-comparison.md` |
| 3 | **Product ROI Dashboard v2** (Parts A-D) | Nhóm (mỗi thành viên copy) | 13:00 | Repo cá nhân: `03-product-roi-dashboard.md` + share link repo Discord `#day23-submissions` |
| 4 | **Reflect cá nhân** 150-200 từ: *"1 chỉ số hoặc 1 giả định tôi sẽ sửa"* | Cá nhân | 24h sau lớp | Reply vào thread bài nhóm |

---

## Cách tính điểm

Day 23 = **100 điểm** (75đ nhóm + 25đ cá nhân).

| # | Hạng mục | Điểm | Loại | Khi nào |
|---|----------|------|------|---------|
| 1 | Ghi chú thách thức cá nhân | 15 | Cá nhân | 09:25 |
| 2 | Nghiên cứu case study thành công/thất bại | 15 | Nhóm | 10:40 |
| 3 | Dashboard hành động nhóm | 60 | Nhóm | 13:00 |
| 4 | Reflect cá nhân sau lớp | 10 | Cá nhân | Trong 24h sau lớp |
| | **Tổng** | **100** (75 nhóm + 25 cá nhân) | | |

### 6 điều kiện chấm Dashboard

- **Scope rõ:** 1 sản phẩm cụ thể + 2-4 quy trình chính, mỗi quy trình có vai trò AI, người kiểm tra và cách xử lý khi AI sai.
- **Nguyên nhân gốc rõ:** dùng lens phù hợp, có evidence/quan sát, kết luận được 1-2 root cause.
- **Giải pháp + roadmap rõ:** giải pháp gắn với root cause, có lộ trình 30/60/90 ngày.
- **Chỉ số tốt:** có product-level + workflow-level metrics, không chỉ đo usage.
- **Dữ liệu thực tế:** baseline, target, data source, owner rõ.
- **Rủi ro red-team + phần sửa v2:** có ít nhất 2 thay đổi cụ thể từ v1 sang v2.

### Lưu ý chấm nhanh

- Không nộp Dashboard hành động trước 13:00: mất phần Dashboard 60đ.
- Reflect cá nhân copy-paste giữa thành viên: 0 điểm Reflect cá nhân cho tất cả người liên quan.
- Không có rủi ro red-team + phần sửa v2: tối đa 3/10 ở điều kiện thứ 6.

> Chi tiết rubric: [`../../assessment/day23-rubric-requirements.md`](../../assessment/day23-rubric-requirements.md)

---

## Product ROI Dashboard — Parts A-D (group, product-level + per-workflow)

| Part | Nội dung | Khi build |
|------|----------|-----------|
| *(setup)* | **Phase 0 — Pick product + extract 2-4 core workflows on whiteboard (before opening Part A)** | Block 3 Phase 0 (11:00-11:10, 10') |
| **Part A — Adoption Context** | Product name / User+team / **2-4 core workflows extracted** (each: name + AI role + human review + failure path) / Main ADKAR barrier (product-level) / 3 adoption tactics (product-level) | Block 3 Phase 1 (11:10-11:30, 20') |
| **Part B — Product ROI Dashboard (8 cols, B.1 product-level + B.2 per-workflow)** | B.1: 2-3 whole-product metrics. B.2: 6-layer metric tree (Activation / Engagement / Productivity / Quality / Trust / Value) **per core workflow extracted**. All cols: Layer / Metric / Baseline / Target / Data source / Owner / Red-team risk / Fix | Cols 1-6 Block 3 Phase 2 (11:30-11:55), Col 7 Block 4, Col 8 Block 5 Phase 1 |
| **Part C — Dashboard Mock** | 4-6 tiles: top tile product-level overview, remaining per-workflow signals | Block 3 Phase 3 (11:55-12:00) |
| **Part D — Decision Memo (4 q)** | (1) Continue/pivot/kill **product** (2) Strongest metric + why (3) Metric replaced after red-team (4) Before scaling product, we must... | Block 5 Phase 2 (12:50-12:55) |

**Constraints:**
- Choose **1 product** với **2-4 core workflows extracted** (không 1 workflow đơn lẻ — metric quá generic; không >4 workflow — dilutes attention).
- Metrics phải có ít nhất 1 outcome HOẶC trust metric (không chỉ MAU/login/prompt count).
- ≥2 mandatory v1→v2 changes in Block 5 (replace vanity / add quality+trust / refine decision rule / add data source / add tactic).
- VN groups: nếu Desire là risk → phải bao gồm anonymous/1:1 mechanism.

---

## Product examples gợi ý (chọn 1 — hoặc dùng product hiện tại của team)

| Product type | Sample 2-4 core workflows |
|----------|--------|
| AI chatbot product | (1) Question intake → AI answers (2) Escalation handoff (3) Knowledge gap → KB update |
| AI learning tool product (Bridge AI) | (1) Upload PDF → AI summarize (2) Quiz generate (3) Progress track + suggest next |
| AI coding assistant product | (1) Inline suggestion (2) Test gen (3) PR review draft (4) Doc gen |
| AI content tool product | (1) Brief → draft (2) Edit + tone calibration (3) Multi-channel adapt (4) Performance feedback |
| AI analytics tool product | (1) NL → SQL gen (2) Chart suggest + render (3) Anomaly explain |
| AI support tool product | (1) Triage + priority (2) Draft response (3) Agent review/send (4) Re-contact tracking |
| AI HR/People Ops product | (1) Feedback notes → summary (2) Theme cluster + manager brief (3) 1:1 prompt suggestion |
| AI Finance/Legal review product | (1) Doc classify (2) First-pass review draft (3) Risk flag + escalation |

---

## Hướng dẫn nộp bài

**Mỗi học viên tạo MỘT GitHub repo cá nhân duy nhất để nộp tất cả deliverables Day 23.**

| Trường | Giá trị |
|---|---|
| Tên repo | `Day23-Track01-<MãHọcViên>` (ví dụ: `Day23-Track01-V202301001`) |
| Visibility | **public** (để instructor + TA chấm) |
| Branch | `main` |
| Stay public | tối thiểu 2 tuần sau lớp |

### Cấu trúc repo

```
Day23-Track01-<MãHọcViên>/
│
├── README.md                       ← Họ tên · Mã học viên · Tên nhóm + thành viên
├── 01-case-evidence-matrix.md      ← Block 2 — Case Evidence Matrix (cá nhân fill)
├── 02-case-comparison.md           ← Block 2 — Bảng so sánh case thành công/thất bại (group; mỗi thành viên copy)
├── 03-product-roi-dashboard.md     ← Block 3-5 — Product ROI Dashboard Parts A-D (group; mỗi thành viên copy)
├── 04-reflection.md                ← Reflect cá nhân 150-200 từ "1 metric tôi sẽ replace + tại sao"
└── assets/                         ← (optional) screenshot dashboard mock + hình ảnh phụ
```

### Workflow nộp bài

| # | Bài | Khi nào | Action |
|---|---|---|---|
| 0 | Setup repo + README | Trước 09:00 | Tạo repo `Day23-Track01-<MãHọcViên>` (public), commit README có họ tên + mã học viên + tên nhóm |
| 1 | Case Evidence Matrix (cá nhân) | 09:25-11:00 | Commit `01-case-evidence-matrix.md` + push |
| 2 | Bảng so sánh case (group) | 10:40 | Group share file → mỗi thành viên copy vào repo cá nhân + push |
| 3 | Product ROI Dashboard v2 (group) | 13:00 | Group share file → mỗi thành viên copy vào repo + push. Share link repo lên Discord `#day23-submissions` |
| 4 | Reflect cá nhân | 24h sau lớp | Commit `04-reflection.md` + push |

### README.md repo cá nhân — template

```markdown
# Day 23 Track 01 — <Họ tên>

**Mã học viên:** <MãHọcViên>
**Nhóm:** <Tên nhóm>
**Thành viên nhóm:** <liệt kê tên + mã 4-6 người>
**Course repo:** https://github.com/VinUni-AI20k/Day23-Track01-AI-Adoption

## Files
- `01-case-evidence-matrix.md` — Cá nhân fill Block 2
- `02-case-comparison.md` — Group bảng so sánh case
- `03-product-roi-dashboard.md` — Group Product ROI Dashboard Parts A-D
- `04-reflection.md` — Cá nhân reflect 24h sau lớp
```

### Lưu ý quan trọng

- **Group artifacts (#2 + #3):** mỗi thành viên trong nhóm copy file group vào repo cá nhân — đảm bảo mỗi học viên có bundle đầy đủ để chấm. Ghi tên người phụ trách tại đầu mỗi Part A/B/C/D trong dashboard.
- **File format:** Markdown (`.md`). Có thể thêm `assets/` cho hình ảnh (screenshot dashboard mock, photo whiteboard, etc.).
- **Discord** `#day23-submissions`: CHỈ dùng để share link repo cá nhân (cuối Block 5). KHÔNG nộp file qua Discord.
- **Oral check rule:** thành viên không giải thích được phần mình làm trong oral check (Lab Coach hỏi nhanh) → 0đ phần đó (cùng convention với Day 5 vibe-coding rule).
- **Red-team participation:** mỗi thành viên phải attack ≥1 nhóm khác trong Block 4 — empty Red-team contribution = 0 điểm phần đó.
- **Late submission:** repo phải public trước 13:00. Late = bị giảm điểm theo rubric §5 late policy.

---

## Tài liệu trong repo này

| File | Mô tả |
|------|-------|
| [`Day23-Lab-Assignment.md`](Day23-Lab-Assignment.md) | THE assignment brief — v4 5-block flow + Parts A-D + 5-gate rubric |
| [`01-worksheet.md`](01-worksheet.md) | Master worksheet — Parts A-D consolidated fill-in template |
| [`02-templates/00-case-evidence-matrix.md`](02-templates/00-case-evidence-matrix.md) | Block 2 Case Evidence Matrix (8-field, cá nhân fill) |
| [`02-templates/01-part-a-adoption-context.md`](02-templates/01-part-a-adoption-context.md) | Part A (Adoption Context — product + 2-4 core workflows + ADKAR + tactics) |
| [`02-templates/02-part-b-roi-dashboard.md`](02-templates/02-part-b-roi-dashboard.md) | Part B (Product ROI Dashboard — B.1 product-level + B.2 per-workflow, 8 cols với Red-team risk + Fix) |
| [`02-templates/03-part-c-dashboard-mock.md`](02-templates/03-part-c-dashboard-mock.md) | Part C (Dashboard Mock 4-6 tiles ASCII) |
| [`02-templates/04-part-d-decision-memo.md`](02-templates/04-part-d-decision-memo.md) | Part D (Decision Memo 4 questions) |
| [`02-templates/05-red-team-template.md`](02-templates/05-red-team-template.md) | Block 4 Red-Team attack scaffold (4 roles × attack dimensions) |
| [`03-tools-guide/prompts-for-self-research.md`](03-tools-guide/prompts-for-self-research.md) | AI prompt templates cho self-research |
| [`03-tools-guide/adoption-diagnostic-toolkit.md`](03-tools-guide/adoption-diagnostic-toolkit.md) | Gartner-Lite + ADKAR + Mollick how-to + decision tree |
| [`04-reference/day23-cheatsheet.md`](04-reference/day23-cheatsheet.md) | 1-page reference khi ngồi lab |
| [`04-reference/case-clinic-summary.md`](04-reference/case-clinic-summary.md) | 8 cases nén lại làm evidence pack |
| [`05-reference-document.md`](05-reference-document.md) | Student handbook — theory + cases + tactics + VN context (1800+ lines) |

---

## Rời lớp Day 23 (13:00), mỗi nhóm phải có (v4)

1. **Part A — Adoption Context:** 1 product (1 câu cụ thể) + **2-4 core workflows** extracted (mỗi workflow = name + AI role + human review + failure path) + 1 product-level ADKAR barrier + 3 product-level tactics
2. **Part B — Product ROI Dashboard v2:** B.1 product-level (2-3 metrics) + B.2 per-workflow (6-layer × baseline / target / data source / owner / red-team risk / fix per workflow), với ≥1 outcome HOẶC trust metric
3. **Part C — Dashboard Mock:** 4-6 tiles (top tile product-level, remaining per-workflow)
4. **Part D — Decision Memo:** Continue / Pivot / Kill product + strongest metric + metric replaced after red-team + "before scaling product, we must..."
5. **Red-team evidence:** Part B col 7 (Red-team risk) + col 8 (Fix) filled — ≥2 mandatory changes v1→v2

---

*Ngày 23 — VinUni A20 — AI Thực Chiến · 2026*
