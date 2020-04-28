# Connecting Docker to Github

Github Actions are a cool way to create a pipeline for code. This is a brief overview of how to create a pipeline with Docker and Github Actions.

Set up a GitHub account and repo for your code.

Create a action using workflow, see the GitHub documentation for a walk through.

Install docker on your laptop and create a secure Dockerfile that containerizes your application.

### This is where I got stuck, how do I save the container in Github container registry?

1. Create new Github Token
    1. Create a new Token and store it in User root directory: 
        1. `cd ~/.`
        1. `ssh-keygen -t rsa -b 4096 -C “<email associated with gitlab>“`
        1.  Follow the prompts nd save it as `.GITHUB_TOKEN` and create a private key. Learn more about that here: https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key
    1. Add generated token to Github SSH keys.
        1.  Copy the output of `cat .GITHUB_TOKEN.pub`
        1. Use this to create a new Github SSH key.
            1. Github / Settings / SSH and GPG keys follow directions here: https://help.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key
    1. Connect to docker in terminal.
        1. https://help.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-docker-for-use-with-github-packages
