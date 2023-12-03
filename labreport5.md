## Part 1

1. I'm trying to run my grade.sh and I'm prety sure I have everything I need for it to give me what I want but for some reason when I do bash grade.sh it doesn't work. Here's a screenshot of what happens when I run it:
   - <img width="644" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/3b59104b-2d00-4a71-a57e-e7985d0e0d6a">

2. I think reviewing on how to write if statements in bash would the correct path to go for your issue.
3. Oh, I forgot that the square brackets and what's written inside need to have a space in between. Thank you it works now.
   - Here's the fixed file:
    - <img width="448" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/f0638158-5157-427f-bf52-96c8cab1b19d">
   - Here's the output that I was expecting and got returned:
    - <img width="649" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/629686cb-612a-401a-be29-a08f8bd3f434">
4. The file and directory structure and contents of files, other than grade.sh, are the same as https://github.com/ucsd-cse15l-s23/list-examples-grader because that's what I used.
  - Contents of grade.sh before changes:
    - <img width="443" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/31758896-2208-4905-8ffa-a82142b3ec68">
  - Contents after changes:
    - <img width="453" alt="image" src="https://github.com/MayXpan/cse-15l-labs/assets/130320757/7f9b48de-72c7-46a4-a6dd-cabeb39cd8ca">
  - Command line to trigger the bug while in the directory that contains grade.sh:
    - ```bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected```
  - What needed to be fixed was just adding a space in between the square brackets and the contents inside of them. I essentially recreated what happened with me when doing lab6 where I forgot that you had to have a space inbetween the square brackets and if statement so I was getting the same issue.  I also once forgot to add the then after the if statement line so that also gave me issues but I didn't want to recreate that one for this lab.

## Part 2

Once again, like the last time this type of question was asked, everything we learned in the second half of the labs were all new to me so every single one of them were interesting, although some where quite annoying and frustrating to deal with, like when I originally did lab 6 and 8.  However overall all the labs were pretty good learning experiences.
