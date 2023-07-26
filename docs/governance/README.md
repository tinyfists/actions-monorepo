# Managing repository access, pull request assignment, and code ownership using nested GitHub teams

Monorepos create an additional challenge regarding permissions and governance as general and microservice-specific concerns must be addressed.

`actions-monorepo` has been designed to leverage [nested teams](https://docs.github.com/en/enterprise-cloud@latest/organizations/organizing-members-into-teams/about-teams#nested-teams) to easily onboard users in multiple ways:

- using parent team to assign default pull request reviewers and require code reviews
- using per-microservice child teams to assign microservice-specific pull request reviewers and require code reviews
- granting repository access through membership in parent or child teams

![Screenshot of pull request limited to microservice-specific changes and reviewers](nested_teams_pr.png)

## How does it work

1. Create parent team with children teams for monorepo and microservices

   ![Screenshot of organization teams for monorepo and microservices as parent and children teams](design_nested_teams.png)

1. Grant `write` repository permissions to parent team

1. Commit code owners file, specifying parent team as default owner, overriding it with children teams per microservice

   ```codeowners
   # Each line is a file pattern followed by one or more owners.
   
   # These owners will be the default owners for everything in the repo.
   # Unless a later match takes precedence, @actions-monorepo will be requested for review when someone opens a pull request.
   
   * @tinyfists/actions-monorepo
   
   
   # Teams can be specified as code owners as well.
   # Teams should be identified in the format @org/team-name.
   # Teams must have explicit write access to the repository.
   
   /microservices/a/ @tinyfists/actions-monorepo-microservice-a
   /microservices/b/ @tinyfists/actions-monorepo-microservice-b
   /microservices/c/ @tinyfists/actions-monorepo-microservice-c
   /microservices/d/ @tinyfists/actions-monorepo-microservice-d
   ```

   For complete example, see [`/CODEOWNERS`](https://github.com/tinyfists/actions-monorepo/blob/bfca31c9cd800cb0351621d9aae79cad69da0d3d/CODEOWNERS)

1. Create or update [ruleset](https://docs.github.com/en/enterprise-cloud@latest/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets) or [branch protection rule](https://docs.github.com/en/enterprise-cloud@latest/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule) with **Require a pull request before merging** including:
   - Require approvals
   - Require review from Code Owners

   ![Screenshot of branch protection rule requiring pull requests and code owners reviews](design_nested_teams_rule.png)
