# GIT Continous Integration/Continous Delivery 
## Github Actions-Github Pages

![Applaudo.png](https://i.postimg.cc/Kc5J8TGf/Applaudo.png)
    
The purpose of this repository is to identify some fetures available in Github actions to deploy an efficient workflow for continous integration and delivery taking as an example a free template application developed in CSS and using Github Pages as the hosting platform to automate the final deployment of this static webpage. 


## Deployment Steps

- Create a directory in your GIT bash or Linux terminal where you can deploy and clone the repository:

```sh
https://github.com/renzzog777/Builders
```

- Assuming you already have GIT installed on your machine, you have to initialize the Gitflow method on GIT with this comand:

```sh
git flow init
```
Follow the suggested configuration by default until the end.

- The following step is to create a new Feature branch, you'll use this branch apply all the necessary cahnge to the source code. To create it, enter this command of Git Flow:
```sh
git flow feature start feature_branch
```
Replace the text "feature_branch" for a custom name skipping the "feature" prefix.

- Check  out to the new created branch and perform all the necessary changes in the source code of the CSS App (Preferably in index.html for practicality)

-After that, perform all the regular GIT command to commit and push the changes into the feature remote branch of the repository.

```sh
git add .
git commit -m "Message"
git push origin feature/"created branch"
```
- Github will request for the repository token, these are the credentials (Token is coded in base 64):

```sh
User: renzzog777
token: 'Z2hwX2Eyc3BxRkl6OXdOV1RUNk9heE14dXpNTDRaTXE4ZDMzSUdLQQ=='
```
You can decode the token with the following command:
```sh
echo 'given coded token' | base64 --decode
```

- The changes will be automatically upload into the remote 'develop' branch. Under the "actions" tab you must see a message like this: 

![automerge.png](https://i.postimg.cc/VLXxWg88/automerge.png)

This lets you know that feature branch  is merging into develop branch. The feature branch will be automatically deleted from the remote repository.

- As in real production environments, the repository admin will receive a pull-request, if everything's ok, he/she will accept it and merge 'develop' branch and 'master' branch with a couple of clicks.

Once they are merged, all the cahanges will rest in the master branch which is our default branch for releases and deployment.

- At this point another Github action has alredy been setup, it's the GH Pages 'build and deployments' action and you must see this process in the 'actions' tab of the repo:

![gp.png](https://i.postimg.cc/VLXxWg88/automerge.png)

- If you click on this process you'll be able to see the deployment fork where the URL of the webpage is allocated, you can copy and paste it into a browser, or you can copy it directly from here:

```sh
https://renzzog777.github.io/Builders/
```
In this case, some font color and headers cahnges were applied, you shuld see a webpage like this one:

![web.png](https://i.postimg.cc/h4NkWwrx/web.png)

## Requiered Files and Actions

Dillinger uses a number of open source projects to work properly:


| File  | Action |
| ------ | ------ |
| Auto_Merge.yml | [Detects PR's in the feature branch and merges with the 'develop' branch ][PlDb] |
| Master.yml | [Sends the PR to the repo for authorization, and merges 'develop' and 'master' later][PlGh] |

| Action  | Feature |
| ------ | ------ |
| Pages build and deployment | [Apply all the changes found in the 'master' branch into the Github Pages server and deploys the webpage][PlDb] |

## Author

Renzzo Gomez Reatiga
AWS DevOps- Trainnee.

Applaudo Studios

**rgomez@applaudostudios.dev**