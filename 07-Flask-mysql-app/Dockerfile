FROM python:3.10-slim AS base

RUN apt update && apt install -y \
    default-libmysqlclient-dev \
    && pip install pipenv

WORKDIR /app


FROM base AS builder

ENV PIPENV_VENV_IN_PROJECT=1

RUN apt install -y build-essential

COPY Pipfile* ./

RUN pipenv install


FROM base

ENV FLASK_APP=todos/app.py

COPY --from=builder /app/.venv ./.venv

COPY . .

EXPOSE 5000

CMD pipenv run flask run --host 0.0.0.0
