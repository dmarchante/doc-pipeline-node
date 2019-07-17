# How to Deploy a Node Project to AWS using Pipeline, Github, and Elastic Beanstalk


## Step 1: Write a Node App

Make sure it runs locally, and deploy it to Github. 

## Step 2: Create an Elastic Beanstalk App

It's okay to initialize with sample code for now. We will be overwriting it with the Pipeline later. 

## Step 3: Create a Pipeline

Go to the AWS console and click the "Create Pipeline" button.  

#### Important fields to fill out:

##### Pipeline name:

Pick something that makes sense. You will be living with it.

##### Service Role:

This will determine the permissions and access for your Pipeline. 

Pick a role that makes sense for your project. 

For our purposes, we created a new role which automatically grants default privileges.

![Pipeline Settings Screenshot](./assets/Pipeline_Settings.png) 

#### Source 

Your Github repo. 

You can log in with your Github credentials and select your repo. You can also customize which branch you want 
Pipeline to deploy. 

We recommend using your master branch.

##### Code Detection Options

Go with Github webhooks. 

![Source Screenshot](assets/Add_Source.png)


#### Build

Create build using AWS Code Build

Config section
![CodeBuild Config Screenshot](assets/1-create-build-config.png)

Source section
![CodeBuild Source Screenshot](assets/2-create-build-source.png)

Environment section
![CodeBuild Environment Screenshot](assets/3a-create-build-env.png)
![CodeBuild Environment Screenshot](assets/3b-create-build-env.png)

Specification section
![CodeBuild Specification Screenshot](assets/3a-create-build-spec.png)

Artifacts section
![CodeBuild Artifact Screenshot](assets/3a-create-build-artifact.png)

Logs section
![CodeBuild Artifact Screenshot](assets/3a-create-build-logs.png)

Create
![CodeBuild Artifact Screenshot](assets/3a-create-build-create.png)

Add Build Stage to Pipeline

Add Stage
![Add StageScreenshot](assets/0-add-stage.png)

Name Your Stage
![Add StageScreenshot](assets/0a-add-stage.png)

Add Action Group
![Add StageScreenshot](assets/0b-add-action-group.png)

Name Your Action
![Add StageScreenshot](assets/0c-add-action.png)

Enter Action Parameters
![Add StageScreenshot](assets/0d-add-action.png)

Click Done
![Add StageScreenshot](assets/0e-add-action.png)

Your Done
![Add StageScreenshot](assets/0f-add-action.png)

#### Provider

We are going to choose Elastic Beanstalk and the EB app we made in step 2.

![Deploy Screenshot](assets/Deploy.png) 

## Step 4: Create Pipeline

Click the **Create Pipeline** button. You're done!

Need proof? Here's [a link](http://mainnodepipeline-env.ptrkp2rcp6.us-west-2.elasticbeanstalk.com/) to our deployed "app."



![Success](./assets/Success.png)

Added Build Section
![Build Success One](./assets/build-success-1.png)
![Build Success Two](./assets/build-success-2.png)

## Troubleshooting

For most issues, you can find out where it went wrong by checking the checkmarks on the right. If the error is on the
 source, the first checkmark will be red. If it's on the deployment, the second checkmark will be red. 
 
 In those situations, you can either click the "Details" link in that pane for more info on the error, or you can go 
 to the original logs at the respective service. 
 
 ## Team
 Jhia Turner
 Roger Huba
 David Marchante
 Kent Ketter



 



















