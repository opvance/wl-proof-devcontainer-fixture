FROM mcr.microsoft.com/devcontainers/base:bookworm
RUN echo "wl-proof no-gnupg fixture layer" > /etc/wl-proof-built \
 && apt-get remove -y --purge gpg gnupg gnupg2 gpg-wks-server gpg-wks-client \
 && ! command -v gpg
