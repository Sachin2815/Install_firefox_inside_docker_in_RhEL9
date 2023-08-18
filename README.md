step1 : make a docker file

step2 : build the image
#docker build -t sachin5858/newos:v1 filename .

step3 : push to docker hub
#docker push sachin5858/newos:v1 

In local system pull docker image
#docker pull sachin5858/newos:v1


in local system rub the command : docker run -it --rm --net=host --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xuthority:rw" imagename step4 : use anywhere to launch the firefox.
