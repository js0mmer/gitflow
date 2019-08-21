# gitflow

Team Names: Megan Ngai, Jacob Sommer, Anika Surapaneni

Name of Workflow: Gitflow

## Description of Basic Git workflow
Basic git workflow is making commits to master. No branches are used. This is a big problem when working in large groups.

## Description of Gitflow workflow
The majority of the development happens on the develop branch. Features are created as branches of the develop branch. They are later merged into the develop branch. A release branch is created off of a development branch after it is mostly ready and bug free. Any last bug fixes happen on the release branch. The release branch is then merged into the master branch and the develop branch. The master branch can then be deployed. If any severe bugs are found in production, a hotfix branch is created off of the master and fixes are applied to it. The hotfix branch is then merged back into the master branch and can be deployed again. The process continues. The only commits ever made to the master branch are merges from the release branch or the hotfix branch.

## Key Differences from basic workflow, and key use cases
Gitflow utilizes many branches to allow multiple features to be developed at once and to make sure code is thoroughly tested and reviewed before being deployed to production. This workflow would work great for a large project by a company being worked on many people.

Link to your Git example repository: [https://github.com/js0mmer/gitflow](https://github.com/js0mmer/gitflow)

## Diagram or Diagrams of workflow
![Workflow diagram](https://miro.medium.com/max/1400/1*9yJY7fyscWFUVRqnx0BM6A.png)
Retrieved from https://miro.medium.com/max/1400/1*9yJY7fyscWFUVRqnx0BM6A.png


## Documentation of git commands used, and annotated sample sequence of commands used in creating your repository
1. Clone the repository
`$ git clone https://github.com/js0mmer/gitflow`

1. Change into its directory
`$ cd gitflow`

1. Create the develop branch
`$ git branch develop`

1. Create the feature branch and switch over to it
`$ git branch feature-1 && git checkout feature-1`

1. Add all files to the staging area
`$ git add .`

1. Commit changes to feature branch
`$ git commit -m "Add feature-1"`

1. Add all files to staging area after making further changes at a later date
`$ git add .`

1. Commit new changes to feature branch
`$ git commit -m "More work to feature-1"`

1. Push changes to origin
`$ git push origin feature-1`

1. Switch to the develop branch
`$ git checkout develop`

1. Merge the feature-1 branch
`$ git merge feature-1`

1. Push changes made to develop branch to the origin
`$ git push origin develop`

1. Create release branch and switch to it
`$ git checkout -b release/0.1.0`

1. Add changes to staging area after testing
`$ git add .`

1. Commit bug fixes
`$ git commit -m "Bug fixes"`

1. Push release branch to origin
`$ git push origin release/0.1.0`

1. Switch to master branch
`$ git checkout master`

1. Merge release branch into master
`$ git merge release/0.1.0`

1. Push master branch to origin
`$ git push origin master`

1. Switch to development branch
`$ git checkout develop`

1. Merge release branch into develop
`$ git merge release/0.1.0`

1. Push develop branch to origin
`$ git push origin develop`

1. Switch to master branch
`$ git checkout master`

1. Create and switch to hotfix branch
`$ git checkout -b hotfix/0.1.1`

1. Stage changes made to files
`$ git add .`

1. Commit changes
`$ git commit -m "Severe bug hotfix - v0.1.1"`

1. Push branch to origin
`$ git push origin hotfix/0.1.1`

1. Switch to master branch
`$ git checkout master`

1. Merge release branch into master
`$ git merge hotfix/0.1.1`

1. Push master branch to origin
`$ git push origin master`

1. Switch to development branch
`$ git checkout develop`

1. Merge hotfix branch into develop
`$ git merge hotfix/0.1.1`

1. Push develop branch to origin
`$ git push origin develop`