# Recommended Practices for the Continuous Improvement of Software Delivery in ESDC

Published: _This document is currently a draft_  
Updated: September 19, 2019 (by: [@gocGrabinski](https://github.com/gocGrabinski), [@jeanbenoitrochon](https://github.com/jeanbenoitrochon))

## Purpose of this living document.

The purpose of this document is to identify and recommended practices and behaviors that all software development teams can adopt to improve software delivery performance in ESDC. This document is intended to be a living document that is continuously revised as development teams adopt and experiment with these recommendations.

## Software Delivery Performance Metrics

All practices and behaviors identified in this document are focused on improving performance in these four software delivery metrics ( Nicole Forsgren,  Jez Humble,  Gene Kim (March 27, 2018). _Accelerate_. Retrieved from ["https://itrevolution.com/book/accelerate/"](https://itrevolution.com/book/accelerate/)):
1. Improve production deployment frequencies.
2. Improve the time between commit of code to that code successfully running in production.
3. Improve the time to restore a service after an incident that impacts users.
4. Reduce the percentage of incidents or degraded service after changes/deployments to production.

## Software Delivery Performance Objectives
The initial objective is to put in place behaviors and practice that will enable ESDC to reach a "medium" level of Software Delivery Performance. More specifically:
1. Improve production deployment frequencies *to between once per week and once per month for all IITB products*.
2. Improve the time between commit of code to that code successfully running in production *to between one week and one month for all IITB products*.
3. Improve the time to restore a service after an incident that impacts users *to less than one day for all IITB products*.
4. Reduce the percentage of incidents or degraded service after changes/deployments to production *to between 0 and 15% for all IITB products*.

The ulitmate goal is to achieve a culture of continuous improvement in software devlivery within ESDC which would enable the department to achieve and surpass these initial objectives.

---
## Recommended Practices and Behaviours

* [Use Git Based Version Control](RecommendationGitForVersionControl.md)
* [Use Git Based Collaborative Development Environment](RecommendationGitBasedCollaborativeDevelopmentEnvironment.md)