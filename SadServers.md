 

Sad Server Commands - Google Docs 

 

 

TASK 1: 

/ ps auxf 

/ lsof (list processes) /var/log/bad.log  

Get process ID 

/ kill –9 PID 

 

TASK2: There's a web server access log file at /home/admin/access.log. The file consists of one line per HTTP request, with the requester's IP address at the beginning of each line. 
 
Find what's the IP address that has the most requests in this file (there's no tie; the IP is unique). Write the solution into a file /home/admin/highestip.txt. For example, if your solution is "1.2.3.4", you can do echo "1.2.3.4" > /home/admin/highestip.txt 

 

 

Use awk command 

This command is a scanning command  

 

Print first column awk '{print $1}' 

 

Sort the ip address use same command then pipe into sort command 

Then uniq command then –c prefixes how many 

Then sort –n to sort by how many times is appears 

/ sort –nr to reverse in decending order 

Then | head –1 first line 

 

Then awk $2 just for second column 

 

Task 3:  

Description: This is the Command Line Murders with a small twist as in the solution is different 
 
Enter the name of the murderer in the file /home/admin/mysolution, for example echo "John Smith" > ~/mysolution 
 
Hints are at the base of the /home/admin/clmystery directory. Enjoy the investigation! 

Root (sudo) Access: False 

Test: md5sum ~/mysolution returns 9bba101c7369f49ca890ea96aa242dd5 
 
(You can always see /home/admin/agent/check.sh to see how the solution is evaluated). 

Tall male 6' 

Woman at coffee shop had blonde hair ANNABEL , blond spiky hair, new zealand accent 

Found a wallet believed to belong to the killer: no ID, just loose change, and membership cards for Rotary_Club, Delta SkyMiles, the local library, and the Museum of Bash History. The cards are totally untraceable and have no name, for some reason. 

 

Annabel Church  F       38      Buckingham Place, line 179 

People and vehicles ls 

SEE INTERVIEW #47246024- not annabel sun 

SEE INTERVIEW #699607  

Seen a blue Honda with licence plate  

 

In order to actually get information about vehicles that might match our description, 

we need to get multiple lines AROUND each match.  We can use the -A, -B, or -C option with grep: 

  

        grep -A 5 "L337" mystery/vehicles 

  

This will match the license plates that contain "L337" and, for each match, show us the five lines AFTER it. 

License Plate L337QE9 

Make: Honda 

Color: Blue 

Owner: Erika Owens 

Height: 6'5" 

Weight: 220 lbs 

 

License Plate L337DV9 

Make: Honda 

Color: Blue 

Owner: Joe Germuska 

Height: 6'2" 

Weight: 164 lbs 

-- 

License Plate L3375A9 

Make: Honda 

Color: Blue 

Owner: Jeremy Bowers 

Height: 6'1" 

Weight: 204 lbs 

-- 

License Plate L337WR9 

Make: Honda 

Color: Blue 

Owner: Jacqui Maher 

Height: 6'2" 

Weight: 130 lbs 

 

Rotary_Club, Delta SkyMiles, the local library, and the Museum of Bash History. 

 

To see who was a member of several different groups, you can combine their membership lists into one and search against that. 

  

        cat Fitness_Galaxy AAA United_MileagePlus | grep "John Smith" 

  

If you only want to see the number of matches, you can use grep's -c option (the c must be lowercase): 

  

        cat Fitness_Galaxy AAA United_MileagePlus | grep -c "John Smith" 

  

Or you can pipe the result to 'wc -l': 

  

        cat Fitness_Galaxy AAA United_MileagePlus | grep "John Smith" | wc –l 

 

Joe germuska 

 

 

TASK 4: "Taipei": Come a-knocking 

 

"Taipei": Come a-knocking is another sadserver Description: There is a web server on port :80 protected with Port Knocking. Find the one "knock" needed (sending a SYN to a single port, not a sequence) so you can curl localhost. 

 

use the knock utility, for example to knock on port 3000: knock localhost 3000 

 

Netcat (nc) and nmap are also available. Note than nmap has some options where you'd need to be root (not possible here) 

 

 

 nmap against all ports, for example: nmap -p- localhost. 

 

Task 5: "Resumable Server": Linux Upskill Challenge 

 

This is a Debian 11 server without a challenge; it's for you to do as you please. 
 
It's meant in principle for guided tutorials like the Linux Upskill Challenge, with some limitations (there's still no outgoing Internet access). 
 
TASK 6: "Lhasa": Easy Math 

 
There's a file /home/admin/scores.txt with two columns (the first number is a line number and the second one is a test score for example). 
 
Find the average (more precisely; the arithmetic mean: sum of numbers divided by how many numbers are there) of the numbers in the second column (find the average score). 
 
Use exactly two digits to the right of the decimal point. i. e., use exaclty two "decimal digits" without any rounding. Eg: if average = 21.349 , the solution is 21.34. If average = 33.1 , the solution is 33.10. 
 

First just get 2nd row awk '{ print $2 }' scores.txt 

 

 

We can use the paste tool to add a plus symbol between the score numbers, so we can pass the expression to bc: sumexpr=$(awk '{ print $2 }' scores.txt | paste -sd+) 

 

The sum of the numbers in the second column would be then: sum=$(echo $sumexpr | bc) , this returns 520.4 (regardless of bc "scale" or number of digits to the right of the decimal point).  

 

 

 

 

 

 

 
