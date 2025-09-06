# Astemes LMock Toolkit
[![Image](https://www.vipm.io/package/astemes_lib_lmock/badge.svg?metric=installs)](https://www.vipm.io/package/astemes_lib_lmock/) [![Image](https://www.vipm.io/package/astemes_lib_lmock/badge.svg?metric=stars)](https://www.vipm.io/package/astemes_lib_lmock/)
[![Test Runner](https://github.com/astemes/astemes-lmock/actions/workflows/workflow.yml/badge.svg)](https://github.com/astemes/astemes-lmock/actions/workflows/workflow.yml)

LMock is a LabVIEW mocking toolkit used for automatically generating and maintaining mock classes.
A mock is a test double used, in place of a concrete implementation, when writing automated tests.
This enables testing units of code in isolation, as the interface to the rest of the system is "mocked".
Using a mock the behavior of the code under test can be verified, by checking that the expected VI calls are made.
Furthermore, outputs from calls to the mocked objects can be predefined to stimulate and control the system under test.
The LMock toolkit features an expressive API, powerful scripting features, and detailed failure descriptions.

The easiest way to install LMock is through [VIPM](https://www.vipm.io/package/astemes_lib_lmock/).
LMock is an add-on to [LUnit](https://www.github.com/astemes/astemes-lunit) and is maintained by Astemes under an MIT license.

The full documentation is available at [https://lmock.astemes.com](https://lmock.astemes.com).

A presentation giving an introduction to LMock was given during GLA Summit 2024 and is available [here](https://www.youtube.com/watch?v=AvenQTc_GCc).

## Getting Started

Before beginning to use LMock, you will need to have LUnit installed (available at NI Tools Network and VIPM) and you should be familiar with the toolkit.
Next install the LMock latest package, either from the [Releases](https://github.com/Astemes/astemes-lmock/releases) section of through VIPM.
After installing LMock, the API is available in the LMock Functions Palette and the right-click menus are avaliable after restarting LabVIEW.
Please see the [getting started documeentation](https://lmock.astemes.com/).).

For some general advice on working with mocks, see e.g. [this page](https://github.com/mockito/mockito/wiki/How-to-write-good-tests).


## Test Doubles and Mocks

When writing unit tests there are basically three ways for tests to make assertions about the system under test. 

1. Verify an output given some input data 
2. Verify the state of an external object acted uppn by the unit under test
3. Verify calls to code external to the unit under test

In general, one should have a preference for the earlier types of tests in the list, but there are many cases where it is simply not feasible to have a pure functional VI. 
Test doubles are used to handle the latter items in the listing and are valueable tools for verifying the behavior of the code.
Examples could be interation with instrumentation, the file system, a network, a database, or any situation where one need to verify the interaction with an external component. 

There is a lot of literature available on the subject and it is not the purpose of this document to pharaphrase existing material.
I gave [a presentation](https://www.youtube.com/watch?v=6cfifZbhZsE&t=44s) during GDevCon 2022, which explores unit testing and introduced the concept of mocks.

## Purpose of LMock

While it is pretty easy to write test diubles in LabVIEW, it is a task which becomes repetitive and a bit dull.
Often the same type of code is written or copy/pasted repeatedly in slightly different ways, which makes the tests error prone and unnecessarily difficult to understand.

The reasons why LMock exists is to:

- Enable robust and low maintenance mock-based testing
- Eliminate mistakes and inconsistency caused by manual duplication of boilerplate code
- Improve expressiveness and fault localization of mock-based tests
- Reduce test time through very fast mock code execution
- Reduce development time through automatic code generation
- Minimize friction for creating good design

In many common languages, there is good tooling available for generating and working with mocks.
LMock was inspired by the Java libraries [jMock](http://jmock.org/) and [Mockito](http://mockito.org).
These libraries uses and abuses the syntax of Java to generate very elegant test code, and LMock brings this tradition into LabVIEW with some slightly unorthodox design choices. 

## A Recommendation

If you are new to unit tests and test driven development, learning to use a mocking library is not the best way to get started.
Mocks are powerful tools, but should only be used when direct verification cannot be achieved.
While using a toolkit such as LMock can save some time writing, reading, and maintaining code, it is important that the developer understands the underlying concepts.

## Is it free and open source?

Yes, absolutely!
LMock is released by [Astemes](https://www.astemes.com) under the MIT license.
If you find it useful, please consider starring the project on GitHub and VIPM.

## Versioning

LMock uses semantic version in the format major.minor.fix.build. 
The build version is of little significance as it only denotes the number of the build.
The fix indicates a bug fix, minor feature, or other improvement. 
As new major features are released or the number of minor feature releases accumulates, the minor version is incremented.
Minor version updates are uploaded to VIPM and NI Tools Network after an initial testing period.
These updates should be non-breaking and should not require any changes to the client code.
A major version update would mean that code developed using an earlier version might need modification.

## Support

LMock is an open source toolkit provided as is and without guarantees by [Astemes](https://www.astemes.com). If you encounter issues, use GitHub Issues to report and track the progress. If you have a suggestion for a solution, please consider making pull request. For paid-for professional support, please [contact Astemes directly](https://www.astemes.com/contact).

## Contribute

If you find LMock useful, please share it with your colleagues and network to help grow the user base.
Also, consider starring the project on VIPM or GitHub to let us know that you like it.
If you find a bug, use the Issues section on GitHub.
To take a more active role, please feel free to fork the project and make a pull request.

This toolkit explores ideas and the paradigm for working with mocks in LabVIEW. 
Any kind of feedback, such ass usability improvements, missing features, bug reports or general discussion, is always welcome. 
