# Progress Report: Issue #3748

## Objective
To reproduce and address the bug in `waste.t`, which triggers warnings related to uninitialized variables and numeric operations.

---

## What I Have Done

### Environment Setup
- Cloned the FixMyStreet repository and configured it for local development.
- Set up the application using Docker with the `docker/compose-dev` setup.
- Faced issues with running the test suite due to missing PostgreSQL components (`postmaster` not found in the container).
- Adjusted environment variables (`POSTGRES_HOME` and `PATH`) and verified PostgreSQL binaries, but the setup remained incomplete.

### Dependency Installation
- Attempted to install required Perl modules using `cpanm` inside the Docker container.
- Encountered issues with the `cpanm` installation failing on certain dependencies like `Test::MockModule`.

### Running `waste.t`
- Attempted to directly execute `waste.t` within the Docker container but ran into multiple challenges:
  - "Permission denied" when running the file directly.
  - Errors related to missing Perl dependencies when using `perl controller/waste.t`.
- Explored the possibility of debugging and bypassing the errors but couldn't fully replicate the bug due to the incomplete test environment.

### Configuration Issues
- Encountered errors with `setenv.pl` during the execution of `script/test`. The issue likely stems from missing configurations or unresolved dependencies, preventing the script from running successfully.

---

## Challenges Encountered
- **Dependency Management:** Missing Perl modules and PostgreSQL binaries in the Docker container delayed the setup.
- **Incomplete Test Environment:** Unable to execute `waste.t` due to configuration and dependency issues.
- **Debugging Blockers:** Errors in `setenv.pl` and unresolved dependencies prevented the recreation of the bug.

---

## Next Steps
1. **Resolve the `setenv.pl` Error:**
   - Debug the script and ensure all dependencies and environment variables are properly set.
2. **Address Missing Dependencies:**
   - Install required Perl modules like `Test::MockModule` and verify PostgreSQL setup.
3. **Revisit Bug Reproduction:**
   - Retry running `waste.t` once the environment is fully operational.

---

## Reflection
I tried every possible way I could imagine for days to recreate the bug and failed. I feel stuck on this project and am considering moving on to something else that aligns better with my energy and skills at this time.
