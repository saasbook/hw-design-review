# Final Checkpoint and Handoff

The goal of this checkpoint is to ensure your project can be handed off to a future team for enhancements and maintenance.

To pass this checkpoint, the "reviewer" of your repo---whether that is a course instructor or member(s) of another team---will have to confirm that the following procedures all work when they clone or fork your team's repo.  If any additional steps are necessary to make the below processes work--setting special environment variables, provisioning add-ons for deployment, adding fake data to the database, using a particular login name/password to behave as an admin vs. a regular user,
etc.--the `README.md` should document all such steps.

*  `bundle install --without production` and `rake db:setup`  run successfully (if any additional preparation steps are needed to deploy the app in development, ensure that the `README.md` explains them clearly)
*  `rails server` starts the app successfully
*  `rake cucumber` and `rake spec` pass all the tests on master branch and do not give errors
*  `rake cucumber` does not have undefined steps
*  `rake spec` does not have have skipped/pending scenarios
* The repo has up-to-date badges for CodeClimate maintainability, CodeClimate test coverage, and Travis build status
* The app can be deployed to Heroku (or some other way, if so indicated in its `README.md`), including documentation of any addons, environment variables (`figaro`), or special configuration needed to make this happen
*  All branches in repo have either been merged upstream to the master branch/master repo, or have been killed. That is, at the close of the project engagement, there should be no open/unmerged branches in the home team's repo or fork.
* All Pivotal Tracker stories are either Unstarted, Accepted, or (if absolutely necessary) Rejected.  That is, no stories should be a started-but-unfinished state, and all finished stories should be signed off by the Customer or Product Owner (Accepted or Rejected) and, if accepted, deployed to the cloud.
* All features that have been merged upstream are also deployed to production (in whatever manner is appropriate for that customer).
