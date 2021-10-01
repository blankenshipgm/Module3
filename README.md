# Introduction 
This page covers the workflow of using a github repository.

# Installation
### Requirements
* A linux terminal
* A github accout
  * Click here to create github account: (https://github.com/login)

# Process
Here's a list of steps to clone a repository, make changes, and then merge the changes to the main repository.

### Step one
Create branch for new work.

### Step Two
Create, modify files.

### Step Three
Add and Commit changes.

### Step Four
Generate pull request.

### Step Five
Conduct code review.

### Step Six
Merge main with branch.

# Example
 
### Access repository and perform clone function
1. Click here to access repository: (https://github.com/blankenshipgm/hello-world)
2. Then click the drop down arrow on the green button labeled "Code"
3. Make Sure HTTPS is selected and copy the address to your clipboard
4. Access your linux terminal
5. 
6. Run the command below:
```
 $ python3 scrape.py --link=https://novelfull.com/library-of-heavens-path.html --start=1 --end=23 -i
```

![Long option example](/assets/images/git clone.PNG)

### Getting chapters 66 through chapter 84 and storing them in one file.
- Run in Wuxia Scrape sub directory scrape:
```
$ python3 scrape.py -lhttps://novelfull.com/library-of-heavens-path.html -s66 -e84
```

![Short option example](/assets/images/short-opt.png)

# Troubleshooting

- No such file or directory
    - Make sure you are in the folder /wuxia-scrape when running the script.
    
```
$ python3 scrape.py --link=https://novelfull.com/library-of-heavens-path.html -s1 -e23 -i
python3: can't open file 'scrape.py': [Errno 2] No such file or directory
```
  
- "I downloaded all the chapters to one file and there's a chapter missing!"
    - Sometimes the title of a chapter isn't parsed when retrieving all the chapters. The chapter should still be in the file and in the correct order. 
  
- IndexError
    - Make sure you are using Python3 and not Python2.
    - Double check that the start and or end flags are followed by valid chapter numbers.
  
```
Traceback (most recent call last):
  File "scrape.py", line 38, in <module>
    chapterLinks = nf.getChapterLinks(contentPages)
  File "/home/UserName/DownloadLocation/scrape/search.py", line 26, in getChapterLinks
    chapterLinks.append('http://novelfull.com' + linkTables[x])
IndexError: list index out of range
```

 - "The novel text file is blank!"
    - Make sure the ending parameter comes after the start parameter.
  
 - "I got chapter 49 instead of 1!"
    - Check if your start or end number is negative or if a dash was mistyped.
  
# Support
  1. Create an [Issue](https://github.com/BrickGoat/wuxia_scrape/issues).
  2. Provide an in-depth explanation of your problem.
     - Refer to the GitHub Issue [guide](https://guides.github.com/features/issues/) if needed.
