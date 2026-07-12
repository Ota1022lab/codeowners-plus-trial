# Sample File

codeowners-plus の動作確認用に追加したファイル。

`.codeowners` では全パスのオーナーが `@Ota1022` になっているため、このファイルの
変更でも同じオーナーの承認が要求される。`codeowners.toml` の
`allow_self_approval = false` により、PR 作成者本人の承認では要求を満たせない。

## 確認したいこと

- Run Codeowners Plus のジョブに `@Ota1022` が必須オーナーとして表示されるか
- 承認がない状態で `enforcement.fail_check = true` によりチェックが失敗するか
