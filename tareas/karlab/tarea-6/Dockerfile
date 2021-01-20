# Base image
FROM python:3

# directory
WORKDIR /code_python

# dependencies
ADD requirements.txt /code_python
RUN pip install -r requirements.txt

# files
COPY orm.py /code_python

# commands
CMD ["python3", "orm.py"]