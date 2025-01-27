# Setting up a dev container for Rust

* Primary author: [Cem Baykal](https://github.com/baykalcem)
* Reviewer: [hugh toomey](https://hughtoomey)

Hello! In this tutorial you will learn how to create a "Hello World" project in Rust.

## Prerequisites
Ensure you have satisfied the following before continuing:<br>
1. A GitHub account which is available at <a href="https://github.com">GitHub</a>.<br>
2. Git which can be found at  <a href="https://git-scm.com/book/en/v2/Getting-Started-Installing-Git">Installing Git</a> <br>
3. Visual Studio Code: <a href="https://code.visualstudio.com/">Install VS Code</a><br>
4. Docker Desktop: <a href="https://www.docker.com/products/docker-desktop/">Install Docker</a><br>
5. Fundamentals of using the command-line.

## 1. Repository Setup
1. Local Repository Setup:
    1. Open either terminal or command-prompt on Mac and Windows respectively. <br>
    2. Use the command line to create a new directory and go to it by using the following commands: <br>
    ```
    mkdir comp423-rust-tutorial
    cd comp423-rust-tutorial
    ```
    3. Use Git to initialize a new Git repository:
    ```
    git init
    ```
    4. Let's create a README file to explain our new repository:
    ```
    echo "# COMP423 Rust Tutorial > README.md
    git add README.md
    git commit -m "Initial commit with README"
    ```
2. Remote Repository Setup:
    1. Sign into your GitHub account
    2. Go to <a href="https://github.com/new">new repository</a> and fill in the following: <br>
        - Repository Name: comp423-rust-tutorial
        - Description: "Hello World in Rust"
        - Visibility: Public <br>
        - Do not initialize a README, .gitignore, or license.
    3. Hit "Create Repository"
3. Link Local And Remote Repositories:
    1. Back in the command line add your GitHub repository as a remote where ```<yourusername> ``` is your GitHub username using: 
    ```git remote add origin https://github.com/<your-username>/comp423-rust-tutorial.git```
    2. Using ```git branch``` check your default branch name. If it is not ```main``` use ```git branch -M main```.
    3. Push your local changes to the remote: 
    ```
    git push --set-upstream origin main
    ```
    4. If you refresh your repository in your browser you should see your changes. You can use ```git log``` to see the commit ID's and messages of your commits.
## 2. Development Container Setup
1. Let's create a Development Container Configuration <br>
    1. Back in Visual Studio Code, open the newly created ```comp423-rust-tutorial``` directory using File > Open Folder. <br>
    2. Navigate to Extensions and install the "Dev Containers" extension. <br>
    3. Create a ```.devcontainer``` directory and add a file named ```devcontainer.json``` within. <br>
    4. Add the following to this file: <br>
    ```
    {
    "name": "COMP423 Rust Tutorial",
    "image": "rust:latest",
    "customizations": {
        "vscode": {
            "settings": {},
            "extensions": [
                "rust-lang.rust-analyzer"
            ]
        }
    },
    "postCreateCommand": "",
    }
    ```
2. Press ```Ctrl+Shift+P on Windows or Cmd+Shift+P on Mac``` then type and select "Dev Containers: Reopen in Container". Then press enter to reopen your project in a development container.
4. Rust!
    1. Once your development container is open, use the built-in terminal and run ```rustc --version```. You should see ```rustc 1.84.0```.
    2. In the VS Code terminal, write ```cargo new hello_423```.
    3. This will create a new directory. Navigate to this folder in your terminal using ```cd hello_423```.
    4. Go to the ```hello_423/src/main.rs``` file. Replace this file with:
    ```
    fn main() {
    println!("Hello 426");
    }
    ```
    5. In your terminal, write ```cargo run```.