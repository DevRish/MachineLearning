### Install `virtualenv` package

```
pip install virtualenv
```

### Create virtual environment and activate it

```
python3 -m virtualenv ml-env

source ml-env/bin/activate
```

### Install dependencies from `requirements.txt`

```
pip install -r requirements.txt
```

**Note:** `jupyter notebook` and `jupyter lab` are also included within the requirements file and are to be installed within the virtual environment.

### Create a kernel corresponding to the virtual env for the notebooks

```
# Make sure the virtual env is activate before running below command
# Also, ipykernel is already included in requirements file

ipykernel install --user --name=ml-env
```

### Find and set the kernel within jupyter

```
# Launch jupyter notebook or jupyter lab

jupyter lab
```

Select "Kernel" > "Change Kernel" in the GUI and choose the kernel that was created just above.

### For nlp : Set the nltk installation path:

```
# Add the following entry at the end of your ~/.bashrc file (while ml-env is deactivated)
export NLTK_DATA=<path to MachineLearning folder>/nlp/nltk_data

# Activate the ml-env
source ml-env/bin/activate

# Now download all libraries of data nltk requires
python -m nltk.downloader -d $NLTK_DATA all

# Adding the variable to bashrc was essential because it would not only be used in above command,
# nltk will also se it later to find and access it's libraries
```