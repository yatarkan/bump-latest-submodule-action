# Bump Latest Submodule

A GitHub Action to bump latest submodule changes triggered by comment in pull request.

## Prerequisites

 - Repository with a submodule
 - Opened pull request with changes
 - :warning: Repository secrect with name `ACTIONS_PAT` - private access token (PAT) should be created and configured in repository settings. For more information, see [Creating a personal access token](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token) and [Creating encrypted secrets for a repository](https://docs.github.com/en/actions/reference/encrypted-secrets#creating-encrypted-secrets-for-a-repository).

## Usage

To trigger action you need to add a commen to opened pull request with the command.
This command has the following syntax:
```
/bump:{submodule_path}:{bump_branch}
```

#### Command parameters
Parameter | Explanation
--|--
`submodule_path` | **Required**. Path to the submodule in main repository
`bump_branch` | _Optional_. Branch in the submodule to checkout and rebase to. Default is `master`

### Examples

#### Run command **without** explicit bump branch
 ```
 /bump:client
 ```
    
 ![image](https://user-images.githubusercontent.com/41733560/110045907-79de3100-7d5c-11eb-8497-7689e0b238b1.png)

 This command will fetch the latest code changes in the host repository, navigate to `client` submodule directory, rebase **default** (`master`) branch, commit and push submodule changes to the host repository.

#### Run command with custom bump branch
 ```   
 /bump:client:main
 ```   

 ![image](https://user-images.githubusercontent.com/41733560/110046306-d7727d80-7d5c-11eb-9e3a-9bb8a05f9f7d.png)

 This command will fetch the latest code changes in the host repository, navigate to `client` submodule directory, rebase **custom** (`main`) branch, commit and push submodule changes to the host repository.

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
