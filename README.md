## Description

When opening a Pull Request from Colibri for the first time in a newly loaded repository, the PR is not created on GitHub.

The UI switches from **Open PR** to **Show PR**, but:
- No toast notification appears
- No Pull Request is actually created

After reloading Colibri and trying again, the PR creation works correctly.

## Steps to Reproduce

1. Load a new repository into Colibri.
2. Make a change in the README.
3. Create an annotation.
4. Click **Open Pull Request**.
5. Wait until the button changes from `Open PR` to `Show PR`.
   - A toast notification is expected here but does not appear.
6. Check GitHub → No PR has been created.
7. Copy the Colibri room URL.
8. Reload Colibri using the same URL.
9. The button now shows `Open PR` again.
10. Click **Open PR**.
11. Colibri switches to **Show PR** and a toast notification appears.
12. Check GitHub → The PR is now created.

## Expected Behavior

- The Pull Request should be created on the first attempt.
- A toast notification should appear confirming the PR creation.
- The UI state should match the actual PR status on GitHub.

## Actual Behavior

- The first attempt fails silently.
- No PR is created.
- The toast notification is missing.
- The UI switches to `Show PR` even though no PR exists.
- After a reload, the process works as expected.

## Impact

- Users may think the PR was created when it was not.
- Creates confusion and breaks the expected workflow.
- Requires a manual reload to fix.

## Acceptance Criteria

- PR creation works on the first attempt.
- Toast notification appears after successful PR creation.
- UI state reflects the real GitHub PR status.
- No reload should be required.
