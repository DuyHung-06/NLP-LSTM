# IMDB Sentiment Analysis with LSTM

Bài tập phân loại cảm xúc đánh giá phim IMDB: Positive / Negative.

## Các mô hình
- Logistic Regression (TF-IDF)
- Linear SVM (TF-IDF)
- MLP (TF-IDF)
- LSTM (chuỗi token)

## 1. Chuẩn bị dữ liệu
Tải dataset Kaggle tại :
- https://www.kaggle.com/datasets/rehanliaqat17/imbd-dataset/data 
- `review`: nội dung đánh giá
- `sentiment`: `positive` hoặc `negative`

Đặt file CSV tại `data/IMDB Dataset.csv`. Nếu file có tên hoặc vị trí khác, sửa biến `DATA_PATH` ở đầu notebook.

Cấu trúc thư mục:
```text
LSTM-Sentiment-Analysis/
├── data/
│   └── IMDB Dataset.csv       # không commit dữ liệu nếu file quá lớn / có điều kiện Kaggle
├── notebooks/
│   └── sentiment_analysis.ipynb
├── results/
│   └── comparison.csv         # được notebook tạo ra
├── requirements.txt
├── .gitignore
└── README.md
```

## 2. Cài đặt và chạy
Python 3.10 hoặc 3.11 được khuyến nghị.

```bash
python -m venv .venv
```

Windows:
```bash
.venv\Scripts\activate
```

macOS/Linux:
```bash
source .venv/bin/activate
```

Cài thư viện:
```bash
pip install -r requirements.txt
jupyter notebook
```

Mở `notebooks/sentiment_analysis.ipynb` và chạy các cell từ trên xuống dưới.

## 3. Ghi chú
- Notebook tự chia dữ liệu train/test theo tỷ lệ 80/20, stratified và seed cố định.
- Các mô hình dùng cùng tập test để so sánh.
- Kết quả trong `results/comparison.csv` được sinh ra từ lần chạy thực tế; không điền số liệu giả.
- LSTM có thể chạy chậm trên CPU. Có thể giảm `MAX_TRAIN_SAMPLES` để thử nhanh, rồi chạy toàn bộ dữ liệu trước khi nộp.
