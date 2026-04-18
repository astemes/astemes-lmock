# LMock

[![VIPM installs](https://www.vipm.io/package/astemes_lib_lmock/badge.svg?metric=installs)](https://www.vipm.io/package/astemes_lib_lmock/)
[![VIPM stars](https://www.vipm.io/package/astemes_lib_lmock/badge.svg?metric=stars)](https://www.vipm.io/package/astemes_lib_lmock/)
[![Test, Build and Release](https://github.com/astemes/astemes-lmock/actions/workflows/workflow.yml/badge.svg)](https://github.com/astemes/astemes-lmock/actions/workflows/workflow.yml)

LMock is a mocking toolkit for LabVIEW that automatically generates and maintains mock classes for use in unit tests. It is an add-on to [LUnit](https://github.com/astemes/astemes-lunit) and features an expressive API, powerful scripting for mock generation, and detailed failure descriptions.

Full documentation: **[lmock.astemes.com](https://lmock.astemes.com)**

## Why LMock

Writing test doubles by hand in LabVIEW is easy but repetitive, and the same boilerplate tends to get copy-pasted in slightly different ways across a project. That makes tests error-prone and harder to read than they need to be. LMock exists to:

- Enable robust and low-maintenance mock-based testing
- Eliminate mistakes and inconsistency caused by manual duplication of boilerplate
- Improve expressiveness and fault localization in mock-based tests
- Reduce test execution time through very fast mock code
- Reduce development time through automatic code generation
- Minimize friction for creating good design

LMock was inspired by the Java libraries [jMock](http://jmock.org/) and [Mockito](http://mockito.org), which use (and abuse) the syntax of Java to produce very elegant test code. LMock brings this tradition into LabVIEW with some slightly unorthodox design choices.

## Prerequisites

- **LUnit** must be installed — see the [LUnit repository](https://github.com/astemes/astemes-lunit) for LabVIEW and OS requirements.
- You should be familiar with LUnit before starting with LMock.

## Installation

The recommended way to install LMock is via [VI Package Manager (VIPM)](https://www.vipm.io/package/astemes_lib_lmock/). This installs the latest stable release.

Pre-release builds are available on the [GitHub Releases page](https://github.com/Astemes/astemes-lmock/releases) as VIPM packages that can be installed manually through VIPM.

After installation, restart LabVIEW. The API is then available on the LMock Functions Palette and the right-click menus are active.

## Getting started

See the [getting started documentation](https://lmock.astemes.com) for a full walk-through. The typical workflow is:

1. Identify the interface (a LabVIEW class) that the code under test depends on.
2. Use LMock's code generation to produce a mock class for that interface.
3. In your test, configure the mock — set expected calls and predefine outputs to stimulate the system under test.
4. Inject the mock in place of the real implementation, run the test, and LMock verifies the expected interactions.

For general advice on working with mocks, see Mockito's [How to write good tests](https://github.com/mockito/mockito/wiki/How-to-write-good-tests).

## When to use mocks

When writing unit tests there are essentially three ways to assert something about the system under test:

1. Verify an output given some input data.
2. Verify the state of an external object acted upon by the unit under test.
3. Verify calls to code external to the unit under test.

Prefer the earlier types in the list whenever possible, but there are many cases where a pure functional VI is not feasible. Test doubles — mocks, stubs, fakes — are how you handle the third case: verifying interaction with instrumentation, the file system, a network, a database, or any external component.

**A recommendation:** if you are new to unit testing and test-driven development, learning a mocking library is not the best place to start. Mocks are powerful tools, but should only be used when direct verification cannot be achieved. A toolkit like LMock can save time writing, reading, and maintaining tests, but it is important that the developer understands the underlying concepts first.

## Learning resources

- Full documentation: [lmock.astemes.com](https://lmock.astemes.com)
- [Introduction to LMock — GLA Summit 2024](https://www.youtube.com/watch?v=AvenQTc_GCc)
- [Unit testing and mocks — GDevCon 2022](https://www.youtube.com/watch?v=6cfifZbhZsE&t=44s)
- [Mocks and Functional Programming — GDevCon 2025](https://www.youtube.com/watch?v=OV9L9G1TFvA))

There is a lot of literature available on test doubles more broadly, and it is not the purpose of this README to paraphrase existing material.

## Is it free and open source?

Yes, absolutely. LMock is released by [Astemes](https://www.astemes.com) under the MIT license. If you find it useful, please consider starring the project on GitHub and VIPM.

## Versioning

LMock uses semantic versioning in the form `major.minor.fix.build`:

- **Build** — build number, no significance beyond identification.
- **Fix** — bug fixes, minor features, and improvements.
- **Minor** — non-breaking updates. Published to VIPM and NI Tools Network after an initial testing period. No client code changes should be needed.
- **Major** — may require changes to code developed against earlier versions.

## Support

LMock is provided as-is and without guarantees by [Astemes](https://www.astemes.com). To report bugs or track progress, use [GitHub Issues](https://github.com/astemes/astemes-lmock/issues). If you have a solution in mind, a pull request is very welcome. For paid professional support, [contact Astemes directly](https://www.astemes.com/contact).

## Contributing

If you find LMock useful, please share it with colleagues and your network to help grow the user base, and consider starring the project on GitHub or VIPM.

This toolkit explores ideas and a paradigm for working with mocks in LabVIEW — feedback of any kind (usability improvements, missing features, bug reports, or general discussion) is always welcome. For bugs, open an issue. To contribute code, fork the project and open a pull request.
