FROM ubuntu:latest

WORKDIR /app

COPY requirements.txt /app
COPY devops /app/devops

RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /app/venv && \
    /app/venv/bin/pip install --upgrade pip && \
    /app/venv/bin/pip install -r requirements.txt

EXPOSE 8000

# Set the environment variables for the virtual environment
ENV VIRTUAL_ENV=/app/venv
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

ENTRYPOINT ["python"]
CMD ["devops/manage.py", "runserver", "0.0.0.0:8000"]




