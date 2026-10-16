# Security Policy

This policy applies to every repository of [https://github.com/openrosde](https://github.com/openrosde) that has no security policy of its own.

## 🔒 Reporting a Vulnerability

Please report a vulnerability privately, and never in a public issue, pull request, or discussion.

- Use the private vulnerability reporting of GitHub, with **Report a vulnerability** in the **Security** tab of the affected repository.
- Write to `info@coarobo.com` if that button is missing, or if the vulnerability spans several repositories.

Include the affected repository, the release tag or the commit, the platform or the setup, the steps to reproduce, and the impact you expect.
Coarobo GK, which maintains OpenRoSDE, keeps the report private until a fix is available.

## 🧭 Scope

- The entry scripts, the Docker images, the workspaces, and the CI of the core, [https://github.com/openrosde/openrosde](https://github.com/openrosde/openrosde).
- The platforms and the devices in their own repositories, such as [https://github.com/openrosde/openrosde-platform-fetch](https://github.com/openrosde/openrosde-platform-fetch).
- The website and its source, [https://github.com/openrosde/openrosde-docs](https://github.com/openrosde/openrosde-docs).

A vulnerability of an upstream package that the images bundle, such as ROS, Gazebo, or a driver, belongs to its own project, and a report here is still welcome when OpenRoSDE makes it reachable.

## 🤖 Robots & Safety

The CI of the core never moves a real robot.
It runs every check in a container disconnected from every network, and `gitlab-ci/check-no-motion.bash` fails on any command that could start a motion, as the [Extensions](https://openrosde.org/docs/guides/extensions#-testing-an-extension) guide describes.
A way around these checks, or anything else that could make a robot move unexpectedly, is a security issue, so please report it privately as well.

## 🔑 Secrets

Never paste a password, a token, or the content of `.env.custom` in an issue, a pull request, or a log.
The entry scripts print every `OPENROSDE_*` variable, with its passwords, tokens, and secrets as `<redacted>`, and `OPENROSDE_QUIET=true` leaves the list out.
If a secret leaks anyway, revoke it first, then tell the maintainers through the private channels above.
