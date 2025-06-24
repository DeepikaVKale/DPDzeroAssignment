FROM ghcr.io/astral-sh/uv:python3.13-bookworm-slim

WORKDIR /app

COPY pyproject.toml uv.lock ./

RUN uv sync --locked

COPY . /app/

ENV PATH="/app/.venv/bin:$PATH"

EXPOSE 8002

CMD ["uv", "run", "app.py"]