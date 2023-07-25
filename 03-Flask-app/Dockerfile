FROM python:3.12.0b4-bookworm

WORKDIR /app

RUN python3 -m venv .venv

ENV VIRTUAL_ENV=/app/.venv
ENV PATH="$VIRTUAL_ENV/bin:$PATH"

COPY requirements.txt ./

RUN pip install -r requirements.txt

COPY . .

ENV FLASK_APP=src/main.py

EXPOSE 5000

CMD flask run --host 0.0.0.0
