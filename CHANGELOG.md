## [1.1.1](https://github.com/marslo/github-optimized-layout/compare/v1.1.0...v1.1.1) (2026-07-23)

### Bug Fixes

* fix: keep issues-list nav sidebar at its natural width

### CI/CD

* ci(releaserc.js): upgrade releaserc.js for `conventional-changelog-conventionalcommits` - v10.0.0 BREAKING CHANGES
  - check more : https://github.com/conventional-changelog/conventional-changelog/commit/78761ae19b4711260d015f599316f2558804cbbc
  - release notes: https://github.com/conventional-changelog/conventional-changelog/releases/tag/conventional-changelog-conventionalcommits-v10.0.0

## [1.1.0](https://github.com/marslo/github-optimized-layout/compare/v1.0.6...v1.1.0) (2026-06-11)

### ⚠ BREAKING CHANGE

* set 85vw width for commits history page and branch list page

Signed-off-by: marslo <marslo.jiao@gmail.com>

### refactor

* refactor!: remove full width(100%) for commits(history) and branch list

BREAKING CHANGE: set 85vw width for commits history page and branch list page

## [1.0.6](https://github.com/marslo/github-optimized-layout/compare/v1.0.5...v1.0.6) (2026-06-11)

### fix

* fix: branch show layer after selection abnormal, set the text center vertically

## [1.0.5](https://github.com/marslo/github-optimized-layout/compare/v1.0.4...v1.0.5) (2026-05-20)

### ci

* ci: fix the 'Node.js 20 actions are deprecated' issue in pre-commit workflow
* ci: remove `Signed-off-by` from changelog and release notes
* ci: update pre-commit workflow

## [1.0.4](https://github.com/marslo/github-optimized-layout/compare/v1.0.3...v1.0.4) (2026-05-20)

### CI/CD

* ci(workflow): using pre-commit workflow instead of pre-commit application - to prevent PR auto creation
  Signed-off-by: marslo <marslo.jiao@gmail.com>

### Others

* chore: widen the Contribution Calendar (green cell)
  Signed-off-by: marslo <marslo.jiao@gmail.com>

### Bug Fixes

* fix: resolving the issue of cells being uneven in width
  Signed-off-by: marslo <marslo.jiao@gmail.com>

## [1.0.3](https://github.com/marslo/github-optimized-layout/compare/v1.0.2...v1.0.3) (2026-05-15)

### Bug Fixes

* fix(action): fixed the bug that limited the width (85vw) of the Action and Models page
  - identity full-width React page automatically by excluding the app-name="code-view"

  Signed-off-by: marslo <marslo.jiao@gmail.com>

## [1.0.2](https://github.com/marslo/github-optimized-layout/compare/v1.0.1...v1.0.2) (2026-05-15)

### CI/CD

* ci: introduce the semantic-release rc file, and update the version in css automatically
  Signed-off-by: marslo <marslo.jiao@gmail.com>

## [1.0.1](https://github.com/marslo/github-optimized-layout/compare/v1.0.0...v1.0.1) (2026-05-14)

### Bug Fixes

* fix: prevent subsequent sibling nodes being squeezed or forced to wrap to a newline in PR list
  - sibling nodes: review required, update time, branch name

  Signed-off-by: marslo <marslo.jiao@gmail.com>

## 1.0.0 (2026-05-14)

### Others

* chore: add project docs, stylelint, and pre-commit config
  Signed-off-by: marslo <marslo.jiao@gmail.com>

### Features

* feat(init): init the github-optimized-layout.user.css
  Signed-off-by: marslo <marslo.jiao@gmail.com>
