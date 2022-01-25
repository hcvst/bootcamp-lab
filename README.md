# Bootcamp lab

## Windows Subsystem for Linux
- https://docs.microsoft.com/en-us/windows/wsl/install

## Git
- `sudo apt install git`

## Github
- Fork https://github.com/hcvst/bootcamp-lab
- Clone your fork

## Nix
Install the nix package manager from https://nixos.org/.

- `sh <(curl -L https://nixos.org/nix/install) --no-daemon`

## Visual Studio Code
Setup VS Code as per https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode

## Spark
- Configure a nix shell for spark development by placing shell.nix with \
the following contents in your project's root directory.

```
{ pkgs ? import <nixpkgs> {}
}:

pkgs.mkShell {
  name="bootcamp-lab";
  buildInputs = [
    pkgs.python39
    pkgs.python39Packages.ipykernel
    pkgs.python39Packages.pyspark
    pkgs.python39Packages.pandas
  ];
  shellHook = ''
    echo Welcome to your Bootcamp Lab 
  '';
}
```


- Enter shell with `nix-shell`
- Write word count example
- Commit your changes and push them to your github account
- For a Python refresher consult https://learnxinyminutes.com/docs/python/.
