# syntax=docker/dockerfile:1

FROM python:3.10.6

RUN adduser --home /app --system --group dmitry
RUN chown -R dmitry:dmitry /app

USER dmitry

RUN python3 -m ensurepip --upgrade

WORKDIR /app

COPY requirements.txt ./requirements.txt

ENV PATH=/app/.local/bin:${PATH} \
    PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

RUN pip3 install --upgrade pip
RUN pip3 install --no-cache-dir -r ./requirements.txt
RUN pip3 install SQLAlchemy Flask-SQLAlchemy

COPY . .

#ENTRYPOINT ["python3", "./app.py", "my_var"]
CMD ["python3", "./app.py"]
#CMD [ "python3", "-m", "flask", "run","--host=0.0.0.0"]


#RUN source /home/myuser/venv/bin/activate

#RUN pip install --root-user-action=ignore --upgrade pip

#RUN useradd -ms /bin/bash myuser
#RUN adduser --home /app --system --group myuser

#ENV PATH=/app/.local/bin:${PATH} \
#    PYTHONUNBUFFERED=1 \
#    PYTHONDONTWRITEBYTECODE=1

#WORKDIR /app



#COPY requirements.txt requirements.txt

#USER myuser
#RUN pip install -r /requirements.txt


#COPY --chown=myuser:myuser . .

#CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]

