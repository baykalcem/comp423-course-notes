# Setting up a dev container for Rust

* Primary author: [Cem Baykal](https://github.com/baykalcem)
* Reviewer: [Hugh Toomey](https://hughtoomey)

Hello! In this tutorial you will learn how to create a "Hello World" project in Rust. You will learn how to setup a Git repository, create a Rust development container, and how to make a simple Hello World program in Rust. Much of this tutorial is inspired by <a href="https://comp423-25s.github.io/resources/MkDocs/tutorial/#conclusion">Starting a Static Website Project with MkDocs</a> by Kris Jordan.<br>

## Prerequisites
Ensure you have satisfied the following before continuing:<br>
1. A GitHub account which is available at <a href="https://github.com">GitHub</a>.<br>
2. Git which can be found at  <a href="https://git-scm.com/book/en/v2/Getting-Started-Installing-Git">Installing Git</a> <br>
3. Visual Studio Code: <a href="https://code.visualstudio.com/">Install VS Code</a><br>
4. Docker Desktop: <a href="https://www.docker.com/products/docker-desktop/">Install Docker</a><br>
5. Fundamentals of using the command-line.

## Repository Setup
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
    echo "# COMP423 Rust Tutorial" > README.md
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
## Development Container Setup
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
    !!! note "Extra Info"
        * name: The label that appears in your VS Code Dev Container environment.
        * image: Points directly to an existing Docker image—in this case, the official Rust image on Docker Hub.
        * settings: Custom VS Code settings inside the container. For our purposes, we can leave this blank.
        * extensions: Lists extensions that will be installed automatically in the container. In this, case we are installing the official rust-analyzer extension.
        * postCreateCommand: Runs after the container is created. We do not need to do anything after creation.

2. Opening Dev Container
    1. Press ```Ctrl+Shift+P on Windows or Cmd+Shift+P on Mac``` then type and select "Dev Containers: Reopen in Container". Then press enter to reopen your project in a development container.
## Rust!
1. Once your development container is open, use the built-in terminal and run ```rustc --version```. You should see ```rustc 1.84.0```.
2. In the VS Code terminal, write ```cargo new hello_423 --vcs none```.
3. This will create a new directory. Navigate to this folder in your terminal using ```cd hello_423```.
4. Go to the ```hello_423/src/main.rs``` file. Replace this file with:
```
fn main() {
println!("Hello 426");
}
```
4. In your terminal, write ```cargo build```. This command is equivalent to using ```gcc``` to compile a program into an executable file. This command compiles the code then places it into the ```target/debug``` directory. Then, enter ```./target/debug/hello_423```. This runs the file and is equivalent to writing ```./``` for a file compiled with ```gcc```.
5. In your terminal, write ```cargo run```. You will see the output immediately. This is because this command compiles and automatically executes the compiled program unlike ```build```.
!!! note "Build vs Run"
    When you use `cargo build`, Cargo compiles your Rust code and produces an executable or library, but it does not run the resulting binary. This means Cargo simply downloads any missing dependencies, compiles the project, and places the build artifacts in a designated target directory. On the other hand, `cargo run` not only builds your code—downloading and compiling dependencies as needed—but also executes the resulting binary immediately afterward. It’s a convenient way to streamline development, letting you compile and run your program in a single step rather than manually running the built binary each time.

Finally, CELEBRATE!!! You have successfully made a Hello World program from scratch in Rust! 