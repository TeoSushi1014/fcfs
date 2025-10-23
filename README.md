## 1) Tóm tắt (8–10 dòng)

* Mục tiêu: cài đặt và đánh giá **FCFS non-preemptive**; minh họa **convoy effect**. FCFS phục vụ theo **thứ tự đến** (FIFO). ([GeeksforGeeks][1])
* Chỉ số dùng: **CT, TAT, WT, Response**. Công thức bắt buộc phải ghi:
  TAT = CT − AT, WT = TAT − BT, Response = thời điểm chạy lần đầu − AT. ([Baeldung on Kotlin][2])
* Kết quả chính (điền số của bạn): dataset “normal” có Avg TAT, WT thấp; dataset “convoy” tăng mạnh WT do job dài đứng đầu → đúng **convoy effect**. ([GeeksforGeeks][3])

> Mẫu câu:
> “Chúng tôi hiện thực FCFS (không tiền ngắt), đo CT, TAT, WT, Response trên hai workload nhỏ. Kết quả cho thấy ở kịch bản có tiến trình dài, thời gian chờ trung bình tăng rõ rệt, phù hợp mô tả convoy effect.”

---

## 2) Giới thiệu (bối cảnh 0.5–1 trang)

* Vì sao cần định thời CPU, vai trò của FCFS trong nhóm thuật toán nền. Nhấn mạnh: **đơn giản, công bằng theo thứ tự đến, nhưng phản hồi kém** khi có job dài. ([cs341.cs.illinois.edu][4])
* Mục tiêu báo cáo: cài đặt, minh họa, so sánh nhanh với RR, SJF/SRTF.

---

## 3) Cơ sở lý thuyết (1 trang)

* **FCFS (First-Come First-Served)**: hàng đợi FIFO, **non-preemptive**, dễ gặp **convoy effect** (job dài làm chậm cả đoàn). ([GeeksforGeeks][1])
* **Chỉ số & công thức** (viết bằng công thức hiển thị):

  * Turnaround (TAT) = CT − AT
  * Waiting (WT) = TAT − BT
  * Response = Start_first_run − AT ([Baeldung on Kotlin][2])
* **Liên hệ so sánh** (để dùng ở phần Discussion):

  * **SJF/SRTF**: tối ưu **WT trung bình** về lý thuyết, nhưng có nguy cơ **starvation** nếu job ngắn đến liên tục. ([GeeksforGeeks][5])
  * **RR**: quantum càng lớn **càng tiệm cận FCFS**; quantum quá nhỏ → nhiều context switch, nhưng đáp ứng tốt hệ tương tác. ([andrew.cmu.edu][6])
* (Tham khảo nền tảng/metrics của OSTEP để trích dẫn chuẩn). ([UW Computer Sciences][7])

---

## 4) Thuật toán & Cài đặt (0.5–1 trang)

* Mô tả ngắn thuật toán FCFS bạn đã code:
  Sắp theo **AT**, nếu rỗi thì chèn **IDLE**, rồi chạy theo thứ tự, tính **Start, CT, TAT, WT**; **không ngắt** giữa chừng (đây là đúng bản chất FCFS). ([GeeksforGeeks][1])
* Sơ đồ luồng 5 bước: Nhập dữ liệu → Sắp theo AT → Mô phỏng theo thời gian → Tính CT/TAT/WT/Response → In bảng + Gantt.

---

## 5) Thực nghiệm & Kết quả (1–2 trang)

* **Dataset 1 – “normal”**

  * Chèn bảng: `normal.png` (CT/TAT/WT/Avg).
  * Chèn Gantt: `Gantt_1.drawio.png`.
  * Nhận xét 3–4 dòng: có **idle** 1–2; trình tự đúng AT; Avg TAT, WT thấp hơn kịch bản convoy.
* **Dataset 2 – “convoy”**

  * Chèn bảng: `convoy.png`.
  * Chèn Gantt: `Gantt_2.drawio.png` (nhớ xóa dòng “P04” trùng khi xuất).
  * Nhận xét 3–4 dòng: **P04 dài** (BT lớn) chạy sớm gây **convoy effect** → **Avg WT tăng mạnh**, đúng lý thuyết. ([GeeksforGeeks][3])

> Mẹo: kết thúc phần này bằng 1–2 câu tổng hợp số liệu (Avg TAT/WT) để bắc cầu sang Discussion.

---

## 6) Thảo luận (Discussion) (0.5–1 trang)

* **Vì sao xảy ra convoy** trong FCFS và khi nào đáng lo (workload có job dài, hệ tương tác). ([GeeksforGeeks][3])
* **So sánh gọn** (đặt `BangSoSanh.drawio.png`):

  * **SJF/SRTF**: giảm WT TB nhưng **starvation** có thể xảy ra, cần ước lượng BT. ([GeeksforGeeks][5])
  * **RR**: cải thiện **responsiveness**; **quantum lớn ≈ FCFS**, nhỏ → nhiều context switch. ([andrew.cmu.edu][6])
* **Giới hạn thực nghiệm**: dữ liệu toy, chưa đo context-switch overhead; chưa so sánh xác suất trên phân phối AT/BT.

---

## 7) Kết luận & Hướng mở (5–7 dòng)

* FCFS **đơn giản, dễ hiện thực**, minh họa convoy rõ ràng; kết quả **khớp lý thuyết và công thức**.
* Hướng mở: mô phỏng thêm phân phối AT/BT, so sánh định lượng với RR/SRTF, đo thêm **Response time** để đánh giá hệ tương tác. ([UW Computer Sciences][7])

---
