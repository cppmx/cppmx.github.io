---
layout: post
title:  General Testing Principles
date:   2020-07-25 10:00:00 -0500
categories: tests
author: Carlos Colón
short: Testing is a very complex activity, here are some general testing principles.
---
## Testing shows the presence of bugs

Running a test through a software system can only show that one or more defects exist. Testing cannot show that the software is error free. Although there may be other objectives, usually the main purpose of testing is to find defects. Therefore tests should be designed to find as many defects as possible.

## Exhaustive testing is impossible

If testing finds problems, then surely you would expect more testing to find additional problems, until eventually we would have found them all. Could it be possible to test small pieces of software exhaustively, and only incorporate exhaustively tested code into large systems?

Consider a small piece of software where one can enter a password, specified to contain up to three characters, with no consecutive repeating entries. Using only western alphabetic capital letters and completing all three characters, there are 26 × 26 × 26 input permutations (not all of which will be valid). However, with a standard keyboard, there are not 26 × 26 × 26 permutations, but a much higher number, 256 × 256 × 256, or 224. Even then, the number of possibilities is higher.

- What happens if three characters are entered, and the ‘delete last character’ right arrow key removes the last two?
- Are special key combinations accepted, or do they cause system actions (Ctrl + P, for example)?
- What about entering a character, and waiting 20 minutes before entering the other two characters? 

It may be the same combination of keystrokes, but the circumstances are different. We can also include the situation where the 20-minute break occurs over the change-of-day interval. It is not possible to say whether there are any defects until all possible input combinations have been tried.

Even in this small example, there are many, many possible data combinations to attempt. The number of possible combinations using a smartphone might be significantly less, but it is still large enough to be impractical to use all of them.

## Early testing

This principle is important because, as a proposed deployment date approaches, time pressure can increase dramatically. There is a real danger that testing will be squeezed, and this is bad news if the only testing we are doing is after all the development has been completed. The earlier the testing activity is started, the longer the elapsed time available. Testers do not have to wait until software is available to test.

Studies have been done on the cost impacts of errors at the different development stages. While it is difficult to put figures on the relative costs of finding defects at different levels in the SDLC, the next table does concentrate the mind!

|Stage eror is found|Comparative cost|
|-------------------|----------------|
|Requirements|$1|
|Coding|$10|
|Program testing|$100|
|System testing|$1,000|
|User acceptance testing|$10,000|
|Live running|$100,000|

This is known as the cost escalation model. **The earlier a problem (defect) is found, the less it costs to fix.**

The objectives of various stages of testing can be different. For example, in the review processes, we may focus on whether the documents are consistent and no errors have been introduced when the documents were produced. Other stages of testing can have other objectives. The important point is that testing has defined objectives.

One of the drivers behind the push to Agile development methodologies is to enable testing to be incorporated throughout the software build process. This is nothing more than the ‘early testing’ principle.

## Defect clustering

Problems do occur in software. It is a fact. Once testing has identified (most of) the defects in a particular application, it is at first surprising that the spread of defects is not uniform. In a large application, it is often a small number of modules that exhibit the majority of the problems. This can be for a variety of reasons, some of which are:

- System complexity.
- Volatile code.
- The effects of change on change.
- Development staff experience.
- Development staff inexperience.

This is the application of the Pareto principle to software testing: approximately 80 per cent of the problems are found in about 20 per cent of the modules. It is useful if testing activity reflects this spread of defects, and targets areas of the application under test where a high proportion of defects can be found. However, it must be remembered that testing should not concentrate exclusively on these parts. There may be fewer defects in the remaining code, but testers still need to search diligently for them.

## The pesticide paradox

**Running the same set of tests continually will not continue to find new defects.** Developers will soon know that the test team always tests the boundaries of conditions, for example, so they will test these conditions before the software is delivered. This does not make defects elsewhere in the code less likely, so continuing to use the same test set will result in decreasing effectiveness of the tests. Using other techniques will find different defects.

## Testing is context dependent

Different testing is necessary in different circumstances. A website where information can merely be viewed will be tested in a different way to an ecommerce site, where goods can be bought using credit/debit cards. We need to test an air traffic control system with more rigour than an application for calculating the length of a mortgage.

## Absence of errors fallacy

Software with no known errors is not necessarily ready to be shipped. Does the application under test match up to the users’ expectations of it? The fact that no defects are outstanding is not a good reason to ship the software.

___
Reference:
- *Software Testing - An ISTQB-BCS Certified Tester Foundation guide 3rd edition 2015, Brian Hambling (editor), accessed 25 July 2020, <https://learning.oreilly.com/library/view/software-testing-/9781780172996/>.*