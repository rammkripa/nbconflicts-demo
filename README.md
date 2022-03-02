# A simple repo to demonstrate merge conflicts in Jupyter Notebooks

This small repo contains two branches with conflicting changes in code and markdown. Branch `main` and branch `experiment` both have edits to the same cells.

You can configure git to use nbdime [see instructions for details](https://nbdime.readthedocs.io/en/latest/vcs.html#git-integration); here we assume you have already run this command (if you haven't, do it now):

```
nbdime config-git --enable --global
```

We will use the VNC desktop viewer to run the graphical merge tool, which is a bit easier to access and control than through JupyterLab.

Once you clone this repository

git mergetool --tool=nbdime