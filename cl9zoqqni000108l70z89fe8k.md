# How to Contribute to Open Source Project

**Open source project** is any project freely available for everyone to use or modify. Contributing to these projects will help improve the project and you the developer.
# Steps to Contributing to Open-source projects:
1. Pick an open-source project to contribute to.
2. Read the CONTRIBUTING.md and README.md files
3. Fork the Repository
4. Clone the Repository
5. Create a new branch
6. Make necessary changes and commit those changes locally
7. Push Changes to GitHub
8. Update the local repository 
9. Submit changes for review

# **(Step 1) Pick an open-source project to contribute to**

 Pick an open-source project on the internet you have used or are interested in.
You can check this link for beginners' open-source projects:

https://up-for-grabs.net/#/

https://github.com/mungell/awesome-for-beginners

https://goodfirstissue.dev/

https://github.com/firstcontributions/first-contributions

We will contribute to this project:
https://github.com/firstcontributions/first-contributions



![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666437806478/tBYpDit2Z.png align="left")


# **(Step 2) Read the CONTRIBUTING.md and README.md files**

Read the README.md and CONTRIBUTING.md file to get a sense of what the project is about and how to contribute to the project. At this stage, you want to get every information necessary about the project.

For the project we are contributing to: https://github.com/firstcontributions/first-contributions, the README.md file explains that the project helps beginners make their first contribution to open-source by adding their names to Contributors.md file.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666438099491/fEjKXbIqe.png align="left")


We will stick to the information we got from the README.md file. We will add our name to the  Contributors.md file, to contribute to the project. 
Okay guys let's start coding!!


# **(Step 3) Fork the Repository**

To Fork a repository mean to make a copy of a project or repository in your own GitHub account.
On the project we want to contribute to: https://github.com/firstcontributions/first-contributions  click on the Fork button,
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666440036771/N4WHHsEuD.png align="left")
It will take you to a page as below to Create a new fork. Click on Create fork, which will take you to your own GitHub account having the project

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666440293399/y8mqJQKK4.png align="left")


Below is my Github account with the project. Check the link on your browser and notice your username is there.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666440576386/TWnsqgwtK.png align="left")

# **(Step 4) Clone the Repository**

This will make a local copy of the project on your computer. Copy the URL of the project. Notice your username in the URL

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666442992429/19YzNvonY.png align="left")
and run the following commands on your terminal(command prompt-window users) to make a copy of the project on your Desktop. 
```
cd desktop
```
```
git clone https://github.com/emmakodes/first-contributions.git
``` 
Notice .git added to the URL

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666443704874/_shzkYaTY.png align="left")

# **(Step 5) Create a new branch**

Go to your Desktop you will find a folder "first-contributions", Open the folder with your favorite code editor(visual studio code, pycharm etc). Open the terminal and run the following command
```
git branch my-new-branch
```
Executing the above command will isolate your code so that you can make your changes and then merge back to the main code. Most times, you will want to use a more descriptive name instead of my-new-branch 

Next, run below to switch to that branch
```
git checkout my-new-branch
```
# **(Step 6) Make necessary changes and commit those changes locally**

One way of contributing to the project is by adding our names to Contributors.md. Open the Contributors.md file and add your name in between other names.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666449940963/RpZPnCgnj.png align="left")
Mine added.

Run the following command on the terminal to add and commit the new change
```
git add Contributors.md
```
```
git commit -m "Add emmakodes to Contributors list"
```

# ** (Step 7) Push Changes to GitHub**

Run the following command to push changes to the current branch of our forked repository. 
```
git push --set-upstream origin my-new-branch
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666451242638/RWARRV6cu.png align="left")
You should see the response above when you execute the command on your terminal

# **(Step 8) Update the local repository **

Since we are contributing to an open-source project, other developers might have contributed or applied changes to the online project since the last time we check, so we have to get those changes before we apply for our own contribution to be added to avoid conflicts.
Run the following command on your terminal:
```
git remote add upstream https://github.com/firstcontributions/first-contributions.git
```
https://github.com/firstcontributions/first-contributions.git should be the URL of the repo you forked from. upstream is an alias for the URL. Run the following command:
```
git fetch upstream
```
```
git checkout main
```
```
git merge upstream/main
```
Above, we set up and fetch changes from the GitHub repo we forked from and then merge those changes to our local repo.

# **(Step 9) Submit changes for review**

We can submit our changes for it to be reviewed by the maintainers of the open-source project. 
Go to your GitHub account, then Your repositories, access the first-contributions repositories, and click on Compare and pull request, 
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666655576238/EE28AzCla.png align="left")
It will take you to the following page, you can add comments and then click on Create pull request.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1666655651447/z83IoJbIJ.png align="left")
When you click on Create pull request, the maintainers of the project will receive a notification to merge your changes to the main project. They may decide to merge if everything is okay or make a comment for you to make changes to your pull request.

If they merge your changes, then congratulations on making your first open-source contribution. Go further, look for more projects and contribute to those projects.


