#This is How I Work:

 My name is Nate.  I'm a teaching assistant for Rutgers Coding Bootcamp, and this is how I use ```Git``` on a daily basis.

## Why do I use Git?
--------------------
I use it to grab lesson plans and your homework assignments and load a local version on my machine.  
Please submit on time, follow the file/folder structure, and Always Be Commiting.
  


## File/Folder Structure


For all things pertaining to coding, I have a folder ```Code``` in my root directory.  (Similar to C:\ for windows.)

```
OS X				     	Windows
$ nate ~/code           	C:\Code\
```

I have a separate folders for projects, testing, blog test, my Bootcamp file directory and my directory for RCB

```
nate ~/code
$ ls -a
./             .swp           code_test/     practice/      rucb/
../            Icon?          fire_mover/    project_euler/ testing/
.DS_Store      blog/          home/          projects/      wdi/
```

RCB is further broken down into another set of folders INSTRUCTORS, SFSFEB2016 and SFSOCT 2015

```
rucb/
├── INSTRUCTORS
│   ├── All-Classwork-Homework
│   └── All-Lesson-Plans
├── SFSFEB0216
│   ├── 02-16-JC-Class-Content
│   ├── INSTRUCTORS
│   ├── STUDENTS
│   └── stuff.html
├── SFSOCT2015
│   ├── 1026-mon-wed-in-class-code
│   ├── 1027-tue-thu-in-class-code
│   ├── Personal
│   └── STUDENTS
└── test.html
```

At this point no folder I've gone through is a git folder. I haven't run ```git init``` and there is no ```/.git``` folder.  And if I have accidentally run ```git init```, I can check to be sure if there's a ```.git/``` tracking my changes with ```ls al```.  I will do an ```rm -rf .git/``` in any folder I don't want to be tracked by git.


Within SFSFEB2016, here I have structured my folders the following way for my understanding and faster navigation ~/code/rcb/SFSFEB0216/STUDENTS/Wk##/nameOfStudent

```
$ tree STUDENTS/
├── INSTRUCTORS
│   └── NateTuvera
│       └── first_day_stuff
│           └── first_day.html
├── STUDENTS
│   ├── wk01
│   │   ├── AngelTrinh
│   │   │   └── PortolioHW
│   │   ├── JasonMartocci
│   │   │   └── Portfolio
│   │   ├── JeffYourman
│   │   │   ├── assets
│   │   │   ├── contact.html
│   │   │   ├── index.html
│   │   │   ├── portfolio.html
│   │   │   └── portfolio2.html
│   │   ├── KellyMersereau
│   │   │   └── Portfolio
│   │   ├── ReynaldoNicolas
│   │   │   └── Portfolio
│   │   └── WilliamVasquez
│   │       └── portfolio
│   ├── wk02
│   │   ├── AngelTrinh
│   │   │   └── my-portfolio
│   │   ├── JamesLado
│   │   │   └── Portfolio-HW-week-1
│   │   ├── JasonMartocci
│   │   │   ├── My-Portfolio
│   │   │   └── Portfolio
│   │   ├── KellyMersereau
│   │   │   └── my-portfolio
│   │   ├── ReynaldoNicolas
│   │   │   └── my-portfolio
│   │   └── WilliamVasquez
│   │       └── bootstrap_portfolio
```

Once I ```cd``` into a week and name of a student, I will ```git clone``` the target repo.  ```git clone``` creates another folder with their repo contents named after their repo and it's linked to GitHub through git and Githubs API.

This is how I begin the process of checking homework submissions.



## Git commmands that I use

```git init```

Initializes Git and allows you to start tracking changes on your local machine.  I'm sure you've heard this before.  This means that it will create a hidden folder ```/.git``` in the directory you initialized in and then can start tracking changes.  From here you can start using commands you should be familiar such ```git add```, ```git commit```, ```git status```

I rarely use ```git init```, because I dont just use git locally.  I prefer to create a repo on Github.com and ```git clone``` instead.

If you accidentally ```git init``` in a folder you didn't mean to initialize, ```ls -al``` to make sure there's a ```.git/``` folder.  Don't want to track changes?  You don't want that folder.  Run ```rm -rf .git/```
***
<br>
```git status```

In an initialized git folder, it will show green or red to help keep you see what has changed within the file/folder structure.  Green means "go", changes are tracked and staged (ready to be committed).  Red is for untracked changes, you'll need to ```git add [file name]``` or ```git add .``` for all changes.

I will run ```git status``` to remind myself what's going on.  
***
<br>
```git add . ```

Adds files to Staging (Green means Go, Red means No)  If you have something you want to add to be tracked, this is how you add it to git.

This is part of a muscle memory set of commands that I'm always running.  If you dont use ```git add```often, you're not using git.
***
<br>
```git commit -m 'insert witty message here'```


Takes all staged files and creates a snapshot which we can reference back to.  This is the snapshot for Version control.  

This is part of a muscle memory set of three commands that I'm always running.  If you dont use ```git commit```at some point, you're not using git.
***
<br>
```git remote -v```

This command allows me to see where git push is pushing code to.  ```git remote -v``` should return something that looks like this.

```
heroku	https://git.heroku.com/peaceful-dawn-34964.git (fetch)
heroku	https://git.heroku.com/peaceful-dawn-34964.git (push)
origin	git@github.com:ntuvera/dotenv_test.git (fetch)
origin	git@github.com:ntuvera/dotenv_test.git (push)

```
Seeing this output lets me know that I have remote setup.  I will check this to make sure that I am linked to the correct .gits 

For Heroku deployment, if I haven't created an app yet I run ```heroku create```, and it adds the remote for me and connects to Heroku's API and creates the repo all from command line.
***
<br>
Now that we've seen how to do all these steps manually, here's a shortcut

```git clone [url]```

The [url] can be replaced with any url that ends with .git and will create a new folder in the directory and clone the file/folder structure of the repo and add the remotes.  As long as you have access rights to the repo, you should be all set to be up and running.

I clone your repos on my local machine and then I can see exactly what you say based on your last commited ```git push```.  

<br>
<br>



##Common error messages and what to do about them.

```
fatal: 'somePlaceNotListed' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```
When I see an error that looks _remotely_ like this, I usually need to add the remote repo or change the destination url.  I'll use the following command

```git remote add [name] [url]```

For example, if I have a repo on github called myCoffee that I want to link to my local machine 
```git remote add origin git@github.com:/myCoffeeApp```

I can also add heroku endpoints to push to manually, if I already have a Heroku App created and a url I can use.
```git remote add heroku git@heroku:peaceful:warzone-123123```



[Will Update as I remember or run into more errors]



