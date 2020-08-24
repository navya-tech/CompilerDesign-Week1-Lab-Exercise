# CompilerDesign-Week1-Lab-Exercise

## Program 1:
Implement a language recogniser which accepts set of all strings over the alphabet ∑={a,b} containing an even number of a’s and an even number of b’s.
### Description:
The acceptable strings of the language are ε(Null string), aa, bb, abba, babbab etc.

Deterministic Finite Automata for the given language is given below:

.

DFA M=(Q,∑,δ,Q0,F) Where

Q=Set of all states ={Q0,Q1,Q2,Q3}

∑=Input Alphabet={a,b},

Start state is Q0

F=Set of all final States={ Q0}

And the transitions are defined  as δ(Q0, a)=Q1, δ(Q0, b)= Q3

                                    δ(Q1, a)= Q0, δ(Q1,b)= Q2
                                    
                                    δ(Q2, a)=Q3, δ(Q2, b)= Q1
                                    
                                    δ(Q3, a)= Q2, δ(Q3, b)= Q0
                                    
### Algorithm: Language recognizer
#### Input:
input //input string
#### Output:
Algorithm prints a message

“String accepted”: If the input is acceptable by the language,

“String not accepted” otherwise,

“Invalid token”: If the input string contains symbols other than input alphabet.


## Method:
state=0 //initial state

while((current=input[i++])!='\0'){

switch(state)

case 0: if(current=='a') state=1;

else if(current=='b') state=2;

else

Print "Invalid token" ; exit;

case 1: if(current=='a') state=0;

else if(current=='b') state=3;

else

Print "Invalid token" ; exit;

case 2: if(current=='a') state=3;

else if(current=='b') state=0;

else

Print "Invalid token" ; exit;

case 3: if(current=='a') state=2;

else if(current=='b') state=1;

else

Print "Invalid token" ; exit;

end switch

end while

//Print output

if(state==0)

Print ”String accepted”

else

Print ”String not accepted”


### Test cases:

Input       Expected Output         Output

aabb        String accepted         String accepted

abab        String accepted         String acccepted

aaabb       String not accepted     String not accepted

aaa         String not accepted     String not accepted

abcd        Invalid token            Invalid token








## PROBLEM 2
    Implementation of Language recognizer for set of all strings over the Alphabet ∑={a,b} ending with two symbols of same type.
### Description
   The strings accepted by this language is aa,bb,aaa,baa,abb,bbb,abaabb, etc....
   
   Deterministic Finite Automata accepting the given language is given below:
   
   DFA: M={Q,∑,δ,Q0,F}, where
   
   Q={Q0,Q1,Q2,Q3,Q4)
   
   ∑={a,b}
   
   F={Q2, Q4}
   
   and the transition functions are defined as δ(Q0,a)=Q1, δ(Q0,b)=Q3
   
                                               δ(Q1,a)=Q2, δ(Q1,b)=Q3
                                               
                                               δ(Q2,a)=Q2, δ(Q2,b)=Q3
                                               
                                               δ(Q3,a)=Q1, δ(Q3,b)=Q4
                                               
                                               δ(Q4,a)=Q1, δ(Q4,b)=Q4
                                               
### Algorithm: Language recognizer
#### Input:
input //input string
#### Output:
Algorithm prints a message

“String accepted”: If the input is acceptable by the language,

“String not accepted” otherwise,

“Invalid token”: If the input string contains symbols other than input alphabet.

### Method:
state=0 //initial state

while((current=input[i++])!='\0'){

switch(state)

case 0: if(current=='a') state=1;

else if(current=='b') state=3;

else

Print "Invalid token" ; exit;

case 1: if(current=='a') state=2;

else if(current=='b') state=3;

else

Print "Invalid token" ; exit;

case 2: if(current=='a') state=2;

else if(current=='b') state=3;

else

Print "Invalid token" ; exit;

case 3: if(current=='a') state=1;

else if(current=='b') state=4;

else

Print "Invalid token" ; exit;

case 4: if(current=='a') state=1;

else if(current=='b') state=4;

else

Print "Invalid token" ; exit;

end switch

end while

//Print output

if(state==2|| state==4)

Print ”String accepted”

else

Print ”String not accepted”

### Test cases:

Input       Expected Output         Output

aabb        String accepted         String accepted

abab        String not accepted     String not acccepted

aaabb       String accepted         String accepted

aaa         String accepted         String accepted

abcd        Invalid token            Invalid token
