<header>

<!--
  <<< Author notes: Course header >>>
  Include a 1280×640 image, course title in sentence case, and a concise description in emphasis.
  In your repository settings: enable template repository, add your 1280×640 social image, auto delete head branches.
  Add your open source license, GitHub uses MIT license.
-->

# Test with Actions

_Create workflows that enable you to use Continuous Integration (CI) for your projects._

</header>

<!--
  <<< Author notes: Step 4 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
-->

## Step 4: Add branch protections

_Great job uploading test reports! :partying_face:_

Take a look at the merge box, you'll notice you can merge this even though the review process hasn't been met.

Protected branches ensure that collaborators on your repository cannot make irrevocable changes to branches. Enabling protected branches also allows you to enable other optional checks and requirements, like required status checks and required reviews.

### :keyboard: Activity: Add branch protections



You can follow along as GitHub Actions runs your job by going to the __Actions__ tab or by clicking "Details" in the merge box below.


   ```yml
   build:
     runs-on: ubuntu-latest
     steps:
       - uses: actions/checkout@v4

       - name: Run markdown lint
         run: |
           npm install remark-cli remark-preset-lint-consistent vfile-reporter-json
           npx remark . --use remark-preset-lint-consistent --report vfile-reporter-json 2> remark-lint-report.json

       - uses: actions/upload-artifact@v4
         with:
           name: remark-lint-report
           path: remark-lint-report.json
   ```


1. Commit your change to this branch.

1. Wait about 20 seconds and then refresh this page (the one you're following instructions from). [GitHub Actions](https://docs.github.com/actions) will automatically update to the next step.

Like the upload action to send artifacts to the storage, you can use the download action to download these previously uploaded artifacts from the `build` job: [`actions/download-artifact`](https://github.com/actions/download-artifact). For brevity, we'll skip that step for this course.


<footer>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Get help: [Post in our discussion board](https://github.com/orgs/skills/discussions/categories/test-with-actions) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

&copy; 2023 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

</footer>
