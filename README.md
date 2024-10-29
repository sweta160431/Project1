
# Project 1

# Deploy Static Website

This guide will walk you through the process of installing Docker, creating a simple static website (HTML/CSS), and deploying it using Docker with Nginx.

## Step 1: Install Docker

### 1. Update the apt package index:

sudo apt-get update

### 2. Install Docker Using this command:

sudo apt-get install docker.io

### 3. Verify that Docker is installed:

docker --version

Docker is now installed. You can run containers and build Docker images.

## Step 2: Create Project Folder for Static Website

### 1. Create a new dire

### 2. Add the following basic HTML content to index.html:

```bash
  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Poppins&display=swap" rel="stylesheet">
    <script src="https://kit.fontawesome.com/235004aab8.js" crossorigin="anonymous"> </script>
    <title> Destination 2: Boracay </title>
</head>
<body>  
        </div>
    </div>
    <div class="main_content">
      <div class="about" id="center_content">
        <h3> Project 1 </h3>
        <p> Welcome To My Static Website </p>
        <div>
          <p>
         This is a simple, fast-loading, and lightweight static website. Explore the features, services, and information below.We specialize in providing quick and efficient solutions for small websites. This static site is built using HTML, CSS, and hosted in a Docker container, demonstrating how easy it is to get a website up and running.	  </p>
        </div>    
      </div>
    </ul>
    </div>   
    </div>
    <nav>
          <a href="https://www.geeksforgeeks.org" class="button"> HOME </a>
          <a href="https://www.geeksforgeeks.org/devops-tutorial/?ref=ghm" class="button"> ABOUT DEVOPS </a>
          <a href="https://www.geeksforgeeks.org/introduction-to-docker/?ref=lbp" class="button"> DOCKER </a> 
           <a href="https://www.geeksforgeeks.org/what-is-dockerfile-syntax/?ref=lbp" class="button"> DOCKERFILE </a> 
          <a href="https://www.geeksforgeeks.org/introduction-to-docker/?ref=lbp#install-docker-on-ubuntu" class="button"> DOCKER INSTALLATION </a> </ul>
        </nav>
</body>
</html>
```

3. Save and exit (Esc, :wq , Enter to exit vim).

## Step 4: Create style.css for Styling

You can also add some simple styles to your website by creating a style.css file.

### 1. Create and open the style.css file:

```bash
body, div, h1, h2, ul, li, i, a, p, h3, footer {
    padding: 0;
    margin: 0;
    border: 0;
}
body {
    background-image: url(https://sitecore-cd.shangri-la.com/-/media/Shangri-La/boracay_boracayresort/about/2023_SLBO_Explore-Boracay.jp);
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
    font-family: 'Poppins', sans-serif;
    color: white;
}

::-webkit-scrollbar {
  width: 7px;
}

::-webkit-scrollbar-thumb {
  background-color: #faf7f7;
}

body a {
    color: white;
     text-decoration: none;
}

body ul li {
       list-style:none;
    margin-top: 10px;
}

p {
    font-size: 55px;
    padding-top: 20px;
    padding-bottom: 20px;
}

#center_content {
      padding-left: 60px;
}

.main_content {
    position: relative;
    width: 64%;
    height: 100%;
    Float: center 
}

.about h3 {
    padding-top: 110px;
}

.about div {
    height: 100%;
    width: 90%;
    border-radius:0.5em;
    background-color: #121212;
}

.about div p {
    font-size: 20px;
    margin: 20px 20px 20px 20px;
}

.div {

    height: 100%;
    width: 90%;
    border-radius:0.5em;
    background-color: #121212;
}

nav {
  font-family:"Rubik", sans-serif;
  color: black;
  height: 100px;
  margin: 0px;
  display:flex;
  justify-content:space-around;
}

.button {
  background-color:#FFFFFF;
  margin:20px;
  height:20px;
  width:250px;
  padding:20px;
  text-align:center;
}
```

### 3. Save and exit (Esc, :wq , Enter to exit vim).

## Step 5: Create a Dockerfile A Dockerfile is needed to define how to containerize the static website using Nginx.

### 1. Create and open the Dockerfile:
vim Dockerfile

### 2. Add the following content to the Dockerfile:
FROM nginx:latest

COPY . /usr/share/nginx/html

Expose 80

## Step 6: Build the Docker Image Now that you have your project files and Dockerfile ready, you need to build a Docker image.
### 1. Build the Docker image:
docker build -t static-website .

### 2. To check Docker Images:
docker images

## Step 7: Run the Docker Container After building the Docker image, you can now run the container and access the website in a browser.
### 1. Run the container:
docker run -d -p 80:80 static-website

### 2. Verify that the container is running:
docker ps

## Step 8: Access the Website
### 1. Open your browser and navigate to:
http://localhost:8080

You should now see your static website up and running, served by the Docker container using Nginx.








