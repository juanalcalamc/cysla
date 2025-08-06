# Usa una imagen oficial de Python
FROM python:3.12

# Establece el directorio de trabajo
WORKDIR /app

# Copia el contenido de tu proyecto
COPY . .

# Instala dependencias
RUN pip install --upgrade pip && pip install -r requirements.txt

# Expone el puerto del contenedor
EXPOSE 8000

# Comando por defecto
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
