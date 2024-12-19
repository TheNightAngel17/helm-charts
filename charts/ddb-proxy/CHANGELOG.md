# Changelog

This changelog is based off of the [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) format.

## [Unreleased]

## [0.1.0] | Initial Release

### Added

- README.md updates
- CHANGELOG.md

## Changed

- Re-Added probes for `/ping` endpoint
- Added chart details
- Moved tag to hard-coded version

## [0.1.0] | Initial Release

### Added

- New chart from `helm create ddb-proxy`

## Changed

- Defined values as needed
  - Image Repository & Tag to latest
  - Service Port
  - Removed probes as main path returns `Cannot GET`, and IDK if that'll mess things up or not
