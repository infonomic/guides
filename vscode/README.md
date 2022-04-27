# Infonomic VS Code Usage Guide

Infonomic has a recommended VS Code theme that we suggest is used for all code reviews.

https://github.com/infonomic/infonomic-dark

Another very useful setting is to set the workbench tree indent size, greatly increasing
'readability' of the current folder in the project tree.

The following setting can be placed in the main settings.json file...

```
"workbench.tree.indent": 18,
```

We use the following ESLint plugin, combined with our standard ESLint settings (which should be in every project)

https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint

You may need to place the following in your settings.json file in order to have ESLint 'fixes' applied on save.

```
"editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
```

(more soon...)