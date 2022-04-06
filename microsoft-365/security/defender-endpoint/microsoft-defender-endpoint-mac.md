---
title: Mac 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Mac にインストール、構成、更新、および使用する方法についてMicrosoft Defender for Endpointします。
keywords: microsoft、 defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, モントレー, big sur, catalina, mojave, mde for mac
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
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2e982a32826906feb65b05837506ff2f513eb27e
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507303"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Mac 用 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Mac 上で Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Mac で他のサード パーティ製のエンドポイント保護製品Microsoft Defender for Endpointと共に実行すると、パフォーマンスの問題や予期しない副作用が発生する可能性があります。 Microsoft 以外のエンドポイント保護が環境の絶対的な要件である場合でも、パッシブ モードで実行するウイルス対策機能を構成した後も、Defender for Endpoint on Mac EDR の機能を安全に利用できます。[](mac-preferences.md#enforcement-level-for-antivirus-engine)

## <a name="whats-new-in-the-latest-release"></a>最新リリースの新機能

[Microsoft Defender for Endpoint の新機能](whats-new-in-microsoft-defender-endpoint.md)

[Mac の新しいMicrosoft Defender for Endpoint](mac-whatsnew.md)

> [!TIP]
> 共有するフィードバックがある場合は、デバイスの Mac  \> で Microsoft Defender for Endpoint を開き、[フィードバックの送信に役立つ] に移動して送信 **します**。

プレビュー機能 (Mac デバイスの エンドポイントでの検出と対応 など) を含む最新の機能を取得するには、Microsoft Defender for Endpointを実行している macOS デバイスを "Insider" デバイスに構成します。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Mac にインストールするMicrosoft Defender for Endpoint方法

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
> macOS 11 (Big Sur) 以上では、Microsoft Defender for Endpoint構成プロファイルが必要です。 以前のバージョンの macOS からアップグレードする既存のお客様の場合は、 [macOS Catalina および新](mac-sysext-policies.md)しいバージョンの macOS の新しい構成プロファイルに記載されている追加の構成プロファイルを必ず展開してください。

- 12 (モントレー), 11 (Big Sur), 10.15 (Catalina)
- ディスク領域: 1 GB

macOS のベータ版はサポートされていません。

M1 チップ ベースのプロセッサを搭載した macOS デバイスのサポートは、エージェントのバージョン 101.40.84 以降正式にサポートされています。

サービスを有効にした後、ネットワークまたはファイアウォールを構成して、ネットワークとエンドポイント間の送信接続を許可する必要がある場合があります。

### <a name="licensing-requirements"></a>ライセンスの要件

Microsoft Defender for Endpoint Mac では、次のいずれかの Microsoft ボリューム ライセンスの提供が必要です。

- Microsoft 365 E5 (M365 E5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 (M365 A5)
- Windows 10 Enterprise E5
- Microsoft 365 Business Premium
- Windows 11 Enterprise E5
- Microsoft Defender for Endpoint

> [!NOTE]
> 資格を持つライセンスユーザーは、最大 5 Microsoft Defender for Endpoint同時デバイスで使用できます。
> Microsoft Defender for Endpoint (CSP) から購入クラウド ソリューション プロバイダー利用できます。 CSP を介して購入した場合、Microsoft ボリューム ライセンスの提供は必要とされません。

### <a name="configuring-exclusions"></a>除外の構成

除外を追加する場合は、一般的な除外ミスに[Microsoft Defender ウイルス対策。](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)

### <a name="network-connections"></a>ネットワーク接続

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、許可ルールを作成する必要があります。


|ドメインリストのスプレッドシート| 説明|
|---|---|
|Microsoft Defender for Endpointの URL リスト| 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender for Endpoint/Gov/GCC/DoD の URL リスト | Gov/GCC/DoD のお客様向けサービスの場所、地理的な場所、OS の特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

Microsoft Defender for Endpoint検出方法を使用してプロキシ サーバーを検出できます。

- プロキシの自動構成 (PAC)
- Web プロキシ自動発見プロトコル (WPAD)
- 静的プロキシの手動構成

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。

> [!WARNING]
> 認証されたプロキシはサポートされていません。 PAC、WPAD、または静的プロキシだけが使用されている必要があります。
>
> SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。 SSL インスペクションとプロキシ サーバーの例外を構成して、macOS 上の Microsoft Defender for Endpointから、インターセプトなしで関連する URL にデータを直接渡します。 インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。

接続がブロックされていないとテストするには、ブラウザーで<https://x.cp.wd.microsoft.com/api/report><https://cdn.x.cp.wd.microsoft.com/ping>開きます。

コマンド ラインが必要な場合は、ターミナルで次のコマンドを実行して接続を確認することもできます。

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

このコマンドからの出力は、次のようになります。

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> クライアント デバイスで [システム整合性保護](https://support.apple.com/HT204899) (SIP) を有効にすることをお勧めします。 SIP は、OS の低レベル改ざんを防止する組み込みの macOS セキュリティ機能であり、既定で有効になっています。

インストールMicrosoft Defender for Endpoint、ターミナルで次のコマンドを実行して接続を検証できます。

```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Mac で更新Microsoft Defender for Endpointする方法

Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。 Mac でMicrosoft Defender for Endpoint更新するには、Microsoft AutoUpdate (MAU) という名前のプログラムが使用されます。 詳細については、「[Deploy updates for Microsoft Defender for Endpoint Mac」を参照してください](mac-updates.md)。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Mac でMicrosoft Defender for Endpoint構成する方法

エンタープライズ環境で製品を構成する方法のガイダンスについては、「Mac でのユーザー設定の設定[Microsoft Defender for Endpoint参照してください](mac-preferences.md)。

## <a name="macos-kernel-and-system-extensions"></a>macOS カーネルとシステム拡張機能

macOS の進化に合わせ、カーネル拡張機能の代わりにMicrosoft Defender for Endpoint拡張機能を活用する Mac 更新プログラムの開発を準備しています。 関連する詳細については、「[What's new in Microsoft Defender for Endpoint Mac」を参照してください](mac-whatsnew.md)。

## <a name="resources"></a>リソース

- ログ記録、アンインストール、その他のトピックの詳細については、「[Resources for Microsoft Defender for Endpoint Mac」を参照してください](mac-resources.md)。
- [Mac でのMicrosoft Defender for Endpointプライバシー](mac-privacy.md)。
