# TensorFlow Developer Certification Exam Preparation Guide for Visual Studio Code

This guide will help you set up your Visual Studio Code environment for the TensorFlow Developer Certification Exam.

## File System Structure

Before we start, it's important to have a clear file system structure. Here's a proposed structure:

```plaintext
/my_project
    /venv
    /src
    /tests
    requirements.txt
    setup_instructions.md
```

In this structure:

- `my_project` is the root directory of your project.
- `venv` is the directory where your virtual environment and its dependencies are stored.
- `src` is the directory where your source code is stored.
- `tests` is the directory where your test code is stored.
- `requirements.txt` is a file that lists all of the Python packages that your project depends on.
- `setup_instructions.md` is this file.

You can create this structure using the following commands:

```bash
mkdir my_project
cd my_project
mkdir venv src tests
touch requirements.txt
```

Now, let's move on to the environment setup.

### Setup Environment

---

This section will guide you through setting up a specific version of Python (3.8) in your Visual Studio Code environment using Pipenv, a tool that aims to bring the best of all packaging worlds to the Python world. It harnesses Pipfile, pip, and virtualenv into one single command. After setting up the environment, it also guides you to install a specific version of protobuf (3.20.3).

Here's a step-by-step explanation of what each command does:

1. `pip install pipenv`: This command installs Pipenv, a tool that creates and manages a virtual environment for your project and adds/removes packages from your Pipfile as you install/uninstall packages.

2. `pipenv --python 3.8`: This command creates a new virtual environment and specifies that Python 3.8 should be used.

3. `pipenv install jupyter`: This command installs Jupyter in the virtual environment.

4. `pipenv install protobuf==3.20.3`: This command installs a specific version of protobuf (3.20.3).

**After running these commands**, you should **activate the virtual environment by running `pipenv shell`**. All the commands you run within this shell will use the Python version and packages installed in the virtual environment.

Please note that this method of changing the Python version is recommended and should not lead to unexpected issues. It's generally recommended to write your code in a way that it can run on the Python version you specified.

---

```bash
pip install pipenv
pipenv --python 3.8
pipenv install jupyter
pipenv install protobuf==3.20.3
pipenv shell
```

### Check the Python Version

You can check the Python version by running the following command in your terminal:

```python
import sys
print(f"Current Python Version: {sys.version}")
```

### Install all the dependencies in the `requirements.txt` file

You can install all the dependencies listed in the `requirements.txt` file by running the following command in your terminal:

```bash
pipenv install -r requirements.txt
```

### Test the overall setup

You can test the overall setup by running the following Python code in your terminal:

```python
def test_environment():
    import sys

    if sys.base_prefix == sys.prefix:
        print("\\033[91mWarning: You are probably not using a virtual environment on this project.\\033[0m")
    
    assert sys.version_info[:2] == (3, 8), "Expected Python version is 3.8"
    
    print("\\033[92mYou are currently using Python {}\\033[0m".format(sys.version))


def test_package(package_name, expected_version):
    import importlib

    package = importlib.import_module(package_name)
    current_version = package.__version__

    assert current_version == expected_version, \
        "\\033[91m{} version isn't {}, yours currently is {}\\033[0m".format(package_name, expected_version, current_version)

    print("\\033[92m{} version is good\\033[0m".format(package_name))


def test_packages():
    packages_to_test = {
        'tensorflow': '2.9.0',
        'tensorflow_datasets': '4.6.0',
        'PIL': '9.1.1',
        'pandas': '1.4.2',
        'numpy': '1.22.4',
        'scipy': '1.7.3'
    }

    for package_name, expected_version in packages_to_test.items():
        test_package(package_name, expected_version)

test_environment()
test_packages()
```

This code checks if you are using a virtual environment, if your Python version is 3.8, and if the versions of several packages are as expected. If any of these checks fail, you will see an error message.