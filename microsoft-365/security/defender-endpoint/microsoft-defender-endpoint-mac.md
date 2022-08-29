---
title: Mac 用 Microsoft Defender for Endpoint
ms.reviewer: ''
description: Mac でMicrosoft Defender for Endpointをインストール、構成、更新、および使用する方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 展開, アンインストール, intune, jamf, macos, 回覧, big sur, catalina, mojave, mde for mac
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
ms.openlocfilehash: 97f7477c1216bfa25e25f6fc3086cf62a8b4b5a3
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67384098"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Mac 用 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Mac 上の Defender for Endpoint をインストール、構成、更新、および使用する方法について説明します。

> [!CAUTION]
> Mac で他のサード パーティ製のエンドポイント保護製品をMicrosoft Defender for Endpointと共に実行すると、パフォーマンスの問題や予期しない副作用が発生する可能性があります。 Microsoft 以外のエンドポイント保護が環境の絶対的な要件である場合でも、 [パッシブ モード](mac-preferences.md#enforcement-level-for-antivirus-engine)で実行するようにウイルス対策機能を構成した後でも、Defender for Endpoint on Mac EDR 機能を安全に利用できます。

## <a name="whats-new-in-the-latest-release"></a>最新リリースの新機能

[Microsoft Defender for Endpoint の新機能](whats-new-in-microsoft-defender-endpoint.md)

[Mac でのMicrosoft Defender for Endpointの新機能](mac-whatsnew.md)

> [!TIP]
> 共有したいフィードバックがある場合は、デバイスで Mac でMicrosoft Defender for Endpointを開き、[フィードバックの送信に **役立つ**\>] に移動して **送信します**。

プレビュー機能 (Mac デバイスのエンドポイント検出や応答など) を含む最新の機能を取得するには、Microsoft Defender for Endpointを実行している macOS デバイスを "Insider" デバイスとして構成します。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Mac にMicrosoft Defender for Endpointをインストールする方法

### <a name="prerequisites"></a>前提条件

- Defender for Endpoint サブスクリプションとMicrosoft 365 Defender ポータルへのアクセス
- macOS と BASH スクリプトの初心者レベルのエクスペリエンス
- デバイスに対する管理者特権 (手動展開の場合)

### <a name="installation-instructions"></a>インストール手順

Mac 上の Defender for Endpoint のインストールと構成に使用できる方法と展開ツールがいくつかあります。

- サード パーティの管理ツール:
    - [Microsoft Intune ベースの展開](mac-install-with-intune.md)
    - [JAMF ベースのデプロイ](mac-install-with-jamf.md)
    - [その他の MDM 製品](mac-install-with-other-mdm.md)

- コマンド ライン ツール:
    - [手動展開](mac-install-manually.md)

### <a name="system-requirements"></a>システム要件

macOS の最新の 3 つのメジャー リリースがサポートされています。

> [!IMPORTANT]
> macOS 11 (Big Sur) 以降では、Microsoft Defender for Endpoint追加の構成プロファイルが必要です。 以前のバージョンの macOS からアップグレードしている既存の顧客の場合は、 [macOS Catalina および新しいバージョンの macOS 用の新しい構成プロファイル](mac-sysext-policies.md)に記載されている追加の構成プロファイルを必ずデプロイしてください。

- 12 (弔弔)、11 (ビッグ サー)、10.15 (Catalina)
- ディスク領域: 1 GB

macOS のベータ版はサポートされていません。

M1 チップベースのプロセッサを搭載した macOS デバイスのサポートは、エージェントのバージョン 101.40.84 以降で正式にサポートされています。

サービスを有効にした後、ネットワークまたはファイアウォールを構成して、サービスとエンドポイント間の送信接続を許可することが必要になる場合があります。

### <a name="licensing-requirements"></a>ライセンスの要件

Mac のMicrosoft Defender for Endpointには、次のいずれかの Microsoft ボリューム ライセンス プランが必要です。

- Microsoft 365 E5 (M365 E5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 (M365 A5)
- Windows 10 Enterprise E5
- Microsoft 365 Business Premium
- Windows 11 Enterprise E5
- Microsoft Defender for Endpoint

> [!NOTE]
> 資格のあるライセンスを持つユーザーは、最大 5 台の同時デバイスでMicrosoft Defender for Endpointを使用できます。
> Microsoft Defender for Endpointは、クラウド ソリューション プロバイダー (CSP) から購入することもできます。 CSP を介して購入した場合、Microsoft ボリューム ライセンス プランの一覧は必要ありません。

### <a name="configuring-exclusions"></a>除外の構成

除外を追加する場合は、 [Microsoft Defender ウイルス対策の一般的な除外ミスに](/microsoft-365/security/defender-endpoint/common-exclusion-mistakes-microsoft-defender-antivirus)注意してください。

### <a name="network-connections"></a>ネットワーク接続

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスとその関連 URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター規則がないことを確認する必要があります。または、それらに対して特別に *許可* ルールを作成する必要がある場合があります。


|ドメイン リストのスプレッドシート| 説明|
|---|---|
|商用顧客向けの Microsoft Defender for Endpoint の URL リスト| 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Gov/GCC/DoD 向けの Microsoft Defender for Endpoint の URL リスト | Gov/GCC/DoD のお客様向けのサービスの場所、地理的な場所、OS の特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

Microsoft Defender for Endpointは、次の検出方法を使用してプロキシ サーバーを検出できます。

- プロキシの自動構成 (PAC)
- Web プロキシ自動発見プロトコル (WPAD)
- 手動の静的プロキシ構成

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、前述の URL で匿名トラフィックが許可されていることを確認します。

> [!WARNING]
> 認証されたプロキシはサポートされていません。 PAC、WPAD、または静的プロキシのみが使用されていることを確認します。
>
> セキュリティ上の理由から、SSL 検査とインターセプト プロキシもサポートされていません。 SSL 検査とプロキシ サーバーの例外を構成して、macOS 上のMicrosoft Defender for Endpointからインターセプトなしで関連する URL にデータを直接渡します。 インターセプト証明書をグローバル ストアに追加すると、インターセプトは許可されません。

接続がブロックされていないかどうかをテストするには、ブラウザーを開 <https://x.cp.wd.microsoft.com/api/report> いて <https://cdn.x.cp.wd.microsoft.com/ping> 開きます。

コマンド ラインを使用する場合は、ターミナルで次のコマンドを実行して接続を確認することもできます。

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

このコマンドの出力は、次のようになります。

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> クライアント デバイスで [システム整合性保護](https://support.apple.com/HT204899) (SIP) を有効にしておくことをお勧めします。 SIP は、OS の低レベル改ざんを防止する macOS セキュリティ機能が組み込まれており、既定で有効になっています。

Microsoft Defender for Endpointをインストールしたら、ターミナルで次のコマンドを実行して接続を検証できます。

```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Mac でMicrosoft Defender for Endpointを更新する方法

Microsoft は、パフォーマンス、セキュリティ、新機能を提供するために、ソフトウェア更新プログラムを定期的に発行しています。 Mac でMicrosoft Defender for Endpointを更新するには、Microsoft AutoUpdate (MAU) という名前のプログラムが使用されます。 詳細については、「[Mac でMicrosoft Defender for Endpoint用の更新プログラムを展開](mac-updates.md)する」を参照してください。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Mac でMicrosoft Defender for Endpointを構成する方法

エンタープライズ環境で製品を構成する方法のガイダンスについては、「[Mac でMicrosoft Defender for Endpointの環境設定を設定](mac-preferences.md)する」を参照してください。

## <a name="macos-kernel-and-system-extensions"></a>macOS カーネルとシステム拡張機能

macOS 11 (Big Sur) 以降、Microsoft Defender for Endpointはカーネル拡張機能からシステム拡張機能に完全に移行されました。 カーネル拡張機能は macOS 10.15 (Catalina) で引き続き使用されています。

## <a name="resources"></a>リソース

- ログ記録、アンインストール、またはその他のトピックの詳細については、「[Mac でのMicrosoft Defender for Endpointのリソース」を](mac-resources.md)参照してください。
- [Mac でのMicrosoft Defender for Endpointのプライバシー](mac-privacy.md)。
- [macOS のネットワーク保護を有効にする](network-protection-macos.md)
