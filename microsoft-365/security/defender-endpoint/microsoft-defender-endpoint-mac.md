---
title: Microsoft Defender for Endpoint on Mac
ms.reviewer: ''
description: Mac で Microsoft Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, catalina, mojave, mde for mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.technology: mde
ms.openlocfilehash: 81c64c7a73a7d298c4468f5c7735ee3e16cf55ac630e502364170b71a1b32a5e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53894217"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender for Endpoint on Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Mac 上で Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Microsoft Defender for Endpoint on Mac で他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しない副作用につながる可能性があります。 Microsoft 以外のエンドポイント保護が環境の絶対的な要件である場合でも、パッシブ モードで実行するウイルス対策機能を構成した後も、Defender for Endpoint on Mac EDR[](mac-preferences.md#enable--disable-passive-mode)の機能を安全に利用できます。

## <a name="whats-new-in-the-latest-release"></a>最新リリースの新機能

[Microsoft Defender for Endpoint の新機能](whats-new-in-microsoft-defender-atp.md)

[Microsoft Defender for Endpoint on Mac の新機能](mac-whatsnew.md)

> [!TIP]
> 共有するフィードバックがある場合は、デバイスで Microsoft Defender for Endpoint on Mac を開き、[フィードバックの送信に役立つ] に移動して送信  >  **します**。

プレビュー機能 (Mac デバイスのエンドポイント検出や応答など) を含む最新の機能を取得するには、Microsoft Defender for Endpoint を実行している macOS デバイスを "Insider" デバイスに構成します。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Mac に Microsoft Defender for Endpoint をインストールする方法

### <a name="prerequisites"></a>前提条件

- Defender for Endpoint サブスクリプションとポータルへのアクセスMicrosoft 365 Defenderする
- macOS と BASH スクリプトの初心者レベルのエクスペリエンス
- デバイスの管理特権 (手動展開の場合)

### <a name="installation-instructions"></a>インストール手順

Defender for Endpoint on Mac のインストールと構成に使用できる方法と展開ツールがいくつかあります。

- サードパーティの管理ツール:
    - [Microsoft Intune ベースの展開](mac-install-with-intune.md)
    - [JAMF ベースの展開](mac-install-with-jamf.md)
    - [その他の MDM 製品](mac-install-with-other-mdm.md)

- コマンド ライン ツール:
    - [手動展開](mac-install-manually.md)

### <a name="system-requirements"></a>システム要件

macOS の最新の 3 つのメジャー リリースがサポートされています。

> [!IMPORTANT]
> macOS 11 (Big Sur) では、Microsoft Defender for Endpoint には追加の構成プロファイルが必要です。 以前のバージョンの macOS からアップグレードする既存のお客様の場合は [、macOS Catalina](mac-sysext-policies.md)および macOS の新しいバージョンの新しい構成プロファイルに記載されている追加の構成プロファイルを必ず展開してください。

> [!IMPORTANT]
> macOS 10.13 (High Sierra) のサポートは、2021 年 2 月 15 日より中止されました。

- 11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)
- ディスク領域: 1 GB

macOS のベータ版はサポートされていません。

M1 プロセッサを搭載した macOS デバイスはサポートされていません。

サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の送信接続を許可する必要がある場合があります。

### <a name="licensing-requirements"></a>ライセンスの要件

Microsoft Defender for Endpoint on Mac では、次のいずれかの Microsoft ボリューム ライセンス オファーが必要です。

- Microsoft 365 E5 (M365 E5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 (M365 A5)
- Windows 10 Enterprise E5
- Microsoft Defender for Endpoint

> [!NOTE]
> 対象となるライセンスユーザーは、最大 5 つの同時デバイスで Microsoft Defender for Endpoint を使用できます。
> Microsoft Defender for Endpoint は、ユーザー (CSP) から購入クラウド ソリューション プロバイダー利用できます。 CSP を介して購入した場合、Microsoft ボリューム ライセンスの提供は必要とされません。

### <a name="network-connections"></a>ネットワーク接続

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、許可ルールを作成する必要があります。 

|ドメインリストのスプレッドシート|Description|
|---|---|
|![Microsoft Defender for Endpoint URL スプレッドシートのサム イメージ](images/mdatp-urls.png)|サービスの場所、地理的な場所、および OS の特定の DNS レコードのスプレッドシート。 <p> スプレッドシートをダウンロードするには、 [ 次の ](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)mdatp-urls.xlsxします。

Microsoft Defender for Endpoint では、次の検出方法を使用してプロキシ サーバーを検出できます。

- プロキシの自動構成 (PAC)
- Web プロキシ自動発見プロトコル (WPAD)
- 静的プロキシの手動構成

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。

> [!WARNING]
> 認証されたプロキシはサポートされていません。 PAC、WPAD、または静的プロキシだけが使用されている必要があります。
>
> SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。 SSL インスペクションとプロキシ サーバーの例外を構成して、macOS 上の Microsoft Defender for Endpoint のデータを、傍受なしで関連する URL に直接渡します。 インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。

接続がブロックされていないとテストするには、ブラウザー <https://x.cp.wd.microsoft.com/api/report> で <https://cdn.x.cp.wd.microsoft.com/ping> 開きます。

コマンド ラインが必要な場合は、ターミナルで次のコマンドを実行して接続を確認することもできます。

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

このコマンドからの出力は、次のようになります。

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> クライアント デバイスでシステム [整合性保護](https://support.apple.com/HT204899) (SIP) を有効にすることをお勧めします。 SIP は、OS の低レベル改ざんを防止する組み込みの macOS セキュリティ機能であり、既定で有効になっています。

Microsoft Defender for Endpoint をインストールすると、ターミナルで次のコマンドを実行して接続を検証できます。

```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender for Endpoint on Mac を更新する方法

Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。 Microsoft Defender for Endpoint on Mac を更新するには、Microsoft AutoUpdate (MAU) という名前のプログラムが使用されます。 詳細については [、「Deploy updates for Microsoft Defender for Endpoint on Mac」を参照してください](mac-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Mac で Microsoft Defender for Endpoint を構成する方法

エンタープライズ環境で製品を構成する方法については、「Mac での Microsoft Defender for Endpoint の設定 [」を参照してください](mac-preferences.md)。

## <a name="macos-kernel-and-system-extensions"></a>macOS カーネルとシステム拡張機能

macOS の進化に合わせ、カーネル拡張機能の代わりにシステム拡張機能を活用する Microsoft Defender for Endpoint on Mac 更新プログラムを準備しています。 関連する詳細については [、「Microsoft Defender for Endpoint on Mac の新機能」を参照してください](mac-whatsnew.md)。

## <a name="resources"></a>リソース

- ログ記録、アンインストール、その他のトピックの詳細については [、「Resources for Microsoft Defender for Endpoint on Mac」を参照してください](mac-resources.md)。
- [Microsoft Defender for Endpoint on Mac のプライバシー](mac-privacy.md)。
