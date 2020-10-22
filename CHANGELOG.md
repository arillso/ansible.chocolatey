# Changelog

This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html)
and [human-readable changelog](https://keepachangelog.com/en/1.0.0/).

## 1.3.6

### Fixed

- Solution of the problem that meta must not have any conditions.

## 1.3.5

### Fixed

- Added Reset_connection

## 1.3.4

### Fixed

- Added Task Restart sshd for ENV:PATH.

### Added

- Adding Super Lint.

## 1.3.3

### Changed

- `useRememberedArgumentsForUpgrades` from false to true.

## 1.3.2

### Fixed

- If `state` or `source` is empty, it will continue to run.

## 1.3.1

### Changed

- Disabled features usePackageRepositoryOptimizations and useEnhancedExitCodes by default
- Changelog has been moved to its own file
- Travis file has been updated
- Documentation has been improved

### Added

- Molecule testing

### Fixed

- Add missing tags

## 1.3.0

### Changed

- Updated min ansible version to 2.7
- Make chocolatey config idempotent
- Switch to using win_chocolatey\* modules

### Added

- Add chocolatey to windows path

## 1.2.0

### Added

- Add support chocolatey feature

## 1.1.0

### Added

- Add support for choco config

### Changed

- Add change remove source when absent

## 1.0.0

### Added

- Initial release
