FROM python:3.11 AS builder
WORKDIR /install
COPY requirements.txt .
RUN pip install --prefix=/install/deps --no-cache-dir -r requirements.txt

FROM python:3.11
WORKDIR /app
COPY --from=builder /install/deps /usr/local
COPY app.py .
EXPOSE 5000
CMD ["python", "app.py"]
