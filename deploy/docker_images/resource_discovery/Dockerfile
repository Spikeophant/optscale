FROM python

WORKDIR /src
ENV PYTHONPATH=/src

COPY scheduler.py worker.py ./
COPY cloud_adapter ./cloud_adapter
COPY config_client ./config_client
COPY rest_api_client ./rest_api_client
CMD ["python", "-u", "/src/scheduler.py"]
