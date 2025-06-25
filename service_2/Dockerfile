#Use a Python image with uv pre-installed
FROM ghcr.io/astral-sh/uv:python3.13-bookworm-slim

#set the working directory inside container 
WORKDIR /app

#Install dependencies for health check and debugging
RUN apt-get update && apt-get install -y curl && rm -rf /v

#copy dependencies to container's app directory
COPY pyproject.toml uv.lock ./

#install and sync project into new environment 
RUN uv venv && uv sync --locked

#copy current directory contents to conatiner's app directory
COPY . /app/

# Place executables in the environment at the front of the path
ENV PATH="/app/.venv/bin:$PATH"

#expose the port the app will run on
EXPOSE 8002

#command to run the app
CMD ["uv", "run", "app.py"]