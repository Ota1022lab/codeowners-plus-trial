# Sample

codeowners-plus の動作確認用に追加したファイル。

`.codeowners` では全パスが `@Ota1022` と `@io2210` の所有になっているため、
このファイルを含む PR には両者の承認が要求される。`codeowners.toml` で
`allow_self_approval = true` を設定しているので、PR 作成者は自分自身の
承認要件を満たせる。

確認したいこと:

- Run Codeowners Plus のジョブに、要求される承認者として両名が表示されるか
- 承認が揃うまで `enforcement.fail_check = true` によりチェックが失敗するか
