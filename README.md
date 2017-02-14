# Skywalker Project
---

## How to setup the development enviroment

This project run in **(ubuntu 16.04)**

### Install Dependencies

`sudo apt-get install git python-virtualenv libpq-dev python-dev python3.5-dev libtiff5-dev libjpeg8-dev zlib1g-dev libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev python-tk postgresql postgresql-contrib`

### Create a virtual enviroment

Create the enviroment for the skywalker project

`virtualenv -p /usr/bin/python3.5 sky-env`

Activate the enviroment

`source sky-env/bin/activate`

Verify the version

`python -V`



### Fork and Clone

Create a fork of the project 


You can clone the repo wherever you want but we recomment to install it inside the enviroment folder (sky-env)


**Origin remote** 

This remote is the principal repository, we wont push directly to this repo, we will create pull request to this repo using our forks
	
You can clone the repo Using SSH `git clone git@bitbucket.org:nezara/skywalker.git` (you need to configure the ssh key) 

**Fork remote**

This remote is the fork repository, in this fork you should do the necessary changes, create a commit, and push the branch to this fork, then you should create a pull request against the integration branch in the principal repo.

you can add a remote in your local machine using this commmand

`git remote add fork git@bitbucket.org:USERNAME/skywalker.git`

 

### Installing Django dependencies

Activate the sky-env enviroment, go to the repo folder and execute

`pip install -r requirements.txt`


### Database Configuration

Ìnstall pgadmin3 (optional)

`sudo apt-get install pgadmin3`

create a database named skywalker

`sudo -u postgres createdb skywalker`

Change the password for the user postgres (or any other you have)

`sudo -u postgres psql`

`ALTER USER postgres WITH SUPERUSER;`

`ALTER USER postgres PASSWORD 'newpassword';`

configure the pgadmin3 connection with the user and the password that you create


![pgadmin.png](https://bitbucket.org/repo/jqbXE8/images/663939298-pgadmin.png)

### Configure the settings


### Execute the project

`python manage.py makemigration --settings=skywalker.settings.dev`

`python manage.py migrate_schemas --shared --settings=skywalker.settings.dev`

`python manage.py runserver --settings=skywalker.settings.dev`


## Git Workflow

![Untitled Diagram.png](https://bitbucket.org/repo/MyGzrq/images/1091835688-Untitled%20Diagram.png)