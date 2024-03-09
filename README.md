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

```bash
git clone https://github.com/lod3456/bingo_template.git
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

```bash
body {
    background-image: url('images/your-new-background.jpg');
}
```
Replace your-new-background.jpg with the name of your new image file.

#### Running the Game
To view the game:

1. Open the folder where the project is cloned.
2. Open the index.html file in a web browser.

### Using GitHub Actions for Build and Deployment
This project is configured to use GitHub Actions for automated building and deployment to GitHub Pages.

### Workflow Setup
1. Navigate to your repository on GitHub.
2. Click on the "Actions" tab.
3. Click on "New workflow".
4. Set up a workflow yourself or use an existing template for GitHub Pages deployment.
4. Configure the workflow .yml file to build your project and deploy it to GitHub Pages. An example setup might look like this:
   
```yaml
# Sample workflow for building and deploying a Jekyll site to GitHub Pages
name: Deploy Jekyll with GitHub Pages dependencies preinstalled

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ["main"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v4
      - name: Build with Jekyll
        uses: actions/jekyll-build-pages@v1
        with:
          source: ./
          destination: ./_site
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3

  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```
1. Commit your workflow file to the repository. GitHub Actions will automatically run the workflow when you push changes to the specified branch.
#### Customization
You may need to customize the workflow file based on your project's requirements, such as specifying a different branch or folder to deploy.

### Contributing
Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated.

1. Fork the Project
2. Create your Feature Branch (git checkout -b feature/AmazingFeature)
3. Commit your Changes (git commit -m 'Add some AmazingFeature')
4. Push to the Branch (git push origin feature/AmazingFeature)
5. Open a Pull Request

### License
Distributed under the MIT License. See LICENSE for more information.
