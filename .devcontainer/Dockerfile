FROM mcr.microsoft.com/devcontainers/python:3.12-bookworm
# gnupg stays (unlike no-gnupg): only the ceiling/installs leg is under test.
# No apt: the egress-restricted cells have no Debian mirror route (envbuilder
# exit 100). The python base already carries python3 + venv + gpg + vscode.
# /opt/venv is the venv the launcher installs devworkspace.yaml install.pypi
# into (uv: VIRTUAL_ENV=/opt/venv; else pip3, which resolves to the venv's).
RUN echo "wl-proof entitled-installs fixture layer" > /etc/wl-proof-built \
 && command -v gpg \
 && python3 -m venv /opt/venv \
 && chown -R 1000:1000 /opt/venv
ENV PATH="/opt/venv/bin:${PATH}"
