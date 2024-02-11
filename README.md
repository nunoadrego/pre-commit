# pre-commit

Instructions to set up [pre-commit](https://pre-commit.com/).

Includes an example of a configuration file focused on Terraform, Terragrunt, and GitHub actions.

## Requirements
pre-commit
```
brew install pre-commit
```

## Usage

### Setup
Create a `.pre-commit-config.yaml` file.

### Install hooks
```
pre-commit install --hook-type pre-commit --hook-type pre-push
```

### Test
Add a malformatted file to the staging area:
```
git add invalid.yaml
```

Attempt to commit:
```
git commit
```

Result:
```
check yaml...............................................................Failed
- hook id: check-yaml
- exit code: 1

while scanning a simple key
  in "invalid.yaml", line 3, column 1
could not find expected ':'
  in "invalid.yaml", line 4, column 1
```

## Usage without hooks installed

### Setup
Create a `.pre-commit-config.yaml` file.

### Create alias
In `.zshrc`/`.bashrc`:
```
alias lint="pre-commit run --files ./* -c ~/path-to-config/.pre-commit-config.yaml"
```

### Test
In a folder:
```
lint
```
