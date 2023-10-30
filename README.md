# tgui-builder
A GitHub workflow which builds tgui from a selected repository on-demand.

## Usage
1. Fork the repository
1. Configure the default repository by adding a repository environment variable with the name `DEFAULT_REPOSITORY`
1. Create a deploy key with write access in the default repository
1. Add a repository secret with the name `REPOSITORY_SSH_KEY` and set its value to the deploy key created earlier
1. Go to the Actions tab and initiate a build
