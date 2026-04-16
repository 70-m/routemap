# APP_VERSION 更新

PR作成前に `index.html` の `APP_VERSION` を正しい値に更新する。

## 手順

1. 作業中のブランチ名・直近のコミットから、今回作成予定のPR番号を特定する。
   - GitHubのPR一覧（`mcp__github__list_pull_requests`）を確認し、最新PR番号+1を次のPR番号とする。
   - 既にPRが作成済みの場合はそのPR番号を使用する。

2. 今日の日付を `YYMMDD` 形式（例: 2026年4月16日 → `260416`）で取得する。
   - Bash で `date +%y%m%d` を実行して取得する。

3. `index.html` の `APP_VERSION` を以下の形式に更新する:
   ```
   const APP_VERSION='{YYMMDD}PR{PR番号}';
   ```
   例: `const APP_VERSION='260416PR41';`

4. 変更をコミットする（他の修正と同じコミットに含めてよい）。

## 注意事項

- PR番号はIssue番号と異なる場合がある。GitHubのPR番号を必ず確認すること。
- バージョン文字列の形式は `YYMMDDPRnn` で固定（変更しない）。
- APP_VERSIONの更新だけを単独でコミットせず、関連する修正と一緒にコミットする。
