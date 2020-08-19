---
layout: post
title: Testing - Who does what?
date: 2020-07-24 09:00:00 -0500
short: Do you know who is responsible for doing the tests? Read this post to find out.
author: Carlos Colón
categories: tests
---
So we have Unit Testing, Integration Testing, System Testing and User Acceptance Testing. Of these, the Unit Testing is primarily the responsibility of the Development team. While Integration Testing has a shared responsibility between developers and testers. The term test level serves to indicate the focus of testing and the typical problems uncovered.

## Unit or Component or Module testing
A unit or component is the smallest block of code that can be independently executed. And testing this Unit or program is usually done by the author or developer of the code. This testing is called Unit Testing. It can also be called Component or Module testing. The Program specification forms the basis for the tests and expected results.

The focus at this level is to find out if the code does what it is intended to do. So functional tests are first conducted. This can be followed by other test types like non-functional and coverage measures. Defects found will be fixed by the developer and not typically logged into any defect tracking system. So tests related to changes are conducted as well.

## Integration Testing
The next step is to put together these individual independent pieces of code together. This is called Integration and the individual components can be put together in one shot or they can be joined one by one. A decision on how to put the pieces together is called the Integration Strategy. If done together in one shot, it is called Big Bang. If they are joined one by one, it can be done in two ways – the Top Down Integration, Bottom Up Integration.

The test objective during this phase, is to verify if the interactions between the modules are working correctly. This includes checking for data flows and control flows between the modules.

The Technical Specification forms the basis from which the tests and expected results are derived. Defects at this level may or may not be logged in the Defect Tracking System.

When Integration testing happens before System testing, it is called Component Integration or Integration testing.

Integration testing can also be conducted across multiple applications, after each application has undergone system testing eg. a Trading Exchange with multiple platforms. This testing conducted by testers is called the System Integration testing.