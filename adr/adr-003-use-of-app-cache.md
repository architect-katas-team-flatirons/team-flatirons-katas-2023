# ADR-003: Use of an App Cache

The proposed deployment architecture for The Road Warrior includes an app cache. This is meant to ensure improved performance

## Status
Accepted

## Decision
One of the significant NFRs for The Road Warrior platform is Performance. Given this requirement it has been decided to use an app caches.

## Consequences
The use of an app cache introduces the risk of stale data. However it has been determined that the risk is manageable with a combination of code and cache retention policies.