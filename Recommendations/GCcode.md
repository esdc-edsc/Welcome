# GCcode Recommendation

Published: July 10, 2018 (by: [@s-laugh](https://github.com/s-laugh))  
Updated: May 27, 2019 (by: [@s-laugh](https://github.com/s-laugh))

## Overview

### Summary

This document provides guidelines to manage the projects in ESDC that are hosted in GCcode and provide strong recommendations as to the implementation and use of the tool for these projects.
GCcode is running an instance of GitLab using the Git repository technology.
This is not a recommendation for the use of GCcode, that can be found in the [GCDevOps League Strategy - OfficalGCCodeSupport.md](https://github.com/gcdevops/strategie-devops-strategy/blob/WorkInProgress/Content/OfficalGCCodeSupport.md).

Groups using or looking to use GCcode should register their group on GCcode by opening an issue on our [ESDC Welcome project (internal)](https://gccode.ssc-spc.gc.ca/iitb-dgiit/welcome) with the appropriate issue template.

### Purpose

With the growing interest and effectiveness in the Git technology along with the platforms that run it, we need to establish a guideline for supporting how teams should make use of these tools within the department.

This recommendation is in line with the department’s attempts to modernize the development life cycle. 
It enables and encourages us to work with Continuous Integration in SADE (work in progress), testing automation, and may other modern development practices. 

### Refrences

**[Git](https://git-scm.com/)** is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

**[GCcode (internal)](https://gccode.ssc-spc.gc.ca)** is an instance of [GitLab Community Edition (CE)](https://gitlab.com/gitlab-org/gitlab-ce/) hosted by Share Services Canada (SSC) internally to the Government of Canada (GoC).

### Scope

The recommendations and guidelines in this document are inclusive to department approved applications or enterprise applications stored with GCcode. 
These recommendations and guidelines should not limit the use of GCcode for projects that would be considered as Research and Development (R&D).

## User Accounts

Each person working on the project stored in GCCode from any area (Developers, Technical Analysts, Project Leaders, Managers, Consultants, Clients, Testers, and Business Analysts) will need to create their own account on GCCode with their department email. 

## Projects

### General Settings

#### Permissions

This refers to whether your project is Public, Internal or Private.

Unless there is a specific reason to hide information the project should be public. 
If you think you have a good reason for it to be private, double check your reasoning and then consider making only the one part (Issues or Merge requests or …) of your project private.

#### Merge request settings

The Merge method you have selected should depend on the [branching model](#branches) you are using. 

If you are using the Enterprise method, your Merge method should be *Merge commit*.  
If you are using the Light method (Continuous Deployment), your Merge method should be *Fast-forward merge*.

The project should also have the following checked/enabled:

- Only allow merge requests to be merged if the pipeline
- Only allow merge requests to be merged if all discussions are resolved

### Location

Projects should never be added to a specific user, but always under a group. 
The group should be the [Team Group](#team-group) or a [Sub Group](#sub-group) of that Team Group.

### Code

All the code related to the project should be in the Repository inclusive of any build scripts. 
Secrets should not be kept in GCcode as it is not rated for protected information. 
Secrets in this case mean any hash keys, DB passwords or anything of the like.

*Note: Our version of GitLab currently only supports PostgresSQL databases. 
This database isn’t recommended for our department. 
Therefore storing a database in GitLab is not recommended; however storing stored procedures, source code and/or DDL/DML/SQL scripts in the repository may be considered if it suits your development team.*

#### Branches

There are two types of models that are recommended. 
The one that is suitable for your project depends on the type of project and how you manage your releases.

- Both models contain a *master* branch that will be protected and the default. 
  This branch is always your "source of truth" and **must be passing all tests at all times**. 
  You should never allow anyone to push directly to this branch, it should only be updated by merge requests.
- Both models also contain a *work* or *issue* branch that would be created from an Issue. 
  Use the button *Create merge request* to create a Merge Request and Branch (using the default name for the branch) from the appropriate branch to do your work. 
  These branches should be the only place you are pushing new code to. 
  These should contain relatively small changes (at most one Issue fix) or a portion of a feature. 
  You should be rebase-ing or merging down (depending on the branching model) from the associated before the associated Merge Request is assigned to another Developer for review and merging. 
- Both models allow for the use of a *feature* branch. 
  The feature branch allows for large chucks of work to be done that are not ready for a higher level branch and would take a week or more to complete. 
  You may decide to protect the feature branch.

##### Continuous Deployment model

This method should only be used for a project that is either very light weight and isn't pushing massive code changes to production and isn't likely to have as much work in parallel development. 
It is also a very effective method if the project is using Continuous Deployment.

This branching method is primarily to only ever use the *master* and *issue* branches. 
It focuses on small changes being made to production regularly meaning you don't need release branches. 
Using the feature branch may lead to issues with rebase-ing if new changes are continually pushed to master while working on the feature when the feature branch is protected.

##### GitFlow model

This method is great for managing releases and parallel development in large applications. 
It is also similar to the recommendations for TFS branching (but don't fool yourself into thinking it is exactly the same, TFS branching style won't work well in Git). 
This is the notable public model, GitFlow; documentation for that can be found here https://datasift.github.io/gitflow/IntroducingGitFlow.html.

This model makes use of the *master* and *issue* branches but also has additional branch *dev* (which should be protected). 
Other than master and dev all branches should only exist as long as they are serving a functional purpose. 
Once a feature branch has been pushed to dev, it is no longer needed. 
The same goes for any hotfix or release branch, once they have been merged to master they are no longer needed and should be deleted. 
(Remeber deleting these branches does not mean you are deleting the changes)

GitFlow can be fairly simplistic but also get very complex. 
We recommend you try to keep it as simple as possible, but don't shy away from getting complex if that is what the project requires.

#### Tags

Tags should be added for each production release attached to the merge request from the development branch to master. 
You should add your release notes to the tag.

The Tag name should be the version, the Message should in a few words indicate why this tag is needed, the release notes should reference all of the changes in that version.

**This is how you can store old production versions of your code.**

### Issues

You should use issues for tracking all changes to the project, providing good labels and names will allow you find them later. 

#### Labels

We recommend that you start with the "key" labels from [ESDC Labels project](https://gccode.ssc-spc.gc.ca/iitb-dgiit/esdc-labels) to add default labels to your project or group and add more as it helps you organize your project. 
You should have labels that identify key parts of your application. 
You should add labels to help with the flow of your team’s processes.

#### Milestones

There should be a Backlog milestone that represents "Tracking items approved for development but not yet scheduled."  
There should also be a milestone for every feature and release branch. 

### Merge Requests

- Should be created from the Issue (in GCcode) when creating your Branch
- Your merge requests should never be merged by the person who made the changes.
- The person making the merge must be reviewing the code changes and commenting on anything they don’t fully understand.
- Merge request should be between 1 and 200 line changes. (Some exceptions should be allowed)

### CI / CD

This refers to Continuous Integration and Continuous Deployment.
At this moment we are working towards enabling Continuous Integration but don’t know what it will take to get there. 
Once we have established CI we will then begin working towards CD.

Part of this solution will need to include integration with a test case management tool that will allow for reporting, automated execution of system testing tests, as well as requirements and bug traceability. 
Testing services will need to be heavily involved in finding the right tool/plugin for this. 
We have identified a few potential tools/plugins that might work but we need to look into them more and create some proof of concepts. 

### Wiki

You should use this section to store documentation about the project overview. 
Documentation that should be versioned with a release or deployment, should be stored as Markdown files in the repository. 

### Member Access

Members should be given access to the project at the lowest level required to do their job. 
The details below outline it a bit more in detail.

The Project Leader for the project should inherit Owner rights (same as Maintainer) to the project from the Group the project is in.

You may consider adding another group access to your project if the group is from another team, but works closely with your development. 
You should give that group the minimum level required for all members in that group. 
You can then give higher access to the specific people that need it.

#### Maintainer

Any Technical Advisor (CS03) that is developing on the project should be given Maintainer rights to that project. 
At the discretion of the Project Leader for that project, they can grant Maintainer rights to a Lead Project Developer. 
You should have at least one Maintainer per project.

#### Developer

Any person actively developing code for the project should be given developer rights to that project.

#### Reporter

Any person working on the project in some capacity should be given Reporter access. 
That may include, but is not limited to: Clients, Testers, Business Analysts, Project Manager, and Project Director.

#### Guest

For Private projects, any CS03 or higher that requests it, should be given guest rights to the project.  
For Public projects, everyone signed in is already a guest. 

## Groups

### Group levels

#### Organization Group

For ESDC – IITB, we have one organization group “ESDC – Innovation Information Technology Branch” https://gccode.ssc-spc.gc.ca/iitb-dgiit. 
This group is to hold all the team groups and provide minimal administrative help when needed. 
This group is managed by the Solution Design Services team. 
This is to help us determine who is using the tool at ESDC and provide assistance when needed. 
This is to enable developers in the use of the tool not restrict them.

#### Team Group

All team groups should be a sub group of the organization group. 
Groups using or looking to use GCCode should register their group on GCCode by an issue on our [ESDC Welcome project](https://gccode.ssc-spc.gc.ca/iitb-dgiit/welcome/issues/new) with the appropriate issue template.

#### Sub Group

Each team group can create sub groups to group multiple projects that are similar in nature. 
Use common sense when doing this.

### Member Access

#### Owner

There will be a minimum of two owners on your group at all times (except the organization group with one). 
One will be inherited from the organization group and the other will be the Team Leader for the team group. 
A sub group will inherit all owners.

#### Other

The minimum level required for all projects in the group. 

## Appendix

### Minimum level required example

#### Example 1

Person A is a Master for project Z and Guest for project X that are both in the same group. 
Person A should be given Guest for the Group

#### Example 2

Person B is a Developer for project X and not in project Y, which is private; both projects are in the same group. 
Person B shouldn’t have any access to the Group but should have access to project X.

#### Example 3

Person C is a Master of project X and a Developer on Project Z that are both in the same group. 
Person C should be given Developer for the Group.

### Branching example

#### Example 1

Your team is starting work on version 2.2, so from the master, create a v2.2 branch. 
There are 3 features, identified by issues 32, 33 and 34 so branches for each are created from v2.2 branch. 
But then a bug, issue 35 is found, so create a new branch off of v2.2 branch (or master if a production bug). 
Then personB finishes issue 32, creates merge request. 
Maintainers reviews and has questions, comments in the code, has discussion, finally accepts and merges. 
