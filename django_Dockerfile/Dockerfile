# base image
FROM python:3.10.6

# set environment variables
ENV DockerHOME /home/app/webapp

# create the appropriate directories
RUN mkdir -p $DockerHOME

# set work directory
WORKDIR $DockerHOME

# copy project to working directory
COPY . $DockerHOME

# environment variables
ENV PYTHONDONTWRITEBYTECODE 1
# to avoid buffering ( directly print to console )
ENV PYTHONUNBUFFERED 1 

# install dependencies
RUN pip install --upgrade pip
RUN pip install -r requirements.txt

# port where the Django app runs
EXPOSE 8000

# start server command
# specifying the port manually is necessary for the container to be accessible from outside
# build the image and run the container with exposing/mapping the port 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]