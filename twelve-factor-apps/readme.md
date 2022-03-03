# I. Codebase
One codebase tracked in revision control, many deploys
![](./codebase.png)

# II. Dependencies
Explicitly declare and isolate dependencies

- **A twelve-factor app never relies on implicit existence of system-wide packages.**
- It declares all dependencies, completely and exactly, via a dependency declaration manifest. (package.json, Gemfile, pip)
- Furthermore, it uses a dependency isolation tool during execution to ensure that no implicit dependencies (system-wide) “leak in” from the surrounding system.
- Twelve-factor apps also do not rely on the implicit existence of any system tools. Examples include shelling out to ImageMagick or curl. While these tools may exist on many or even most systems, there is no guarantee that they will exist on all systems where the app may run in the future, or whether the version found on a future system will be compatible with the app. If the app needs to shell out to a system tool, that tool should be vendored into the app.