# GitHub Actions

This is workspace branch of GitHub Actions multi project repository based on [orphan](https://git-scm.com/docs/git-checkout#Documentation/git-checkout.txt---orphanltnew-branchgt) branches.

| Branch                                   | Description                                                                                                          |
|------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| [tbd](../../tree/tbd)                    | TDB                                                                                                                  |

## Get Started

1. Clone the repository
	```shell
	git clone git@github.com:zxteamorg/actions.git
	```
1. Enter into cloned directory
	```shell
	cd actions
	```
1. Initialize [worktree](https://git-scm.com/docs/git-worktree) by execute following commands
	```shell
	for BRANCH in $(cat README.md | tail -n +3 | grep -E '^\| \[([a-z]+)\]' | awk -F'[][]' '{print $2}'); do git worktree add "${BRANCH}" "${BRANCH}"; done
	```
1. Open VSCode Workspace
	```shell
	code "Actions.code-workspace"
	```

## Notes

Add new orphan branch

```shell
NEW_ORPHAN_BRANCH=mybranch
git switch --orphan  "${NEW_ORPHAN_BRANCH}"
git commit --allow-empty -m "Initial Commit"
git push origin "${NEW_ORPHAN_BRANCH}"
```
