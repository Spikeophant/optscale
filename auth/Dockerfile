FROM python

WORKDIR /usr/src/app/auth_server
ENV PYTHONPATH /usr/src/app/

COPY auth_server/alembic ./alembic
COPY auth_server/controllers ./controllers
COPY auth_server/handlers ./handlers
COPY auth_server/auth_token ./auth_token
COPY auth_server/models ./models
COPY auth_server/*.py ./
COPY auth_server/alembic.template .
COPY auth_server/swagger ./swagger
COPY auth_server/config_client ./config_client
COPY auth_server/rest_api_client ./rest_api_client
COPY auth_server/optscale_exceptions ./optscale_exceptions
COPY auth_server/zoho_integrator ./zoho_integrator
COPY requirements.txt ./requirements.txt

RUN pip install -r requirements.txt
RUN python -u write_spec.py

CMD ["python", "-u","/usr/src/app/auth_server/server.py"]
EXPOSE 8905
