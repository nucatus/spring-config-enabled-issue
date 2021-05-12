# Spring cloud config client enable issue

This project demonstrates the issue with disabling spring cloud config on a specific profile, but not only.

## 🙂 Expected behavior

When the spring cloud config client is disabled by setting the `spring.cloud.config.enabled` property to `false`, the config servers that are already configured are ignored.

## 🙁 Observed behavior

Even if the spring cloud config client is disabled, the config server endpoint gets called, and a decision to fail the application startup process is made based on the `isOptional` and `isNotFailFast` flags.

## ⏯ Run

Try to run this demo with no profile selected 

```shell
gradle bootRun
```

and then with the `dev` profile selected, where the cloud config was explicitly disabled.

```shell
SPRING_PROFILES_ACTIVE=dev gradle bootRun
```