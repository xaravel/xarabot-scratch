---
name: bmad-build-auto
description: "Stand-in for the stock bmad-build-auto in the Xarabot scratch repo. Builds one Story by writing two files, then halts done. Use when told to run bmad-build-auto with a line like: Build Story 1.6 (`1-6-some-key`)."
---

# bmad-build-auto (scratch stand-in)

This scratch repo has no BMAD install. This skill stands in for the stock `bmad-build-auto`, so a real session builds a Story here in about a minute.

## Input

One line, of this form:

```text
Build Story <e>.<s> (`<key>`)
```

`<e>` is the Epic number, `<s>` the Story number and `<key>` the Story's sprint key, which starts with `<e>-<s>-`. If the input has another form, halt `blocked`: the input names no Story.

## Steps

1. Write the file `verify/<key>.md` holding this line:

   ```text
   Built for <key>.
   ```

2. Write the file `_bmad-output/implementation-artifacts/spec-<e>-<s>-verify.md` holding exactly this text, with `<e>`, `<s>` and `<key>` filled in:

   ```markdown
   ---
   title: 'Story <e>.<s>: a scratch build'
   status: done
   followup_review_recommended: false
   ---

   # Story <e>.<s>: a scratch build

   Built <key>: wrote verify/<key>.md.

   ## Auto Run Result

   Status: done
   ```

3. Change nothing else: no other file, no commit, no branch, no other skill. There are no verification commands to run.
4. Halt `done`.
