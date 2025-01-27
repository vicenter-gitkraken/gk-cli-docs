---

title: GitKraken CLI
description: Learn how to work with the GitKraken CLI
taxonomy:
    category: cli

---

`gk` is GitKraken on the command line. It makes working across multiple repos easier with Workspaces, provides access to pull requests and issues from multiple services (GitHub, GitLab, Bitbucket, etc.), and seamlessly connects with [GitKraken Client](https://www.gitkraken.com/git-client) and [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) in VS Code to visualize `git` information when you need it.

<img src="/wp-content/uploads/cli-gk.png" class="img-responsive center img-bordered">

GitKraken CLI is available on macOS, Windows and Unix systems.

<div class='callout callout--basic'>
   	<p>Note: GitKraken CLI is currently a preview.</p>
</div>

***

## Documentation

Check out the [installation instructions](/gitkraken-client/gitkraken-cli/#Installation) and [examples](/gitkraken-client/gitkraken-cli/#Examples) below. For command usage [see the docs](https://gitkraken.github.io/gk-cli/).

***

## Installation

### macOS 

`gk` is available from [Homebrew](https://brew.sh/) and [MacPorts](https://www.macports.org/) with the following command:

Homebrew:

```
brew install gitkraken-cli
```

MacPorts:

```
sudo port install gk
```

Or download it from the [releases page](https://github.com/gitkraken/gk-cli/releases/latest) and add it to your binaries folder:

```
mv ~/Downloads/gk /usr/local/bin/gk
``` 

### Unix

`gk` is available as a downloadable binary from the [releases page](https://github.com/gitkraken/gk-cli/releases/latest). Once you have it, add it to your binaries folder:

```
mv ~/Downloads/gk /usr/local/bin/gk
``` 

You can also [download](https://github.com/gitkraken/gk-cli/releases/latest) your corresponding package (`.dev`, `.rpm`) and install it with:

```
sudo apt install ./gk.deb
```

or 

```
sudo rpm -i ./gk.rpm
```

### Windows

`gk` is available from [Winget](https://github.com/microsoft/winget-cli) with the following command:

```
winget install gitkraken.cli
```

You can also download it using [Chocolately](https://community.chocolatey.org/packages/GKCLI):

```
choco install gkcli --version=1.0.7
```

Or download the binary from the [releases page](https://github.com/gitkraken/gk-cli/releases/latest) and place the `gk.exe` in a desired folder. Then edit your environment variables to add it to your PATH.

1. In Search, search for **Environment Variables**.
2. Click on the **Edit the system environment variables** result.
3. In the modal, click on the **Environment Variables...** button.
4. In the **System Variables** section, scroll until you find the **PATH** variable. Click on it.
    - If it doesn't exist, create a variable with the name **PATH**. 
5. Add the path to the `gk` binary at the end.

***

## Examples

### Create Workspaces to group repos

```
gk ws create
```

GitKraken workspaces associate groups of repos and set the context for helpful commands that can operate on, or get information for, multiple repos at once. There are two types of workspaces:

#### Local
Local Workspaces exist only on your machine.

#### Cloud
Cloud Workspaces are accessible on any machine, and can be connected to hosting and issue providers like GitHub and GitLab to get additional information about pull requests and issues. Share Cloud Workspaces with your team to improve onboarding with the ability to clone all repos at once. To enable this extra functionality, Cloud Workspaces require a free GitKraken account. We are continuing to evolve and improve GitKraken Workspaces and welcome any feedback.

<img src="/wp-content/uploads/cli-ws-create.png" class="img-responsive center img-bordered">

### Adding and locating repos

```
gk ws add-repo
```

This will add a new repo to a workspace either by path or remote URL.

```
gk ws locate
```

If you're accessing a Cloud Workspace for the first time, you might need to `locate` the local repos on your machine. Run this command in the directory where youre repos are located so `gk` knows where they are.

```
gk ws clone
```

You can also `clone` all repos in a Workspace at once into a single directory. This is helpful for onboarding when your team works on multiple repos.

### Perform `git` actions on multiple repos at once

```
gk ws [action]
```

In any workspace, you can perform `git` operations like `fetch`, `pull`, `push`, and `checkout` across all repos in the workspace.

### Get pull requests and issues

```
gk provider add
```

Before fetching pull requests and issues, ensure that you have the appropriate provider (GitHub, GitLab, etc.) connected. This will open a browser to authenticate.

```
gk pr list
```

When a Cloud Workspace has a provider connected, you can list all pull requests and issues for repos in the workspace, and view details for a specific one.

<img src="/wp-content/uploads/cli-pr-list.png" class="img-responsive center img-bordered">

```
gk pr view
```

Returns a list of all pull requests for all repos in a workspace. Type to search for a specific pull request and press `enter` to view details.

<img src="/wp-content/uploads/cli-pr-view.png" class="img-responsive center img-bordered">

### Pull Request Insights

```
gk ws insights
```

See the following metrics for all repositories in a Cloud Workspace. The default time period is 7 days, but can be increased to 14 days with any paid GitKraken license.
- Average Cycle Time
- Average Throughput
- Merge Rate
- Opened Pull Requests
- Merged Pull Requests
- Closed Pull Requests

<img src="/wp-content/uploads/cli-ws-insights.png" class="img-responsive center img-bordered">

### Visual Commit Graph

```
gk ws graph
```

Open a visual graph of the repo in your current directory in either [GitKraken Client](https://www.gitkraken.com/git-client) or [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) in VS Code.

<img src='/wp-content/uploads/cli-gk-graph.gif' class='img-bordered img-responsive center'>
