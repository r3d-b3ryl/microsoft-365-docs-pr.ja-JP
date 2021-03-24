---
title: Microsoft Defender ATP for Mac - システム拡張機能 (プレビュー)
description: この記事では、Microsoft Defender ATP for Mac のシステム拡張機能の機能を試す手順について説明します。 この機能は現在パブリック プレビュー中です。
keywords: microsoft, defender, atp, mac, kernel, system, extensions, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 8b644e27c5a36d2175ab18ae92424e7c70f39d0f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062228"
---
# <a name="microsoft-defender-for-endpoint-for-mac---system-extensions-public-preview"></a>Microsoft Defender for Endpoint for Mac - システム拡張機能のパブリック プレビュー)

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

macOS の進化に合わせ、カーネル拡張機能ではなくシステム拡張機能を活用する Defender for Endpoint for Mac 更新プログラムを準備しています。 この更新プログラムは、macOS Catalina (10.15.4) 以降のバージョンの macOS にのみ適用されます。

この機能は現在パブリック プレビュー中です。 この記事では、デバイスでこの機能を有効にする方法について説明します。 この機能は、独自のデバイスでローカルで試したり、管理ツールを使用してリモートで構成することができます。

これらの手順では、デバイスで Defender for Endpoint が既に実行済みである必要があります。 詳細については、「[このページ](microsoft-defender-endpoint-mac.md)」をご覧ください。

## <a name="known-issues"></a>既知の問題

- ネットワーク拡張機能が Apple SSO Kerberos 拡張機能に干渉しているという報告を受け取っています。
- 製品の現在のバージョンでは、カーネル拡張機能がインストールされます。 カーネル拡張機能はフォールバック メカニズムとしてのみ使用され、この機能がパブリック プレビューに達する前に削除されます。
- 現在も、macOS 11 Big Sur で適切に展開および機能する製品バージョンに取り組まれています。

## <a name="deployment-prerequisites"></a>展開の前提条件

- macOS オペレーティング システムの最小バージョン: **10.15.4**
- 最小製品バージョン: **101.03.73**
- デバイスが Insider Fast 更新チャネル **にある必要があります**。 次のコマンドを使用して更新チャネルを確認できます。

  ```bash
  mdatp health --field release_ring
  ```

  デバイスが Insider Fast 更新チャネルにまだ存在しない場合は、ターミナルから次のコマンドを実行します。 チャネル更新プログラムは、次に製品を起動するときに有効になります (次の製品更新プログラムがインストールされている場合、またはデバイスが再起動された場合)。

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  または、管理環境 (JAMF または Intune) を使用している場合は、更新プログラム チャネルをリモートで構成できます。 詳細については [、「Deploy updates for Microsoft Defender ATP for Mac: Set the channel name 」を参照してください](mac-updates.md#set-the-channel-name)。

## <a name="deployment-steps"></a>展開手順

環境に対応する展開手順と、この機能を試す方法に従います。

### <a name="manual-deployment"></a>手動展開

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a>システム拡張機能を承認し、ネットワーク拡張機能を有効にする

1. すべての展開の前提条件が満たされた後、デバイスを再起動して、システム拡張の承認とライセンス認証プロセスを起動します。

   Defender for Endpoint システム拡張機能を承認する一連のシステム プロンプトが表示されます。 シリーズのすべてのプロンプト **を** 承認する必要があります。macOS では、Defender for Endpoint for Mac がデバイスにインストールする拡張機能ごとに明示的な承認が必要です。
   
   承認ごとに、[Open **Security Preferences]** を選択し、[許可] を選択してシステム拡張機能の実行を許可します。

   > [!IMPORTANT]
   > 後続の承認の間に **、[System Preferences**  >  **Security] ウィンドウを閉じて&再度** 開く必要があります。 それ以外の場合、macOS では次の承認は表示されません。

   > [!IMPORTANT]
   > 製品がカーネル拡張機能に戻る前に 1 分のタイムアウトがあります。 これにより、デバイスが保護されます。
   >
   > 1 分以上経過した場合は、デバイスを再起動するか、承認フローを再度トリガーするために使用してデーモン `sudo killall -9 wdavdaemon` を再起動します。

   ![システム拡張機能の承認ポップアップ](images/mac-system-extension-approval.png)

   ![システム拡張機能の承認ウィンドウ](images/mac-system-extension-pref.png)

1. システム拡張機能が承認されると、macOS はネットワーク トラフィックのフィルター処理を許可する承認を求めるメッセージを表示します。 **[許可]** をクリックします。

   ![ネットワーク拡張機能の承認ポップアップ](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a>エンドポイント セキュリティ システム拡張機能へのフル ディスク アクセスの付与

[System **Preferences** Security &プライバシー] タブを開き、Microsoft Defender Endpoint Security Extension へのフル ディスク アクセス  >    >  **を許可します**。 

![Endpoint Security システム拡張機能の完全なディスク アクセス](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a>デバイスを再起動する

変更を有効にするには、デバイスを再起動する必要があります。

#### <a name="verify-that-the-system-extensions-are-running"></a>システム拡張機能が実行されているのを確認する

ターミナルから、次のコマンドを実行します。

```bash
mdatp health --field real_time_protection_subsystem
```

ターミナル出力 `endpoint_security_extension` は、製品がシステム拡張機能機能を使用している状態を示します。

### <a name="managed-deployment"></a>管理された展開

この新機能のために展開する必要がある新しい構成プロファイルについては、「macOS Catalina および新しいバージョンの [macOS: JAMF」](mac-sysext-policies.md#jamf) を参照してください。

これらのプロファイルに加えて、「展開の前提条件」の説明に従って、ターゲット デバイスを Insider Fast update チャネルに配置するように [構成してください](#deployment-prerequisites)。

すべての前提条件が満たされ、新しい構成プロファイルが展開されているデバイスで、次のコマンドを実行します。

```bash
$ mdatp health --field real_time_protection_subsystem
```

このコマンドが印刷される `endpoint_security_extension` 場合、製品はシステム拡張機能の機能を使用しています。

## <a name="validate-basic-scenarios"></a>基本的なシナリオの検証

1. ヨーロッパコンピューターウイルス対策研究所 (EICAR) の検出をテストします。 ターミナル ウィンドウで、次のコマンドを実行します。

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   EICAR ファイルが検疫済みである必要があります。 次のコマンドを使用して、ユーザー インターフェイスの [保護履歴] ページまたはコマンド ラインからファイルの状態を確認できます。

    ```bash
    mdatp threat list
    ```

2. エンドポイント検出と応答 (EDR) DIY シナリオをテストします。 ターミナル ウィンドウから、次のコマンドを実行します。

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   EICAR および EDR DIY シナリオのコンピューター ページのポータルに 2 つのアラートがポップアップしたと検証します。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

- Q: 実行するときにまだ表示 `kernel_extension` される理由 `mdatp health --field real_time_protection_subsystem` は何ですか?

    A: [展開の前提条件] [セクションを](#deployment-prerequisites) 参照し、すべての前提条件が満たされていることをもう一度確認します。 すべての前提条件が満たされている場合は、デバイスを再起動し、もう一度確認します。

- Q: macOS 11 Big Sur がサポートされるのは、いつですか?

    A: macOS 11 のサポートの追加に積極的に取り組む予定です。 詳細については、[新しい情報 [] ページに投稿](mac-whatsnew.md) します。
