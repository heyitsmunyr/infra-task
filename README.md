# infra-task
This is a task repo with sample flask app!

You can follow these instructions to build, run and push/pull the image from local!

1. The docker file is already there, it simply copies the requirement.txt to the container's working directory which is app in our case and installs the dependencies first. Then copies the content of local directory to the container's working directory and then runs the app.py as executable.

2. Thats how the Dockerfile is working, we now need to build the image from it, we'll run:
docker build -t itsmunyrhere/flaskapp:latest .

I am using the image name as itsmunyrhere/flaskapp and the tag is latest. itsmunyrhere is my docker repo, that's why I am using this naming convention.

3. Time to run this image in a container! 
docker run -d -p 5000:5000 itsmunyrhere/flaskapp

I am simply binding container's port with my local port, 5000 in this case. Running in detached mode as well. 



NOTE: 
To push the image:
1. Login using: 
docker login

2. docker push itsmunyrhere/flaskapp:latest


To pull the image: 
docker pull itsmunyrhere/flaskapp:latest





#CI
1. Github actions is being used, a simple workflow created that just runs on Saturday at 7pm using cron. 
