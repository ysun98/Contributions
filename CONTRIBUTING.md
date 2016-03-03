
# Contribute a Bioconductor Package

## Terms Of Use

By using this service, you acknowledge that:

* Your package code will be public, where anyone can see it.
* The build reports and comments during the package review
  process are public.
* Any GitHub user may add comments to the package review.

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
  and Windows). A build report will be appended to the
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


 ## Adding a Web Hook

Go to your repository page on GitHub. The link to it will look
something like this:

    https://github.com/yourusername/yourpackagename

The username and repository name will be different, of course.

Click on "Settings", which is currently located towards the top,
on the right-hand side of the page.

In the left hand "Options" section, click on "Webhooks & Services".

Click on "Add webhook".

Paste the following URL into the `Payload URL` box:

    http://issues.bioconductor.org

You can leave the other settings alone and click 'Add Webhook'

Assuming your package has been authorized to use our build system,
subsequent pushes will now trigger builds, and the build reports
will be posted to the issue you created in this repository.

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
