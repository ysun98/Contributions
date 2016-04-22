
# Contribute a _Bioconductor_ Package

By using this service, please note that:

* Your package code will be public, where anyone can see it.
* The build reports and comments during the review process are public.
* Any GitHub user may add comments to the package review.
* You are submitting a package for inclusion in [Bioconductor][1]; the
  build service we provide is meant only for individuals submitting
  _Bioconductor_ packages.

## How it Works

To contribute a _Bioconductor_ package

1. Open a [new issue](../../issues/new) in this GitHub repository. The
   new issue requires a link to an existing [GitHub repository][2]
   containing your package.
2. [Add a webhook][3] to your repository. The webhook means that any
   commit to the default (typically 'master') branch automatically
   triggers a new package build.

Here's what will happen when you do that:

* A _Bioconductor_ team member will take a very brief look at your
  package, to ensure that it is intended for _Bioconductor_.
* The package will be submitted to the _Bioconductor_ build
  system. The system will build your package, using the 'devel'
  version of _Bioconductor_, on three platforms (Linux, Mac OS X, and
  Windows). A link to a build report will be appended to the new
  package issue.
* If the build report indicates problems, modify your package and
  commit changes to the default branch of your GitHub
  repository. Committing to the default branch will trigger another
  build report. If there are problems that you do not understand, seek
  help on the [bioc-devel][9] mailing list.
* A _Bioconductor_ team member will be assigned as primary reviewer
  of your package.  Other _Bioconductor_ developers and users with
  domain expertise are actively encouraged to provide additional
  community commentary.  Reviewers will add comments to the issue you
  created.
* You will respond to the issues raised by the reviewers. You _must_
  respond to the primary reviewer, and are strongly encouraged to
  consider community commentary. Typically your response will involve
  code modifications; commit these to the default branch of the GitHub
  repository to trigger subsequent builds. When you have addressed all
  concerns, add additional text to the new package issue to explain
  your response.
* The reviewer will assess your responses, perhaps suggesting further
  modifications or clarification. The reviewer will then accept your
  package for inclusion in _Bioconductor_, or decline it.
* If your package is accepted, it will be added to _Bioconductor_'s
  source control repository and to the nightly 'devel' builds.
* Once the review process is complete, the issue you created will be
  closed. All updates to your package will be through the
  _Bioconductor_ [Subversion repository][10] (optionally,
  [using GitHub][11]).

## Adding a Web Hook

To add a web hook:

1. Go to your repository page on GitHub. The link to it will look
   something like this:

        https://github.com/yourusername/yourpackagename

   Of course, `yourusername` and `yourpackagename` will be different.

2. Click on `Settings`, which is currently located towards the top, on
   the right-hand side of the page.

3. In the left hand `Options` section, click on `Webhooks & services`.

4. Click on `Add webhook`.

5. Paste the following URL into the `Payload URL` box:

        http://issues.bioconductor.org

   You can leave the other settings alone and click `Add webhook`.

Subsequent pushes to the default (usually `master`) branch of your
repository will now trigger builds, and the build reports will be
posted to the issue you created in this repository.  Note that pushes
to non-default branches are ignored.

If you do not want a build to occur on each push, temporarily remove the
webhook until you are ready to reactivate the automated builds.

## Multiple Related Packages

Sometimes you wish to contribute more than one package at a time. For
example, you may contribute a software package and a data package that
goes with it.

All of these packages should go under the same GitHub issue. However,
you can only submit one GitHub repository URL at once to an issue.

If you are submitting multiple related packages, the first one you
submit should be one that can be installed without a dependency on any
of the other packages you are submitting as a group.

Wait until it builds, and then you can submit additional related
packages to the same issue, by posting a comment containing a line
like:

    AdditionalPackage: https://github.com/username/repositoryname

Of course, you need to change `username` and `repositoryname` to match
your repository.  You can only have one `AdditionalPackage` line per
comment.  Wait until this related package builds before submitting
further related packages.

The `AdditionalPackages` comment must be posted by the same GitHub
user who created the issue. Also, the initial package submitted in the
issue must have completed the 'moderation' step. If these conditions
are not met, the additional package will not build.

**IMPORTANT**: You need to [add a webhook][3] for these additional
related packages as well, if you want pushes to them to trigger new
builds.

## Resources

Our package build system will run `R CMD check` on your package, as
well as the [BiocCheck][4] package. Avoid surprises by running these
checks on your package before submitting them to us.

The following pages contain more information about package submission.

* [Package Guidelines][6].
* [Package Submission][7].
* The above and many other developer resources are available at the
  [developers' page][8].

If you have a question not answered above, please post it to the
[bioc-devel][9] mailing list.

[1]: https://bioconductor.org
[2]: https://help.github.com/articles/create-a-repo/
[3]: #adding-a-web-hook
[4]: https://bioconductor.org/packages/devel/bioc/html/BiocCheck.html
[6]: https://bioconductor.org/developers/package-guidelines/
[7]: https://bioconductor.org/developers/package-submission/
[8]: https://bioconductor.org/developers/
[9]: https://stat.ethz.ch/mailman/listinfo/bioc-devel
[10]: http://bioconductor.org/developers/how-to/source-control/
[11]: http://bioconductor.org/developers/how-to/git-mirrors/
