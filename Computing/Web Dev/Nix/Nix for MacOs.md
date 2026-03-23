### `nix-darwin` (MacOs-specific binary)

- Nix can replace Homebrew
- Nix for MacOs is called `nix-darwin`

## The Nix Package manager

### First, a primer on Functional Programming

The way in which the Nix Package Manager handles packages on your system has influences from [functional programming](https://www.yld.io/blog/the-not-so-scary-guide-to-functional-programming) . 

According to [yld.io](https://www.yld.io/blog/the-not-so-scary-guide-to-functional-programming), functional programming stipulates that functions which follow it's concept follow two discrete principles:

a) Given the same inputs an implemented function will always return the same output

b) The function will not affect anything outside of the parameters it has been provided when executing (i.e: it will not modify environment values in the execution environment or alter the value of a variable in a parent scope)

The [Nix docs](https://nix.dev/manual/nix/2.28/introduction) state that:

> Nix is a _purely functional package manager_. This means that it treats packages like values in purely functional programming languages such as Haskell - they are built by functions that don’t have side-effects, and they never change after they have been built

Despite the esoteric reference to Haskell, the main point is that  packages which are built by Nix do not affect the rest of the system. 

Other package managers may stipulate [side-effects] by altering system config files etc. For instance, installing a package via `apt` on a Linux system may imply the creation or modification of service files used by [`systemd`](https://systemd.io/).
### 'Nix Store'

The nix store is a central reserve of Nix Packages, located at path `/nix/store`.

Each time a new package is created by the Nix package manager, a unique hash is generated for it - this hash is assigned under the directory name for the contents of the new package.

The hash for a specific package directory is derived from the entire dependency graph for the package itself, thus ensuring no overlap of the hash naming, and all packages can be stored at the base level of `/nix/store/`.  



Multi-user installations are possible, wherein each user registered on the OS has a different 'profile' designated, detailing which packages they are in need of using. Each time that there is an overlap between a specific package version between OS user profiles, Nix will recognise this and use the same package install for both users, eliminating package overlaps. 

### Minimising missing build dependencies

When building packages with a typical (non-declarative) package manager system such as RPM, there is the potential for missing dependencies through oversight, due to pre-existing binaries installed upon your system enabling the build of the package. Because such packages are often taken for granted on your local machine, it can be easy to omit them from the build specification. Once the package is distributed to another machine with a different architecture or OS, the globally-installed package you benefitted from during a build on your local machine is no longer present, and the package build fails

Nix doesn't install dependencies in a globally, so there are not 'global packages' per se. This ensures that build specifications for packages are very likely to be complete.


### Atomic Kitten

Each package operation (i.e: update, remove) in Nix can be guaranteed to be atomic, due to the fact that each different package version is stored in it's own unique file path based upon the unique hash it  is assigned from it's dependency tree.