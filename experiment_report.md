# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600016
**Name:** Chu Tuấn Nghĩa
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Ket qua hop ly vi du lieu electronics sach va Laptop co gia cao nhat trong tap du lieu da xu ly. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Agent khong phat hien outlier phi thuc te va chi don gian chon gia lon nhat trong nhom electronics. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai vi logic trong `agent_simulation.py` rat don gian: no loc cac ban ghi co `category = electronics` roi chon san pham co `price` lon nhat. Trong `garbage_data.csv`, ban ghi `Nuclear Reactor` co gia `999999` la mot outlier phi thuc te, nhung agent khong co buoc kiem tra tinh hop le nen van xem day la lua chon tot nhat. Ngoai ra, file garbage con co duplicate ID (`id = 1`), sai kieu du lieu (`ten dollars`), va gia tri rong o cot `id` va `category`. Cac loi nay cho thay du lieu khong duoc validation day du. Du mot so loi khong tac dong truc tiep den cau tra loi trong lan chay nay, chung van lam giam do tin cay cua tap du lieu va co the gay loi hoac ket qua sai trong cac truy van khac.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y.

Prompt trong thi nghiem nay khong doi, nhung ket qua thay doi hoan toan theo chat luong du lieu dau vao. Khi du lieu sach, agent tra loi hop ly. Khi du lieu rac, agent van tu tin dua ra dap an sai. Dieu nay cho thay chat luong du lieu quan trong hon prompt neu muon he thong AI hoat dong on dinh va dang tin cay.
