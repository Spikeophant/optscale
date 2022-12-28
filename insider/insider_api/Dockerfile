FROM python

WORKDIR /usr/src/app/insider_api
ENV PYTHONPATH /usr/src/app/


COPY controllers ./controllers
COPY handlers ./handlers
COPY swagger ./swagger
COPY *.py ./

COPY cloud_adapter ./cloud_adapter
COPY config_client ./config_client
COPY optscale_exceptions ./optscale_exceptions
COPY requirements.txt ./requirements.txt
run pip install -r requirements.txt
RUN python -u write_spec.py

CMD ["python", "-u","/usr/src/app/insider_api/server.py"]
EXPOSE 8945
