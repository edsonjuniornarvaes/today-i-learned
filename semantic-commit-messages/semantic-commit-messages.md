# Semantic Commit Messages

See how a minor change to your commit message style can make you a better programmer.

Format: `<type>(<scope>): <subject>`

`<scope>` is optional

## Example

```
feat: add hat wobble
^--^  ^------------^
|     |
|     +-> Summary in present tense.
|
+-------> Type: chore, docs, feat, fix, refactor, style, or test.
```
- `feat`: (new feature for the user, not a new feature for build script)
- `fix`: (bug fix for the user, not a fix to a build script)
- `docs`: (changes to the documentation)
- `style`: (formatting, missing semi colons, etc; no production code change)
- `refactor`: (refactoring production code, eg. renaming a variable)
- `test`: (adding missing tests, refactoring tests; no production code change)
- `chore`: (updating grunt tasks etc; no production code change)

More Examples:

## Conventional Commits
The commit contains the following structural elements, to communicate intent to the consumers of your library:

fix: a commit of the type fix patches a bug in your codebase (this correlates with PATCH in semantic versioning).
feat: a commit of the type feat introduces a new feature to the codebase (this correlates with MINOR in semantic versioning).
BREAKING CHANGE: a commit that has the text BREAKING CHANGE: at the beginning of its optional body or footer section introduces a breaking API change (correlating with MAJOR in semantic versioning). A breaking change can be part of commits of any type. e.g., a fix:, feat: & chore: types would all be valid, in addition to any other type.
Others: commit types other than fix: and feat: are allowed, for example @commitlint/config-conventional (based on the the Angular convention) recommends chore:, docs:, style:, refactor:, perf:, test:, and others. We also recommend improvement for commits that improve a current implementation without adding a new feature or fixing a bug. Notice these types are not mandated by the conventional commits specification, and have no implicit effect in semantic versioning (unless they include a BREAKING CHANGE, which is NOT recommended). A scope may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis, e.g., feat(parser): add ability to parse arrays.
Examples
Commit message with description and breaking change in body
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
Commit message with no body
docs: correct spelling of CHANGELOG
Commit message with scope
feat(lang): added polish language
Commit message for a fix using an (optional) issue number.
fix: minor typos in code

see the issue for details on the typos fixed

fixes issue #12

References:

- https://seesparkbox.com/foundry/semantic_commit_messages
- https://www.conventionalcommits.org/