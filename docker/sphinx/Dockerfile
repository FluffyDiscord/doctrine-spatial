FROM alpine:latest
WORKDIR /etc/
RUN mkdir -p /etc/Sphinx/build

RUN apk add --no-cache python3 make git py3-pip
RUN pip3 install git+https://github.com/sphinx-doc/sphinx --break-system-packages && \
    pip3 uninstall sphinx_rtd_theme  --break-system-packages && \
    pip3 install sphinx_rtd_theme sphinx-autobuild  --break-system-packages

CMD sphinx-autobuild -b html --host 0.0.0.0 --port 80 /etc/Sphinx/source /etc/Sphinx/build
