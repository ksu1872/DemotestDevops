ARG BASE_IMAGE=python:3.9-slim-bullseye
FROM ${BASE_IMAGE}
ARG REQUIREMENTS=requirements.txt
RUN useradd --uid 10001 --create-home app
WORKDIR /app
COPY ${REQUIREMENTS} requirements.txt
RUN pip install --no-cache-dir -r requirements.txt
COPY app.py .
USER 10001
EXPOSE 8080
HEALTHCHECK NONE
CMD ["python", "app.py"]
