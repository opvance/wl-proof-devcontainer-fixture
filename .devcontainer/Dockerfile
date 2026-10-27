FROM mcr.microsoft.com/devcontainers/base:bookworm
# gnupg stays (unlike no-gnupg): only the ceiling/installs leg is under test.
# /opt/venv is the venv the launcher installs devworkspace.yaml install.pypi
# into (uv: VIRTUAL_ENV=/opt/venv; else pip3, which resolves to the venv's).
RUN echo "wl-proof entitled-installs fixture layer" > /etc/wl-proof-built \
 && command -v gpg \
 && apt-get update \
 && apt-get install -y --no-install-recommends python3 python3-venv \
 && rm -rf /var/lib/apt/lists/* \
 && python3 -m venv /opt/venv \
 && chown -R 1000:1000 /opt/venv
ENV PATH="/opt/venv/bin:${PATH}"
