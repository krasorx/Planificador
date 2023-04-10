FROM odoo:15.0

USER root

RUN apt-get update && apt-get install -y wget

RUN wget https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.5/wkhtmltox_0.12.5-1.focal_amd64.deb 
RUN chmod +x ./wkhtmltox_0.12.5-1.focal_amd64.deb 

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    git \
    default-libmysqlclient-dev \
    python-setuptools \
    python-dev \
    swig \
    build-essential \
    python3-pip \
    python3-dev

RUN pip3 install --upgrade pip

RUN pip install --upgrade pip

# RUN apt-get install -y build-essential libssl-dev libffi-dev python-dev

COPY ./requirements.txt /opt/requirements/requirements.txt

RUN pip3 install -r /opt/requirements/requirements.txt

USER odoo

CMD ["odoo"]
