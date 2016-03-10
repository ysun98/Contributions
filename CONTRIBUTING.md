
# Contribute a Bioconductor Package

## Terms Of Use

By using this service, you acknowledge that:

* Your package code will be public, where anyone can see it.
* The build reports and comments during the package review
  process are public.
* Any GitHub user may add comments to the package review.
* You are submitting a package for inclusion in
  [Bioconductor](https://bioconductor.org); the build
  service we provide is meant only for Bioconductor package
  submitters.

## How it Works

The way to contribute a
[Bioconductor](https://bioconductor.org/) package is to
file a [new issue](../../issues/new) in this GitHub repository,
including the link to a
[GitHub repository](https://help.github.com/articles/create-a-repo/)
you've set up that contains your package.

Here's what will happen when you do that:

* A Bioconductor team member will take a very brief
  look at your package, mostly to make sure it's a
  geniune package intended for Bioconductor.
  This is *not* a free build service for the community,
  it is only for Bioconductor package contributors.
* Once the package has been moderated, it will be built
  on our build system, on three platforms (Linux, Mac OS X,
  and Windows). A link to a build report will be appended to the
  issue that you've created in this repository.
* **IMPORTANT**: For subsequent changes to your package
  to be picked up, you must [add a webhook](#adding-a-web-hook)
  to your repository.
* If the build report reports issues with your package, you
  may modify your package (by committing and pushing changes)
  to your repository. Assuming you have
  [added a webhook](#adding-a-web-hook), this will trigger
  another build and build report.
* A Bioconductor team member will be assigned to review your
  package and will add further comments in the issue you created.
  Because of the 'social coding' nature of GitHub, any GitHub user
  may comment on your package.
* If your package is accepted, it will be added to Bioconductor's
  source control repository.   
* Once the review process is complete, the issue you created
  will be closed.

## Adding a Web Hook

Go to your repository page on GitHub. The link to it will look
something like this:

    https://github.com/yourusername/yourpackagename

The username and repository name will be different, of course.

Click on `Settings`, which is currently located towards the top,
on the right-hand side of the page.

In the left hand `Options` section, click on `Webhooks & services`.

Click on `Add webhook`.

Paste the following URL into the `Payload URL` box:

    http://issues.bioconductor.org

You can leave the other settings alone and click `Add webhook`.

Assuming your package has been authorized to use our build system,
subsequent pushes will now trigger builds, and the build reports
will be posted to the issue you created in this repository.

Note that pushes to non-default branches (`master` is usually
the default branch, unless you have set it to be something
different) are ignored.

If you do not want a build to occur on each push, temporarily remove the
webhook until you are ready to reactivate the automated builds.

## Multiple Related Packages

Sometimes you wish to contribute more than one package at a time. For
example, you may contribute a software package and a data package that
goes with it.

All of these packages should go under the same GitHub issue. However,
you can only submit one GitHub repository URL at once to an issue.

If you are submitting multiple related packages, the first one you
submit should be one that can be installed without a dependency on
any of the other packages you are submitting as a group.

Wait until it builds, and then you can submit additional related packages
to the same issue, by posting a comment containing a line like:

    AdditionalPackage: https://github.com/username/repositoryname

Of course, you need to change `username` and `repositoryname` to
match your repository.
You can only have one `AdditionalPackage` line per comment.
Wait until this related package builds before submitting further
related packages.

The `AdditionalPackages` comment must be posted by the same
GitHub user who created the issue. Also, the initial
package submitted in the issue must have completed the
'moderation'  step. If these conditions are not met, the
additional package will not build.

**IMPORTANT**: You need to [add a webhook](#adding-a-web-hook)
for these additional related packages as well, if you want
pushes to them to trigger new builds.

## Resources

Our package build system will run `R CMD check` on your package,
as well as the
[BiocCheck](https://bioconductor.org/packages/devel/bioc/html/BiocCheck.html)
package. You can avoid surprises by running these checks on your
package before submitting them to us.

The following pages contain more information about package submission.

* [Building Packages For Bioconductor](https://bioconductor.org/packages/devel/bioc/html/BiocCheck.html)
* [Package Guidelines](https://bioconductor.org/developers/package-guidelines/)
* [Package Submission](https://bioconductor.org/developers/package-submission/)
* The above and many other developer resources are available
  at the [developers' page](https://bioconductor.org/developers/).

If you have a question not answered above, please post it to
the [bioc-devel](https://stat.ethz.ch/mailman/listinfo/bioc-devel)
mailing list.
