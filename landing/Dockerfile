# --- Базовый образ: лёгкий nginx на Alpine (~25 МБ) ---
FROM nginx:1.27-alpine

# Убираем дефолтную страницу nginx
RUN rm -rf /usr/share/nginx/html/*

# Копируем файлы сайта в контейнер
COPY index.html /usr/share/nginx/html/index.html
COPY logo.jpg   /usr/share/nginx/html/logo.jpg

# Свой конфиг nginx (опционально, см. ниже)
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Порт, который слушает nginx
EXPOSE 80

# Запуск nginx в foreground (иначе контейнер сразу завершится)
CMD ["nginx", "-g", "daemon off;"]