# **LAB REPORT: RESEARCHING COMMANDS FOR `grep`**
### In this report, I will be demonstrating three alternate uses of the `grep` command, with nine examples in total. 

---

*NOTE: For efficiency purposes, I have already done `cd docsearch` and `cd technical` to go into the **technical** directory to access the multiple sub directories/files within it. I will not be showing how to do that in this lab report.*

## **1) `grep -c`**
- This command will diplay the number of lines that contain the specified string in the files of the directory. 
- Below, I will be showing multiple examples of this command, all executed from the remote command line of my UCSD ieng6 account.

**EXAMPLE #1: `grep -c "United States" 911report/*`**

```
 [cs15lfa22ig@ieng6-202]:technical:434$ grep -c "United States" 911report/* 
```
Here, I am searching for how many times the string "United States" appears within every file in the directory 911reports (which is why the /* is included).

```
911report/chapter-1.txt:8
911report/chapter-10.txt:27
911report/chapter-11.txt:21
911report/chapter-12.txt:79
911report/chapter-13.1.txt:19
911report/chapter-13.2.txt:4
911report/chapter-13.3.txt:84
911report/chapter-13.4.txt:61
911report/chapter-13.5.txt:33
911report/chapter-2.txt:26
911report/chapter-3.txt:70
911report/chapter-5.txt:45
911report/chapter-6.txt:45
911report/chapter-7.txt:63
911report/chapter-8.txt:52
911report/chapter-9.txt:1
911report/preface.txt:3
```
This is the output, which clearly demonstrates this command in action. The file with the most appearances of "United States" is chapter-13.3.txt, with 84. 

This command is useful in the sense that we don't have to be too specific about what we are looking for, since we have the help of the star *. We are simply searching for any instances of "United States" within every file in the directory 911reports. 


**EXAMPLE #2: `grep -c "oxide" biomed/rr74.txt`**

```
[cs15lfa22ig@ieng6-202]:technical:418$ grep -c "oxide" biomed/rr74.txt
5
```

Compared to the previous example, we can see how specific this one is. I am no longer using the star * to search for the given string within the directory, but I specified a sub directory and file to search for "oxide." 
Since I just specified one file, it returned one singular number: 5. 

This particular command is useful, depending on how specific the search is. In this example, it is extremely useful, since I specified the sub directory and the file in which I was searching for the string; we could use this exact command format (being very specific) if we know where we want to look for what we want (think about looking for how many words are repeated in one file, such as an essay).

**EXAMPLE #3: `grep -c "nature" plos/*`**

```
[cs15lfa22ig@ieng6-202]:technical:508$ grep -c "nature" plos/*
```

In this example, I am searching for how many times the word "nature" is in every file in the plos directory. 

*WARNING: LONG OUTPUT AHEAD* 

*NOTE: I could've shortened this output by deleting some of it on this page, but I have decided not to for demonstration purposes.*

```
plos/journal.pbio.0020001.txt:0
plos/journal.pbio.0020010.txt:0
plos/journal.pbio.0020012.txt:0
plos/journal.pbio.0020013.txt:0
plos/journal.pbio.0020019.txt:0
plos/journal.pbio.0020028.txt:2
plos/journal.pbio.0020035.txt:0
plos/journal.pbio.0020040.txt:0
plos/journal.pbio.0020042.txt:1
plos/journal.pbio.0020043.txt:2
plos/journal.pbio.0020046.txt:1
plos/journal.pbio.0020047.txt:3
plos/journal.pbio.0020052.txt:0
plos/journal.pbio.0020053.txt:3
plos/journal.pbio.0020054.txt:0
plos/journal.pbio.0020063.txt:0
plos/journal.pbio.0020064.txt:1
plos/journal.pbio.0020067.txt:1
plos/journal.pbio.0020068.txt:0
plos/journal.pbio.0020071.txt:1
plos/journal.pbio.0020073.txt:0
plos/journal.pbio.0020100.txt:0
plos/journal.pbio.0020101.txt:4
plos/journal.pbio.0020105.txt:0
plos/journal.pbio.0020112.txt:0
plos/journal.pbio.0020113.txt:0
plos/journal.pbio.0020116.txt:2
plos/journal.pbio.0020121.txt:0
plos/journal.pbio.0020125.txt:1
plos/journal.pbio.0020127.txt:3
plos/journal.pbio.0020133.txt:1
plos/journal.pbio.0020140.txt:3
plos/journal.pbio.0020145.txt:0
plos/journal.pbio.0020146.txt:0
plos/journal.pbio.0020147.txt:1
plos/journal.pbio.0020148.txt:0
plos/journal.pbio.0020150.txt:1
plos/journal.pbio.0020156.txt:0
plos/journal.pbio.0020161.txt:0
plos/journal.pbio.0020164.txt:0
plos/journal.pbio.0020169.txt:0
plos/journal.pbio.0020172.txt:0
plos/journal.pbio.0020183.txt:2
plos/journal.pbio.0020187.txt:1
plos/journal.pbio.0020190.txt:0
plos/journal.pbio.0020206.txt:1
plos/journal.pbio.0020213.txt:0
plos/journal.pbio.0020214.txt:0
plos/journal.pbio.0020215.txt:0
plos/journal.pbio.0020216.txt:0
plos/journal.pbio.0020223.txt:2
plos/journal.pbio.0020224.txt:0
plos/journal.pbio.0020228.txt:0
plos/journal.pbio.0020232.txt:1
plos/journal.pbio.0020241.txt:0
plos/journal.pbio.0020262.txt:0
plos/journal.pbio.0020263.txt:0
plos/journal.pbio.0020267.txt:0
plos/journal.pbio.0020272.txt:1
plos/journal.pbio.0020276.txt:0
plos/journal.pbio.0020297.txt:1
plos/journal.pbio.0020302.txt:3
plos/journal.pbio.0020306.txt:0
plos/journal.pbio.0020307.txt:2
plos/journal.pbio.0020310.txt:2
plos/journal.pbio.0020311.txt:0
plos/journal.pbio.0020337.txt:2
plos/journal.pbio.0020346.txt:0
plos/journal.pbio.0020347.txt:6
plos/journal.pbio.0020348.txt:0
plos/journal.pbio.0020350.txt:0
plos/journal.pbio.0020353.txt:0
plos/journal.pbio.0020354.txt:0
plos/journal.pbio.0020394.txt:2
plos/journal.pbio.0020400.txt:1
plos/journal.pbio.0020401.txt:1
plos/journal.pbio.0020404.txt:0
plos/journal.pbio.0020406.txt:0
plos/journal.pbio.0020419.txt:1
plos/journal.pbio.0020420.txt:2
plos/journal.pbio.0020430.txt:0
plos/journal.pbio.0020431.txt:2
plos/journal.pbio.0020439.txt:2
plos/journal.pbio.0020440.txt:4
plos/journal.pbio.0030021.txt:0
plos/journal.pbio.0030024.txt:1
plos/journal.pbio.0030032.txt:0
plos/journal.pbio.0030050.txt:0
plos/journal.pbio.0030051.txt:1
plos/journal.pbio.0030056.txt:0
plos/journal.pbio.0030062.txt:3
plos/journal.pbio.0030065.txt:0
plos/journal.pbio.0030076.txt:0
plos/journal.pbio.0030094.txt:0
plos/journal.pbio.0030097.txt:0
plos/journal.pbio.0030102.txt:0
plos/journal.pbio.0030105.txt:2
plos/journal.pbio.0030127.txt:0
plos/journal.pbio.0030129.txt:0
plos/journal.pbio.0030131.txt:0
plos/journal.pbio.0030136.txt:0
plos/journal.pbio.0030137.txt:0
plos/pmed.0010008.txt:2
plos/pmed.0010010.txt:0
plos/pmed.0010013.txt:0
plos/pmed.0010021.txt:0
plos/pmed.0010022.txt:0
plos/pmed.0010023.txt:0
plos/pmed.0010024.txt:0
plos/pmed.0010025.txt:0
plos/pmed.0010026.txt:0
plos/pmed.0010028.txt:1
plos/pmed.0010029.txt:0
plos/pmed.0010030.txt:0
plos/pmed.0010034.txt:0
plos/pmed.0010036.txt:0
plos/pmed.0010039.txt:0
plos/pmed.0010041.txt:1
plos/pmed.0010042.txt:0
plos/pmed.0010045.txt:0
plos/pmed.0010046.txt:0
plos/pmed.0010047.txt:0
plos/pmed.0010048.txt:0
plos/pmed.0010049.txt:0
plos/pmed.0010050.txt:0
plos/pmed.0010051.txt:0
plos/pmed.0010052.txt:13
plos/pmed.0010056.txt:0
plos/pmed.0010058.txt:0
plos/pmed.0010060.txt:0
plos/pmed.0010061.txt:0
plos/pmed.0010062.txt:0
plos/pmed.0010064.txt:0
plos/pmed.0010066.txt:0
plos/pmed.0010067.txt:0
plos/pmed.0010068.txt:0
plos/pmed.0010069.txt:0
plos/pmed.0010070.txt:0
plos/pmed.0010071.txt:0
plos/pmed.0020002.txt:0
plos/pmed.0020005.txt:2
plos/pmed.0020007.txt:0
plos/pmed.0020009.txt:1
plos/pmed.0020015.txt:1
plos/pmed.0020016.txt:0
plos/pmed.0020017.txt:0
plos/pmed.0020018.txt:0
plos/pmed.0020019.txt:0
plos/pmed.0020020.txt:0
plos/pmed.0020021.txt:0
plos/pmed.0020022.txt:0
plos/pmed.0020023.txt:0
plos/pmed.0020024.txt:0
plos/pmed.0020027.txt:0
plos/pmed.0020028.txt:0
plos/pmed.0020033.txt:11
plos/pmed.0020034.txt:0
plos/pmed.0020035.txt:0
plos/pmed.0020036.txt:1
plos/pmed.0020039.txt:0
plos/pmed.0020040.txt:1
plos/pmed.0020045.txt:0
plos/pmed.0020047.txt:0
plos/pmed.0020048.txt:0
plos/pmed.0020050.txt:0
plos/pmed.0020055.txt:0
plos/pmed.0020059.txt:3
plos/pmed.0020060.txt:1
plos/pmed.0020061.txt:0
plos/pmed.0020062.txt:0
plos/pmed.0020065.txt:0
plos/pmed.0020067.txt:0
plos/pmed.0020068.txt:0
plos/pmed.0020071.txt:0
plos/pmed.0020073.txt:0
plos/pmed.0020074.txt:0
plos/pmed.0020075.txt:0
plos/pmed.0020082.txt:0
plos/pmed.0020085.txt:0
plos/pmed.0020086.txt:0
plos/pmed.0020088.txt:0
plos/pmed.0020090.txt:0
plos/pmed.0020091.txt:0
plos/pmed.0020094.txt:0
plos/pmed.0020098.txt:0
plos/pmed.0020099.txt:0
plos/pmed.0020102.txt:0
plos/pmed.0020103.txt:0
plos/pmed.0020104.txt:0
plos/pmed.0020113.txt:0
plos/pmed.0020114.txt:0
plos/pmed.0020115.txt:1
plos/pmed.0020116.txt:0
plos/pmed.0020117.txt:0
plos/pmed.0020118.txt:0
plos/pmed.0020120.txt:0
plos/pmed.0020123.txt:0
plos/pmed.0020140.txt:0
plos/pmed.0020144.txt:0
plos/pmed.0020145.txt:0
plos/pmed.0020146.txt:0
plos/pmed.0020148.txt:0
plos/pmed.0020149.txt:0
plos/pmed.0020150.txt:0
plos/pmed.0020155.txt:0
plos/pmed.0020157.txt:0
plos/pmed.0020158.txt:1
plos/pmed.0020160.txt:0
plos/pmed.0020161.txt:0
plos/pmed.0020162.txt:0
plos/pmed.0020180.txt:1
plos/pmed.0020181.txt:0
plos/pmed.0020182.txt:0
plos/pmed.0020187.txt:0
plos/pmed.0020189.txt:0
plos/pmed.0020191.txt:0
plos/pmed.0020192.txt:0
plos/pmed.0020194.txt:0
plos/pmed.0020195.txt:1
plos/pmed.0020196.txt:0
plos/pmed.0020197.txt:0
plos/pmed.0020198.txt:0
plos/pmed.0020200.txt:0
plos/pmed.0020201.txt:0
plos/pmed.0020203.txt:0
plos/pmed.0020206.txt:0
plos/pmed.0020208.txt:0
plos/pmed.0020209.txt:0
plos/pmed.0020210.txt:0
plos/pmed.0020212.txt:0
plos/pmed.0020216.txt:1
plos/pmed.0020226.txt:0
plos/pmed.0020231.txt:0
plos/pmed.0020232.txt:1
plos/pmed.0020235.txt:0
plos/pmed.0020236.txt:0
plos/pmed.0020237.txt:0
plos/pmed.0020238.txt:1
plos/pmed.0020239.txt:0
plos/pmed.0020242.txt:0
plos/pmed.0020246.txt:0
plos/pmed.0020247.txt:0
plos/pmed.0020249.txt:0
plos/pmed.0020257.txt:1
plos/pmed.0020258.txt:0
plos/pmed.0020268.txt:0
plos/pmed.0020272.txt:0
plos/pmed.0020273.txt:0
plos/pmed.0020274.txt:0
plos/pmed.0020275.txt:0
plos/pmed.0020278.txt:0
plos/pmed.0020281.txt:0
```

For this command, I am once again being somewhat specific,  but with the sub directory. Similar to the first example, I used the star * again. This time I am searching for how many times "nature" appears within every sub directory and file in the **plos** directory. Even though there were small instances of the word throughout the sub directories and the files, it still returned the number of times, even if the word was not mentioned at all. 

This could be useful in the way that we could be technically hand-picking the files that don't have the word we are searching for, since the `grep -c` command will still show the files that don't have the searched string, returning for each file. In other words, this command could be useful for knowing what files don't have the word we need and that way we can get rid of them. 

## **2) `grep -r`**
- This command is similar to `grep -c`, with the exception that it doesn't count how many times the specified string is counted. Instead, `grep -r` will return the lines themselves that contain the specified string, along with what directory it is found in (if the directory is not specified).
- In other words, it will search for the string across all the files found within the directory or specified directory/sub directory. 


**EXAMPLE #1: `grep -r "Kill"`**

```
[cs15lfa22ig@ieng6-203]:technical:516$ grep -r "Kill"
```

For this command, I am looking for the specific instances of the word "Kill" within every sub directory and files of the main directory, docsearch. Following this command, this is the output: 

```
biomed/1471-2121-2-6.txt:          measured according to the methods of Killilea et al. [
biomed/1471-2172-3-9.txt:        cytotoxic cells that lyse tumor targets. Natural Killer
biomed/1471-2172-3-9.txt:        cause neither an increase in the Natural Killer phenotype
biomed/1471-2172-3-9.txt:        to Lymphokine Activated Killer activity, reaffirming that
biomed/1471-2172-3-9.txt:        LAK - Lymphokine Activated Killer
biomed/1471-2172-3-9.txt:        NK - Natural Killer cells.
biomed/1471-2180-2-35.txt:        Superbug Killers, News Week, Dec. 17, 2001 50-51) and, of
biomed/1476-4598-1-5.txt:          B cells Natural Killer cells) by 4 hour adherence step.
plos/journal.pbio.0020112.txt:        When Food Kills: BSE, E. coli,
```
This output displays all the instances of the word "Kill" across all sub directories and files within the technical directory. Instead of counting the instance of the word, like `grep -c` would, it returns the whole line containing the word, even if it is not a complete sentence (as shown above).

 Furthermore, we did not have to specify a sub directry to look for this word in, which is extremely convenient. 

This command might be helpful when looking for an exact sentence mentioning the desired word, and that way once you find the line you could go into the file that contains it and do whatever is needed (copying the line, editing the line, pasting something into the line, etc)--take writing an essay for example. 

**EXAMPLE #2: `grep -r "medic" 911report/*.txt`**

```
[cs15lfa22ig@ieng6-203]:technical:520$ grep -r "medic" 911report/*.txt
```

In this example, my goal is to find all sentences containing the word "medic," especifically within the 911report sub directory. Notice that I used the star * again, and after .txt; essentially what this means is that I am looking for "medic" within 911reports, across all files that end with ".txt"--hence, the star * is used. 

```
911report/chapter-1.txt:    At 8:41, Sweeney told Woodward that passengers in coach were under the impression that there was a routine medical emergency in first class. Other flight attendants were busy at duties such as getting medical supplies while Ong and Sweeney were reporting the events.
911report/chapter-10.txt:                medical assistance teams.
911report/chapter-11.txt:                medications. What is missing is the attending physician who makes sure they work as
911report/chapter-13.4.txt:                described the two Saudis as sons of a sick father who was seeking medical treatment       
911report/chapter-13.5.txt:                11,2001,08:47:20-09:54:29. For the paramedic, see FDNY interview 32, Chief (Feb. 9,       
911report/chapter-13.5.txt:                were appropriate is still a subject for medical and scientific debate. See EPA
911report/chapter-3.txt:                the attack, offer medical and technical advice, and coordinate state and local
911report/chapter-3.txt:                medical services, air traffic control, financial services, telephone systems, and
911report/chapter-5.txt:                the cover story that he would be visiting a medical clinic to obtain a new
911report/chapter-5.txt:                    in the German army before obtaining a medical discharge, and lived with Atta and
911report/chapter-5.txt:                    Hamburg in 1998, where he studied medical technology. Soon after moving to
911report/chapter-9.txt:                medical service, and building safety professionals.
911report/chapter-9.txt:            Emergency medical services (EMS) personnel were directed to one of four triage areas
911report/chapter-9.txt:                specific casualty reports. In addition, many ambulance paramedics from private
911report/chapter-9.txt:                injured-they need to get a medic and a stretcher to this floor, and described the
911report/chapter-9.txt:                9:57, an EMS paramedic approached the FDNY Chief of Department and advised that an
911report/chapter-9.txt:                and medical response from Arlington County at the U.S. military's headquarters-a
```
The output is exactly what we are expecting: parts of sentences containing the word we are looking for, across all files ending with ".txt." 

Recalling the previous example, this example could also be helpful in a similar way. Using `grep -r` and being specific about the sub directory could be really helpful if we want to, for example, remember the name of a file but we only know the contents of it. This way, we could use this command with the word we want to look for, across all files, and find the name of the file we want (or files). 

**EXAMPLE #3: `grep -r "tech" government/Media/Using_Tech_Tools.txt`**

```
[cs15lfa22ig@ieng6-203]:technical:534$ grep -r "tech" government/Media/Using_Tech_Tools.txt
```
For this example, I am being extremely specific about the word I am looking for and where I want to look for it, as I also specified the file to look in. I am basically telling the terminal "go into this directory and its sub directory, and into this specific file, and look for this specific word." 

```
technology, such as Internet connections. Those places need
But as lawyers try to meet demands with technology, the basic
When small firms and solos do use technology to help smaller
```
The output, as we can see, is not long, but we do have what we are looking for.

In a similar sense to the previously discussed example (EXAMPLE #2 FOR THIS COMMAND), this command could be helpful if we want to make sure a word is in a specific file. In the previous example, I mentioned how we could use that command to remember the name of a file if we only know the contents of it. For this command, we could use it as means of ensuring that the particular word is in a specific file. If this command doesn't return anything, then we can delete it or edit it so that it contains the word. 




## **3) `grep -l`**
- This command holds somewhat of the previous two ideas discussed, in the sense that it also incorporates a specific string to search for. However, the difference between `grep -l` to the previous commands discussed is that instead of printing out a sentence where the word we're looking for is, or printing the count of the instances of that word, this command will **return the path(s) where the word is found.**
- ***Note: When using `grep -l`, you MUST specify the directory where you are looking for the specified string.***
- Its behavior will be demonstrated with the following three examples below. 

**EXAMPLE #1: `grep -l "abuse" government/Media/*`**

```
[cs15lfa22ig@ieng6-203]:technical:565$ grep -l "abuse" government/Media/*
```


```
government/Media/A_Perk_of_Age.txt
government/Media/Abuse_penalties.txt
government/Media/All_May_Have_Justice.txt
government/Media/Annual_Fee.txt
government/Media/Avoids_Budget_Cut.txt
government/Media/Boone_legal_service.txt
government/Media/Butler_Co_attorneys.txt
government/Media/City_Council_Budget.txt
government/Media/CommercialAppealMemphis2.txt
government/Media/Domestic_Violence_Ruling.txt
government/Media/Domestic_violence_aid.txt
government/Media/Few_who_need.txt
government/Media/Firm_to_the_Poor_Needs_Help.txt
government/Media/Funding_May_Limit.txt
government/Media/Hard_to_Get.txt
government/Media/Helping_Hands.txt
government/Media/Higher_Registration_Fees.txt
government/Media/Legal-aid_chief.txt
government/Media/Legal_Aid_campaign.txt
government/Media/Legal_Aid_in_Clay_County.txt
government/Media/Low-income_children.txt
government/Media/Marylands_Legal_Aid.txt
government/Media/Too_Crucial_to_Take_Cut.txt
government/Media/Understanding.txt
government/Media/Using_Tech_Tools.txt
government/Media/Weak_economy.txt
government/Media/Workers_aid_center.txt
government/Media/fight_domestic_abuse.txt
```

**EXAMPLE 2: `grep -l "dioxide" biomed/*`**

```
[cs15lfa22ig@ieng6-203]:technical:571$ grep -l "dioxide" biomed/*
```

```
grep -l "dioxide" biomed/*
biomed/1471-2105-1-1.txt
biomed/1471-213X-1-9.txt
biomed/1471-2180-2-22.txt
biomed/1471-2180-3-4.txt
biomed/1471-2415-3-3.txt
biomed/1472-6793-2-4.txt
biomed/1472-6793-3-4.txt
biomed/1472-6793-3-5.txt
biomed/1472-6831-3-1.txt
biomed/1475-2867-3-12.txt
biomed/1476-069X-1-3.txt
biomed/1476-069X-2-4.txt
biomed/cc1495.txt
biomed/cc1538.txt
biomed/cc1856.txt
biomed/cc1882.txt
biomed/cc2172.txt
biomed/cc3.txt
biomed/cc4.txt
biomed/gb-2001-2-10-research0041.txt
biomed/gb-2001-3-1-research0001.txt
biomed/rr172.txt
```


**EXAMPLE #3: `grep -l "oxygen" plos/journal*.txt`**

```
[cs15lfa22ig@ieng6-203]:technical:583$ grep -l "oxygen" plos/journal*.txt
```

```
plos/journal.pbio.0020012.txt
plos/journal.pbio.0020150.txt
plos/journal.pbio.0020272.txt
plos/journal.pbio.0020302.txt
plos/journal.pbio.0020348.txt
plos/journal.pbio.0020400.txt
plos/journal.pbio.0030102.txt
```








