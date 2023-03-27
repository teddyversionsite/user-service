# User Service

A service for users.

## Building

Standard spring boot with gradle things apply. You can `gradle test` or `gradle bootRun` to your heart's content.

## Publishing

We're going to use [Jib](https://github.com/GoogleContainerTools/jib/tree/master/jib-gradle-plugin) to do the dockerization because I trust Google to keep my container up to date better than I can. Plus it "just works" with the GCR upload and all the things.

This does, however, mean that you need to have the right magic incantations set up to auth to GCR from local (at least initially, until we automate this in github). You can find info on that [here](https://github.com/GoogleContainerTools/jib/blob/master/jib-maven-plugin/README.md#authentication-methods).

## Databases

We're going to use [spring boot magic™](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#howto.data-initialization.migration-tool) to manage migrations for us via flyway. Migrations are therefore in `src/main/resources/db/migration` and are auto-run on app boot.

For now, you need to manually start a postgres container and give it a `teddyversion` database.

```sh
docker run -d -p 5432:5432 -e POSTGRES_DB=teddyversion -e POSTGRES_PASSWORD=postgres postgres:14
```
