# **Welcome!**

If you’re reading this document, you’re interested in contributing to the **kraken-lib project**. Many thanks for that! We welcome all types of contributions. So please feel free to share ideas, documentation, code, patches, bug reports, feature requests and more. And you don’t need to be a programmer to speak up.

# **Workflows**

This section explains how to perform common activities, such as reporting a bug or merging a pull request.

## **Reporting bugs**

To report a bug, [open an issue](https://github.com/samsung-cnct/k2/issues) and summarize the bug. If you’ve never used GitHub, you first need to open a free account, log in and then click "New Issue." (Explore [GitHub Help](https://help.github.com) for more assistance).

To help us understand and fix the bug, please provide the following:

1. The detailed steps we need to take to reproduce the bug, including which kraken-lib version you were using

2. The expected behavior

3. The actual, incorrect behavior

Feel free to search our issue tracker for existing issues (aka tickets) similar to yours. If you find one, please add your information to it as a comment.

If you want to provide a patch with your bug report, please do by sending us a pull request as described in *Create a pull request* below. You can also opt to attach a patch file to the issue, but we prefer pull requests because they are easier to work with.

## **Requesting new features**

To request a new feature you should [open an issue](https://github.com/samsung-cnct/k2/issues) in github and summarize the desired functionality. If you have not used github before you will need to register an account (free), log in, and then click on the "New Issue" button.

## **Contributing code**

Before contributing code, please familiarize yourself with the kraken-lib codebase.

If interested in contributing code but you don’t know where to begin, [browse our issue tracker for open issues and tasks](https://github.com/samsung-cnct/k2/issues). You may want to start with beginner-friendly, easier issues found in [Help Wanted](https://github.com/samsung-cnct/k2/issues?q=is%3Aopen+is%3Aissue+label%3A%22help+wanted%22), because you only need to learn an isolated portion of the codebase and are a relatively small amount of work).

Please install [pre-commit](http://pre-commit.com/) to check your code against the ansible linter.

Contributions to the kraken-lib codebase should be sent as GitHub pull requests. See section *Create a pull request* below for details. If there is any problem with the pull request we can iterate on it using the commenting features of GitHub.

* For *small patches*, feel free to submit pull requests directly for those patches.

* For *larger code contributions*, please use the following process. The idea behind this process is to prevent any wasted work and catch design issues early on.

    1. [Open an issue](https://github.com/samsung-cnct/k2/issues) on github if a similar issue does not exist already. If a similar issue does exist, then you may consider participating in the work on the existing issue.

    2. Comment on the issue with your plan for implementing the issue. Explain what pieces of the codebase you are going to touch and how everything is going to fit together.

    3. kraken-lib committers will iterate with you on the design to make sure you are on the right track.

    4. Implement your issue, create a pull request (see below), and iterate from there.

### **Recommended Dev Tooling**

The recommended kraken-lib developer tool can be accessed in the /hack directory and is called dockerdev, a tool that pulls down a [Kraken-tools](https://github.com/samsung-cnct/k2-tools) image. The container will provide you with a console that contains the correct environment for developing and running kraken-lib. The intent is to mitigate version issues and requirements, allowing you the Developer to focus on coding and not worry on dependencies.

#### **Developer Workflow with Kraken-Tools**

Here we document how a developer would use Kraken-tools to work with a cluster.

##### **Assumptions**

* You have used either kraken-lib or Kraken to generate a config file.

* You have pulled the latest kraken-lib master branch on your machine, and are working on a fork.

docker pull quay.io/samsung_cnct/k2-tools

* You are currently on the your local kraken-lib github fork directory

##### **Steps**

* Generate latest configuration file, for example:

k2cli generate

* Next we should create a docker container that points to you (and mount your kraken-lib workspace) cluster config (generated earlier)

hack/dockerdev -c <PATH_TO_CONFIGS>/<YOUR_CONFIG>.yaml

* After some time, you will be in the bash terminal of the container, bring up your cluster as you would normally when developing kraken-lib (including any flags you require).:

/bin/up.sh -c <PATH_TO_CONFIGS>/<YOUR_CONFIG>.yaml

At this point since you have mounted your workspace, you should be able to make changes to kraken-lib here and even access git commands.

### **Testing**

All pull requests must pass integration testing.

## **Contribute documentation**

Documentation contributions are very welcome!

You can contribute documentation by pull request, as same as code contribution. Main directory is Documentation/.

## **Pull requests**

### **Create a pull request**

Pull requests should be done against the read-only git repository at [https://github.com/samsung-cnct/k2](https://github.com/samsung-cnct/k2).

Pull requests must only address one issue. For multiple issues, submit multiple pull requests. If a pull request depends on another pull request, add a comment explaining that.

Take a look at [Creating a pull request](https://help.github.com/articles/creating-a-pull-request). In a nutshell you need to:

1. [Fork](https://help.github.com/articles/fork-a-repo) the kraken-lib GitHub repository at [https://github.com/samsung-cnct/k2/](https://github.com/samsung-cnct/k2/) to your personal GitHub account. See [Fork a repo](https://help.github.com/articles/fork-a-repo) for detailed instructions.

2. Commit any changes to your fork.

3. Send a [pull request](https://help.github.com/articles/creating-a-pull-request) to the kraken-lib GitHub repository that you forked in step 1. If your pull request is related to an existing kraken-lib issue -- for instance, because you reported a bug report earlier -- then mention that your pull request fixes #123 in the description.

You may want to read [Syncing a fork](https://help.github.com/articles/syncing-a-fork) for instructions on how to keep your fork up to date with the latest changes of the upstream (official) kraken-lib repository.

### **Approve a pull request**

A pull request must pass CI testing and be reviewed by a core committer with a LGTM. If changes are requested, those must be addressed.

### **Merge a pull request or patch**

*This section applies to committers only.*

Important: A pull request must first be properly approved before you are allowed to merge it.

To pull in a merge request, you should generally follow the command line instructions sent out by GitHub.

Squash pull requests when merging.

# **Questions?**

If you have any questions after reading this document, please reach out to us.

And of course we also welcome any contributions to improve the information in this document!
