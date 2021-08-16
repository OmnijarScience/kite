# Contributing

## Getting Started

Before you make your changes check to see if an [issue exists](https://github.com/omnijarscience/kite/issues/) already for the change you want to make.

### Don't see your issue? Open one

If you spot something new, open an issue using a [template](https://github.com/omnijarscience/kite/issues/new/choose). We'll use the issue to have a conversation about the problem you want to fix.

### Ready to make a change? Fork the repo:

Fork using the command line:

- [Fork the repo](https://docs.github.com/en/github/getting-started-with-github/fork-a-repo#fork-an-example-repository) so that you can make your changes without affecting the original project until you're ready to merge them.

Alternatively, if you're a core contributor you can make changes using feature branches. Firstly create a branch with the `feature/<name-of-feature>` pattern. If it's a fix, rather than a feature than use `fix/<name-of-fix>` instead. This allows us to priorities milestones changes appropriately.

### Make your update:
Make your changes to the file(s) you'd like to update. 

### Testing Locally

If you want to test locally (why wouldn't you?) then it's recommended to use the official [nginx](https://nginx.org) [Docker](htts://docker.com) image.

```shell
docker run --name "kite-nginx" -v $(pwd)/publish:/usr/share/nginx/html:ro -p 8080:80 -d nginx; docker rm "kite-nginx"
```

This shell command will download (if the image is not already downloaded) the latest `nginx` image, name an instance `kite-nginx`, attach the local volume (your current working directory (PWD) `publish` folder to the image's `/usr/share/nginx/html` folder in `read-only` mode (`ro`), and open up the local 8080 port to the image's port 80, with the container instance running as a non-interactive daemon (`-d`). After you've finished with this instance it'll remove it (`rm`) to ensure you're always working with a clean instance (this is not necessary).

To access the web site locally you can simply visit `localhost:8080` in your browser of choice.

### Open a pull request
When you're done making changes and you'd like to propose them for review, use the [pull request template](#pull-request-template) to open your PR (pull request).

### Submit your PR & get it reviewed
- Once you submit your PR, others from the community will review it with you. The first thing you're going to want to do is a [self review](#self-review).
- After that, we may have questions, check back on your PR to keep up with the conversation.
- Did you have an issue, like a merge conflict? Check out our [git tutorial](https://lab.github.com/githubtraining/managing-merge-conflicts) on how to resolve merge conflicts and other issues.

### Your PR is merged!
Congratulations! 

Once your PR is merged, you will be proudly listed as a contributor in the [contributor chart](https://github.com/github/docs/graphs/contributors).

## Appendix: Getting the Code

For those wishing to get started as the first contribution to a collaborative project on [GitHub](https://github.com), the following is a step-by-step guide of how to begin.

### SSH Keys

SSH keys (or Secure SHell keys) are public and private key pairs used to access remote systems. The public key is to be shared with a remote machine (in this case we'll be sharing it with [GitHub](https://github.com)), and the private key we'll keep safely on our own machine (typically in `~/.ssh/` where `~` shortcuts the shell terminal to our home folder).

You will need to ensure you have your [SSH key configured with GitHub](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account). 

Once created and added to [GitHub](https://github.com) you'll need to add your private key to your system's keychain, e.g:

```shell
ssh-add ~/.ssh/id_rsa_gh
```

Where `id_rsa_gh` is the name of the private key generated for accessing GitHub. 


### Cloning the Repository

After you have guaranteed secure access to [GitHub](https://github.com) with your SSH key you can clone the project into a suitable folder:

```shell
git clone git@github.com:OmnijarScience/kite.git
```

Once you have the project locally you can make changes at will (see "Getting Started").