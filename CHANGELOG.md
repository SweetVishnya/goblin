# Changelog
All notable changes to this project will be documented in this file.

Before 1.0, this project does not adhere to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

I'm sorry, I will try my best to ease breaking changes.  We're almost to 1.0, don't worry!

## [Unreleased]
### Changed
- all scroll::Error have been removed from public API ref #33
- more elf relocations
- mach relocations
- better mach symbol iteration
- better mach section iteration
- relocation iteration
- convenience functions for many elf structures that elf writer will appreciate
- remove wow_so_meta_doge due to linker issues
- Strtab.get now returns a Option<Result>, when index is bad
- elf.soname is &str
- elf.libraries is now Vec<&str>

## [0.0.10] - 2017-05-09
### Added
- New goblin::Object for enum containing the parsed binary container, or convenience goblin::parse(&[u8) for parsing bytes into respective container format
### Changed
- All binaries formats now have lifetimes
- Elf has a lifetime
- Strtab.new now requires a &'a[u8]
- Strtab.get now returns a scroll::Result<&'a str> (use strtab[index] if you want old behavior and don't care about panics); returning scroll::Error is a bug, fixed in next release

## [0.0.9] - 2017-04-05
### Changed
- Archive has a lifetime
- Mach has a lifetime