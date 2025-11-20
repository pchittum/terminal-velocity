# First Exercise

1. Open your terminal. Either Windows Terminal or Mac Terminal.
2. If using Windows, make sure you're running PowerShell. 
3. Note the directory you're open in. You'll want to go to your user home directory. 

```
Windows
> cd ~

Mac
> cd
```

4. Make a new directory. Then change to the new directory. 

```
Windows
> md learncli
> cd learncli


Mac
> mkdir learncli
> cd learncli
```

5. Make a new file and view it in the directory

```
Windows
> New-Item myfile.txt -ItemType File
> dir

Mac
> touch myfile.txt
> ls -l
```

6. Make a new hidden file and view that in the directory

```
Windows
> (New-Item -Path .\hidden.txt -ItemType File).Attributes = 'Hidden'
> dir -Force

Mac
> touch .hidden
> ls -al
```

7. Find out where you are in the file system

```
Windows
> Get-Location

Mac
> pwd
```

8. Using the command you used above previously, create a new directory called `dir1` in your workshop directory. 
9. Show your directory contents again using the appropriate command for your shell. 
10. Change to the `dir1` directory. 
11. Create another new file called `myfile2`. 
12. Go back to the parent directory. In either shell you can use the command `cd ..` (spaces matter!). 
13. Show your directory contents one last time using the appropriate command for your shell. 


## Extra Fun
Download the git directory [file](https://github.com/pchittum/terminal-velocity/tree/begin-exercises#) and unzip. Make sure you're using the following URL to do the download from GitHub: 

```
https://github.com/pchittum/terminal-velocity/tree/begin-exercises#
```

Once downloaded look around using command line tools and try to do things like show file contents using only the commands listed in the workshop cheatsheet. Or try to look up commands in Google (or your favorite LLM).