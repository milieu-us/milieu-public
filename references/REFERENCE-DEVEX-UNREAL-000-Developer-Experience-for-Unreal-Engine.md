# REFERENCE-DEVEX-UNREAL-000 - Developer Experience for Unreal Engine

- **ID:** REFERENCE-DEVEX-UNREAL-000
- **Status:** Working Draft
- **Created:** 2026-03-06
- **Updated:** 2026-04-11

## Intent

Use this reference record as an informal informational guide. This is not for policy or decisions. Feel free to add notes as needed. Attempt to keep this approximately ordered by what a new developer or technical artist may encounter when running or building Unreal Engine projects either manually or on-demand.

## Live Coding Is Not Trusted for Structural Build Changes

Live Coding may be used for ordinary implementation iteration once the development environment is stable, but it is not the trusted path for changes involving:

- Build.cs
- plugin enablement
- module graph changes
- reflection layout changes

Such changes require editor-closed rebuilds.
