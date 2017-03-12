# USA Rulebook
This is forked from the IUF Rulebook. Not everything below will apply. Substite USA Rulebook and usa-rulebook.tex for IUF Rulebook and iuf-rulebook.tex when relevant.



# IUF Rulebook

The rulebook is written in LaTeX and version controlled with git. Find out more about the [Technology](https://github.com/iuf/rulebook/wiki/Technology).

We also have some [Working Guidelines](https://github.com/iuf/rulebook/wiki).




## Reporting Issues
If you find an issue or have an idea for improvement, you can directly report it here on GitHub. Here is what you need to do:
* Get a GitHub Account and sign in (https://github.com/)
* Browse to the USA rulebook repository (https://github.com/scotthue/rulebook)
* Click on “Issues” (https://github.com/scotthue/rulebook/issues)
* For every issue you want to report, click “New Issue” (https://github.com/scotthue/rulebook/issues/new)
* Enter a title and a description and click “Submit new issue”

## Building the Rulebook

### Requirements

* A latex distribution supporting **pdflatex** with many common packages installed (for example **texlive** with **texlive-latex-extra** on debian based systems like Ubuntu). In addition, the following packages/scripts are required and can be found in the `dependencies` directory:
 * gitinfo
 * latexdiff (with latexdiff-so and latexdiff-vc)

### Building

Open a terminal in the repository root and type **make rulebook**. This will generate **pdf/usa-rulebook-$BRANCHNAME.pdf**.

To include git revision information in the document, you need to install git hooks to extract the information from git.
Do this with **./install_hooks**. Build the document again and the information should appear.

To produce a PDF highlighting the changes, type **make diff**.
This will generate **pdf/usa-rulebook-$OLDBRANCH-diff-$BRANCH.pdf**.
The current branch will be combpared with the branch(es) in the `diff-branches` file.

### Gitinfo package
If the build is failing because the gitinfo2 package cannot be found, copy the `gitinfo2.sty` from `dependencies` into the `src` directory.
