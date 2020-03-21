Minimal Jenkins X demo repo based on https://spring.io/guides/gs/consuming-rest/ with the [Spring Actuator](https://spring.io/guides/gs/actuator-service) added in

While the original example offers both Maven and Gradle the idea with this demo was to focus purely on Gradle, exercising a new Jenkins X Gradle build pack.

Run locally with `gradlew bootRun` 

Test via http://localhost:8080/greeting

Health check at http://localhost:8080/actuator/health

Credit: thanks to https://github.com/Cervator for the contribution of this quickstart
