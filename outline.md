MyUW Processes & Practices outline

An outline, notes supporting a presentation at Open Apereo 2014.

**These notes are not fully baked.**

Abstract
=========

We will present processes and practices at work in My UW Madison portal development and maintenance. We use Scrum, work with a wider Wisconsin team (designer, dba, systems administrators, portlet developers, stakeholders, ? ), and collaborate with the wider uPortal and Apereo open source community. We use GitHub, Bitbucket, local SVN, CVS(!), Maven overlays, and a shared Maven repository. We use Jenkins for continuous integration and more. We tend to prefer entity files and configuration in source control over live Web-based administration of the portal. We will present what our ambitious enterprise uPortal implementation looks like 1000 (binary) years in. Note that this session emphasizes process and practices rather than what portlets and functionality we are delivering to users. This is an intermediate-level presentation. Newcomers might best consider all this and start with a subset of processes and practices. Established adopters will find much to compare and contrast.

Meta
====

License
-------

This presentation licensed to you under [CC-BY 4.0] or under Apache v2, at your option.

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

Disclaimer
----------

Opinions expressed in this presentation are those of the presenter and are not necessarily those of the University.

Context
=======

This presentation is mostly about process and practices, but it will help to have some context on what these processes and practices are accomplishing.

MyUW Madison
------------

MyUW Madison is an enterprise Web portal, built on uPortal, serving the University of Wisconsin-Madison, providing student-targeted tools and information, staff-targeted tools and information, tools for advising, access to Blackboard Collaborate, the course guide, and handy single sign-on links into PeopleSoft Student Center, Faculty Center, WiscMail, Box, etc.

