#This is how I work:
My name is Nate and this is I set up my repos to make it easier for other devs to see my work.

<br>
####Static single page repos for homework and beyond

##File structure for Repos

Whenever I start a homework/repo there are some common conventions for how to setup your files.  These conventions make it easier for other coders to find and navigate through your code which should be separated out into individual files.  

For a static html page, I keep my files organized in a manner similar to the tree below.  If I'm going to link this to a GitHub repository this is where I would run ```git init```, of if I cloned a repo the folder structure should be built out in a manner like this.

Tree View

```
$  tree week#hw/
week#hw/
├── README.md
├── assets
│   ├── css
│   │   └── style.css
│   ├── images
│   │   ├── kittens.png
│   │   └── puppies.png
│   └── javascript
│       └── app.js
└── index.html
```

ls from the working directory I am in

```
nate ~/code/rucb/SFSFEB0216/INSTRUCTORS/NateTuvera/week#hw
$ ls
README.md   assets/     index.html
```

In the above example, I have linked either to a repo, so I dont see a hidden `.git/` folder.  If I were to make this into a git controlled folder I could check with by the following

```
$ ls -a
./          ../         .git/       README.md   assets/     index.html
```
Now there's a hidden `.git/` folder signifying that it's keeping track of my changes.  **Be sure not to nest git controlled folders within eachother**,  It will cause a headache when pushing up changes.

Along with this level of organization, we've separated out or different concerns/types of code.  To make your code more readable, we compartmentalize different types of code and logic.
I could write all my code (javascript and css) in a single .html file.  But what if I want to share those bits of code among other pages?  I would have to re-write those bits in each .html file.  As you can imagine it will be a headache to read and maintain if we make a change in only one file that needs to be elsewhere.  

Granted in this example we only have one .html file so we can make our changes only once.  But keep "scalability" in mind at all times.  It's easier to make the change once and have it export to different sources instead of tweaking each source down the line.

***

Moving forward I will update this when we Get to more complex things like setting up our Node servers with an MVC pattern.  But for now this is a simple guideline I highly suggest you emulate for our smaller apps.
