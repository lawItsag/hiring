# Bluetel Salesforce Candidate Questionnaire

Thanks for taking interest in a position at Bluetel! Answering this set of questions gives us a good idea about your technical and logical capabilities; as well as a couple of personal characteristics. You can be as brief or comprehensive as you wish in your answers. We don’t expect every candidate to know all the answers to these questions, so please don’t be discouraged if you don’t know the answer! Good luck!  

### Question 1
Create an algorithm that prints the integers from 17 to 53. However for multiples of two, print "Foo" instead  of the number and for multiples of five print "Bar". For numbers which are multiples of both two and five print "FooBar". 
Ans:
class FooBar
{ 
 public static void main(String args[]) 
   { 
 int n = 53; 

    // loop for 53 times 
    for (int i=17; i<=n; i++)
   { 
   if (i%10==0)
   System.out.print("FooBar"+" ");
   // number divisible by 5, print 'Bar'
   // in place of the number 
   else if (i%5==0)
   System.out.print("Bar"+" ");

   // number divisible by 2, print 'Foo'
    // in place of the number 
   else if (i%2==0)
  System.out.print("Foo"+" ");

   // number multiples of(
   // both 2 & 5), print 'FooBar' in
   // place of the number 

   else // print the numbers 
   System.out.print(i+" ");
   } 
  } 
} 


### Question 2
In a relational database, why is redundant data (i.e. the same data stored in multiple tables) generally a bad thing?
Ans: 
Redundant data is a bad idea because when you modify data (update/insert/delete), then you need to do it in more than one place. This opens up the possibility that the data becomes inconsistent across the database.
### Question 3
In a relational database, why might redundant data be necessary in real world applications?
Ans: 
This is because data redundancy works to safeguard data and promote consistency.It is  acceptable for data to be stored in multiple places if you have a central master field or space for this data so that  there is a way to update all of the places where data is redundant through one central access point. Otherwise, data redundancy can lead to big problems with data inconsistency, where one update does not automatically update another field. As a result, pieces of data that are supposed to be identical end up having different values. 

### Question 4
In development teams, multiple people are often involved in building and maintaining a single salesforce instance. They may be working on a single task together, or multiple tasks, and changes made by one developer may conflict with those of another. What system would you suggest to help manage this, and why would you choose your solution in particular?
Ans:
 Use a  Version Control Repository Management Services like Git or GitLab. Git is a distributed revision control and source code management system which supports distributed, non-linear workflows allowing users a  frictionless context switching, role based codelines and feature based workflow
### Question 5

The below Salesforce Apex code may fail on any line with a `DMLException`. Modify the code to ensure that if it were to fail then no data would be saved.

```c#
Database.insert(action);
Database.update(actionPlan);
Database.update(customer);

```
Ans:
         insert action;
         update actionPlan;
         update customer;
### Question 6

What is the difference between `Trigger.old` and `Trigger.new`? Under which types of trigger are they each available?
Ans:
Trigger.new is a collection that returns a list of the new versions of the sObject. However, when the new variable is used as a bind variable in an SOQL query, Apex transforms the list of records into corresponding IDs.The new variable is used only for insert and update triggers. However, it can be modified only when it is used with before triggers. Please note that Trigger.new contains references to sObjects that cannot be operated on by Apex DML operations.

 Trigger.old contains the current or existing version of sObjects from the invoking DML action. It is used only in the update and delete triggers. Trigger.old is always read-only because it is not a mechanism by which you can change the data before it is entered in the database. Also trigger.old is NULL in the context of an insert operation.
### Question 7

Provide Salesforce Apex code which uses SOQL to extract the following fields from a custom object named `Visitors` into a List variable. Only records where the value of the `Company__c` field is equal to `Bluetel` should be retrieved.

- Id
- Name
- Visit_Time__c
- Visiting__c

Ans:
String company = 'Bluebel';
List<Visitor__c> Visitors  = Database.query('SELECT Id,Name,Visit__Time__c,Visiting__c FROM Visitor__c WHERE Name = :company’);
### Question 8

The following provides one test scenario for the requirement `Insurance Requests for amounts less than $100,000 should not be submitted to the insurer, and the user should be presented with an error if they attempt to make this submission`. Summarise the minimum test cases that you would define for the <u>entire</u> requirement.

> **Given** I am completing an insurance request 
>
> **When** I specify a cover amount of less than $100,000
> **AND** I choose to submit my request
>
> **THEN** I should receive an error 
> **AND** the request should not be submitted

Ans:use the validation rule below
if(cover_amount__c) < $100,000.00
 error message: cover amounts less than $100,000 cannot be submitted to insurer.

