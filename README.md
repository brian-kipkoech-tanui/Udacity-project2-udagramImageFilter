# Udagram Image Filtering Microservice

## Elastic Beanstalk
EC2, S3, Simple Notification Tool, CloudWatch, autoscaling, and Elastic Load Balancers are just a few of the AWS services that are orchestrated by AWS Elastic Beanstalk, an orchestration service provided by Amazon Web Services for the deployment of applications.

# URL
[Github Link](https://github.com/brian-kipkoech-tanui/Udacity-project2-udagramImageFilter/tree/master)
[ElasticBeanstalk Link](http://udagram-image-filter-dev22222222.us-east-1.elasticbeanstalk.com/)

- [Failed test (422 status code - Unprocessable entity)](http://udagram-image-filter-dev22222222.us-east-1.elasticbeanstalk.com/filteredimage?image_url=https://upload.wikimedia.org/wikipedia/commons/b/bd/Golden_tabby_and_white_kitten_n01.jpg)
![failed deployment screenshot](https://github.com/brian-kipkoech-tanui/Udacity-project2-udagramImageFilter/blob/dev/deployment_screenshots/deployment_screenshot_0_failed.png?raw=true)

- [test passed(200 status code)](http://udagram-image-filter-dev22222222.us-east-1.elasticbeanstalk.com/filteredimage?image_url=https://ichef.bbci.co.uk/onesport/cps/976/cpsprodpb/149BD/production/_126431448_gettyimages-1393565109.jpg)
![deployment screenshot](https://github.com/brian-kipkoech-tanui/Udacity-project2-udagramImageFilter/blob/master/deployment_screenshots/deployment_screenshot1.png?raw=true)

![working elastic Beanstalk scrrenshot](https://github.com/brian-kipkoech-tanui/Udacity-project2-udagramImageFilter/blob/master/deployment_screenshots/deployment_screenshot2.png?raw=true)



Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into three parts:
1. [The Simple Frontend](https://github.com/udacity/cloud-developer/tree/master/course-02/exercises/udacity-c2-frontend)
A basic Ionic client web application which consumes the RestAPI Backend. [Covered in the course]
2. [The RestAPI Backend](https://github.com/udacity/cloud-developer/tree/master/course-02/exercises/udacity-c2-restapi), a Node-Express server which can be deployed to a cloud service. [Covered in the course]
3. [The Image Filtering Microservice](https://github.com/udacity/cloud-developer/tree/master/course-02/project/image-filter-starter-code), the final project for the course. It is a Node-Express application which runs a simple script to process images. [Your assignment]

## Tasks

### Setup Node Environment

You'll need to create a new node server. Open a new terminal within the project directory and run:

1. Initialize a new project: `npm i`
2. run the development server with `npm run dev`

### Create a new endpoint in the server.ts file

The starter code has a task for you to complete an endpoint in `./src/server.ts` which uses query parameter to download an image from a public URL, filter the image, and return the result.

We've included a few helper functions to handle some of these concepts and we're importing it for you at the top of the `./src/server.ts`  file.

```typescript
import {filterImageFromURL, deleteLocalFiles} from './util/util';
```

### Deploying your system

Follow the process described in the course to `eb init` a new application and `eb create` a new environment to deploy your image-filter service! Don't forget you can use `eb deploy` to push changes.

## Stand Out (Optional)

### Refactor the course RESTapi

If you're feeling up to it, refactor the course RESTapi to make a request to your newly provisioned image server.

### Authentication

Prevent requests without valid authentication headers.
> !!NOTE if you choose to submit this, make sure to add the token to the postman collection and export the postman collection file to your submission so we can review!

### Custom Domain Name

Add your own domain name and have it point to the running services (try adding a subdomain name to point to the processing server)
> !NOTE: Domain names are not included in AWS’ free tier and will incur a cost.
