**IMPORTANT**: Since version 1.3.0, this is the main repository of Grease. Versions older than 1.1.9 can only be found in the [Smalltalkhub repository](http://www.smalltalkhub.com/#!/~Seaside/Grease11). Check out the [releases list](https://github.com/SeasideSt/Grease/releases) for all version numbers in this repository.

The Grease Portability Library
======
Grease enhances the ANSI Smalltalk standard. With only a few exceptions, we assume platforms are fully ANSI-compliant. Platforms want to support Seaside and standardization makes this easier for the project’s developers and its porters.

Grease defines expected APIs with unit tests. Platforms can quickly determine if they are compatible and users can examine the tests to determine exactly which behaviours they can count on.

Grease takes a pragmatic approach to compatibility. Sometimes a method behaves so differently on two platforms, for example, that we are forced to avoid it or to standardize on a new selector. To get standard exception signaling on all platforms, Grease is forced to provide special exception classes that can be subclassed. Sometimes we need to put “right” aside and settle, instead, on a solution that can be implemented everywhere.

Grease tries to be concise and consistent. Despite its pragmatic approach, we still want to be “right” as much as possible. Because it’s hard to remove functionality once it has been added, we need to carefully consider each addition before proceeding. We’re moving slowly and looking for methods that are commonly used and that have clear names and semantics.

Grease does not try to solve all problems. We are not testing Sockets or HTTP clients. We don’t expect platforms to have standard SSL or graphics libraries. Its scope may grow over time, but for now we’re focusing on extending the functionality of the core classes defined in the ANSI standard (collections, exceptions, streams, blocks, etc.) and on other pieces of functionality that are critical to the Seaside project (e.g. random number generation and secure hashing).

Grease is widely adopted. Implementations exist already for all platforms that support Seaside 3.x. As well as Seaside, new versions of Magritte, Pier, and Monticello are already being implemented on top of Grease.

## Platform compatibility and Travis builds

The latest Grease version is supported on the following platforms and versions, which are tested using [Travis CI builds](https://travis-ci.org/SeasideSt/Grease):

| Squeak          | Pharo            | GemStone             |
| --------------- | ---------------- | -------------------- |
| [![Build status: Squeak-5.2](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=Squeak-trunk&label=5.2)](http://travis-ci.org/SeasideSt/Grease) | [![Build status: Pharo64-9.0](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=Pharo64-9.0&label=9.0)](http://travis-ci.org/SeasideSt/Grease) | [![Build status: Gemstone-3.5.2](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=GemStone-3.5.2&label=3.5.2)](http://travis-ci.org/SeasideSt/Grease) |
| [![Build status: Squeak-5.1](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=Squeak-5.1&label=5.1)](http://travis-ci.org/SeasideSt/Grease) | [![Build status: Pharo64-8.0](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=Pharo64-8.0&label=8.0)](http://travis-ci.org/SeasideSt/Grease) | [![Build status: Gemstone-3.4.5](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=GemStone-3.4.5&label=3.4.5)](http://travis-ci.org/SeasideSt/Grease) |
|                 | [![Build status: Pharo64-7.0](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=Pharo64-7.0&label=7.0)](http://travis-ci.org/SeasideSt/Grease) | [![Build status: Gemstone-3.3.9](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=GemStone-3.3.9&label=3.3.9)](http://travis-ci.org/SeasideSt/Grease) |
|                 | [![Build status: Pharo-6.1](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=Pharo-6.1&label=6.1)](http://travis-ci.org/SeasideSt/Grease) | [![Build status: Gemstone-3.2.17](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=GemStone-3.2.17&label=3.2.17)](http://travis-ci.org/SeasideSt/Grease) |
|                 | [![Build status: Pharo-5.0](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=Pharo-5.0&label=5.0)](http://travis-ci.org/SeasideSt/Grease) | [![Build status: Gemstone-3.1.0.6](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=GemStone-3.1.0.6&label=3.1.0.6)](http://travis-ci.org/SeasideSt/Grease) |
|                 | [![Build status: Pharo-4.0](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=Pharo-4.0&label=4.0)](http://travis-ci.org/SeasideSt/Grease) | [![Build status: Gemstone-2.4.8](http://badges.herokuapp.com/travis/SeasideSt/Grease?branch=master&env=BUILD_NAME=GemStone-2.4.8&label=2.4.8)](http://travis-ci.org/SeasideSt/Grease) |

Coveralls (experimental): [![Coverage Status](https://coveralls.io/repos/github/SeasideSt/Grease/badge.svg?branch=test-coveralls)](https://coveralls.io/github/SeasideSt/Grease?branch=test-coveralls)

## Installation

#### Prerequisite on Squeak

Make sure you have the [MetacelloPreview version](https://github.com/Metacello/metacello), otherwise the load will not work.

### Squeak and Pharo (4.0 or newer)

Load the latest code from master (i.e. stable):

```Smalltalk
Metacello new
    baseline: 'Grease';
    githubUser: 'SeasideSt' project: 'Grease' commitish: 'master' path: 'repository';
    load
```
-or-

Load a specific version:
(See [Releases](https://github.com/SeasideSt/Grease/releases) for a list of versions)

```Smalltalk
Metacello new
    baseline: 'Grease';
    githubUser: 'SeasideSt' project: 'Grease' commitish: 'v1.3.0' path: 'repository';
    load
```
-or-

Legacy: load older versions from Smalltalkhub:
```Smalltalk
Metacello new
    configuration: 'Grease';
    repository: 'http://www.smalltalkhub.com/mc/Seaside/MetacelloConfigurations/main';
    version: '1.0.0';
    load
```

### GemStone

Grease is part of the GLASS setup. You can upgrade your version of Grease using [GsUpgrader](https://github.com/GsDevKit/gsUpgrader).
GsUpgrader works on all versions of GemStone against all versions of GLASS:

```Smalltalk
Gofer new
  package: 'GsUpgrader-Core';
  url: 'http://ss3.gemtalksystems.com/ss/gsUpgrader';
  load.
(Smalltalk at: #GsUpgrader) upgradeGrease.
```

### Pharo (3.0 or older)

The compatibility for Pharo < 4.0 is not maintained for new releases. If you need grease in Pharo < 4, we recommend to either update your pharo version or reference the latest release compatible with Pharo < 4, which is currently v1.4.1.

For Pharo versions < 3.0, make sure you have the [MetacelloPreview version](https://github.com/dalehenrich/metacello-work), otherwise the load will not work.

Load the latest compatible release:

```Smalltalk
Metacello new
    baseline: 'Grease';
    githubUser: 'SeasideSt' project: 'Grease' commitish: 'v1.4.1' path: 'repository';
    load
```

-or-

Legacy: load older versions from Smalltalkhub:
```Smalltalk
Metacello new
    configuration: 'Grease';
    repository: 'http://www.smalltalkhub.com/mc/Seaside/MetacelloConfigurations/main';
    version: '1.0.0';
    load
```

In case you need a specific feature for Pharo 3, it is still possible to create a new release by branching from v1.4.1.
