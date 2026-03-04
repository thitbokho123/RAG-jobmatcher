# Dùng bản full (Bookworm là bản ổn định nhất hiện nay)
FROM python:3.10-bookworm

WORKDIR /app

# Vì bản full đã có sẵn công cụ biên dịch, bạn chỉ cần cài Tesseract thôi
# Nếu lệnh này vẫn lỗi mạng, bạn thậm chí có thể tạm bỏ qua Tesseract để build chạy thử trước
RUN apt-get update && apt-get install -y tesseract-ocr libtesseract-dev

COPY requirements.txt .
RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt

COPY . .
EXPOSE 8000
CMD ["uvicorn", "test:app", "--host", "0.0.0.0", "--port", "8000"]

