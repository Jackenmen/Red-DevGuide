Making dependency changes
=========================

Updating Python package dependencies
------------------------------------

To update all dependencies, the GitHub Actions workflow for generating requirements files should be used:
https://github.com/Cog-Creators/Red-DiscordBot/actions/workflows/run_pip_compile.yaml

Run the above workflow and, after it finishes, download the "merged" artifact archive.
Copy all of the files from this archive to the ``requirements/`` directory in the repository,
overriding any already present files. Now, you can look at the git diff to see
which dependency versions changed.

When updating a dependency to a newer version:

- Verify that all code commented with ``DEP-WARN`` is not affected by the new dependency versions
- Read the changelogs for dependencies to make sure there are no (breaking) changes
  that may affect our code
