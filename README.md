# Todo
Continuous Integration and Deployment:
You can use a continuous integration (CI) and deployment (CD) tool to automate the release process. For example, you can use Jenkins or Travis CI to build and test your code automatically whenever changes are made, and then deploy the new version to a staging or production environment.

# Managing Different Executables:
To manage different executables for different architectures and clients, you can use Git submodules. You can create a separate repository for each client and architecture, and then add them as submodules to the main repository. This way, you can keep the code for each version separate while still being able to manage them together in the main repository.

Managing different executables for different architectures and clients is an essential aspect of software development, particularly if you want to develop a cross-platform application. As you mentioned in your question, your software has different exe files for 32-bit and 64-bit architecture, and there are changes based on each client, which requires you to maintain two exes for each client. To manage these different executables efficiently, you can use Git submodules. Here's how it works:

# Git Submodules:
Git submodules allow you to include one Git repository within another Git repository as a subdirectory. This means you can keep the code for different versions separate while still being able to manage them together in the main repository. For example, you can create a separate repository for each client and architecture, and then add them as submodules to the main repository.

Here are the steps you can follow to manage different executables using Git submodules:

## Step 1: 
**Create a separate repository for each version:**

You can create a separate repository for each version of your software. For example, you can create a repository for the 32-bit version and another repository for the 64-bit version. Similarly, you can create a separate repository for each client, depending on their specific requirements. Create Tags for each of them

```bash
git tag -a client1_32 -m "Tagging client1 32-bit executable"
git push origin client1_32
```

## Step 2: 
**Add the submodules to the main repository:**

After you have created the separate repositories for each version of your software, you can add them as submodules to the main repository. To do this, navigate to the root of the main repository and run the following command:

`git submodule add <URL of the submodule repository> <path to the submodule>`

For example, if you have a repository for the 32-bit version of your software, you can add it as a submodule to the main repository using the following command:

`git submodule add https://github.com/<username>/<32-bit-repo>.git 32-bit`

Similarly, you can add the 64-bit version and each client repository as submodules to the main repository.

## Step 3: 
**Commit the changes:**

After you have added the submodules to the main repository, you need to commit the changes by running the following commands:

```bash
git add .
git commit -m "Added submodules for different versions"
```

## Step 4: 
**Update the submodules:**

Whenever there are updates to the submodules, you can update them by navigating to the root of the main repository and running the following commands:

```bash
git submodule update --init --recursive
git submodule foreach git pull origin master
```

The first command updates the submodule references in the main repository, while the second command updates the submodules themselves.

## Step 5: 
**Build and Test:**

Once you have added and updated the submodules, you can build and test your code. Depending on your development process, you can use a build tool such as MSBuild or a continuous integration and deployment (CI/CD) tool such as Jenkins or Travis CI to automate the build and test process.

By using Git submodules to manage different executables, you can keep the code for each version separate while still being able to manage them together in the main repository. This makes it easier to maintain and manage different versions of your software and streamline the development process.
