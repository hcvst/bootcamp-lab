# Bootcamp lab

## Install Windows Subsystem for Linux
WSL gives you a Linux environment from inside Windows.
- https://docs.microsoft.com/en-us/windows/wsl/install

## Install Git
Git is a distributed version control system to track changes to program files in 
personal or collaborative projects.

- `sudo apt install git`

## Get started with Github
Github provides git repository hosting. Please *do not* use github for work related repositories
unless it's for non-confidential demos, testing or offically approved project repositories.

- Fork https://github.com/hcvst/bootcamp-lab
- Clone your fork

## Install Nix
Install the nix package manager that is part of the NixOs project - https://nixos.org/.

- `sh <(curl -L https://nixos.org/nix/install) --no-daemon`

## Install Visual Studio Code
Setup VS Code as per https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-vscode

## Hello Spark
- Configure a nix shell for spark development by placing the file `shell.nix` with \
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
    pkgs.python39Packages.ipython
    pkgs.spark
  ];
  SPARK_HOME = "${pkgs.spark}/lib/spark-3.1.2";
  PYSPARK_DRIVER_PYTHON = "ipython";
  shellHook = ''
    echo Welcome to your Bootcamp Lab 
  '';
}
```

- Enter shell by typing `nix-shell` in the project's root directory.
- Test pyspark with `pyspark`
- Implement the Spark word count example.
- Commit your changes to your fork of this repository and push them. 
- For a Python refresher please consult https://learnxinyminutes.com/docs/python/.

