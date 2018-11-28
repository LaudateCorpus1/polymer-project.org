## Polymer documentation site

https://www.polymer-project.org/

### Install

The documentation site runs in Google App Engine, using the App Engine Python standard environment. Before you start
you'll need the following prerequisites:

-   Python 2.7
-   [Google Cloud SDK](https://cloud.google.com/sdk/)
-   App Engine Python standard environment. Ensure this is installed by running the following command:

        gcloud components install app-engine-python

    Or, if you installed via apt:

        sudo apt-get install google-cloud-sdk-app-engine-python

Set up your repo:

    git clone https://github.com/Polymer/docs
    cd docs
    npm install


### Running the site

The first time you run the site, run `gulp` to build the site in its entirety:

    gulp

Then start the App Engine dev server on `dist/app.yaml`:

    dev_appserver.py dist/

The site will be served from http://localhost:8080.


### Run tests

Install [WebTest framework](http://webtest.pythonpaste.org/en/latest/):

    pip install WebTest

Then run:

    npm test

If your Google Cloud SDK isn't installed in `~/google-cloud-sdk`, set the `CLOUD_SDK` environment
variable to the path to the Cloud SDK:

    export CLOUD_SDK=~/cloud/google-cloud-sdk


### Deployment

Build and deploy version `YYY-MM-DD` of the site:

    gulp
    npm run deploy YYYY-MM-DD
