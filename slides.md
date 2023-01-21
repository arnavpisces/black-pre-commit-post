# slide 1
how to lint your python code using pre-commit hooks

# slide 2
pre-commit hooks are essentially a piece of code you can run on every commit. These hooks can check your code for issues and automatically fix them

# slide 3
install the depedencies. We will be using flake8 and black to lint our python code 
`pip install pre-commit black flake8`

# slide 4
add a `.pre-commit-config.yaml` file to the root of your git repository which would look something like this 
``` yaml
repos:
- repo: https://github.com/PyCQA/flake8
  rev: 3.8.4
  hooks:
  - id: flake8
- repo: https://github.com/psf/black
  rev: stable
  hooks:
  - id: black
    args: 
    - --exclude="""\.git |
      \.__pycache__|
      \.venv|
```

# slide 5
install the hook using `pre-commit install` and add your files to git.
On `git commit -m "test commit"` should run your linters as per the config defined.
<br>
`git add .pre-commit-config.yaml`
# slide 6
<linting image>

# slide 7 
now you can review your linted code and push upstream

# slide 8
Thanks for reading! If you found this post helpful, follow me for more quick tips and guides 
