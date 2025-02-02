# Nabi using docs


After you commit and push this workflow, the deploy job will run only if both build and test finish successfully, and it consists of the following steps:

    Download the docs artifact using the actions/download-artifact@v4 action.

    Unzip the website archive using the unzip command.

    Enable GitHub Pages using the actions/configure-pages@v4 action.

    Package and upload an artifact that can be deployed to GitHub Pages using the actions/upload-pages-artifact@v3 action.

    Deploy the artifact to GitHub Pages using the actions/deploy-pages@v4.

If the workflow is successful, the deploy job will output the URL to the published documentation.


> Some important information
>
{style="v"}