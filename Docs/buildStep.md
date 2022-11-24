### Build Step
- Click on `Add Stage` to get started with the pipeline creation
- Select the type of stage as `Build`

- Configure the Stage Settings as below
  - Name: `build test and run`
  - Make sure to turn on `clone codebase`.


![configure_the_stage_setting](/images/About_stage.png)


**Setup the Connector as follows**

Select `Connectors` -> Click on `+ New Connector`

Connector Type: `Github`

Name: `go-sample-connector`

URL Type : `Repository`

Connection Type: `HTTP`

GitHub Repository URL: Paste the link of your forked repository

Username: (Your Github Username)

Personal Access Token: [Check out how to create personal access token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

Secret Name: `Git-Token`

Secret  Value: PAT value generated in Github

Click on Save.

This will allow the repository to be fetched click on it and click `Apply Selected`

Make Enable API access (ON) with the secret token created

Click on **Connect through Harness Platform**.

To develop more understanding on Connectors [check out the docs here](overview.md)

Go the Infrastructure settings of stage and click on `Hosted by Harness`.

Then go to Execution (In this step we are going to compile the code)



![configure_the_stage_setting](/images/Stage_Infrastructure.png)



#### Run-Unit Test

- Click on `Add step`
 - Go to `Build` and click on `Run`
 - Change the settings as following 
 - Name: `run-unit-test`
 - Container Registry -> Choose `New connector`
   - Click on `Docker Registry`
   - Change the settings as following 
       - Overview 
         - Name- `docker quickstart`
       - Details 
         - Docker registry url -  `https://index.docker.io/v1/`
         - Provider type - `Docker Hub`
         - Authentication - `Username and Password`
         - Username - Docker hub username 
         - Secret Token - [Check out how to create docker PAT](DockerPat.md)
       - Connect to Provider 
         - Choose to connect through the Harness Platform
         - It will take sometime to verify your credentials.
  - Image: `golang:1.15`
  - Shell: `Sh`
  - Command: 
  ```set +e
	  go get gotest.tools/gotestsum
	  gotestsum --format=standard-verbose --junitfile unit-tests.xml
	  exit 0
  ```
 - Then click `Apply changes`



![configure_the_stage_setting](/images/run-unit-test.png)




Next we are going to create Image and Push the image to docker registry 

Click on **[Create Image and Push to Docker Registry](DockerPush.md)**
