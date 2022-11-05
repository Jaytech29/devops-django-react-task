# Pull base image
FROM python:3.9.6-alpine

ENV Docker_HOME=/home/app/webapp  

RUN mkdir -p $Docker_HOME  

# Pull base image
WORKDIR $Docker_HOME  
  
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1  

# install dependencies  
RUN pip install --upgrade pip  

# copy to docker home directory. 
COPY . $Docker_HOME  
 
#RUN pip install -r requirements.txt  
RUN pip freeze > requirements.txt
RUN pip install django

# expose port for Django app  
EXPOSE 8000  
# start server  
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
