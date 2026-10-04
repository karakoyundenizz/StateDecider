# StateDecider

**Completed during my software engineering internship at KUARTIS in 2026.**

StateDecider is a C++17 / ROS 2 system that monitors managed lifecycle nodes and
reconciles their states with mission targets. **The implementation is complete;
source code exists and is kept private for confidentiality.** This public
repository contains only architecture diagrams and this project overview.

## Architecture

- **Monitor** observes lifecycle transitions, checks node presence and replies,
  and publishes state changes and periodic snapshots. It reports observations
  without issuing state-change commands.
- **Enforcer** compares those observations with mission targets, requests the
  next lifecycle transition asynchronously, and publishes system readiness.
  Communication and decision work are separated by bounded queues.
- Domain and application logic are independent of ROS 2; ROS communication,
  configuration and clocks are handled at the infrastructure boundary.

## Diagrams

| Diagram | Contents |
| --- | --- |
| [System overview](system_drawio/SystemOverview.drawio) | Monitor, Enforcer, managed nodes and the observation / reconciliation loop |
| [Monitor](system_drawio/Monitor.drawio) | State observation, polling, snapshots and interfaces |
| [Enforcer](system_drawio/Enforcer.drawio) | Decision layers, asynchronous transitions and the two-owner runtime (two pages) |

Download a `.drawio` file and open it in [diagrams.net](https://app.diagrams.net/)
or the draw.io desktop application. The diagrams include internal type and
interface names to explain the architecture. References to implementation files
or `ProjectDesign.md` refer to private project materials and are not included here.

## Implementation status and confidentiality

This is a completed software project, not a diagram-only proposal. The private
implementation includes the Monitor and Enforcer, ROS 2 integration, automated
tests, and a browser demo connected to real ROS 2 nodes. Its source code, tests,
configuration, build artifacts and implementation history are not published in
this repository.

[Deniz Karakoyun — portfolio](https://denizkarakoyun.com/?open=experience&item=kuartis)
