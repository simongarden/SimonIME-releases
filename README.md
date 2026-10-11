# Simon輸入法 更新資訊

這個公開 repo 只放 Simon輸入法（macOS 大易・注音輸入法）的**更新資訊與安裝檔**，不含原始碼。

- 穩定版更新資訊：<https://simongarden.github.io/SimonIME-releases/appcast.json>
- 測試版更新資訊：<https://simongarden.github.io/SimonIME-releases/appcast-beta.json>
- 安裝檔：見 [Releases](https://github.com/simongarden/SimonIME-releases/releases)（每個版本一個 zip）

## 給使用者

Simon輸入法會在獨立的更新程式中（輸入法本身不連網）每天最多檢查一次更新，也可從輸入法選單選「檢查更新…」。安裝前會確認：

1. zip 的 SHA-256 與大小和更新資訊相符；
2. zip 有 Simon輸入法發行金鑰的 Ed25519 簽章；
3. App 由 OKMaster Inc.（Team ID 6524CT75ZS）以 Developer ID 簽署並經 Apple 公證。

任何一項不符就不會安裝。安裝前會先備份目前版本，可在設定頁「回復上一版」。

## 更新資訊格式

```json
{
  "schema": 1,
  "channel": "stable",
  "latest": {
    "version": "0.5.0",
    "build": 55,
    "minOS": "13.0",
    "arch": ["arm64"],
    "url": "https://github.com/simongarden/SimonIME-releases/releases/download/…/SimonIME-0.5.0-55.zip",
    "sha256": "…",
    "size": 12345678,
    "edSignature": "（base64，Ed25519 簽署 zip 位元組）",
    "notes": "更新內容（繁體中文）",
    "releaseDate": "2026-10-11",
    "critical": false
  }
}
```

`latest` 為 `null` 表示目前沒有可用的更新。
