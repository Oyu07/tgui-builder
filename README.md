# tgui-builder
A GitHub workflow which builds tgui from a selected repository on-demand.

## Usage
"Builder Repository" refers to this or a fork of this repository. "Paracode Repository" refers to a fork of the Paradise repository

1. Fork this repository
1. Configure the default Paracode repository by adding a repository variable(Settings > Secrets and variables > Actions > Variables) to the builder repository with the name `DEFAULT_REPOSITORY` in the format `Username/Paradise`. For example, `Arthri/Paradise`
1. Pick and implement one authentication method
1. Go to the Actions tab, select the "Build tgui" workflow from the left panel, and initiate a run

### Authentication

#### Deploy Keys (SSH Keys)
1. Generate a new SSH public-private key pair. A guide is available at https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key. Do not set a passphrase on the key. Do not add the generated key to ssh-agent unless desired.
1. Add the public key as a deploy key(Settings > Deploy keys) to the Paracode repository. Give the key write access
1. Add the private key as a repository secret(Settings > Secrets and variables > Actions) to the builder repository with the name `REPOSITORY_SSH_KEY`

#### Personal Access Token (PAT)
1. Go to https://github.com/settings/personal-access-tokens/new and create a new PAT
1. Limit the PAT's access to the Paracode repository
1. Under "Repository permissions", give the PAT write access to the repository's contents(pull/push permissions)
1. Add the PAT as a repository secret(Settings > Secrets and variables > Actions) to the builder repository with the name `REPOSITORY_TOKEN`

### Custom Username and Email
By default, the commit is created by the user "tgui builder" with the email `41898282+github-actions[bot]@users.noreply.github.com`. The email can be changed by creating a repository variable(Settings > Secrets and variables > Actions > Variables) with the name `GIT_EMAIL`, while the username can be changed by creating a repository variable with the name `GIT_USERNAME`
