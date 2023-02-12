# Lab Report 3

## Grep -v

Found: ChatGPT

        grep -v History find_results.txt 

Output:

        berlitz1
        berlitz1/HandRLasVegas.txt
        berlitz1/IntroMalaysia.txt
        berlitz1/HandRIstanbul.txt
        berlitz1/HandRJamaica.txt
        berlitz1/HandRHongKong.txt
        berlitz1/IntroEdinburgh.txt
        berlitz1/IntroDublin.txt
        berlitz1/IntroFrance.txt
        berlitz1/IntroMadeira.txt
        berlitz1/WhatToLakeDistrict.txt
        berlitz1/IntroIbiza.txt
        ...

This command is searching through the txt file find_results, which contains all the file names from berlitz1, for the lines that do not contain the word "History." This can be useful when looking to make sure all files have a certain naming pattern, or just when you want to ignore certain files in search.

        grep -v Japan IntroJapan.txt
        
Output:

        Its famous bullet trains zip through the country at up to
        300 km (186 miles) per hour. Its factories feature the latest
        generation of industrial robots that don’t eat, don’t sleep, and never
        strike. Its high-tech consumer electronics companies have placed
        affordable — and notoriously reliable — electronic products in
        households around the world.
        But peel back a layer and a different picture starts to
        social roots still lie deeply in its past as a feudal society of
        countless closely knit agricultural communities dominated by a small
        political elite.
        ...
        
This command is searching through the file IntroJapan.txt for all the lines that do not contain the word Japan. This function is especially useful when trying to ignore certain words when looking through a txt file.

## Grep -l

Found: ChatGPT

        grep -l India /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/*
        
Output:

        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HandRIsrael.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryEgypt.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryFWI.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryFrance.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryGreek.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryHongKong.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryIndia.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryIstanbul.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryLasVegas.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/HistoryMalaysia.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/IntroFWI.txt
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1/IntroIndia.txt
        ...
        
This command is searching through the berlitz1 directory for any files that contain the word India. This is useful when looking for files that have certain contents.

        grep -l India /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/*  
     
Output:

        grep: /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz1: Is a directory
        grep: /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/berlitz2: Is a directory
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/files_results
        /Users/yashravipati/Documents/GitHub/docsearch/written_2/travel_guides/find_results.txt
        
This commmand is looking through the travel_guides directory for any files that contain the word India. As there are two directories in addition to text files, it labels the two as directories and doesn't look through them, a useful feature when a directory you want to look through contains both files and directories.

## Grep -c

Found: https://linuxcommand.org/lc3_man_pages/grep1.html

        grep -c India HistoryIndia.txt 
        
Output:

        111
        
This command counts how many lines contain a certain word instead of displaying all of them. This is useful when trying to just find out how many of something exists in a file.

        grep -c India files_results

Output:

        4

This command counts how many lines in files-results contains a certain word, meaning it counts how many filenames in berlitz1 contain the word. This is useful when trying to find out how many files contain a certain word in the name.

## Grep -w

Found: https://linuxcommand.org/lc3_man_pages/grep1.html

        yashravipati@Yashs-MacBook-Pro berlitz1 % grep -w add HistoryIndia.txt

Output:

        add the title Empress of India to her roll of honor, proclaimed that

This command searches for the whole word, instead of just what could be the inputted pattern as a part of another word. This is useful when trying to look for certain words that are often parts of other words.

        grep -w HistoryIndia find_results.txt

Output:

        berlitz1/HistoryIndia.txt
        
This command searches for the word HistoryIndia in find_results, which contains all the filenames in berlitz1. This is useful when trying to find if a certain file exists, especially when the filename is likely to be a part of another filename.
