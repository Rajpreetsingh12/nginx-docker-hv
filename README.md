# nginx-docker-hv
The public repo which contains the docker file of the nginx image,the index.html file and the nginx.conf file used for deploying the simple nginx custom web-page on the docker container on local host.

Documentation of Graded Assignment on Dockerizing a Plain HTML Page displaying Hello docker on Nginx web-server on localhost 8088:-

Objective:-

The objective of this assignment is to familiarize yourself with Docker and containerization by Dockerizing a simple HTML page using Nginx as the web server:-

Requirements:

1. Basic HTML Page:

   - Created a plain HTML page named `index.html` with some content (e.g., "Hello, Docker!").

2. Nginx Configurations:

   - Created an Nginx configuration file named `nginx.conf` that serves the `index.html` page.

   - Configured Nginx to listen on port 80.

3. Dockerfile:

   - Created a `Dockerfile` to define the Docker image.

   - Used an official Nginx base image.

   - Copied the `index.html` and `nginx.conf` files into the appropriate location in the container.

   - Ensure that the Nginx server is started when the container is running.


4. Building the Docker Image:

   - Built the Docker image using the `Dockerfile`.

     ![image](https://github.com/user-attachments/assets/c176c38b-df2a-4f1f-8a03-3a68dd8fdae7)


5. Pushed the image on ECR

  - created the  the public repository and push them on the ECR

    ![image](https://github.com/user-attachments/assets/c8bd6011-e519-490a-8310-5eb576c13ed2)

  - took the login into the docker on ubuntu 22.4 by hitting "docker login"

    ![image](https://github.com/user-attachments/assets/e8b96f2b-ddac-4818-bef1-daded32b48ae)


  -  clicked on the view push commands button on the right corner of the ecr dashboard

    ![image](https://github.com/user-attachments/assets/7e5edf92-238d-43ce-82db-30d365e1cef3)

  - Then step by step  executed the commands available in the macos/linux tab:-

    Retrieve an authentication token and authenticate your Docker client to your registry. Use the AWS CLI:-

    aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/f8g8h5d4

    ![image](https://github.com/user-attachments/assets/a72cf902-e1ca-4547-be63-e27cf9924e98)

 - the image was already build before logging into the aws ecr to test the app on localhost so i directly tagged the image
   in the next step

 - As I have image already built in my local, so i tagged this image so that i  can push it to aws ecr public repository:

   ![image](https://github.com/user-attachments/assets/0489bd1b-c7d6-46e5-be32-621fbe48c377)

   Tagged the above image by hitting the command "docker tag nginxrepo:latest public.ecr.aws/f8g8h5d4/nginxrepo:latest"

    ![image](https://github.com/user-attachments/assets/f1cd7bc3-d862-42a1-ae59-13bd17544557)

    ![image](https://github.com/user-attachments/assets/7524499e-3898-4dae-9ff3-96c1058b1088)

  - Now pushed the image by hitting the command "docker push public.ecr.aws/f8g8h5d4/nginxrepo:latest"
  
   ![image](https://github.com/user-attachments/assets/006df137-fbd7-4dbf-92c2-d55d1ebaa7bd)

   The deployed artifacts including the link of the public ecr  repository is in  the README.md file (this file)

   public.ecr.aws/f8g8h5d4/nginxrepo:v1.0

   

   



   






   
