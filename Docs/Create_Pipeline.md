In this tutorial you will learn how you can seamlessly get started with Harness CI for ```GO```. In this pipeline we will be implementing a Hello World Server in `GO`.
### Step 1: Fork the repository 


- Go to [Go-Pipeline-Samples Repo](https://github.com/harness-community/go-pipeline-sample)
- Now fork this repository in your Github [Forking a repository in Github](https://docs.github.com/en/get-started/quickstart/fork-a-repo)


### Step 2: Create your Harness Project

- Move to the Harness Platform & click on Project -> New Project
- Configure the project settings as below

  `Name: (Default Project Name)`


  `Organization: Default`
 

 ![configure_the_stage_setting](/images/about_the_project.png)
   
   In Configure your pipeline -> Select Stater Pipeline.

- Select CI Module in the modules sections


### Step 3: Pipeline Creation & Configure Stages

- Click on `Pipelines` -> Create a Pipeline 
- Configure the pipeline as below

  `Name: Build go-pipeline-sample`

  `Set up pipeline as: Inline`

 ![configure_the_stage_setting](/images/Pipeline_Creation_&_Configure_Stages.png)

Next, we are going to add Stages and steps to our Pipeline and compile our Go code.

Click on **[Build step](buildStep.md)**
