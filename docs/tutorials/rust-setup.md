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
1. Open either terminal or command-prompt on Mac and Windows respectively <br>
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
