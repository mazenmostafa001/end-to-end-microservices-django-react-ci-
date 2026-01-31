FROM python:3.10-slim

WORKDIR /app

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]



# # ==============================
# # Stage 1: Backend Build
# # ==============================
# FROM python:3.10-slim AS backend-build

# WORKDIR /app

# # نسخ requirements أولاً للاستفادة من caching
# COPY requirements.txt .
# RUN pip install --upgrade pip \
#     && pip install --no-cache-dir -r requirements.txt

# # نسخ باقي ملفات الباكند
# COPY . .

# # ==============================
# # Stage 2: Final Image
# # ==============================
# FROM python:3.10-slim

# WORKDIR /app

# ENV PYTHONDONTWRITEBYTECODE=1
# ENV PYTHONUNBUFFERED=1
# ENV DJANGO_SETTINGS_MODULE=gig_router.settings

# # تثبيت مكتبات ضرورية
# RUN apt-get update && apt-get install -y libpq-dev --no-install-recommends \
#     && rm -rf /var/lib/apt/lists/*

# # نسخ الباكند من مرحلة البناء
# COPY --from=backend-build /app /app

# EXPOSE 8000

# # أمر التشغيل (تقدر تغيّره لاحقاً لـ gunicorn في production)
# CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

