FROM mcr.microsoft.com/devcontainers/python:3.12-bookworm

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Copy and install Python dependencies early for layer caching
COPY requirements.txt* /tmp/pip-reqs/
RUN if [ -f /tmp/pip-reqs/requirements.txt ]; then \
        pip install --no-cache-dir -r /tmp/pip-reqs/requirements.txt; \
    fi
