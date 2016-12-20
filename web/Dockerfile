FROM python:2.7
ENV PYTHONUNBUFFERED 1
RUN mkdir /src
WORKDIR /src

COPY requirements.txt /src/

# Install dependencies

RUN apt-get update && apt-get install -y \
  libxml2-dev \
#  libxslt1-dev \
  python-dev \
  postgresql

# Install reqs  

RUN pip install -r requirements.txt

# Install the Git stuff

COPY ./git /src/git
COPY wait-for-it.sh /src/wait-for-it.sh
COPY init.sh /src/init.sh
COPY settings.ini /src/git/cobradb/settings.ini
#RUN ["chmod", "+x", "/src/wait-for-it.sh"]
#RUN ["chmod", "+x", "/src/init.sh"]
#RUN ["chmod", "+x", "/src/git/cobradb/bin/load_db"]

#chmod -R 755 /src;
RUN find /src -type f \( -name "*.sh" -o -not -name "*.*" \) -exec chmod +x \{\} \;
RUN cd /src/git/cobradb && pip install -e /src/git/cobradb
RUN cd /src/git/bigg_models && pip install -e /src/git/bigg_models

# Database stuff

COPY database.dump /src
#RUN cd /src/git/bigg_models_data && python download_genbank foo@bar.ly