* Courses portlet
* [Payroll](http://cl.ly/image/0o2H1J2F2A3o)
* [W2 access](http://cl.ly/image/152G2A1i1m3f)
* [Leave balances](http://cl.ly/image/1z11271O3E2V)
* [Personal information](http://cl.ly/image/1v1J0q3N2x0C)
* [Benefits](http://cl.ly/image/3U01143C122z)
* Advising
* Scheduling
* [IT Helpdesk tickets](http://cl.ly/image/1o1w0G0Y2W1Z)
* [Single sign-on links](http://cl.ly/image/2y0h2w010D1k)
* [Web conferencing](http://cl.ly/image/2N2R1d0T3e0I)

And yes, there's bookmarks and weather.

* [Bookmarks](http://cl.ly/image/2T0X1s0I091l)
* [Weather](http://cl.ly/image/3p36320X3w1L)

We're federated, serving the wider University of Wisconsin system providing staff-targeted tools around access to payroll and benefits information.

[WAYF](http://cl.ly/image/0J3C0e01362d)

And we even provide a limited public view to deliver the course guide.

[Course Guide](http://cl.ly/image/1w1J0r2l3m0S)


Jenkins-Driven Maven
--------------------

Recap of last year's presentation re Jenkins and Maven.

Commit --> Jenkins build of product --> Jenkins build of overlay atop of product --> Deployment to a target environment.

Jenkins
Maven
Nexus
Source control



Redesign
--------

We've got a pretty good portal!  Serving lots of users, providing convenient single sign-on, MyUW provides a unified service delivery platform.  The reality of how benefits, payroll, and W2 data are drawn together is kind of messy, but we can present this in a unified way.

But we can do better.

So, [redesign][MyUW Redesign public website].

### Vision

> MyUW will provide the unified platform, services, and support to help everyone at UW-Madison work smarter, faster, and safer.

> Guiding principle: Listen hard.  Change fast.

### Redesign Glyphs

http://cl.ly/image/2V133p0s1O1u


### This isn't that presentation

So, this isn't the presentation about the redesign, that was [this morning][MyUW Redesign presentation at Apereo 2014].  But I hope that's enough about the redesign to give some context for what we're working on.

Without further ado:


Scrum
=====

Scrum defined
-------------

Scrum is a set of processes and practices implementing a specific agile method.


Product Owners
--------------

* Jim Helwig
* Annette Stratman-Durrer


Scrum Team
----------
* Tim Levett
* Andrew Petro
* Tim Vertein
* Web Developer TBD!

Story
-----

Something that the Scrum team can do that has value to the stakeholders.

The Product Backlog
-------------------

Infinite, prioritized queue of stories.

Sprint
------

A short iteration in which we can design, develop, and deploy artifacts that fulfill some stories to a test server.  For us, two weeks.

Sprint planning
---------------

Meeting in which the Scrum Team works with the Product Owners to pick out some high-priority stories to commit to for the Sprint.

Sprint backlog
--------------

Set of stories the Scrum Team committed to for the sprint.

Daily Scrum
-----------
Daily Stand Up Meeting in which each Scrum Team member looks other team members in the eye and says:
* What was accomplished since the previous standup
* What will be accomplished before the next standup
* What impediments stand in the way



Sprint review
-------------

Meeting in which the team demonstrates the *working code* that was developed in the sprint.

Retrospective
-------------

Between-sprints meeting to inspect and adapt the process.  What's working well, what's worth tweaking.

Backlog grooming
----------------

Meeting in which the team grooms the top-priority product backlog entries.

Between sprints
---------------

R&D?


Definition of done
------------------

What does it mean for something to be done?  "Working code"?

Migration
=========

We have a migration process whereby completed development items percolate through a test tier, a QA tier, and then to production.

Some changes come in as migration requests, as in requests to incorporate updated versions or configuration of portlets, entities in tiers.

[Migration request example](http://cl.ly/image/2b2p1y1B1h1v).

JIRA.

Working with others
===============================

Kanban
------

Scrum works great when there's a capacity of resources dedicated to your project.  It's a method for prioritizing, focusing, and getting continual value out of the efforts of that dedicated team.

But what about project participants in a supporting role, who contribute in important ways but who aren't dedicated to this project?

Kanban to the rescue.

# Kanban board for working with UX Consultant

Trello.

# Kanban board for working with systems / application administration

JIRA.


Jim Helwig goes to a lot of meetings
------------------------------------

Jim often serves as the "face" of the team and of the MyUW service, meeting with stakeholders and then translating those desires into Product Backlog entries and serving as a local proxy for the stakeholders in his Product Owner role.


Source control
==============

Our project is source control driven.

GitHub
------

We like GitHub a lot. 

Public repos are great!

Private repos are pretty great too.  Except you have to pay for them.

Bitbucket
---------

* Free as in zero dollars private repos.


Institutional SVN
-----------------

Environment-specific overlays and entity files are in SVN.

### Entity file driven configuration

We curate entity files in source control and run uPortal import regularly.



CVS
---

We've still got some historical usages of CVS for source control going on.  We're trying to migrate off of that.
 


Code review
===========

GitHub Pull Requests for code review.

This works pretty well
----------------------

What happens if you don't review
--------------------------------

SVN overlay WiscMail hyperlink goof anecdote.

Participating and Collaborating at Apereo layer
===============================================

TODO: content re

Unicon assistance
-----------------

The University subscribes to Unicon's "Open Source Support" program.  That's been useful for:

* review and validation of the CONFIG permission vulnerability and its fix
* advice about avoiding layout corruption for the specifics of MyUW's aggressive usage of `db-import`
* nailing that uPortal session management choking on latest Tomcat bug
- [ ] Note JIRA for session management bug

Tweaks and lessons and directions
=================================

Product Owner Queue
-------------------

JIRA's an issue tracker.  So it's a decent place to track issues.  When you discover a problem, or think of a potentially worthy feature, it's probably a good idea to capture it to the issue tracker.

How, however, do you differentiate stories-to-be-prioritized from stories that have been prioritized by the Product Owners?  Well, you can add all new stories to the bottom of the backlog, but that's not quite right, in that how do you then tell the difference between stories that are sent-to-bottom because they have not yet been triaged, versus stories that have been sent-to-bottom because that's the priority they are due?

We're solving this with a Product Owner JIRA project.  New stories come in as MUMPO issues and through the ministrations of Product Owners they are transformed into issues in the JIRA project modeling the product they're part of (say, MUMUP if they're in My UW-Madison's uPortal implementation, or WCP if they're in My UW-Madison's web conferencing portlet implementation).  This way you can tell from the issue identifier / project whether it has been triaged by Product Ownership.  (Note that this could probably have been solved with JIRA labels instead, with some tradeoffs.)

Epics?
------

When do you create an Epic?  If you don't create enough epics, you miss a chance to organize issues and you don't ever close any epics because they aren't scoped tightly enough to be completed. But if you create too many epics, then it starts to feel like an overwhelming slate of epics to sift through.

We're still figuring this out, but have moved epic creation/organization to the group issue grooming sessions in order to try to navigate this better.

The rule of two
---------------

When do you merge a pull request?

We're trying a Rule of Two wherein once a pull request hits +2 (via two +1s or one +2), it's mergeable and ought to be immediately merged by whoever can get to it next.

So, if you're coming along reviewing something that already has a +1, and you like it and are also giving it a +1, hit Merge.  

Or if you're reviewing something and you really think it's solid, maybe you even actually tested it, if you want to stick your neck out you can give it a +2 and hit Merge.

See also Chwayatyun / http://starwars.wikia.com/wiki/File:SidiousVaderPromo.JPG .

Portlet Development Guide
-------------------------

How do you help your portlets to work better and be more consistent, to feel like they belong together in your portal?

We're early in building this out, but we've hit upon the idea of a Portlet Development Guide.




Forking uPortal
---------------

Like many (all?) other uPortal adopters, we have a local copy of the uPortal source code and locally apply modifications.  Usually we're trying to apply modifications both to `Jasig/uPortal` and to `MyUW/uPortal`.  Sometimes we code against one first and then merge to the other, or the other way around.  These codebases naturally diverge.  This is a huge pain.

Sometimes we try to just put a fix in Jasig/uPortal and then gain the benefit of it on a subsequent merge of Jasig/uPortal into our local uPortal fork.  But that's kind of broken in that we should be realizing the feature or fix in our own local merged test environment to demonstrate it during sprint demos and to fulfill the Scrum premise of releasable code every sprint.  Releasable means we're demonstrating it really working on the test server.

Sometimes we try to develop a feature for a while in our local uPortal fork and only share it up against Jasig/uportal "when it's ready".  But that's broken in that it's less transparent than it could be and it misses theoretical opportunity for collaboration and feedback.

Duplicate code review opportunities are a pain.  Sometimes it feels redundant to do two pull requests in two different contexts for the same changeset.  Sometimes different ideas come to the fore in the different contexts.  Once the change has merged in one or the other, it's kind of a pain if the changeset diverges in the other context, creating merge debt later.

So, we muddle along, composing changesets and proposing/merging them against both, and paying some friction costs.

Bigger picture, I think there's opportunity to move towards 

* factoring uPortal into smaller, cohesive modules so that there isn't one complected codebase that you have to fork to get frameworky things done
* Engineering the build and adoption process so that locally forking the uPortal codebase is less necessary and you can adopt components via declarative dependencies and write add-ons to well-defined APIs
* Releasing uPortal (and uPortal components) more frequently (milestones? automated?) so that progress is more frequently available for inclusion as a declared dependency

and that might allow us to get to a place where there's less friction in merging changes back and forth between `uw-master` and `Jasig/uPortal/master`.  

Bottom line, it would be great if MyUW just didn't have a fork of the core uPortal codebase, and instead was exclusively adding local special sauce.


Adding a web developer
----------------------

As we look to add a web developer (focusing on markup, JavaScript, CSS) to the team, looking at how to make web layer development more feasible without requiring a whole running uPortal instance.  Potential in static snapshots of markup to work with and then merging those changes back in to the "real" product?  Potential in moving towards templating technologies (Thymeleaf?  Angular?) where the templates are more readily renderable?

XSLT isn't feeling great these days.  Come to my BoF about how to evolve the uPortal codebase away from relying upon it.



[CC-BY 4.0]: http://creativecommons.org/licenses/by/4.0/
[MyUW Redesign presentation at Apereo 2014]: http://lanyrd.com/2014/apereo/sdbbbm/
[MyUW Redesign public website]: http://redesign.my.wisc.edu/

