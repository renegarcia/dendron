---
id: 631hw9oh0k8jhc0wlm0joyz
title: Coding tips
desc: ''
updated: 1743091729520
created: 1685471254996
---

## Customize Latex Workshop extenral viewer

In Vscode the following configuration works well with Latex workshop.


### Sumatra

```json
{
    "latex-workshop.view.pdf.viewer": "external",
    "latex-workshop.view.pdf.external.viewer.command": "C:\\Program Files\\SumatraPDF\\SumatraPDF.exe",
    "latex-workshop.view.pdf.external.viewer.args": [
        "%PDF%"
    ],
    "latex-workshop.view.pdf.external.synctex": "sumatrapdf",
    "latex-workshop.view.pdf.external.synctex.args": [
    "-forward-search",
    "%TEX%",
    "%LINE%",
    "-reuse-instance",
    "-inverse-search",
    "\"C:\\Users\\<Username>\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\" \"C:\\Users\\<U>\\AppData\\Local\\Programs\\Microsoft VS Code\\resources\\app\\out\\cli.js\" --ms-enable-electron-run-as-node -r -g \"%f:%l\"",
    "%PDF%"
  ]
}
```

### Sioyek

```json
{
    "latex-workshop.view.pdf.external.viewer.command": "C:\\path\\to\\sioyek\\sioyek.exe",
    "latex-workshop.view.pdf.external.synctex.command": "C:\\path\\to\\sioyek\\sioyek.exe",
    "latex-workshop.view.pdf.external.synctex.args": [
        "--inverse-search",
        "\"C:\\path\\to\\vscode\\Code.exe\" \"C:\\path\\to\\vscode\\resources\\app\\out\\cli.js\" --ms-enable-electron-run-as-node -r -g \"%1:%2\"",
        "--reuse-instance",
        "--forward-search-file",
        "%TEX%",
        "--forward-search-line",
        "%LINE%",
        "%PDF%"
    ]
}
```

## Biblatex bibliography trick

To change the `url` biblatex entry string from _retrieved from_ to _available at_, do this:

```latex
\DefineBibliographyStrings{english}{%
   retrieved = {available},
   from = {at},
}
```

## Create a new sveltekit project

```bash
pnpm dlx sv create my-app
cd my-app
git init && git add -A # (optional)
pnpm run dev
```

## How to install strapi

```bash
pnpm dlx create-strapi-app@latest
```

See [strapi.io](https://strapi.io) for details.

## Clone only the latest commit of a Git repository

```bash
git clone --depth 1 <url>
```

If you need an specific commit, you can obtain it with the `git checkout`
command:

```bash
git checkout <commit_hash>
```

## Source

1. Bing AI Chat, 21/9/2023.
2. [Copie un repositorio de git sin historial - QA Stack.](https://qastack.mx/programming/29368837/copy-a-git-repo-without-history)
3. [Clonar repositorio remoto de git hasta cierto commit.](https://es.stackoverflow.com/questions/91014/clonar-repositorio-remoto-de-git-hasta-cierto-commit)
4. [Regresar un repositorio a un commit especifico - Stack Overflow.](https://es.stackoverflow.com/questions/1458/regresar-un-repositorio-a-un-commit-especifico)
5. [Atlassian Git Tutorial.](https://www.atlassian.com/es/git/tutorials/setting-up-a-repository/git-clone)

# Edit Git Remote URL

```bash
git remote set-url origin <new-url>

```

[Source](https://chat.openai.com/share/5bbfc058-d6be-4ec8-b03f-be8df3619c37)

# Django tests not running

__Solution.__ Make sure you are writing your tests wrapped in classes that inherit from `TestCase`. Example:

```python
from django.test import TestCase


class FooTest(TestCase):
    def setUp(self):
        pass

    def tearDown(self):
        pass

    def test_this_will(self):
        print 'Win'
```

[Read more](https://stackoverflow.com/questions/2037364/django-test-runner-not-finding-tests)
