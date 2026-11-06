# Báo cáo cá nhân — Day 01: Lọc tin nhắn rác bằng ML, DL, Embedding và LLM

> Đổi tên file này thành `MSSV_HoTen.md` của bạn, ví dụ `2A20260000_NguyenVanAn.md`, rồi điền từng mục. Xoá các dòng hướng dẫn in nghiêng khi xong.

- **MSSV:** 2A202603740
- **Họ và tên:** Tran Thanh Hai
- **SEED** (in ở ô đầu notebook): 1860

## 1. Bằng chứng

| Tệp | Có? |
| --- | --- |
| [`day01_lab.ipynb`](day01_lab.ipynb) — notebook đã chạy, còn output | ☐ |
| [`lab1_report.json`](lab1_report.json) — do ô "Báo cáo cuối" sinh ra | ☐ |
| [`hand_calc.jpg`](hand_calc.jpg) — ảnh tính tay có các bước | ☐ |

## 2. Kết quả chính
precision  recall  F1 (test)  F1 (SUB 40)  \
1. BoW + LogReg (tự code)            0.989   0.807      0.889        0.947   
3a. Encoder (MiniLM) + kNN           0.852   0.956      0.901        0.950   
3b. Encoder (MiniLM) + LogReg        0.957   0.965      0.961        1.000   
3c. Encoder (MiniLM) + MLP head      0.991   0.947      0.969        1.000   

train (s)  tin/s (cả lô)  p50 ms/tin  \
1. BoW + LogReg (tự code)            4.704      27021.384       0.060   
3a. Encoder (MiniLM) + kNN          87.694         20.781      55.677   
3b. Encoder (MiniLM) + LogReg       88.885         33.663      30.222   
3c. Encoder (MiniLM) + MLP head     89.273         19.271      61.507   

 p95 ms/tin  USD / 1k tin  
1. BoW + LogReg (tự code)             0.106           0.0  
3a. Encoder (MiniLM) + kNN           76.512           0.0  
3b. Encoder (MiniLM) + LogReg        40.207           0.0  
3c. Encoder (MiniLM) + MLP head     174.482           0.0  
• Hàng LLM chỉ đo trên SUB (40 tin) → so sánh chất lượng công bằng bằng cột 'F1 (SUB 40)'.
• SUB chỉ 40 tin: 1 tin sai đổi F1 vài điểm. Chênh < ~0.05 F1 coi như HOÀ — đừng xếp hạng theo số lẻ.
• Inference đo TỪ VĂN BẢN THÔ → NHÃN (gồm cả vectorize / encode). p50/p95 = gọi từng tin một, như một request thật.
• train (s) của 3a/3b/3c = thời gian encoder MiniLM encode tập train (+ train đầu LogReg / MLP); LLM = 0 vì không train. Số đo phụ thuộc CPU/GPU của Colab.

## 3. Dự đoán và thực tế

[16:07:35] ml_f1: 0.76
[16:22:35] ml_lr: 0.001
[16:37:56] emb_tricky: 3b.Encoder+LogReg


## 4. Phân tích 50 case khó



## 5. Thử thách cá nhân


## 6. Phương án cho sản phẩm thật


## 7. AI log và điều đã học

