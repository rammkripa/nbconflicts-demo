# A simple repo to demonstrate merge conflicts in Jupyter Notebooks

This small repo contains two branches with conflicting changes in code and markdown. Branch `main` and branch `experiment` both have edits to the same cells.

You can configure git to use nbdime [see instructions for details](https://nbdime.readthedocs.io/en/latest/vcs.html#git-integration); here we assume you have already run this command (if you haven't, do it now):

```
nbdime config-git --enable --global
```

We will use the VNC desktop viewer to run the graphical merge tool, which is a bit easier to access and control than through JupyterLab.

Once you clone this repository, you will attempt to merge the `experiment` branch into `main` with:

```
git merge origin/experiment
```

This should fail, giving you a message like:

```
(base) (main)alpamayo[nbconflicts-demo]> git merge origin/experiment
[W nbmergeapp:55] Conflicts occured during merge operation.
[I nbmergeapp:68] Merge result written to .merge_file_xBrzjl
Auto-merging subplots_demo.ipynb
CONFLICT (content): Merge conflict in subplots_demo.ipynb
Automatic merge failed; fix conflicts and then commit the result.
```

You will then (in the virtual VNC desktop), run:

```
git mergetool --tool=nbdime
```

and proceed with the graphical 3-way merge.
