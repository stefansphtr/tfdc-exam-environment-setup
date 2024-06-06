# TensorFlow Developer Certification Exam Preparation Guide to run in PyCharm

This guide will help you set up your PyCharm environment for the TensorFlow Developer Certification Exam.

## File System Structure

Before we start, make sure your project directory is structured as follows:

```plaintext
project_directory/
│
├── .idea/ (PyCharm project settings directory)
│
├── venv/ (Python virtual environment directory)
│
├── requirements.txt (Python dependencies file)
│
└── setup_instructions.md (This file)
```


### Preparation to setup the PyCharm for the TensorFlow Developer Certification Exam

#### Setup Environment

This guide will help you set up a specific version of Python (3.8) in the current PyCharm environment using a virtual environment. After setting up the environment, it also guides you to install a specific version of protobuf (3.20.3).

Here's a step-by-step explanation of what each step does:

1. **Create a new virtual environment**: In PyCharm, go to `File > Settings > Project: [Your Project Name] > Python Interpreter`. Click on the gear icon and select `Add...`. In the left pane, select `Virtualenv Environment`. In the right pane, select `New environment`, choose a location for your virtual environment directory (e.g., `venv/`), select `Python 3.8` as the base interpreter, and click `OK`.

2. **Activate the virtual environment**: In PyCharm's Terminal pane (at the bottom), type `venv\Scripts\activate` (Windows) or `source venv/bin/activate` (macOS/Linux) and press `Enter`.

3. **Check the Python version**: In the Terminal pane, type `python --version` and press `Enter`. The output should show `Python 3.8.x`.

4. **Install protobuf 3.20.3**: In the Terminal pane, type `pip install protobuf==3.20.3` and press `Enter`.

#### Check the Python Version

In the Terminal pane, type the following command and press `Enter`:

```bash
python --version
```

#### Install protobuff version 3.20.3

In the Terminal pane, type the following command and press `Enter`:

```bash
pip install protobuf==3.20.3
```

#### Install all the dependencies in the `requirements.txt`file

In the Terminal pane, type the following command and press `Enter`:

```bash
pip install -r requirements.txt
```

#### Test the overall setup

In the Terminal pane, type the following command and press `Enter`:

```python
python -c "import sys; print(sys.version)"
```

This should print out the Python version. Make sure it's `3.8.x`.

Next, type the following command and press `Enter`:

```python
python -c "import tensorflow; print(tensorflow.__version__)"
```

This should print out the TensorFlow version. Make sure it's the version specified in your `requirements.txt` file.

Repeat this process for all the packages listed in your `requirements.txt` file to ensure they've been installed correctly.