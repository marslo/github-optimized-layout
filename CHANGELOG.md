## [1.1.10](https://github.com/marslo/github-optimized-layout/compare/v1.1.9...v1.1.10) (2026-11-25)

### Bug Fixes

* **layout**: restore equal split diff columns ([8f1397a](https://github.com/marslo/github-optimized-layout/commit/8f1397a5dbc123943f2d334f516b5a3886d638b7))
  - restore `table-layout: fixed` on react diff tables tagged `.rgh-no-split-diff`
  - override the `table-layout: auto !important` set by refined-github `no-unnecessary-split-diff-view`
  - scope to `[class*="diffLines__"]` so other tables are unaffected

### CI/CD

* **release**: use function templates for changelog notes ([5c771cc](https://github.com/marslo/github-optimized-layout/commit/5c771cc56918a499a73d4cafa502dab667960824))
  - replace Handlebars `mainTemplate` / `headerPartial` / `commitPartial` strings with function versions
  - add `template`, `preamblePartial` and `footerPartial` for `conventional-changelog-writer` 9
  - fix `headerPartial is not a function` on `semantic-release` 26

## [1.1.9](https://github.com/marslo/github-optimized-layout/compare/v1.1.8...v1.1.9) (2026-11-20)

### Bug Fixes

* **github-optimized-layout**: stack packages registry card items ([ea362c3](https://github.com/marslo/github-optimized-layout/commit/ea362c321789c74ecb1ba813feb853d772c29a0d))
  - force the card body `flex-row flex-wrap` into a column
  - keep the `Learn more` button left-aligned
  - scope rules via `:has()` to the registry cards only
* **layout**: center release page meta row icons ([22e9675](https://github.com/marslo/github-optimized-layout/commit/22e9675e4f8897f80372f7071c9ed3e030a94c66))
  - center the meta row and each of its items vertically
  - center the icon and text inside the tag / commit / compare links
  - drop the inline `top: 1px` nudge on the commit item
* **tampermonkey**: judge trailing whitespace per diff line ([e570886](https://github.com/marslo/github-optimized-layout/commit/e57088630e4d3e2b1bdad9c909185f1dac408d89))
  - walk each line's text nodes from the end instead of a span's siblings, so spaces nested in a token before an inline comment are no longer flagged
  - mark tab spans as well as spaces ( `[data-rgh-whitespace]` )
  - bump the trailing whitespace highlighter to `1.1.0` and refresh the Tampermonkey backup
  - describe the per-line algorithm in the README and note that the Stylus dot-hiding CSS leaves the red highlight alone

## [1.1.8](https://github.com/marslo/github-optimized-layout/compare/v1.1.7...v1.1.8) (2026-11-17)

### Bug Fixes

* **layout**: baseline-align PR review and timeline headers ([362736d](https://github.com/marslo/github-optimized-layout/commit/362736d40268493e2e353aa5aeb72b247a463569))
  - baseline-align the file name and `Line N` in the review thread header
  - baseline-align the author name and `Bot` label in timeline comment headers
* **layout**: make Agents sessions list 100% wide ([24268a2](https://github.com/marslo/github-optimized-layout/commit/24268a2bde4caf528f87b6607448775f7b512fe1))
  - stop excluding `#session-filter` pages from the auto full-width React page rule, so the Agents sessions list root is 100% again
  - keep releasing the 1280px `content__*` cap so the page body fills the root
* **layout**: show the whole commit message in the check run header by releasing github's `max-width: 500px !important` cap on `h2.check-page-commit-message` ([ca2288d](https://github.com/marslo/github-optimized-layout/commit/ca2288dcf6e02aaab4362fd8dc68d6774ac8b770))

## [1.1.7](https://github.com/marslo/github-optimized-layout/compare/v1.1.6...v1.1.7) (2026-11-11)

### Bug Fixes

* **layout**: cap Agents sessions list at 85vw ([bee71ec](https://github.com/marslo/github-optimized-layout/commit/bee71ecc9340a563e15e7cc9ef90ac14fb9cc837))
  - exclude pages containing `#session-filter` from the auto full-width React page rule
  - release the 1280px `content__*` max-width so the body fills the root
* **layout**: restore 85vw on PR overview and commits ([53cb2d6](https://github.com/marslo/github-optimized-layout/commit/53cb2d62393fe5041c644945b4a23698093122a8))
  - replace `#session-filter` with `[id="session-filter"]` in the auto full-width rule exclusion
  - stop the full-width rule from outranking the id-based overview and commits 85vw rule
  - note in the comment to keep attribute selectors inside `:not(:has())`

## [1.1.6](https://github.com/marslo/github-optimized-layout/compare/v1.1.5...v1.1.6) (2026-11-10)

### Bug Fixes

* **layout**: cap PR overview and commits at 85vw ([7a083d5](https://github.com/marslo/github-optimized-layout/commit/7a083d57b80234d2de32ff2be18bb32209c19cfd))
  - cap the shared `#diff-comparison-viewer-container` root at `--gh-custom-width` for overview and commits content
  - match `.js-pull-discussion-timeline` so the page stays 85vw after posting a reply
  - release `constrainedHeader__*` and `constrainedContent__*` max-width so title and body fill their root
  - keep checks and files changed full width

### CI/CD

* **release**: drop breaking-change footer from notes body ([86d87ff](https://github.com/marslo/github-optimized-layout/commit/86d87ff51437e92417a72ea8b1a70be08d7b3fcc))
  - add `stripNotes()` to remove `BREAKING CHANGE:` / `BREAKING-CHANGE:` blocks folded into the commit body
  - keep trailers after a note, such as `Closes #N`
  - collapse repeated blank lines and trim trailing blanks in the rendered body

## [1.1.5](https://github.com/marslo/github-optimized-layout/compare/v1.1.4...v1.1.5) (2026-10-20)

### Bug Fixes

* **layout**: adapt width rules to hashed css-module classes ([80993e3](https://github.com/marslo/github-optimized-layout/commit/80993e3e71f2bf2f27d9a41906ed8e64b2f4d6b3))
  - force full width on tree/blob views via `#repos-file-tree`, `expand-file-tree-button` and `breadcrumbs`, replacing the dead `ReposFileTree` selector
  - keep repo overview and issue detail at 85vw by excluding `.overview-ref-selector` and `issue-header` from the full-width React rule
  - lift the 1280px cap on issue detail `contentContainer__*` and new-issue `createPane__*` / `createPaneContainer__*`
  - add `max-width: 100%` to the MergeBox title input to override RGH `min-content`
  - bump stylelint hook to `v17.16.0` and typos to `v1.51.1`

## [1.1.4](https://github.com/marslo/github-optimized-layout/compare/v1.1.3...v1.1.4) (2026-08-26)

### CI/CD

* **changelog**, **releaserc.js**: format commit lines with bold scopes and per-commit sha links ([0125a63](https://github.com/marslo/github-optimized-layout/commit/0125a638d6a770aaa834f6085ed0dc61c206c81c))

## [1.1.3](https://github.com/marslo/github-optimized-layout/compare/v1.1.2...v1.1.3) (2026-08-07)

### Bug Fixes

* fix(issues): keep issue/PR detail header title full-width on widened pages

### CI/CD

* ci(releaserc.js): add solution to update changelog with or without `changelogTitle`

## [1.1.2](https://github.com/marslo/github-optimized-layout/compare/v1.1.1...v1.1.2) (2026-07-28)

### CI/CD

* ci(releaserc.js): sync up with `$HOME/.releaserc.js`

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
