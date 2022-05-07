# Flower Girl Project 
#### Supervised by: Mr. Vincent Leclère
#### Course: Stochastic Optimization.
#### Programming Language: Julia 1.6.4
Multi-stage Stochastic Program Project

## Introducation 
Assume that every morning you can buy some flower at cost ***c***, during the day you can sell them at price ***p***. At the end of the day you can keep the flowers for the next day. During each day the demand is an integer uniformly taken between ***1*** and ***D***.

At the start of your first day you have no flower in stock. At the end of the ***Tth*** day all stock is lost. You want to minimize your expected loss summed over the ***T*** days. We will denote ***u_t*** the number of flower bought at the beginning of day ***t***. We assume that ***u_t*** in ***[0,U]*** (in particular we assume that it is continuous).

## Question 1: The *T = 1* Case 
### Question 1.1 : Recognizing a known problem
If ***T=1***, recognize the flower girl problem as a known optimization problem? 
### Question 1.2 : Solving the problem

Write the extensive formulation of the problem as an LP and solve it using `JuMP` and a linear solver.
## Question 2 The *T = 2* Case
### Question 2.1 
From Question 1 deduce an upper bound to this problem.
### Question 2.2 : Upper bound
Solve the flower-girl problem with a stochastic programming approach, by solving the associated extensive formulation.
### Question 2.3 : Splitted variables formulation

We give the flower-girl problem for ***2*** time step with splitted variables. Check that you obtain the same value as before.  
### Question 2.4 : Anticipative bound

By suppressing constraints in the splitted version, find the lower-bound given by the anticipative approach.
### Question 2.5 : Two-Stage bound

By suppressing constraints in the splitted version, find the lower-bound given by the 2 stage-approach.
## Question 3 : Heuristics and bounds in long horizon

We assume now that we work on a week, that is ***T=10***. 

### Question 3.1  
How many variables have the extended formulation? 
### Question 3.2 : Anticipative bound

Estimate (by Monte Carlo) the lower-bound given by the anticipative approach.
### Question 3.3 Writing a simulator

Write a simulator that evaluate a policy over a given set of scenarios.

A policy is a function taking as argument ***(t,x)***, ***t*** being the day, ***x*** the amount of newspaper in stock at the beginning of day ***t*** and return ***u*** the quantity of newspaper bought in the morning of day ***t***. The quantity of newspaper sold during day ***t*** will be computed as ***min(x+u,d)***.
### Question 3.4

Evaluate the heuristic consisting in buying the same amount ***u*** of flower everyday, for ***u = 0..m***, and give an upper bound to the problem.
### Question 3.5

Evaluate (by Monte Carlo) a model predictive approach of the problem using the expectation of demand as prediction. Compare it with using the best constant ***u***.
### Question 3.6 

Give an estimated lower bound obtained from a two-stage approximation. 
### Question 3.7 (Optional) 

Evaluate the repeated two-stage approach (start with a small amount of scenarios).
## Question 4 Dynamic Programming


### Question 4.1 : Integrity of stock
Show that the optimal stock at the end of day is integer and no more than ***D***.
### Question 4.2 
How many operations are required to solve the problem by Dynamic Programming? How many scenarios for an extended formulation?
### Question 4.3
Find the optimal value of the flower-girl problem by Dynamic Programming. Describe the optimal strategy.
### Question 4.4

Using function 'simulator' from Q3.3 check that the strategy computed in Q4.3 yield the optimal value also computed in Q4.3.

