FROM ghcr.io/astral-sh/uv:python3.12-bookworm-slim

# Security best practices
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    PIP_NO_CACHE_DIR=off \
    PIP_DISABLE_PIP_VERSION_CHECK=on \
    PIP_DEFAULT_TIMEOUT=100

# Create a non-root user with its home directory
# RUN useradd --create-home pythonuser
# USER pythonuser
WORKDIR /code

# Create uv environment in /code and give user permissions to use it with uv pip
RUN uv venv
ENV PATH="/code/.venv/bin:$PATH"

# Optional: Only if you have specific dependencies
# COPY --chown=appuser:appuser requirements.txt .
# RUN uv pip install --user -r requirements.txt