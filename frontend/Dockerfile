FROM node:18-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]


# # ==============================
# # Stage 1: Build Frontend
# # ==============================
# FROM node:18-alpine AS frontend-build

# WORKDIR /app

# # نسخ ملفات package.json أولاً للاستفادة من cache
# COPY package*.json ./
# RUN npm install

# # نسخ باقي ملفات الفرونت
# COPY . .

# # بناء المشروع
# RUN npm run build

# # ==============================
# # Stage 2: Final Image (serve build)
# # ==============================
# FROM nginx:alpine

# # نسخ build النهائي من المرحلة الأولى
# COPY --from=frontend-build /app/build /usr/share/nginx/html

# # نسخ إعدادات Nginx لو عايز (اختياري)
# # COPY nginx.conf /etc/nginx/conf.d/default.conf

# EXPOSE 3000

# CMD ["nginx", "-g", "daemon off;"]
