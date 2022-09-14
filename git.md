# Gitに関すること
- Gitのブランチ機能を専門的に学習できるサイト [LearnGit Branching](https://learngitbranching.js.org/?locale=ja)  

- [マンガでわかるGit](https://www.r-staffing.co.jp/engineer/entry/20190621_1)
- [Gitをはじめからていねいに](https://github.com/Shinpeim/introduction-to-git)

---
## 使ったコマンド

- ステージ済みファイルをワークツリーにおろす
```git
git restore --staged 【ファイル名】
```

- add前のファイルを直前コミットの状態にもどす
```git
git restore [--worktree] 【ファイル名】
```

- git操作の全ての過去ログを見る  
間違えて``git reset``してしまった場合でも、``git reflog``から``HEAD@{n}``を得て、``git reset --hard 'HEAD@{n}'``などするとreset前の状態に戻すことができる。  
（なので、パスワードが書いた情報はgitにpushしてはいけない。）
```git
git reflog
```

- 差分とり①コミット間の差分
```git
git diff 【変更前のコミット識別子】..【変更後のコミット識別子】
```

- 差分とり②ブランチ間の差分
```git
git diff 【ブランチ名1】..【ブランチ名2】

例
git diff main..news
```

- 差分とり③addする前限定！前回コミットからの変更差分
```git
git diff
```

- 過去のコミットをそっくり打ち消すコマンド。  
git resetは指定したコミットまでのすべてのコミットを消す（実際にはgit reflogで見れるが）ため、危険。  
特に<span style="color: red">複数人開発時にmainブランチでgit resetコマンドを使用してpushすると、他開発者にも影響を与えてしまうため、非常に危険。</span>  
初心者はgit revert推奨。
```git
git revert 【コミット識別子】
```

- ブランチ切り替え
```git
git switch 【ブランチ名】
```

- ブランチ作成＆切り替え
```git
git switch -c 【新ブランチ名】
```

- 
```git

```

- 
```git

```

- 
```git

```

- 
```git

```

- 
```git

```

- 
```git

```