# Base image
FROM python:3

# Make  a directory for our application
WORKDIR /usr/src

# Install dependencies
RUN git clone https://github.com/joaoventura/flask-static-site.git /usr/src/repo

# Make  a directory for our application
WORKDIR /usr/src/repo
RUN pip install -r requirements.txt

# Run de application
CMD [ "python3", "./site.py"]

EXPOSE 8000