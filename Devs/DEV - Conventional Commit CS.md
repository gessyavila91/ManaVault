### **Conventional Commit Cheat Sheet**

| **Type**     | **Explanation**                                                                                       | **Example**                        |
| ------------ | ----------------------------------------------------------------------------------------------------- | ---------------------------------- |
| **feat**     | Introduces a new feature to the codebase.                                                             | `feat: add user login feature`     |
| **fix**      | Fixes a bug or issue in the code.                                                                     | `fix: resolve login crash`         |
| **docs**     | Documentation-only changes (e.g., README updates, comments).                                          | `docs: update API usage`           |
| **style**    | Changes related to code style (e.g., formatting, missing semicolons) that don't affect functionality. | `style: fix code indentation`      |
| **refactor** | Code changes that neither fix a bug nor add a feature but improve structure or readability.           | `refactor: simplify auth flow`     |
| **perf**     | Improves performance without altering functionality.                                                  | `perf: optimize image loading`     |
| **test**     | Adds or updates tests.                                                                                | `test: add unit tests for login`   |
| **chore**    | Maintenance tasks or auxiliary updates (e.g., tool config, package.json changes).                     | `chore: update eslint config`      |
| **build**    | Changes that affect the build system or external dependencies (e.g., npm, Gradle).                    | `build: update webpack config`     |
| **ci**       | Changes to CI configuration files or scripts (e.g., GitHub Actions, Jenkins).                         | `ci: add test coverage workflow`   |
| **revert**   | Reverts a previous commit.                                                                            | `revert: undo feat add user login` |
| **wip**      | Work in progress that isn't ready for production (optional in some teams).                            | `wip: begin dashboard layout`      |
| **deps**     | Updates or modifies project dependencies.                                                             | `deps: bump lodash to v4.17.21`    |

---

### **Additional Notes**

1. **Scope**: Add a scope in parentheses after the type for clarity.
***Example:***
>feat(auth): add JWT token validation

1. **Breaking Changes**: Indicate breaking changes with `!` after the type and before the colon.
***Example:***
>feat!: drop support for Node.js 12

1. **Footer for Breaking Changes**: Use `BREAKING CHANGE:` in the commit message body to explain breaking changes.
***Example:***
>BREAKING CHANGE: This removes compatibility with Node.js 12. Please upgrade to Node.js 14 or newer.

4. **Body (Optional)**: Provide additional context or justification in the body of the commit message.
***Example:***
>fix(auth): resolve token expiration issue  Previously, tokens would expire prematurely due to incorrect timestamp handling.

---

### **Good and Bad Practices with Examples**

#### 1. **Write Clear, Concise Messages**

- **Good Practice:** Use clear, actionable descriptions under 72 characters.  
***Example:***
>feat(auth): add support for OAuth 2.0 authentication

- **Bad Practice:** Avoid vague or generic messages like "update" or "fix stuff."  
***Example:***
>feat: update stuff


---

#### 2. **Use Scopes to Clarify Context**

- **Good Practice:** Add a meaningful scope to identify the affected part of the codebase.  
***Example:***
>fix(ui): correct button alignment in navbar

- **Bad Practice:** Omitting scope can confuse others about the context.  
***Example:***
>fix: correct button alignment

---

#### 3. **Mention Breaking Changes Properly**

- **Good Practice:** Use `!` after the type and include a `BREAKING CHANGE:` footer.  
***Example:***  
>feat!: remove legacy user roles  BREAKING CHANGE: The `admin` and `editor` roles have been replaced with `superuser`.

- **Bad Practice:** Not declaring breaking changes leads to confusion during updates.  
***Example:***
>refactor(core): remove legacy user roles

---

#### 4. **Provide Context in the Body**

- **Good Practice:** Add a body to explain why or how the change was made (for complex changes).  
***Example:***  
>refactor(core): simplify data processing logic  The previous implementation had redundant steps and unnecessary checks.

- **Bad Practice:** No explanation for significant changes, leaving others guessing.  
***Example:***
>refactor(core): simplify data processing logic

---

#### 5. **Combine Small Related Changes**

- **Good Practice:** Group closely related changes into a single commit.  
***Example:***
>chore(deps): update React to v18 and ESLint rules

- **Bad Practice:** Don’t mix unrelated changes in one commit.  
***Example:***
>feat: add search bar and fix footer alignment

---

#### 6. **Misusing Commit Types**

- **Good Practice:** Use types (`feat`, `fix`, `chore`, etc.) appropriately for their purpose.  
***Example:***
>chore(deps): update lodash to v4.17.21

- **Bad Practice:** Using `feat` for non-feature changes like dependency updates.  
***Example:***
>feat: update dependencies

---

#### 7. **Committing Work in Progress**

- **Good Practice:** Use descriptive commit messages for incomplete work. (Optional: `wip` for branches).  
***Example:***
>feat(dashboard): implement initial layout

- **Bad Practice:** Commit "WIP" messages directly to production branches.  
***Example:***
>wip: dashboard implementation





    