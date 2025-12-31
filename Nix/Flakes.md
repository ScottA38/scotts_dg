A flake is a declarative document of:
- **inputs** (package repositories and different packages coming in)
- **outputs** (stuff performed upon the packages coming in)

### Follows

When defining inputs in your flake, i.e:

```json
	inputs = { 
		nixpkgs.url = "github:NixOS/nixpkgs";
		
		nix-darwin.url = "github:lnl7/nix-darwin/master";
		nix-darwin.inputs.nixpkgs.follows = "nixpkgs";
		
		home-manager.url = "github:nix-community/home-manager";
		home-manager.inputs.nixpkgs.follows = "nixpkgs";
	};
```

Then it is important to consider that each of the inputs you define could be flakes in their own right, with it's own set of inputs, for instance, the home-manager [`flake.nix`](https://github.com/nix-community/home-manager/blob/master/flake.nix#L4) also relies upon nixpkgs implementation.

```json
{
  description = "Home Manager for Nix";

  inputs.nixpkgs.url = "github:NixOS/nixpkgs/nixos-unstable"; // Avast!

  outputs =
    {
      self,
      nixpkgs,
      ...
    }:
    {
    ...
}
```

Therefore it is important to tell subsequent inputs which depend on nixpkgs to use the version of nixpkgs that we have already declared. If we neglected to declare `.follows` on our `home-manager` and `nix-darwin` dependencies, then we encounter a risk that our flake could then accumulate 3 seperate versions of nixpkgs being downloaded in parallel (leading to a huge bundle of functionally redunadant code)

```
/nix/dc46b31564888a280db52a4f53b68cf7c12bb675-nixpkgs-25.4.17
/nix/8c03fa207c5c00550c1bf68415d40fed2a1828cd-nixpkgs-25.5.1
/nix/aa5af119a3c32cf1f2a50635a1ed866060540281-nixpkgs-24.10.12
```


### Where to put your central OS config flake

`~/.config/nix/flake.nix`
or
`/etc/nix-darwin/flake.nix`??