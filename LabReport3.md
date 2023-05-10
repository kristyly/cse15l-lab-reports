# Lab Report 3
## Researching Commands

The command I will research is `grep`. My working directory is `/technical`.

```
$ grep -r "<string>" /path-to-directory/
```
To search for a string in a directory and its subdirectories, we can use the command above. The output will be the line with the specified string highlighted and its file path.

Example 1:
```
$ grep -r "healthy a" plos

---------------------------------------------------
technical/plos/journal.pbio.0020113.txt:        only healthy adults but also potentially transporting thousands of viable young—seeding
technical/plos/journal.pbio.0020121.txt:        healthy animals in areas where CWD is detected. But among the first things they need to
technical/plos/journal.pbio.0020187.txt:        restriction of caloric intake considerably extends both the healthy and total life span of
technical/plos/pmed.0020040.txt:        This case presentation illustrates an otherwise healthy appearing patient who is found
technical/plos/pmed.0020247.txt:        presumably healthy—to make societies as healthy as their individual members.

```
In this example, I am searching for the string `"healthy a"` in the directory, `plos`. The right side of the output is the line that contains the specified string.
On the left side is the path to the file that contains the line. This is useful when I know what topic I want to search for, but do not remember which file it is written in.

Example 2:
```
$ grep -r "poverty a"

---------------------------------------------------
government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt:of poverty and injustice. I believed that I would see the day when
government/About_LSC/conference_highlights.txt:poverty around us. I feel this can be done within the current LSC
government/About_LSC/diversity_priorities.txt:eradication of poverty and promoting equality and justice and
government/Media/Higher_court.txt:increased in recent years, and states with increased poverty are
government/Media/Legal_services_for_poor.txt:poverty and will drain additional federal money from the Legal
government/Media/Nonprofit_Buys.txt:services "consistent with CRLA's mission to alleviate poverty and
plos/pmed.0020067.txt:          poverty and poor sanitation.
plos/pmed.0020067.txt:        difficult to eliminate or eradicate in areas of poverty and poor sanitation [19]. Indeed,
plos/pmed.0020216.txt:        causes of poverty and inequality, which give rise to the phenomenon of migration and
```
In this example, I am searching for the string `poverty a`, but I did not specify the directory. This automatically searches for the string in my current working directory
and all subdirectories, as you can see in the path. This is useful when I am looking for a specific topic on a much larger scale.

```
$ grep -v "<string>" /file/
```
This command searches for all lines that do not contained the specified string. The output will be all of the lines that do not contain the specified string.

Example 1:
```
$ grep -v "a" plos/pmed.0020067.txt

---------------------------------------------------




        Introduction

          tropics.





        These two hookworms, together with the roundworm,


        skin (
        (Figure 3).






        the



```
In this example, I am looking for all of the lines that do not contain the word
