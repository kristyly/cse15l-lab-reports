# Lab Report 3
## Researching Commands

The command I will research is `grep`. My working directory is `/technical`.

### Command 1
```
$ grep -r "<string>" /path-to-directory/
```
To search for a string in a directory and its subdirectories, we can use the command above. The output will be the line with the specified string highlighted and its file path. I found this command on this [website.](https://www.howtogeek.com/496056/how-to-use-the-grep-command-on-linux/)

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

### Command 2
```
$ grep -v "<string>" /file/
```
This command searches for all lines that do not contained the specified string. The output will be all of the lines that do not contain the specified string in the listed file. I found this command on this [website.](https://www.howtogeek.com/496056/how-to-use-the-grep-command-on-linux/)

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
In this example, I am looking for all of the lines that do not contain the character `"a"` in the file `/pmed.0020067.txt`. This command is useful if I have a Java file and I want to search for all of the lines that do not use a specific variable.

Example 2:
```
$ grep -v " " government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt

---------------------------------------------------





Xenakis

1
2
successful.
3
4
5
prohibitive.
6
7
8
delivery.


letter.
11
12
supra.
13
14
15
www.naa.org/marketscope/databank/preppriyr.htm.
16


data.19
business).


17
sample.
18
19
20
21
22
23
volume
24
street.
25
hours.
26
incur.
27
28


a


30
areas.
31
delivery.
32

2.
33
34




35
36






39
40
41
considerations.






43
44
paper.


countries.48
45
46
47
48
1997.


APPENDIX







```
In this example, I am searching for all of the lines that do not have a space in the file `/Cohenetal_CreamSkimming.txt`. This is useful if each paragraph in a volume of text files is labeled with a number and I want a list of all of the paragraphs and its location.

### Command 3
```
$ grep "<string>" --exclude=*.<file type> --exclude-dir=<directory>/
```
This command searches for a string while exluding a specific file or directory. The output will have the lines that contain the string on the right side and its path on the left side. I found this command through ChatGPT.

```
$ grep -r "poverty" --exclude-dir=biomed/ --exclude-dir=government/
---------------------------------------------------
911report/chapter-12.txt:            Pakistan's endemic poverty, widespread corruption, and often ineffective government
911report/chapter-12.txt:            Economic openness is essential. Terrorism is not caused by poverty. Indeed, many
plos/journal.pbio.0020310.txt:        simultaneously reducing rural poverty. ‘Much of the information about community-based
plos/pmed.0020067.txt:          poverty and poor sanitation.
plos/pmed.0020067.txt:        of rural poverty in the tropics, including southern China [5], the Indian subcontinent [6],
plos/pmed.0020067.txt:        afflicted population will remain mired in poverty.
plos/pmed.0020067.txt:        difficult to eliminate or eradicate in areas of poverty and poor sanitation [19]. Indeed,
plos/pmed.0020067.txt:        those related to poverty reduction, child health, and education. However, there are also
plos/pmed.0020160.txt:          black, Mexican-American, or other. The self-reported poverty to income ratio, a marker of
plos/pmed.0020160.txt:          potential confounders: age, sex, race, poverty to income ratio, body mass index,
plos/pmed.0020160.txt:        in public policy. Linked to poverty, decreased productivity, and premature death, tobacco
plos/pmed.0020162.txt:        poverty, wealth, and debt; (c) lack of data on gestational age, birth weight, birth order,
plos/pmed.0020216.txt:        causes of poverty and inequality, which give rise to the phenomenon of migration and
plos/pmed.0020235.txt:        time, lack of data on income, poverty, wealth, debt, gestational age, birthweight, and
plos/pmed.0020247.txt:        underlying conditions of poverty, racism, and sexism that support such oppression [5]. This

```
In this example, I am searching for all of the files that have the word `"poverty"` in all of the directories except `biomed/` and `government/`. This is useful when I know that the string I am searching for is not in a specific directory.

Example 2:
```
$ grep -r "poverty" --exclude=*.txt
---------------------------------------------------

```
In this example, I am searching for all of the non-`.txt` files that contain the word `"poverty"`. Since all of the files are `.txt`, nothing is produced in the output.

### Command 4
```
$ grep "<string>\|<string>" /file/
```
With this command, I can search for multiple strings in a file. `\|` is similar to the `or` statement. The output will have the lines that contain at least one of the specified strings on the left and its path on the right. I found this command on this [website.](https://linuxize.com/post/grep-multiple-patterns/)

Example 1:
```
$ grep -r "poverty a\|health and d" plos
---------------------------------------------------
plos/journal.pbio.0020047.txt:        its boundaries with health and disease.
plos/pmed.0020067.txt:          poverty and poor sanitation.
plos/pmed.0020067.txt:        difficult to eliminate or eradicate in areas of poverty and poor sanitation [19]. Indeed,
plos/pmed.0020216.txt:        international response from the health and development community. We argue that there is
plos/pmed.0020216.txt:        causes of poverty and inequality, which give rise to the phenomenon of migration and

```
In this example, I am searching for any instances of the strings `"poverty a"` or `"health and d` in the directory `plos/`. This command is useful if I have a large volume of texts and I need to find specific topics.

Example 2:
```
$ grep "risky\|partner" */pmed.0020216.txt
---------------------------------------------------
HIV-positive [9]. Needle sharing and risky sexual behaviour is common in this group. The
        [27]. The vast majority of young men, about 80%, who had sex with non-regular partners felt
        condoms, and a belief that careful selection of partners offers sufficient protection [27].
        are particularly conducive to risky needle sharing [34]. Unlike IDUs in other Nepalese
        their small amounts of money to buy drugs. Sexual intercourse with casual partners occurs,
        extent of the AIDS epidemic in Nepal will depend upon rates at which sexual partners are
        proportion of the general population that has multiple and concurrent sexual partners.
        risky behaviour [27]. A culturally specific approach to HIV prevention is needed that
        adjacent fields need to interact more and partner with each other, and there needs to be
```
In this example, I am searching for any lines that have the words `"risky"` or `"partner"` in the file `pmed.0020216.txt/`. This command is useful if I need to find multiple words in a book/text online.
