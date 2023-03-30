---
title: "Current Project: Migrate from Seam2"
date: 2015-02-17
draft: false
tags: [development,migration]
---

One of the projects I’m currently working on is an application used for laboratory collaboration. The project started nearly 5 years ago as a small application (mostly) generated from an existing database by [seam-gen](http://docs.jboss.org/seam/2.1.1.GA/reference/en-US/html/gettingstarted.html). Of course some additional handwork was needed e.g. to implement workflows, export facilities, messaging and integration stuff – (*Oracle Application Server 10.1.3 as production environment*)

Today the application is still running fine and the users are still happy – *I hope* – but the technology behind it is getting quite old. Additionally new ideas came up and I really don’t like the thought about implementing them the *old fashioned way*. My Decision: Before I’m going to start implementing new things the old things needed a small refurbishment.

The first investigation result: I should take care of my old projects! Somehow I had missed the release of [Seam 2.3](http://docs.jboss.org/seam/2.3.0.Final/reference/en-US/html/migration23.html) and it seems very easy to run the old application nearly unchanged on a newer system. *Nearly unchanged* – that was a little bit disturbing – What I wanted was the change! In the past five years so many new technologies came up and I have already done some new projects with JavaEE6/7 but never migrated an old application.

Next stop: [https://github.com/seam/migration](https://github.com/seam/migration) – very, very useful and could be seen as step-by-step manual for a migration project like this.

* Migrate to maven – DONE
* Migrate to JPA 2.0 – DONE
* Migrate to Bean Validation – DONE
* Migrate to CDI – NEARLY DONE
* Migrate to JSF 2.0 – DONE

The CDI migration part *“Migrate Query / Home objects”* was done with a little bit more of [DeltaSpike](http://deltaspike.apache.org/documentation/). Additionally I used [JBoss Windup](http://windup.jboss.org/) to get some hints and an overview about the progress. An initial rules set is available [here](https://github.com/windup/windup-legacy/blob/master/application/rules/src/main/resources/windup/java/java-seam-to-cdi.windup.xml).