# DevOps SDLC 

Dev-Sec-Ops Software Development Life Cycle

Published: _This document is currently a draft_  
Updated: April 24, 2019 (by: [@gocGrabinski](https://github.com/gocGrabinski), [@jeanbenoitrochon](https://github.com/jeanbenoitrochon))

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

#### Continuous Integration

All automated tests must pass.

Build Artifacts published to central ‘snapshot’ repository.

**Artifacts**
* Pull request history;
* Branch (coder working copy) history;
* Integrated mainline branch;
* Automated test logs;
* Snapshot build artifacts;

> Involves: Developer

#### Automated Build

The build needs to complete rapidly, to identify and address problems with integration quickly.

> Involves: Developer

#### Automated Artifact CVE Scans	

Automated build artifact scanning for CVEs. 
Will require tuning to reduce false positives.	

**Artifacts**
* Artifact repository automatically generated reports for CVE scans.	

> Involves: IT Security

#### Automated Artifact License Scans

Automated build artifact scanning for license compliance.	

**Artifacts**
* Artifact repository automatically generated reports for license compliance.

> Involves: Developer

#### Automated Smoke Test

A simplified test that ensures that build artifacts actually run and basic functionality is working before running more in depth tests.

Verify expected VMs/Containers/Services are running.

Port scans.

Connectivity tests.	

**Artifacts**
* Smoke Test log(s).	

> Involves: Testing

#### Automated Acceptance Testing	

Done during end to end testing	

**Artifacts**
* Acceptance test log(s).	

> Involves: Testing

#### Automated Accessibility Testing	

Done during end to end testing	

**Artifacts**
* Accessibility test log(s).	

> Involves: Testing & Accessibility

#### Automated Compliance Testing	

Verify that all the required test artifacts were created.	

**Artifacts**
* Compliance test results.	

> Involves: Testing

#### Automated Attack Testing (App Security  Testing)

DAST: Behavioral Driven Design from malicious actors point of view
* XSS
* SQL Injection
* SSL/TLS	

**Artifacts**
* Attack test results.	

> Involves: IT Security

### Release (Staging)

#### Deploy to Staging Environment

Deployment to a staging environment. 

#### Manual Tests

Accessibility & User Acceptance Tests

**Artifacts**
* Manual test reports/results
* Final approval before publish to Production

> Involves: Accessibility Testing

#### Publish Release Artifacts

Build Artifacts published to ‘Release’ repository.

Centralized ‘Release’ Artifact repository (or repositories) simplify CVE and License scanning/checks.

Use tags on release artifacts to link to source code.

**Artifacts**
* Release build artifacts

#### Compliance Review

Verify previous processes and procedures followed. Check ‘Audit Artifacts’. 

**Artifacts**
* Compliance Review results.

> Involves: Release Management

### Deploy

#### Automated Deployment to Production

*Manually triggered* automated deployment.

Auditability and Accountability of deployment to production

Only ‘Release’ repository artifacts deploy to production.

Deployment option examples:
*	Blue, Green
*	Canary

**Artifacts**
Deployment Audit log (Who, When, What etc.).

> Involves: Operations

#### Automated Smoke Test

A simplified test that ensures that production deployment actually runs and basic functionality is working.

**Artifacts**
* Smoke Test log(s)

> Involves: Testing

### Operate & Monitor

#### Read access for monitoring production

To support production applications development teams need access to lots of data. Examples :
*	Visibility and notifications around all application errors
* Access to centralized aggregated log files for viewing and searching
*	Basic server utilization trends and stats. (e.g. CPU, memory, etc)
*	Recording and alerting of key application metrics (KPIs)
*	Tracking of application web page load times
*	Ability to access the application database and run test queries
*	User Feedback: encourage user feedback and store it.

**Artifacts**
* Updates to product backlogs based on production monitoring data.

> Involves: Operations

#### Automated Artifact CVE Scans

Automated build artifact scanning for CVEs. 

**Artifacts**
* Artifact repository automatically generated reports for CVE scans

> Involves: IT Security

#### Automated Artifact License Scans

Automated build artifact scanning for license compliance.

**Artifacts**
* Artifact repository automatically generated reports for license compliance

> Involves: Developer

#### Attack monitoring

To properly address threats to production application development teams need access to data of what attackers are actually attempting.

**Artifacts**
* Updates to product backlogs and threat models to address attacks actually occurring in production.

> Involves: IT Security

#### Accessibility and Usability monitoring

To properly address accessibility and/or usability application development teams need access to telemetry data that gives metrics on how users are actually interacting with UI.

**Artifacts**
* Updates to product backlogs to address UI accessibility and usability concerns based on actual use in production

> Involves: Testing & Accessibility

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


