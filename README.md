# DEV

Development environment setup instructions.

## Git hooks

Based on [conventional commits](https://www.conventionalcommits.org/) and follows [semantic versioning](https://semver.org/).

### Installation

```sh
git config --global core.hooksPath <path_to_hooks_folder>
```

> [!TIP]
>
> Validate installation by trying to commit with an invalid commit message. This operation should throw an error `[ERROR] ...`.

### Commit message structure

```
<type>[!]: <issue> <description>

[body]

[footer(s)]
```

> [!NOTE]
>
> - Line length cannot exceed 80 characters.
> - The body should be composed of well structured sentences (uppercase letters and commas).

### Commit types

| Type       | Title                 | Description                                                                            | Semantic vesion bump |
| ---------- | --------------------- | -------------------------------------------------------------------------------------- | -------------------- |
| `feat`     | Feature               | Adds a new feature                                                                     | `MINOR`              |
| `fix`      | Bug fix               | Fixes a bug                                                                            | `PATCH`              |
| `docs`     | Documentation         | Documentation change                                                                   | `PATCH`              |
| `style`    | Code style            | Code change that does not modify the meaning of the code (whitespace, formatting, etc) | None                 |
| `refactor` | Code refactor         | Code change that is neither a new feature nor a bugfix                                 | `PATCH`              |
| `perf`     | Performance           | Performance improvements                                                               | `MINOR`              |
| `test`     | Test                  | Add or correct tests                                                                   | None                 |
| `build`    | Build                 | Changes to build system                                                                | None                 |
| `ci`       | Continous integration | Changes to CI system                                                                   | None                 |
| `chore`    | Chore                 | Other changes                                                                          | None                 |
| `revert`   | Revert                | Revert a commit                                                                        | None                 |

## Git workflow

- Do not commit on `main` and `dev` branches directly.
- Every **issue** must be assigned to a **branch** to which all commits are to be made.
- Feature branches must follow a naming scheme of `<type>/<branch_name>` (e.g. `ci/buildSystem`).
- After a feature/fix/... has been developed, the branch is merged into `dev` branch using a **pull request**, which deletes the branch after the merge.
- Feature branches are based from `dev` branch and are to be updated using a **pull request branch** on merge **conflicts**.

> [!IMPORTANT]
>
> To use private repos, run the following commands
>
> ```sh
> git config --global url.git@github.com:.insteadOf https://github.com/
> ```
>
> ```sh
> export GOPRIVATE=github.com/RSOPMS/framework
> ```

## Live server

Install [air-verse/air](https://github.com/air-verse/air)

```sh
go install github.com/air-verse/air@latest
```
