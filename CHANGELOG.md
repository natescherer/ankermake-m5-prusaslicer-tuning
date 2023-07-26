# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]
### Added
- Added `Print Settings` profiles: '0.20mm NORMAL @M5-TUNED', '0.10mm DETAIL @M5-TUNED'
- Added `Filament Settings` profiles: 'Generic TPU @M5-TUNED'

### Changed
- Profile versioning moved into the notes for each profile via M5-TUNED_PROFILE_VERSION_# lines
- Profile naming standardized so that all profiles use the suffix '@M5-TUNED'
- `Print Settings` profiles updated for AnkerMake CE v2.3.1: 'Calibration - Extrusion Multiplier', 'Calibration - Full Bed Test'
- `Filament Settings` profiles updated for AnkerMake CE v2.3.1: 'Generic PETG @M5-TUNED', 'Generic PLA @M5-TUNED', 'Generic PLA+ @M5-TUNED', 'Generic Silk PLA @M5-TUNED', 'Inland Luminous PLA @M5-TUNED', 'Inland Marble PLA @M5-TUNED', 'Inland PETG+ @M5-TUNED', 'Inland PLA+ @M5-TUNED', 'Inland Silk PLA @M5-TUNED'
- `Printer Settings` profiles updated for AnkerMake CE v2.3.1: 'Calibration - Temperature Tower @M5-TUNED'

### Removed
- Per-Filament Print Settings profiles, as per-filament speed is now controlled by Max volumetric speed setting

### Fixed
- Extrusion multiplier set to default 0.97 for all Generic filament profiles
- Cost reset to 0 for all filaments
- Specific filaments now inherit from the @M5-TUNED profiles rather than @ANKER-CE profiles

## [0.1] - 2023-06-26
### Added
- Initial release

[Unreleased]: ENTER-URL-HERE
[0.1]: ENTER-URL-HERE