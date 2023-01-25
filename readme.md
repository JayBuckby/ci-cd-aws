# CI CD Jenkins -> AWS

​
Give a brief overview of the project.

This project allows the users to make changes locally to their codebase and once they are pushed to their GitHub on a different branch, Jenkins will build the environment, test to make sure it works and then merges the branches to update to the main branch and push the changes.
​
![Demo](./app/public/projectdemo.gif)
​

## How have you used Jenkins to add Continuous integration with this project?

Built a test environment on Jenkins to test the build when changes are made so that if there are any errors, they're not pushed onto a main branch.
​

### How did you allow Jenkins access to the Github repo?

Setup Jenkins with the required settings: GitHub Project and provided it with the project URL.
​

### How did you get the Github repo to trigger the build?

Added the option on Jenkins to allow GitHub Source Code Management, providing a private SSH key.
Implemented a GitHub webhook and provided it with the Jenkins URL as well as the param for the webhook, this in turn was triggered through any event (Push/Pull/Merge etc)

## ​​

## How have you used Jenkins to add Continuous delivery with this project?

On a successful test build through CI, with a Post-build action that would trigger only if the build was stable it would build the CD Project, which would then push the build to the main branch and executing the shell script commands.
​

### How did you allow Jenkins access to the EC2 instance?

On EC2, we selected our instances and within the security settings, we changed the Security Group and added in the "JenkinsDeployment" option.
In Jenkins under the Build Environment section we enabled the "SSH Agent" option and then specified credentials by adding in our Private AWSKey.
​

### How did you get the CI project to trigger the CD build?

On a successful CI Project build, a post-build action (build other projects) would be implemented that would build the CD Project.

## ​
