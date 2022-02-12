---
title: Microsoft Defender for Endpoint on Mac のインストールに関する問題のトラブルシューティング
description: Microsoft Defender for Endpoint on Mac のインストールに関する問題のトラブルシューティングを行います。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, install
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5f56e28d472cb3fdf8dd089effcd4beac6e42374
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766658"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS での Microsoft Defender for Endpoint のインストールの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>インストールに失敗しました

手動インストールの場合、インストール ウィザードの [概要] ページには、「インストール中にエラーが発生しました。 インストーラーでエラーが発生し、インストールに失敗しました。 ソフトウェア発行元に問い合わせてサポートを受けてください。 MDM の展開では、一般的なインストールエラーとして表示されます。

エンド ユーザーに正確なエラーは表示されませんが、インストールの進行状況を示すログ ファイルを保持します `/Library/Logs/Microsoft/mdatp/install.log`。 このログ ファイルには、各インストール セッションが追加されます。 最後のインストール セッション `sed` のみを出力するために使用できます。

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

この例では、実際の理由の先頭に . が付く `[ERROR]`。
これらのバージョン間のダウングレードがサポートされていないため、インストールに失敗しました。

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP インストール ログが見つからないか更新されない

まれに、インストールは MDATP の /Library/Logs/Microsoft/mdatp/install.log ファイルにトレースを残しません。
最初に、インストールが発生したことを確認します。 次に、macOS ログを照会して、考えられるエラーを分析します。 クライアント UI がない場合は、MDM 展開でこれを行うのが便利です。 膨大な量の情報が含むので、狭いタイム ウィンドウを使用してクエリを実行し、ログ プロセス名でフィルター処理することをお勧めします。

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
