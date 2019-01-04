# Final Checkpoint and Handoff

The goal of this checkpoint is to ensure your project can be handed off to a future team for enhancements and maintenance.

Each project will be "checked off" for this deliverable by the same project team with whom they did the Design Review assignment, which we'll call the "visiting team" again.

The visiting team will:

* Clone the home team's repo, and ensure that  `bundle install --without production` and `rake db:setup`  run successfully (if any additional preparation steps are needed to deploy the app in development, ensure that the `README.md` explains them clearly)
* Ensure `rails server` starts the app successfully
* Ensure `rake cucumber` and `rake spec` pass all the tests on master branch and do not give errors
* Ensure `rake cucumber` does not have undefined steps
* Ensure `rake spec` does not have have skipped scenarios
* Ensure the app can be deployed to Heroku (or some other way, if so indicated in its `README.md`), including documentation of any addons, environment variables (`figaro`), or special configuration needed to make this happen
* If any additional steps are necessary to try out the app in production--putting fake data into the database, using a particular login name/password to behave as an admin vs. a regular user,
etc.--ensure these work as documented as well

**The teams must work together to get each others' apps stood up.**  Each team will only get credit for the final checkpoint if they *both* help the other team get their app in shape *and* get their own app in good enough shape for the other team to stand it up.

