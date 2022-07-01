# Perl-CSV
Complex Google Sheets Formulas in Perl


﻿#Create a CSV spreadsheet for Google Sheets in PERL
#Advanced Sheets formulas 

use strict;
use warnings;


#Create and open CSV in Google Sheets

open (File, ">", "/myfiles/warehouse.csv");
select File;
print ("Product, Year, Price, Stock\n");#Four columns
print File "mascara,2012, 2.50, 520\n";#insert dataset row 1
print File "lipstick,2014,5.00, 260\n";#insert dataset row 2
print File "blush,2012,12.60, 125\n";#insert dataset row 3
print File "nailpolish,2012, 8.50, 185\n";#insert dataset row 4
print File "perfume,2014, 7.60, 370\n";#insert dataset row 5
print File "sunscreen, 2014, 17.00,80 \n";#insert dataset row 5
print File "              \n";#blank row
print File "Calculations\n";
print File "What is the minimum price for products start with p?,\"=MINIFS(c2:c7,a2:a7,\"\"\p*\"\"\")\n";#MinimumIF
print File "What is total quantity in stock?,=SUM(D2:D7)\n";#calculate sum
print File "What is minimum price?,=MIN(C2:C7)\n";#calculate minimum
print File "What is maximum price?,=MAX(C2:C7)\n";#calculate maximum
print File "How many records?,=COUNT(B2:B7)\n";#Count the records
print File "What is average quantity in stock?,=AVERAGE(D2:D7)\n";#calculate average
print File "What is length of nailpolish?,=LEN(A5)\n";#length of string
print File "What is average price for Year 2012?,\"=AVERAGEIF(B2:B7,2012,C2:C7)\n";#AverageIF

#If success does not appear in terminal than error
select STDOUT;
print ("success!");
close (File);
