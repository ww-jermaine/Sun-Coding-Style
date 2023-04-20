# Sun Asterisk Coding Style

## Installation

First, install pre-commit into your system. Python 3.8+ is required.

```bash
pip install pre-commit
```

Then, make sure pre-commit has been installed correctly.

```bash
pre-commit --version
```

## Usage

In your project's repo root, create a `.pre-commit-config.yaml` file with the following content, depending on the language you are using.

```yaml
repos:
- repo: # pre-commit you wish to apply
    ... # 
```

Once you have a configuration file, you can apply it to the project by running `pre-commit install`.

### Python

```yaml
repos:
- repo: https://github.com/psf/black
  rev: stable
  hooks:
  - id: black
    name: black
    entry: black .

- repo: https://github.com/PyCQA/flake8
  rev: 4.0.1
  hooks:
  - id: flake8
    name: flake8
    entry: flake8

- repo: https://github.com/PyCQA/isort
  rev: 5.9.3
  hooks:
  - id: isort
    name: isort
    entry: isort --check --diff

```



### JavaScript

```yaml
repos:
- repo: https://github.com/prettier/prettier
  rev: master
  hooks:
    - id: prettier
      name: prettier
      entry: npx prettier --write
      language: node
      types: [javascript]
    - id: eslint
      name: eslint
      entry: npx eslint --fix
      language: node
      types: [javascript]
```


### Ruby

```yaml
repos:
- repo: https://github.com/brigade/overcommit
  rev: master
  hooks:
    - id: rubocop
      name: rubocop
      entry: rubocop
      language: system
      types: [ruby]
```

### PHP

```yaml
repos:
- repo: https://github.com/FriendsOfPHP/PHP-CS-Fixer
  rev: master
  hooks:
    - id: php-cs-fixer
      name: php-cs-fixer
      entry: php-cs-fixer fix --config=.php_cs --ansi --verbose --dry-run --diff
      language: system
      types: [php]
```

### General Checks

```yaml
repos:
- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v4.3.0
  hooks:
    - id: trailing-whitespace
    - id: end-of-file-fixer

```

