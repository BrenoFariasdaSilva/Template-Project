### Step 2: Make Your Changes

Before making changes, create a descriptive branch:

```sh
git checkout -b feature/AmazingFeature
```

Follow these guidelines:

- **Test Thoroughly:** Ensure your changes work as intended and do not introduce regressions.
- **Commit Wisely:** Divide changes into small, logically organized commits whenever possible.
- **Follow Standards:** Respect the project's coding conventions and use the official [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/) specification.

### Crafting Your Commit Messages

All commit messages must follow the **Conventional Commits 1.0.0** specification.

**Format:**

```text
<type>[optional scope][!]: <description>

[optional body]

[optional footer(s)]
```

**Rules:**

1. **Type:** Identifies the change. Use `feat` for new features and `fix` for bug fixes.
2. **Scope (optional):** Identifies the affected component, enclosed in parentheses, such as `feat(calculator)`.
3. **Description:** A short summary following the required colon and space (`: `).
4. **Body (optional):** Provides additional context, separated from the description by a blank line.
5. **Footers (optional):** Provide metadata such as issue references or breaking changes.
6. **Breaking changes:** Must be indicated using `!` immediately before `:` or a `BREAKING CHANGE:` footer.

#### Common Commit Types

| Type | Purpose |
|---|---|
| `feat` | Introduce a new feature. |
| `fix` | Fix a bug. |
| `docs` | Add or update documentation. |
| `refactor` | Restructure code without fixing a bug or adding a feature. |
| `test` | Add or update tests. |
| `perf` | Improve performance. |
| `style` | Make formatting changes without affecting behavior. |
| `build` | Modify build systems or dependencies. |
| `ci` | Update continuous integration configurations. |
| `chore` | Perform maintenance tasks. |

**Note:** The specification explicitly defines `feat`, `fix`, and breaking-change notation. Other types are permitted but are not mandated by the specification. This project uses the additional types above for consistency.

#### Examples

**New Feature:**
```text
feat(calculator): add daily electricity cost estimates
```

**Bug Fix:**
```text
fix(storage): prevent duplicate device identifiers
```

**Documentation:**
```text
docs(readme): update installation instructions
```

**Refactoring:**
```text
refactor(charts): simplify chart generation
```

**Tests:**
```text
test(calculations): add standby consumption tests
```

**Performance:**
```text
perf(calculations): reduce redundant computations
```

**Breaking Change:**
```text
feat(storage)!: change the backup file structure
```

Alternatively, use a footer:

```text
feat(storage): update the backup format

BREAKING CHANGE: Existing backup files require migration.
```

**Commit with Body and Footer:**
```text
fix(bill-import): correct Copel tariff extraction

Validate the extracted energy and distribution prices before
applying the calculated tariff.

Closes #123
```

#### Important Conventions

- Use the exact format `<type>[optional scope][!]: <description>`.
- Use lowercase types consistently for this project.
- Scopes are optional and should describe the affected component.
- Separate the description, body, and footers with blank lines.
- Use `BREAKING CHANGE:` in uppercase when declaring a breaking change in a footer.
- Avoid combining unrelated changes into a single commit.
- Do not use the previous custom uppercase formats (`FEAT:`, `FIX:`, `DOCS:`, etc.).

### Navigating Commits

To undo the most recent local commit while preserving its changes in the staging area:

```sh
git reset --soft HEAD^
```

To discard the most recent local commit and its changes:

```sh
git reset --hard HEAD^
```

**Warning:** `git reset --hard` permanently discards uncommitted changes to tracked files. Avoid rewriting commits already shared with others.

### Commit Your Changes

After reviewing and testing your changes, stage and commit them using the conventional format:

```sh
git add .
git commit -m "feat(calculator): add daily electricity cost estimates"
```

Commit messages should accurately describe their changes. Multiple focused commits are preferable to one large commit containing unrelated modifications.

For the complete specification, refer to [Conventional Commits 1.0.0](https://www.conventionalcommits.org/en/v1.0.0/).