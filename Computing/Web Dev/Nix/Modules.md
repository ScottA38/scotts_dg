A modules is a file containing a Nix expression in a specific structure.

It can be used as a function, defining specific required arguments for input

```
{ config, pkgs, ... }:

imports {
	...
}
```