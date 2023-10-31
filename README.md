# tgui-builder
A GitHub workflow which builds tgui from a selected repository on-demand.

## Usage
"Builder Repository" refers to this or a fork of this repository. "Paracode Repository" refers to a fork of the Paradise repository

1. Fork this repository
1. Configure the default Paracode repository by adding a repository environment variable(Settings > Secrets and variables > Actions > Variables) to the builder repository with the name `DEFAULT_REPOSITORY` in the format `Username/Paradise`. For example, `Arthri/Paradise`
1. Generate a new SSH public-private key pair. A guide is available at https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key. Do not set a passphrase on the key. Do not add the generated key to ssh-agent unless desired.
1. Add the public key as a deploy key(Settings > Deploy keys) to the Paracode repository. Give the key write access
1. Add the private key as a repository secret(Settings > Secrets and variables > Actions) to the builder repository with the name `REPOSITORY_SSH_KEY`
1. Go to the Actions tab, select the "Build tgui" workflow from the left panel, and initiate a run
