# Orientation exercises

This tutorial & exercise is designed for trainees interested in joining our lab. It reflects our expected computing skills using R, Python, Linux shell commands and bioinformatics workflow languages.
Even if you lack the skills for one or more of the languages at the time you start this tutorial, we believe the learning curve for new skills enough to complete the exercises is reasonable given a few hours of effort. Still,
please do not hesitate to contact us (wang.gao@columbia.edu) if there is a blocker as you go through the material.

## Task 1: Unix command shell and command tools

We assume you are comfortable with command-line interface (on Linux or Mac). In this task you are going to work with git from command shell, and install basic software and packages needed for data analysis of Tasks 2 and 3.

### Git

Most of our work will be saved and shared on github in public or private repositories. If you have not used git in the past, please follow the [instructions here for a 5 minutes git tutorial](https://wanggroup.org/orientation/5m-git).

As the next step please [fork](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/fork-a-repo) this repository, add your name to the Markdown file named `hello.md`, commit it to github with a customized commit message, eg, "Add my name and github handle", and [create a pull request](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/about-pull-requests) so we can see your update and incorporate it to the repository.

### Analysis software setup

This tutorial (and our research in general) requires `R`, `Python`, `Script of Scripts (SoS)` bioinformatics workflow system and `docker`.
Please follow this [setup instruction](https://wanggroup.org/orientation/jupyter-setup.html) to complete the installations.

### Text editor for coding

You can use any editor of choice but if you have not thought about this before, here is a personal suggestion: I use `gvim` for many years before I switched to [VS Code](https://code.visualstudio.com/) text editor --- yes it is from Microsoft but yes it is good! I now use VS Code with Vim key binding (an Extension you can find in VS Code Extension Marketplace) so I can still use keyboard conventions that I'm familiar with.

To open a particular folder (eg a github local clone) on your computer from command terminal:

```bash
cd <path to the folder>
code ./
```

## Task 2: IPython notebook and SoS bioinformatics workflow

This task is an example of a bioinformatics workflow developed at our group. It uses IPython notebook (with JupyterLab IDE as a recommendation), and runs an [SoS kernel for bioinformatics workflows](https://vatlab.github.io/sos-docs/).

Please find the example notebook file `notebook/orientation.ipynb`, follow the instructions and complete the Quiz at the end of the notebook. 

## Task 3: Basic R programming 

Please follow the instructions and complete the R exercise `analysis/orientation.Rmd`. `Rmd` stands for R Markdown. They are text file with R code and narratives that you can open and analyze using software such as Rstudio.

## Task 4: Statistical genetics

Please follow the instructions and complete the genetic fine-mapping exercise `notebook/finemapping.ipynb`. This is somewhat advanced material for those who has a background in statistical genetics. 

## Task 5: Report your work

Organizing and communicating your work with others is essential to your success in conducting reproducible computational research. 
For every project we require the analysis written in Rmd and IPython notebooks to be converted to a research website that will either be hosted on github (a service github provides) or accessed locally on one's web browser.

We will use [workflowr](https://github.com/jdblischak/workflowr) to organize the R analysis. Please follow `workflowr` instructions to convert the Rmd files under `analysis/` folder into HTML based website under a directory called `docs`.
You should find a file `docs/index.html` and view it in your web browser once you successfully build the website.

We will use [jnbinder](https://github.com/vatlab/jnbinder) program to organize the Python analysis. Please follow the section "Run from a docker image" **up to step 3** and return here, then type:

```
jnbinder --root docs/ipynb
```

The first time you run the command above, a website template will be configured under `docs/ipynb` and the program will quit on error with a line of prompt instructing you to edit 
a file called `config.yml`. Please open this file with text editor and uncomment to configure `name`, `repo` and `footer` as you see fit, and set `add_commit_info` to `False` for now. 
Finally for `include_dir` please specify `["notebook", "workflow"]` to include notebooks under these folders to the website to be generated. 

Now please run the command above again to generate IPython based HTML files to `docs/ipynb` folder. You can view `docs/ipynb/index.html` in your web browser, particularly please click and view the tabs "Notebook" and "Workflow".

## Submission

After you have completed all tasks please make a tarball for your `docs` folder and email it to `wang.gao@columbia.edu` for us to review.
