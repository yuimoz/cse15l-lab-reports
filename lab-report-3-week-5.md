# **LAB REPORT: RESEARCHING COMMANDS FOR `grep`**
### In this report, I will be demonstrating three alternate uses of the `grep` command, with nine examples in total. 

---

*NOTE: For efficiency purposes, I have already done `cd docsearch` to go into the **docsearch** directory to access the multiple sub directories/files within it. I will not be showing how to do that in this lab report.*

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

For this command, I am once again being somewhat specific, but just with the sub directory. Similar to the first example, I used the star * again. 




