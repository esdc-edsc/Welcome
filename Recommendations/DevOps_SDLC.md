# DevOps SDLC 
Dev-Sec-Ops Software Development Life Cycle

## Expected Development Team Behaviours in a DevOps SDLC

These tables lists a set of expected behaviors for development teams for each stage of a Dev-Sec-Ops software development life cycle.
This is not an exhaustive list but it gives an indication of the many behaviors a development team needs to demonstrate in a Dev-Sec-Ops culture. 

The establishment and implementation of Dev-Sec-Ops key performance indicators (DSO KPIs) will help development teams identify in what behaviors they need improvement as they move to Dev-Sec-Ops.
The Communities of Practice and/or the Centres of Excellence should establish and maintain standard DSO KPI’s for the identified behaviours.

To achieve a Dev-Sec-Ops culture development teams must demonstrate self-sufficiency in all of these behaviors.

## Stages

### All Stages

#### Continous Improvement

Implement Dev-Sec-Ops key performance indicators to help identify areas where development team can improve.

Accept that team failures will occur.
Teams will learn from failures to Continuously Improve development processes and practices in all stages of Dev-Sec-Ops software development life cycle.

Share lessons learned with Communities of Practice so that other development teams can benefit.

> Involves: all CoPs & CoEs

#### Work in the open

Make source code repositories, task boards, build pipeline dashboards, non-sensitive production-monitoring data available (readable) to all of IITB (ESDC?). 

Source code is open by default.
Justification is required if parts of the code is to be made inaccessible.

Will help the entire organization identify and address issues, bottlenecks in IT processes and procedures.

Allows teams, communities of practice, and centres of excellence to see how other teams have addressed common issues.

> Involves: all CoPs & CoEs

### Plan

#### Define expected outcomes for Sprint/Iteration

Select existing or newly defined backlog items.

Define/refine User stories, Acceptance Criteria and Work tasks to complete in this iteration.

Target 20% of Sprint/Iteration tasks for reduction of any technical debt. 
Technical debt reflects the implied cost of additional rework caused by choosing an easy solution now instead of using a better approach that would take longer. 

**Artifacts**
* Sprint/Iteration Acceptance criteria;
* Product backlog;
* Product technical debt backlog;

> Involves: *Agile Practices (?)*

#### Threat Modeling
Rapid Risk Assessment.
A 30-minute exercise at beginning of Sprint/Iteration.

Identify and address security concerns as early as possible.

**Artifacts** 
* Risk Assessment document

> Involves: IT Security

#### Accessibility and Usability Modeling

User interface prototype: layout, behaviour and navigation.

Identify and address any accessibility and usability issues/concerns as early as possible.

> Involves: Testing & Accessibility

### Code

#### Development Standards

Formatting Standards;
Implement departmental standards for Code “Linting”;
Appropriate variable scoping;
Secrets management;
Adopt Git branching / versioning best practices;

**Artifacts**
* Versioned source code
* Versioned Automated Test/Pipeline Scripts
* Versioned Infrastructure as Code

> Involves: Developer

#### Unit Testing

Apply unit testing methodology, such as Test Driven Development (TDD)

**Artifacts**
* Versioned Unit tests

> Involves: Developer

#### Test Data Management

Test data for each scenario of the code coverage. i.e.: Input and expected results

**Artifacts**
* Test data
* SQL ( DDL, DML) scripts

> Involves: Testing, Storage/Database (CDO?)

#### Continuous Integration

Practice of merging all coder working copies to a shared mainline several times a day.

Encourage coders to work with smaller changes so that integration issues are more easily debugged. 

**Artifacts**
* Pull request history;
* Branch (coder working copy) history;
* Integrated mainline branch;

> Involves: Developer

#### Automated Static Code Analysis

Goal is to keep it fast. 
Shallow scans on code check-in, deeper scans nightly/weekly.

**Artifacts**
* Static Code Analysis log/results.

> Involves: IT Security

#### Code Review

Initiated on shared mainline merge request. (Git pull request)

Encourage coders to work with smaller changes to keep reviews effective. 
The effectiveness of code reviews depend on the speed of reviewing. 

**Artifacts**
* Code reviewer comments;
* Mainline merge history;

> Involves: Developer

### Build & Test

### Release (Staging)

### Deploy

### Operate & Monitor

## DEV-SEC-OPS Development Team Composition

In a Dev-Sec-Ops culture, development teams are responsible for the planning, development, operation and maintenance of reliable, secure and accessible software that the team produces.

Development team size should be small, between five to twelve members. 
Keeping teams small reduces the occurrence of internal team communications errors/bottlenecks. 

All members of these small teams are required to have a solid knowledge of all aspects of their software products Dev-Sec-Ops life cycles.
This ‘end-to-end’ team responsibility will require that development team members develop cross-functional skills (development, testing, security, operations) so that the development team is self-sufficient in all stages of the Dev-Sec-Ops life cycle.

It is important to note that the level of knowledge for various Dev-Sec-Ops skills will vary on a team-by-team basis. 
For example, a team who’s’ products are base on cloud Platform as a service offerings will need less in depth operational skills than a team who’s products require more cloud Infrastructure as a service.

To help teams develop the cross-functional skills required for Dev-Sec-Ops teams will designate one or more team members as ‘Team Champion’ for specific skills required by the team.

### Team Champions

A Team Champion’s role is to:
* Be a coach for other team members as they gain new cross-functional skills.
* Be an active participant in respective Community of Practice – sharing team experiences and learning new practices in specific skill areas to bring back to their team.
*	Provide guidance to team members on where to find resources related to specific skills.  
I.e. Online learning, Available training, Community of Practice resources.

A Team Champion is not:
*	To be the only team member with a specific skill set on a Dev-Sec-Ops team.
*	Expected to take on all team tasks related to the specific skill for which they are the champion.
*	The only champion of all skillsets on a team.

When the Team Champion’s find that their teams coaching requirements are beyond their current capabilities they can:
1. Reach out to the community of practice to see if other teams can provide coaching/guidance
2.	Ask the Centre of Excellence for coaching from a subject matter expert resource.


