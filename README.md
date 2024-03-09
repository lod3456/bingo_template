# Interactive Bingo Game

This repository contains an interactive bingo game that can be easily customized and deployed. The game features a dynamic bingo board populated with words from a text file and offers a responsive design suitable for both desktop and mobile devices. Winners are celebrated with a modal displaying a congratulatory message and a custom image.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

You need `git` installed on your local machine. You can download and install git from [Git's official site](https://git-scm.com/).

### Cloning the Repository

To get a local copy up and running, follow these simple steps:

1. Open your terminal.
2. Change the current working directory to the location where you want the cloned directory.
3. Type the following command and press Enter:

```
git clone https://github.com/yourusername/your-repo-name.git
```
### Setting Up Your Game
Updating the Bingo Words
1. Navigate to the root directory of the project.
2. Open the bingo-words.txt file located in the root.
3. Edit the file to include the words or phrases you want to use in your bingo game, each on a new line.
4. Save your changes.
Changing the Background Image
1. Place your desired background image in the images folder. If the folder doesn't exist, create it within the root directory of the project.
2. Open the style.css file.
3. Find the body selector and the background-image property.
4. Update the URL in the background-image property to the path of your new image. For example:

```
body {
    background-image: url('images/your-new-background.jpg');
}
```
Replace your-new-background.jpg with the name of your new image file.

Running the Game
To view the game:

Open the folder where the project is cloned.
Open the index.html file in a web browser.
Using GitHub Actions for Build and Deployment
This project is configured to use GitHub Actions for automated building and deployment to GitHub Pages.

Workflow Setup
Navigate to your repository on GitHub.
Click on the "Actions" tab.
Click on "New workflow".
Set up a workflow yourself or use an existing template for GitHub Pages deployment.
Configure the workflow .yml file to build your project and deploy it to GitHub Pages. An example setup might look like this:
yaml
Copy code
name: Build and Deploy to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2

    - name: Deploy to GitHub Pages
      uses: JamesIves/github-pages-deploy-action@4.1.0
      with:
        branch: gh-pages
        folder: .
        token: ${{ secrets.GITHUB_TOKEN }}
Commit your workflow file to the repository. GitHub Actions will automatically run the workflow when you push changes to the specified branch.
Customization
You may need to customize the workflow file based on your project's requirements, such as specifying a different branch or folder to deploy.

Contributing
Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

Fork the Project
Create your Feature Branch (git checkout -b feature/AmazingFeature)
Commit your Changes (git commit -m 'Add some AmazingFeature')
Push to the Branch (git push origin feature/AmazingFeature)
Open a Pull Request
License
Distributed under the MIT License. See LICENSE for more information.
