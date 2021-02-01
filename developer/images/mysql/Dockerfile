FROM mysql:5.7

ARG MYSQL_ROOT_PASSWORD

ENV MYSQL_ROOT_PASSWORD $MYSQL_ROOT_PASSWORD

RUN echo "[mysql] "'\n'"user = root "'\n'"password = $MYSQL_ROOT_PASSWORD" > ~/.my.cnf \
    && chmod 600 ~/.my.cnf

EXPOSE 3606