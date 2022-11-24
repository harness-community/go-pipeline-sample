##  DockerFile Creation  
 
 - Click on `Add step`
   - Go to builds and click on run 
   - Change the settings as following:
   
      - Name: `go-build`
      - Container registry: Click on the Docker connecter created in the previous step 
      - Image: `golang:1.15`
      - Commands: Copy the following command and click on apply changes.
 
         ```
         set +e
		go get gotest.tools/gotestsum
		CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -a -tags netgo
		exit 0

         ```

   
    
   ![create_dockerfile_step_step](/images/go_build.png)    
   
   
 ## Build and Push Image to Docker Registry
 - Click on `Add step`
 - Go to `builds` and click on `build and push an image to docker registry`
 -  Change the settings as following:
    - Name: `Build and push image to docker hub`
    - Docker connector: select the Docker connector you created previously 
    - Docker repository: `<docker-hub-username>/<docker-repository name>`
    - Tags: `latest`
    

![build_and_push_image_to_docker](/images/build_and_push_docker.png)   



## Run the Pipeline
 - Click ↑Save.
 - Click ```Run```. 
 - The Pipeline Inputs settings appear.
   - Under CI Codebase, select ```Git branch```.
   - In Git Branch, enter the name of the branch where the codebase is, here ```main```
     - Click Run Pipeline.


