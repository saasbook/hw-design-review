# Doing a Design Review or Approach Review

As Section 10.7 of ESaaS explains (The
Plan-and-Document Perspective section in the Project Management
chapter), a design review is different from a code review.
Specifically, the goal of a design review is to get feedback from
experienced developers who are **not** part of the team on whether the
proposed software architecture and design choices are appropriate for
the application's functionality.  If a design review is done even
earlier in the app's lifecycle, it may be called an "approach review."


# Overview and Goal of assignment

To honor Dave Patterson's passion for sports, in this discussion we will
refer to the "home team" and "visiting team".  The home team is the team
receiving a review; the visiting team is giving the review.  Teams will
be paired up to provide design reviews to each other, so each team will
have the chance to be both a home team and a visiting team.

As in real life, the goal is for the teams to derive mutual benefit.
The benefit to the home team is to get outsider feedback on their design
choices and suggestions on how to improve the app's design or
architecture.  The benefit to the visiting team is sharpening their
skills at understanding someone else's code, and becoming practiced at
giving specific and actionable (vs. vague and non-actionable) feedback.

The assignment is done in two phases.  Each phase has a deliverable
report with a deadline.

1. Preparation (deliverable: pre-meeting report)

2. Review meeting (deliverable: post-meeting report)

# Phase 1: Before the meeting -- visiting team

Each team will take the role of the visiting team and prepare by
reviewing the home team's app.
Chapter 9 of ESaaS (Enhancing Legacy Software) includes advice on how to
approach and understand a legacy codebase; 
you shouldn't need to create your own
characterization tests, but the other approaches are still useful:

* Understand what business problem the home team's app solves.  If the
home team recorded a customer interview, watch it.

* Make sure you have access to all of the design documents, whether they
are part of the GitHub code repo or elsewhere.

* Interact with the live app on Heroku or wherever it's deployed.  

* Get the app running in your development environment, if possible.  Can
you run the tests?  Do they pass?

* Examine the codebase to identify the most important models and how
they are associated with each other.  Consider manually drawing an
entity-relationship diagram to show the associations.

* Look at the tests, especially user stories (Cucumber scenarios) that
may help you understand the flow of the app.

* Look at the test coverage information either by running the tests
yourself or viewing it on the home team's CI server.  It will be most
useful to look at the coverage for each file, rather than just the
overall coverage, so you can make suggestions about how to test
under-tested code.

* Look at the user stories in Pivotal Tracker.  What stories are yet to
be implemented, and do you see any major stories on the horizon that
might be difficult to implement given the app's current architecture?

Keep in mind that you may need the home team's help to do some of the
above, so don't wait until the last minute to start.

## Phase 1 deliverable

Based on exploring the codebase, the visiting team will write a short
pre-meeting report that has two parts.

The first part should be a short summary (a few sentences) of the home
team's app (what problem it solves) and its high-level structure.
Here's an example of such a summary:

> The goal of the app is to sell tickets to moviegoers.  The
main models are moviegoers, movies, showings, and tickets.  The app is
organized around the Ticket model since each ticket is related to a
movie, a moviegoer (purchaser), and a showing, so that model ties the
others together.  There are also secondary models for handling
authentication, promotions, and so on.  The app integrates with Stripe
for payment processing and with Facebook to allow moviegoers' friends to
see which movies they're going to.  The app also integrates with TMDb
(The Movie Database) to show critics' reviews of certain movies.

The second part should list
 **at least three** specific
technical questions or suggestions for the home team (more is OK).  The best
technical questions are those that ask about a design choice and
possibly propose an alternative.  For example: 

* "Since a Professor has-many Students, why didn't you use nested
routes to represent the actions on Students?"

* "The User class seems to have many responsibilities (violating the
Single Responsibility Principle).  We suggest factoring out the
Authentication functionality into a separate class or module.  At the
meeting can we discuss if there's any reason not to do that?"

* "It looks like you used some hacks to get access to model information
from your JavaScript code.  Did you know about the +gon+ gem, designed
to solve that problem?"

* "This JavaScript function is 20 lines long and has other nested
functions in it, violating SOFA.  Did you consider splitting out the
pieces as helper functions so you could test the pieces individually?"

* "This model has some important code in it regarding what happens if
the user supplies a bad password, but there's no tests for it."

* "You have a story in the icebox about offering discount ticket bundles
for movies, but your Ticket model seems to assume all tickets for a
movie cost the same.  How do you plan to implement the discount feature?"

**Your instructor will tell you how to submit this deliverable.**  You
will submit it to both the home team and your instructor or teaching
assistant. 

**Grading** will be based on:

* Did you provide a clear and concise summary of the app's major purpose
and gross structure?

* Did you submit at least five substantive design questions/suggestions
to the home team?

* Were the suggestions delivered on time to the home team and to your
instructor or teaching assistant?

* Did all visiting team members contribute to reviewing the codebase and
suggesting design questions?

# Phase 2: Live meeting

In this phase, one team will first act as the visiting team and discuss
the feedback they gave to the home team.

The home team does not have to agree to implement all the suggestions
given, but should help the visiting team understand why they made the
choices they did.  In some cases, they may decide the visiting team's
feedback is valuable and decide to implement those changes.

The home team should choose one or more members to scribe the meeting.
After about 30 minutes, the review ends, and the teams switch roles.

After each team has given feedback to the other, the teams should
immediately spend an extra 15-20 minutes (more if necessary) working
with their scribes to turn the scribe notes into the meeting report
deliverable, below.

## Phase 2 deliverable: meeting report

After the meeting, each home team should produce a meeting report that highlights the
following:

1. In the opinion of the home team, did the visiting team arrive at the
meeting well prepared?

2. In the opinion of the home team, were all the members of the visiting
team present and actively engaged in the technical discussion (vs. one
or two people dominating)?

3. Based on the feedback, list at least two technical suggestions you
received that, even if you don't have time to implement them, might
represent an improvement to your app's design.

Evaluation of the report will focus on whether you provided well-explained answers to the above questions. 
For example, for question #1, don't just say "yes"; give a specific example of how the visiting team was well prepared (or not well prepared).

