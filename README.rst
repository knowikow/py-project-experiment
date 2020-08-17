=======================================================
Experimenting with semantic release for Python projects
=======================================================

Workflows
=========

On push PR to master
--------------------

- Create or update draft release
   - https://github.com/marketplace/actions/gh-release
   - https://github.com/marketplace/actions/generate-changelog (update draft text)
   - https://github.com/marketplace/actions/generate-changelog-using-github-changelog-generator :x:
   - https://github.com/release-drafter/release-drafter :x:
   - https://github.com/actions/create-release
   - https://github.com/sondreb/action-release
- Calculate semver from last vn.n.n tag using PR labels, version = <semver>rcn (PEP-440)
   - https://github.com/marketplace/actions/pr-semver-bump
   - https://github.com/marketplace/actions/semver-release
   - https://github.com/remorses/bump-version (creates versions 1.2.3-rc4, incompatible with PEP-440)
- Update "Unreleased" section of CHANGELOG.md
   - FIXME :question:
- Update Python version variable
   - convert from semver-2 to PEP-440
- Run tests
- Build distribution packages
- Upload to pypi-test
   - https://github.com/pypa/gh-action-pypi-publish :white_check_mark:


On publish release
------------------

- version = <semver>
- Rename "Unreleased" section of CHANGELOG.md to <version>
   - https://github.com/thomaseizinger/keep-a-changelog-new-release
- Update Python version variable
- Run tests
- Build distribution packages
- tag <version>
- Add packages to release
   - https://github.com/actions/upload-artifact
   - https://github.com/actions/upload-release-asset
   - https://github.com/tix-factory/release-manager
- Upload to pypi :white_check_mark:
