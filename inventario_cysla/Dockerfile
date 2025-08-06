FROM python:3.12-alpine

# Evita archivos .pyc y habilita logs en consola
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Establece directorio de trabajo
WORKDIR /app

# Instala dependencias del sistema necesarias
RUN apk update && apk add --no-cache \
    gcc \
    musl-dev \
    python3-dev \
    libffi-dev \
    mariadb-dev \
    jpeg-dev \
    zlib-dev \
    build-base \
    pkgconfig \
    libjpeg \
    && rm -rf /var/cache/apk/*

# Copia e instala dependencias de Python
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copia el resto de la aplicación
COPY . .

# Expone el puerto del servidor de Django
EXPOSE 8000

# Comando por defecto
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
