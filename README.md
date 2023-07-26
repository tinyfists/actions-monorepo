# actions-monorepo

Monorepos have all the same SDLC requirements as smaller repositories, just on a larger scale and all in one place:

- branching and releasing
- CI/CD automation
- governance

This repository highlights specific challenges and approaches to how to address them.

## Challenges

1. [**Simplifying required status checks by standardizing workflow jobs across microservices workflows**](required_status_checks/)

   ![Screenshot of required status checks fulfilled for all microservices within GitHub pull request](required_status_checks/required_status_checks_pr.png)

1. [**Managing repository access, pull request assignment, and code ownership using nested GitHub teams**](governance/)

   ![Screenshot of pull request limited to microservice-specific changes and reviewers](governance/nested_teams_pr.png)

## Resources

- [GitHub _"Maintaining a Monorepo"_](https://monorepo-book.github.io/)
- [GitHub Blog](https://github.blog//)
  - [`git` articles](https://github.blog/tag/git/)
  - [`monorepo` articles](https://github.blog/tag/monorepo/)
- [`microsoft/scalar`](https://github.com/microsoft/scalar)
  - [GitHub Blog _"The Story of Scalar"_](https://github.blog/2022-10-13-the-story-of-scalar/)
  - [Microsoft Blog _"Introducing Scalar: Git at scale for everyone"_](https://devblogs.microsoft.com/devops/introducing-scalar/)
  - [Git `scalar` man page](https://git-scm.com/docs/scalar)
- Videos
  - [Youtube _"The future of git at scale"_](https://www.youtube.com/watch?v=pXdabSCz4JA)
  - [Youtube _"Optimize your monorepo experience - GitHub Universe 2020"_](https://www.youtube.com/watch?v=RcqLV1lU408&t=15s)
  - [Youtube _"500,000 files and counting - Git tooling for monorepos at Canva - Git Merge 2022"_](https://www.youtube.com/watch?v=W4ACKyaVHzM)
  - [Youtube _"Monorepo Spring Cleaning [Workshop] - Git Merge 2022"_](https://www.youtube.com/watch?v=GQW4tDLu_BM&t=543s)
  - [Youtube _"Improving git status performance in Uber's Go monorepo - Git Merge 2022"_](https://www.youtube.com/watch?v=5xGc3UlsQHQ)
  - [Youtube _"From Monorail to Monorepo: Airbnb's journey into microservices - GitHub Universe 2018"_](https://www.youtube.com/watch?v=47VOcGGm6aU)
- [`korfuri/awesome-monorepo`](https://github.com/korfuri/awesome-monorepo)
