FROM ghcr.io/coder/code-server:4.104.3-ubuntu

USER root

RUN apt update && apt install -y make

USER coder

RUN curl -fsSL https://raw.githubusercontent.com/mklement0/n-install/stable/bin/n-install | bash -s -- -q 22

RUN mkdir -p ~/workspace/example-project

RUN code-server --install-extension dracula-theme.theme-dracula

COPY --chown=coder:coder ./README.md /home/coder/workspace/example-project/README.md
COPY --chown=coder:coder ./settings.json /home/coder/.local/share/code-server/User/settings.json

CMD [ "--disable-proxy", "--disable-telemetry", "--disable-update-check", "--auth=none", "--app-name=run.it.kr", "/home/coder/workspace/example-project" ]
