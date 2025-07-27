$ git push -u origin main --force
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 235 bytes | 117.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To github.com:bgatanasov/Recovering-Lost-Work-and-Rewriting-Git-History.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

valeri@win11-teslab MINGW64 /c/Exam/Recovering Lost Work and Rewriting Git History (main)
$ git reflog
87a1dfa (HEAD -> main, origin/main) HEAD@{0}: checkout: moving from dev-branch to main
b43238d (dev-branch) HEAD@{1}: commit: tirth commit in dev
3ac1df2 HEAD@{2}: commit: second commit in dev
43539d0 HEAD@{3}: commit: firts commit in dev
87a1dfa (HEAD -> main, origin/main) HEAD@{4}: checkout: moving from main to dev-branch
87a1dfa (HEAD -> main, origin/main) HEAD@{5}: commit (initial): ititial commit

valeri@win11-teslab MINGW64 /c/Exam/Recovering Lost Work and Rewriting Git History (main)
$ git rebase -i
Successfully rebased and updated refs/heads/main.

valeri@win11-teslab MINGW64 /c/Exam/Recovering Lost Work and Rewriting Git History (main)
$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

valeri@win11-teslab MINGW64 /c/Exam/Recovering Lost Work and Rewriting Git History (main)
$ git checkout  dev-branch
Switched to branch 'dev-branch'

valeri@win11-teslab MINGW64 /c/Exam/Recovering Lost Work and Rewriting Git History (dev-branch)
$ git rebase -i HEAD~3
[detached HEAD d53aedc] firts  commit in dev
 Date: Sun Jul 27 12:33:06 2025 +0300
 1 file changed, 3 insertions(+)
Successfully rebased and updated refs/heads/dev-branch.

valeri@win11-teslab MINGW64 /c/Exam/Recovering Lost Work and Rewriting Git History (dev-branch)
$ git reflog
d53aedc (HEAD -> dev-branch) HEAD@{0}: rebase (finish): returning to refs/heads/dev-branch
d53aedc (HEAD -> dev-branch) HEAD@{1}: rebase (squash): firts commit in dev
6e5cc52 HEAD@{2}: rebase (squash): # This is a combination of 2 commits.
43539d0 HEAD@{3}: rebase (start): checkout HEAD~3
b43238d HEAD@{4}: checkout: moving from main to dev-branch
87a1dfa (origin/main, main) HEAD@{5}: rebase (finish): returning to refs/heads/main
87a1dfa (origin/main, main) HEAD@{6}: rebase (start): checkout refs/remotes/origin/main
87a1dfa (origin/main, main) HEAD@{7}: checkout: moving from dev-branch to main
b43238d HEAD@{8}: commit: tirth commit in dev
3ac1df2 HEAD@{9}: commit: second commit in dev
43539d0 HEAD@{10}: commit: firts commit in dev
87a1dfa (origin/main, main) HEAD@{11}: checkout: moving from main to dev-branch
87a1dfa (origin/main, main) HEAD@{12}: commit (initial): ititial commit


$ git push -u origin dev-branch --force
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 321 bytes | 64.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'dev-branch' on GitHub by visiting:
remote:      https://github.com/bgatanasov/Recovering-Lost-Work-and-Rewriting-Git-History/pull/new/dev-branch
remote:
To github.com:bgatanasov/Recovering-Lost-Work-and-Rewriting-Git-History.git
 * [new branch]      dev-branch -> dev-branch
branch 'dev-branch' set up to track 'origin/dev-branch'.
