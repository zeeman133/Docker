FROM python:3.7
WORKDIR /opt/app
RUN apt-get update && apt-get install curl libxml2-dev libxml2 libxslt-dev libpq-dev gcc
RUN useradd django
COPY --chown=django:django lib_catalog/ .
RUN /usr/local/bin/python -m pip install --upgrade pip && pip install -r requirements.txt
USER django
EXPOSE 8000
HEALTHCHECK --interval=5s --timeout=10s --retries=3 --start-period=30s CMD curl -sS 127.0.0.1:8000 || exit 1
CMD python manage.py runserver 0.0.0.0:8000


