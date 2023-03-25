# User Service

A service for users.

## Building

Standard spring boot with gradle things apply. You can `gradle test` or `gradle bootRun` to your heart's content.

## Publishing

We're going to use [Jib](https://github.com/GoogleContainerTools/jib/tree/master/jib-gradle-plugin) to do the dockerization because I trust Google to keep my container up to date better than I can. Plus it "just works" with the GCR upload and all the things.

This does, however, mean that you need to have the right magic incantations set up to auth to GCR from local (at least initially, until we automate this in github). You can find info on that [here](https://github.com/GoogleContainerTools/jib/blob/master/jib-maven-plugin/README.md#authentication-methods).
