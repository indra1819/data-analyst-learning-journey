DAY 06 – EXCEL LOOKUP FUNCTIONS

1. VLOOKUP

VLOOKUP = Vertical Lookup

Use:
Table lo oka value search chesi, vere column nundi related value teeskovadaniki.

Syntax:
=VLOOKUP(lookup_value, table_array, col_index_num, FALSE)

Example:

ID     Name     Salary
101    Ravi     40000
102    Arun     35000
103    Sita     50000

Formula:
=VLOOKUP(102,A2:C4,3,FALSE)

Answer:
35000


2. VLOOKUP ARGUMENTS

=VLOOKUP(102,A2:C4,3,FALSE)

102
→ Search cheyyalsina value

A2:C4
→ Table range

3
→ Return cheyyalsina column number

FALSE
→ Exact match


3. TRUE vs FALSE

FALSE
→ Exact match

Example:
=VLOOKUP(A2,E2:G10,3,FALSE)

TRUE
→ Approximate match

Mostly ranges/slabs kosam use chestaru.


4. VLOOKUP LIMITATION

VLOOKUP normally LEFT → RIGHT work chestundi.

Example:

ID     Name     Salary

ID tho Name/Sala​ry search cheyyachu.

Kani Salary tho ID ni normal VLOOKUP tho search cheyyalem.


5. XLOOKUP

XLOOKUP = Modern Lookup Function

Syntax:
=XLOOKUP(lookup_value, lookup_array, return_array)

Example:

=XLOOKUP(102,A2:A4,C2:C4)

Answer:
35000

Advantages:
→ Left lookup possible
→ Right lookup possible
→ Column number avasaram ledu
→ More flexible


6. XLOOKUP NOT FOUND

Value dorakakapothe custom message ivvachu.

=XLOOKUP(105,A2:A4,C2:C4,"Not Found")

Answer:
Not Found


7. HLOOKUP

HLOOKUP = Horizontal Lookup

Horizontal data kosam use chestaru.

Example:

ID       101     102     103
Name     Ravi    Arun    Sita
Salary   40000   35000   50000

Formula:

=HLOOKUP(102,A1:D3,3,FALSE)

Answer:
35000


8. MATCH

MATCH value yokka position find chestundi.

Example:

Ravi
Arun
Sita

Formula:

=MATCH("Arun",A2:A4,0)

Answer:
2

Because Arun 2nd position lo unnadu.


9. INDEX

INDEX position based on value return chestundi.

Example:

Name     Salary
Ravi     40000
Arun     35000
Sita     50000

Formula:

=INDEX(B2:B4,2)

Answer:
35000


10. INDEX + MATCH

INDEX + MATCH = Powerful Lookup Combination

Formula:

=INDEX(C2:C4,MATCH(102,A2:A4,0))

MATCH
→ 102 position find chestundi

INDEX
→ Aa position lo unna value return chestundi

Answer:
35000


11. INDEX + MATCH ADVANTAGES

→ Left lookup possible
→ Right lookup possible
→ Flexible
→ Fixed column number avasaram ledu
→ Large datasets lo useful


12. IFERROR WITH LOOKUP

Lookup value dorakakapothe #N/A vastundi.

IFERROR use chesi custom message ivvachu.

=IFERROR(VLOOKUP("P999",A2:D6,4,FALSE),"Not Found")

Answer:
Not Found


13. VLOOKUP vs XLOOKUP

VLOOKUP
→ Old/common lookup
→ Vertical lookup
→ Column number required
→ Left lookup limitation

XLOOKUP
→ Modern lookup
→ Flexible
→ Left/right lookup
→ Column number required ledu
→ Not Found message easy


14. DATA ANALYST EXAMPLE

Customer_ID    Customer    City         Sales
C101           Ravi        Hyderabad    50000
C102           Arun        Chennai      35000
C103           Sita        Bangalore    60000

C103 sales find cheyyali.

XLOOKUP:

=XLOOKUP("C103",A2:A4,D2:D4)

Answer:
60000

VLOOKUP:

=VLOOKUP("C103",A2:D4,4,FALSE)

Answer:
60000

INDEX + MATCH:

=INDEX(D2:D4,MATCH("C103",A2:A4,0))

Answer:
60000


15. INTERVIEW STICK NOTES

VLOOKUP
→ Vertical Lookup

XLOOKUP
→ Modern Flexible Lookup

HLOOKUP
→ Horizontal Lookup

MATCH
→ Position find chestundi

INDEX
→ Position nundi value return chestundi

INDEX + MATCH
→ Flexible Lookup

IFERROR
→ Errors handle chestundi


16. PRACTICE

Product_ID    Product       Category        Price
P101          Laptop        Electronics     55000
P102          Mouse         Accessories       1000
P103          Keyboard      Accessories       2000
P104          Monitor       Electronics      15000
P105          Headphones    Accessories       3000

Questions:

1. VLOOKUP tho P103 price find cheyyi.

2. XLOOKUP tho P104 category find cheyyi.

3. XLOOKUP tho P105 product name find cheyyi.

4. P999 search chesi "Not Found" return cheyyi.

5. MATCH tho P103 position find cheyyi.

6. INDEX tho P103 price return cheyyi.

7. INDEX + MATCH tho P104 price find cheyyi.

8. IFERROR + VLOOKUP use cheyyi.


DAY 06 COMPLETE

Topics:
✓ VLOOKUP
✓ XLOOKUP
✓ HLOOKUP
✓ MATCH
✓ INDEX
✓ INDEX + MATCH
✓ IFERROR
✓ Exact Match
✓ Lookup Errors
✓ Data Analyst Lookup Scenarios
✓ Practice
