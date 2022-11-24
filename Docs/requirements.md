### Make sure you have the following set up before you begin this tutorial:

- **Github Account:** This tutorial clones a codebase from a Github repo. You will need a Github account so Harness can connect to Github.
- **Docker Hub Account and Repo:** You will need to push and pull the image you build to Docker Hub. You can use any repo you want, or create a new one for this tutorial.
- **Kubernetes cluster for Harness Delegate and build farm:** You'll need a Kubernetes cluster for Harness to use for the Harness Delegate and as a build farm. Ensure you have a cluster that meets the following requirements:
- **Networking:** Outbound HTTPS for the Harness connection, and to connect to Docker Hub. Allow TCP port 22 for SSH.
- **Namespace:** When you install the Harness Delegate, it will create the harness-delegate namespace. You'll use the same namespace for the build farm.

