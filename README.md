# How to Make your Code Shine with GitLab CI Pipelines

A brief introduction to some tools for a cleaner Python code by applying isort, Black, Flake8, and Pylint automatically using GitLab CI Pipelines.

> Check the complete post on [Medium](https://medium.com/semantixbr/how-to-make-your-code-shine-with-gitlab-ci-pipelines-48ade99192d1)

## Python tools

* [Black](https://github.com/psf/black) 
* [Flake8](https://flake8.pycqa.org/en/latest/) 
* [isort](https://pycqa.github.io/isort/)
* [Pylint](https://www.pylint.org/)


## GitLab CI Pipeline

We can create a pipeline in [GitLab CI (Continuous Integration)](https://docs.gitlab.com/ee/ci/) that runs from top to bottom: isort to sort the imports, then Black to format the code, then Flake8 to check the style of the code, and finally Pylint to detect possible errors in the code.

### 1. Create the `.gitlab-ci.yml` file

You can use the condensed version `.gitlab-ci.yml` or replace for the extended version `.gitlab-ci-extended.yml` (_Make sure the file name remains the same file name condensate_). 

The difference is in the time that each one ends up consuming. The extended version gives a more detailed report of possible errors but depending on the number of files to review it can end up consuming more time.

And as a complement, if you want to centralize the project tools configuration you can include a `pyproject.toml` file.

### 2. Configure the CI pipeline for Merge Request

In GitLab go to Settings> General> Merge Request and Activate Pipelines must succeed.

### 3. Create a Merge Request and test!

Let’s try your codes with our CI! 🚀


## Configure environment

- Create the conda environment

```shell
(base)$: conda create --name myenv
```

or create the conda environment from an environment.yml file

```shell
(base)$: conda env create -f environment.yml
```

- Install **development dependencies**

```shell
(base)$: conda env update -n myenv -f environment-dev.yml
```

- Activate the environment

```shell
(base)$: conda activate myenv
```

--- 

made with 💙 by [mafda](https://mafda.github.io/).
