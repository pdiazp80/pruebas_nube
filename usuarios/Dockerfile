# Usa una imagen base de Python 3.10
FROM python:3.10

# Establece el directorio de trabajo dentro del contenedor
WORKDIR /app

# Instala pipenv
RUN pip install --no-cache-dir pipenv

# Copia los archivos de dependencias
COPY Pipfile Pipfile.lock ./

# Establece la variable de entorno para instalar paquetes en el sistema global
ENV PIPENV_VENV_IN_PROJECT=1

# Instala las dependencias desde Pipfile.lock
RUN pipenv install --deploy --ignore-pipfile

# Copia el resto de la aplicación desde el directorio usuarios
COPY . .

# Expone el puerto en el que la aplicación Flask está corriendo
EXPOSE 3000

# Comando para ejecutar la aplicación Flask con pipenv
CMD ["sh", "-c", "pipenv run flask run --host=0.0.0.0 --port=3000"] 
