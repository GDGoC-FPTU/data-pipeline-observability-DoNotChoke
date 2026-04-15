[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573975&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** email@example.com
**Name:** (Dien ten cua ban)

---

## Mo ta

(Mo ta ngan gon bai lab va nhung gi ban da lam)

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python agent_simulation.py
```

Script `agent_simulation.py` mo phong mot agent tra loi dua tren file CSV theo kieu "RAG-like" rat don gian:

- Agent doc du lieu tu file duoc truyen vao bang `pd.read_csv(data_path)`.
- Sau do agent kiem tra noi dung cau hoi. Neu query chua tu `"electronic"`, agent se loc cac dong co `category == "electronics"` (khong phan biet hoa thuong).
- Trong nhom du lieu da loc, agent chon san pham co `price` lon nhat bang `idxmax()` va tra ve cau tra loi theo mau: `best choice is <product> at $<price>`.
- Neu khong co dong nao thuoc nhom electronics, agent se bao khong tim thay du lieu phu hop.
- Neu file loi, thieu cot, sai kieu du lieu, hoac khong doc duoc CSV, toan bo loi se bi `try/except` bat lai va tra ve thong diep `Agent Error: I'm choking on the data! ...`

Khi chay file, chuong trinh se tu dong test 2 truong hop:

1. `processed_data.csv`: du lieu sach sau khi ETL, dung de xem agent tra loi binh thuong.
2. `garbage_data.csv`: du lieu loi/ban do ban tao, dung de stress test va quan sat cach agent "choke" khi gap du lieu xau.

Thu tu chay de demo:

```bash
python solution.py
python agent_simulation.py
```

Neu chua co `garbage_data.csv`, phan test garbage data se bao loi file khong ton tai. Day cung la mot cach de quan sat observability khi dau vao khong hop le.

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

(Tom tat ket qua: bao nhieu records da xu ly, bao nhieu bi loai, v.v.)
