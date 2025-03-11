# DfE Quarto Slides Template

This template gives some basic branding and styling to Quarto slides, including some examples of the features available.

For more information on using Quarto for slides, see the [Quarto documentation](https://quarto.org/docs/presentations/). Styling is mostly controlled through custom CSS in the `dfe-quarto-slides.scss` file.

To use this template either:

- Use the GitHub create from template button
- Clone the repository and copy the files into your own repository manually

## Running the slides

1. Install [Quarto from their website](https://quarto.org/docs/get-started/).

2. Install code depdencies (not needed if you don't execute any code chunks)

```
renv::restore()
```

3. Run the slides

If in R Studio, in an R console using the quarto R package, use `quarto::quarto_preview()`

If elsewhere in a terminal (e.g. VSCode), use `quarto preview`

## Notes about the template

We have set this template up including an R project file and renv, to make it easier for anyone using R code to version control their packages and install dependencies.

We've also set `echo: TRUE` among the default settings, as we're assuming most of the time we want to show the code in our code chunks, this is easy to override for individual chunks or even just change the default if you'd prefer the code itself not to show.

## Deploying slides

We generally recommend if you're going to deploy Quarto slides for anyone to be able to view them at a URL, that you do it using [GitHub Actions](https://github.com/features/actions).

Steps to follow:

1. Ensure there is a `gh-pages` branch

If you don't have one already, create one using these Git commands in a terminal:

```
git checkout --orphan gh-pages
git reset --hard # make sure all changes are committed before running this!
git commit --allow-empty -m "Initialise gh-pages branch"
git push origin gh-pages
```

2. Set up the actions workflow file

For this you don't need to do anything, you should be able use the action already created in `.github/workflows/publish.yml`

3. Set the pages settings in your repo

You'll want to set it so that it deploys using GitHub Actions, and reads from the root (/) folder.

In theory, at this point it should start deploying from your next push to the main branch!
