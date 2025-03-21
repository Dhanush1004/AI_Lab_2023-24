# Ex.No: 10  Logic Programming –  Simple queries from facts and rules
### DATE: 21-03-2025                                                                           
### REGISTER NUMBER : 212222220010
### AIM: 
To write a prolog program to find the answer of query. 
###  Algorithm:
 Step 1: Start the program <br> 
 Step 2: Convert the sentence into First order Logic  <br> 
 Step 3:  Convert the sentence into Horn clause form  <br> 
 Step 4: Add rules and predicates in a program   <br> 
 Step 5:  Pass the query to program. <br> 
 Step 6: Prolog interpreter shows the output and return answer. <br> 
 Step 8:  Stop the program.
### Program:
### Task 1:
Construct the FOL representation for the following sentences <br> 
1.	John likes all kinds of food.  <br> 
2.	Apples are food.  <br> 
3.	Chicken is a food.  <br> 
4.	Sue eats everything Bill eats. <br> 
5.	 Bill eats peanuts  <br> 
   Convert into clause form and Prove that John like Apple by using Prolog. <br> 
### Program:

```
food(apples).
food(chicken).
food(peanuts).
likes(john, X) :-
food(X).
eats(bill, X) :-
food(X).
eats(sue, X) :-
eats(bill, X).
```


### Output:
![image](https://github.com/user-attachments/assets/bf61ed3c-253c-4d61-9682-f796effd7fb4)


### Task 2:
Consider the following facts and represent them in predicate form: <br>              
1.	Steve likes easy courses. <br> 
2.	Science courses are hard. <br> 
3. All the courses in Have fun department are easy <br> 
4. BK301 is Have fun department course.<br> 
Convert the facts in predicate form to clauses and then prove by resolution: “Steve likes BK301 course”<br> 

### Program:
```
likes(steve, X) :-
easy_course(X).
hard_course(science).
easy_course(X) :-
in_department(X, have_fun).
in_department(bk301, have_fun).
```

### Output:
![image](https://github.com/user-attachments/assets/33b96f07-abab-4dee-8203-f975d273775b)

### Task 3:
Consider the statement <br> 
“This is a crime for an American to sell weapons to hostile nations. The Nano , enemy of America has some missiles and its missiles were sold it by Colonal West who is an American” <br> 
Convert to Clause form and prove west is criminal by using Prolog.<br> 
### Program:
```
american(west).
missile(m).
owns(nano, m).
enemy(nano, america).

hostile(Z) :-
    enemy(Z, america).

weapon(Y) :-
    missile(Y).

sells(west, Y, nano) :-
    missile(Y).
criminal(X) :-
    american(X),
    weapon(Y),
    hostile(Z),
    sells(X, Y, Z).

:- discontiguous owns/2.

```

### Output:

![image](https://github.com/user-attachments/assets/ee9394bd-900e-4683-bb1b-682b6cebf8cc)


### Result:
Thus the prolog programs were executed successfully and the answer of query was found.
