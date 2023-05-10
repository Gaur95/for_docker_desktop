# pick a container img
FROM ubuntu
#discription for Image
LABEL Name=Akash
LABEL email=aakash@gmail.com
RUN apt update 
RUN apt install apache2 -y
#to change working directory
WORKDIR /var/www/html/
#copy a code from source to container
COPY ./index.html .
#to publish port
EXPOSE 80
# to run apache service 
CMD [ "apache2ctl" ,"-D", "FOREGROUND" ]