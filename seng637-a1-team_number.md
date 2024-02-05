>   **SENG 637 - Dependability and Reliability of Software Systems**

**Lab. Report \#1 – Introduction to Testing and Defect Tracking**

| Group: 2         |
| ---------------- |
| Corey Yang-Smith |
| Eric (Sieu) Diep |
| Hao Liu          |
| Mehreen Akmal    |
| Jenn  Bushey     |
  
**Table of Contents**

(When you finish writing, update the following list using right click, then
“Update Field”)

[1 Introduction](#introduction)

[2 High-level description of the exploratory testing plan](#high-level-description-of-the-exploratory-testing-plan)

[3 Comparison of exploratory and manual functional testing](#comparison-of-exploratory-and-manual-functional-testing)

[4 Notes and discussion of the peer reviews of defect reports](#notes-and-discussion-of-the-peer-reviews-of-defect-reports)

[5 How the pair testing was managed and team work/effort was divided](#how-the-pair-testing-was-managed-and-team-workeffort-was-divided)

[6 Difficulties encountered, challenges overcome, and lessons learned](#difficulties-encountered-challenges-overcome-and-lessons-learned)

[7 Comments/feedback on the lab and lab document itself](#commentsfeedback)

# Introduction

An introduction of your lab work, and what you knew about exploratory and manual
functional testing before this lab

Our work in this lab involved an exploration of different testing techniques, applied to an ATM simulation developed by [Gordon College](https://www.math-cs.gordon.edu/courses/cs211/ATMExample/Links.html). We performed exploratory testing, manual scripted testing, and regression testing on this system. Before this lab, we knew what was mentioned in the lecture about exploratory and manual testing. That is, that exploratory testing involves designing and executing tests at the same time - creatively considering different aspects and edge cases and then executing on those testing ideas. On the other hand, manual scripted testing involves first designing tests in a single stage, and executing these tests at a later date.

# High-level description of the exploratory testing plan

## Scope of Testing

### Functions To Be Tested

All the features of the ATM as defined in the High Level Requirements are to be tested:

- System Startup
- System Shutdown
- Session
- Transaction
- Withdrawal
- Deposit
- Transfer
- Inquiry
- Invalid PIN extension


### Functions Not Tested

These feature are not be tested because they are not included in the High Level Requirements:

- Performance testing (response time, periods of high usage)
- Usability testing (user interface ease of use)
- Reliability testing
- Security Testing

### Test Types

1. **Manual Exploratory Testing:** This involves exploring the software without predefined test cases, allowing the tester to learn the application, identify defects, and understand user workflows.
1. **Manual Scripted Testing:** This involves executing predefined test cases based on specifications, user requirements, or other documentation. This is more structured than exploratory testing.
1. **Regression Testing:** This type of testing is conducted to ensure that new changes or updates to the software do not negatively impact existing functionalities. This involves re-running both exploratory and scripted tests to verify that the system still behaves as expected.

## Test Logistics
For exploratory unscripted testing, all team members participated in exploration. We employed pair testing and then discussed and compared bugs that had been found and unique bugs were entered into an issue tracking system (Azure). 

Manual Scripted Testing and Regression Testing
| Name    | Test Scripts |
| ------- | ------------ |
| Mehreen | 1 - 8        |
| Jenn    | 9 - 16       |
| Corey   | 17 - 24      |
| Hao     | 25 - 32      |
| Eric    | 33 - 40      |


# Comparison of exploratory and manual functional testing

Our exploratory testing involved reading the system requirements and generating test scenarios to fulfill these requirements. This process involved a deeper understanding of the system requirements in order to generate these test cases, and some creativity to think of the different ways in which the systems could be tested. We found most of the bugs through our collaborative exploratory testing which may indicate this as an effective method for a small system, given explicit system requirements. However, our documentation of these processes were less formal and organized, as they were made on-the-fly and resembled quick-notes as opposed to a rigorous testing structure. With this method, we had the flexibility to consider and explore the system and its requirements any way we wanted.

On the other hand, the manual testing stage did not take any creativity or engineering-prowess as we simply navigated the program as per the various test cases. This is a task that could be carried out by anyone. That being said, the manual testing gave us more confidence in the integrity of the system as it forced us to test an exhaustive list of features that we did not entirely consider in the exploratory stage. We were more sure that we had covered testing the various features available due to having an explicit numbered list of test cases to attempt - that is, the documentation was much better. In this stage, we did encounter many of the same bugs that we found in the first stage.


-   Note that you need to submit a report generated by your defect tracking
    system, containing all defects recorded in the system.

# Notes and discussion of the peer reviews of defect reports

Reviewing other peers’ defect reports proved easier than expected due to the explicit documentation regarding system state, execution, and expected vs actual results. However, at times it was difficult to interpret the reports as we were getting used to the formatting requirements. We suspect that with more practice and iterations on different projects, that we would have developed our own framework for bug reporting, as we have become more comfortable navigating ADO and its features. One thing we would like to improve in future iterations is a consistent naming style, as to be able to quickly identify duplicate bugs at a glance. At times, our explanations of certain bugs seemed similar even if the bugs themselves were different. More care and attention at the bug-naming stage should be considered to provide quick navigation at-a-glance for all group members.

# How the pair testing was managed and team work/effort was divided 

We divided the exploratory testing into groups of 2 and 3 and tested the program freely for 30 minutes. We tested in a logical use fashion. System startup followed by card and PIN input, followed by checking account balances before attempting withdrawal. 

Bugs reported in the exploratory testing for version 1.0 were compared between groups and entered into Azure.

We divided the scripted test cases into segments of 8 test cases. Each team member was responsible for testing the 8 cases in version 1.0 and version 1.1. Any new bugs found were entered into Azure by the person who found them. 

We kept track of the performance of the scripted test case both if they passed or if they resulted in a bug. Following the conclusion of the regression testing on the scripted test cases, we randomly went back to determine if the remaining bugs found were resolved in the new SUT. 


# Difficulties encountered, challenges overcome, and lessons learned

## Difficulties Encountered

Difficulties encountered included:
- Unclear system functionality:
- Example 1, the select account screen displays all three account types even if the card doesn’t have access to one of the account types. It is unclear if this is a bug or performing as intended. 
![](./Example1.png)

- Example 2, in version 1.0, the available balance following a deposit was not updated to match the deposited amount. Unclear if this is a bug or working as intended. Does the bank hold deposit amounts for a period of time before allowing full access to the deposited amounts?
![](./Example2.png)

- During exploratory testing, it was at times hard to separate multiple bugs in one operation and identify what the bug actually was and to document it in a concise manner in the defect report. For example, in version 1.0 when an account was clicked for inquiry that did not belong to the customer instead of “invalid account type” the system displayed account information for a different account and displayed “unknown error” and \$500 on the screen. It was difficult to determine if the unknown error message \$500 value was one error or two and if that had any impact on the balances. 
![](./Example3.png)


## Challenges Overcome

Throughout our testing process, we encountered several challenges, which we successfully overcame through strategic planning and collaboration.
1. Identification and Documentation of Bugs: Accurately identifying and documenting bugs during exploratory testing was challenging due to the unstructured nature of this testing method. To counter this, we developed a standardized bug-reporting template and conducted group discussions and knowledge-sharing sessions on how to use it effectively. This streamlined the process, ensuring that all bugs were accurately reported and documented.
2. Interpreting Ambiguous Requirements: The ambiguity in some of the system requirements led to some initial confusions. We overcame this by conducting internal brainstorming sessions to reach a consensus on how to interpret these requirements. This proactive approach prevented potential misunderstandings and misaligned testing efforts.


## Lessons Learned
Lessons learned:
- Manual bug testing is quite tedious 
- It was easy to get lost in the exploratory bug testing. Where are we in the program? Did we actually enter the right selection?
- The system requirements need to be extremely clear and very detailed. 
- Testing one small workflow can result in multiple test cases. 
- In the exploratory testing, reproducing a bug experienced previously can be tricky if the steps are not clearly documented
- With exploratory testing it is likely that all the bugs are not caught since not all functionality is accounted for. With comparison of the pair testing defect reports there were some overlap of bugs found and there was some difference between the results. 
- Therefore to track bugs efficiently, a scripted and systematic approach is necessary keeping the requirements in mind and recording the bugs in an issue tracking system. The issue tracking system allows for bugs to be prioritized and fixed in a timely manner. 

## Comments/Feedback

This exercise was useful practice in differentiating, understanding and gaining knowledge of the different testing methods. Through execution of each testing type we were able to get practical experience in testing a software system while using an industrial defect tracking system. 
We believe that test case #37 and #39  in Appendix C are the same. However, we followed the instructions as is and created a bug report for each case as if they are different. 

Noted that we have added the test case number in the title of each bug.

Easy to follow ? 

The lab document at first glance was a bit hard to follow as there are many sections however after reading through the whole lab twice it was easier to follow. 

