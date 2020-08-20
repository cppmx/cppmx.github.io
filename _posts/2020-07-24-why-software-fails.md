---
layout: post
title: Why Software Fails
date: 2020-07-24 10:00:00 -0500
short: Examples of software failure are depressingly common. Here are some you may recognise.
author: Carlos Colón
categories: tests
tags: testing,software,devops
---
- After successful test flights and air worthiness accreditation, problems arose in the manufacture of the Airbus A380 aircraft. Assembly of the large subparts into the completed aircraft revealed enormous cabling and wiring problems. The wiring of large subparts could not be joined together. It has been estimated that the direct or indirect costs of rectification were $6.1 billion. (Note: this problem was quickly fixed and the aircraft entered into service within 18 months of the cabling difficulties being identified.)

- When the UK Government introduced online filing of tax returns, a user could sometimes see the amount that a previous user earned. This was regardless of the physical location of the two applicants.

- In November 2005, information on the UK’s top 10 wanted criminals was displayed on a website. The publication of this information was described in newspapers and on morning radio and television and, as a result, many people attempted to access the site. The performance of the website proved inadequate under this load and it had to be taken offline. The publicity created performance peaks beyond the capacity of the website.

- A new smartphone mapping application (app) was introduced in September 2012. Among many other problems, a museum was incorrectly located in the middle of a river, and Sweden’s second city, Gothenburg, seemed to have disappeared from at least one map.

- Security breaches at the US military resulted in the payment details of many personnel (perhaps even ‘all’) being compromised, including names, addresses, email addresses and bank details.

Perhaps these examples are not the same as the notorious final payment demands for ‘zero pounds and zero pence’ of some utilities customers in the 1970s. However, what is it that still makes them so startling? Is it a sense that something fairly obvious was missed? Is it the feeling that, expensive and important as they were, the systems were allowed to enter service before they were ready? Do you think these systems were adequately tested? Obviously, they were not but in this book we want to explore why this was the case and why these kinds of failure continue to plague us.

To understand what is going on we need to start at the beginning, with the people who design systems. Do they make mistakes? Of course they do. People make mistakes because they are fallible, but there are also many pressures that make mistakes more likely. Pressures such as deadlines, complexity of systems and organisations, and changing technology all bear down on designers of systems and increase the likelihood of defects in specifications, in designs and in software code. Errors are where major system failures usually begin. An error is best thought of as ‘invisible’, or better perhaps as intangible – you cannot touch it. It is an incorrect thought, a wrong assumption, or a thing that is forgotten, or not considered. Only when something is written down can it become ‘a fault’ or a defect. So, an incorrect choice can lead to a document with a defect in it, which, if it is used to specify a component, can result in the component being faulty and this may exhibit incorrect behaviour. If this faulty component is built into a system, the system may fail. While failure is not always guaranteed, it is likely that errors in the thought processes as specifications are produced will lead to faulty components and faulty components will cause system failure.

*Extract from: Software Testing - An ISTQB-BCS Certified Tester Foundation guide 4th edition 2019, Brian Hambling, accessed 24 July 2020, <https://amzn.to/2Q2ZQsj>.*

