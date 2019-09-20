# Recommendation: Use Git Based Version Control

Git is an open source distributed version control system. It is designed for coordination of work among developers with a focus on speed, data integrity and non-linear workflows ( branching ).

## Benefits

* Each developer has a local copy of the full development history which makes Git fast as all commits, diffs and retrival of previous versions is done locally.  It also means that the full code repository is backed up on every developer's machine.

* Git branches are very light weight allowing for rapid branching and merging of changes to code. This enables developers to [work with smaller changes and short lived branches]() that can be merged into mainline branches more frequently. "Branch early, branch often" is a common Git user mantra.

* For security and auditing purposes Git history is implemented in such a way that each commit ID is dependent on the previous commit history making it impossible to change previous versions without detection. *TODO: add links or refrences to any audit/release control points that are addressed*


## Related Recommendations

* [Implement Pull Request Base Code Review](#)
* [Use Git Based Collaborative Development Environment](RecommendationGitBasedCollaborativeDevelopmentEnvironment.md)
* [Work with smaller changes and short lived branches](#)