---
title: Microsoft Defender for Endpoint 展開の設定
description: アプリケーションの展開をセットアップする方法についてMicrosoft Defender for Endpoint
keywords: 展開、セットアップ、ライセンス検証、テナント構成、ネットワーク構成
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e1fbfdaa71cc57a7797a2b95c96a56abba4fcc40
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2022
ms.locfileid: "64506991"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>Microsoft Defender for Endpoint 展開の設定

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint の展開は、次の 3 フェーズプロセスです。

|[![展開フェーズ - 準備します。](images/phase-diagrams/prepare.png#lightbox)](prepare-deployment.md)<br>[フェーズ 1: 準備](prepare-deployment.md) | ![展開フェーズ - セットアップ](images/phase-diagrams/setup.png#lightbox)<br>フェーズ 2: セットアップ | [![展開フェーズ - オンボード](images/phase-diagrams/onboard.png#lightbox)](onboarding.md)<br>[フェーズ 3: オンボード](onboarding.md)|
|---|---|---|
||*お前はここにいる!*||

現在、セットアップ フェーズに入っている。

この展開シナリオでは、次の手順について説明します。

- ライセンスの検証
- テナント構成
- ネットワーク構成

> [!NOTE]
> 一般的な展開を案内する目的で、このシナリオでは、このシナリオでは、ユーザーの使用のみをMicrosoft Endpoint Configuration Manager。 Defender for Endpoint は、他のオンボーディング ツールの使用をサポートしていますが、展開ガイドではこれらのシナリオについては説明しません。 詳細については、「オンボード デバイス[を使用してデバイスをMicrosoft Defender for Endpoint](onboard-configure.md)。

## <a name="check-license-state"></a>ライセンスの状態を確認する

ライセンスの状態を確認し、適切にプロビジョニングされたかどうかは、管理センターまたはポータルから **Microsoft Azureできます**。

1. ライセンスを表示するには、Microsoft Azureポータルに **移動** し、[Microsoft Azure [] セクションに移動します](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。

   :::image type="content" source="images/atp-licensing-azure-portal.png" alt-text="[Azure ライセンス] ページ" lightbox="images/atp-licensing-azure-portal.png":::

1. または、管理センターで [課金サブスクリプション] **に** \> **移動します**。

    画面には、すべてのプロビジョニング済みライセンスと現在の状態が表示 **されます**。

    :::image type="content" source="images/atp-billing-subscriptions.png" alt-text="[課金ライセンス] ページ" lightbox="images/atp-billing-subscriptions.png":::

## <a name="cloud-service-provider-validation"></a>クラウド サービス プロバイダーの検証

会社にプロビジョニングされるライセンスにアクセスし、ライセンスの状態を確認するには、管理センターに移動します。

1. パートナー ポータルで **、[サービス** の管理] **を選択> Office 365**。

2. [パートナー ポータル] **リンクをクリック** すると、[代理として管理者] オプションが開き、顧客管理センターにアクセスできます。

   :::image type="content" source="images/atp-O365-admin-portal-customer.png" alt-text="管理者Office 365ポータル" lightbox="images/atp-O365-admin-portal-customer.png":::

## <a name="tenant-configuration"></a>テナント構成

オンボーディングはMicrosoft Defender for Endpoint簡単です。 ナビゲーション メニューから、[エンドポイント] セクションの下の任意のアイテムを選択するか、インシデント、ハンティング、アクション センター、脅威分析などの Microsoft 365 Defender 機能を選択してオンボーディング プロセスを開始します。

Web ブラウザーから、ポータルのMicrosoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">します</a>。

## <a name="data-center-location"></a>データ センターの場所
Microsoft Defender for Endpointは、ユーザーが使用する場所と同じ場所にデータを格納[して処理Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable)。 まだMicrosoft 365 Defenderされていない場合は、Microsoft Defender for Endpoint へのオンボーディングも Microsoft 365 Defender有効にされ、アクティブなデータ センターの場所に基づいて新しいデータ センターの場所が自動的に選択Microsoft 365 セキュリティ サービス。 選択したデータ センターの場所が画面に表示されます。

## <a name="network-configuration"></a>ネットワーク構成

組織がプロキシを使用してインターネットにアクセスするためにエンドポイントを必要としない場合は、このセクションをスキップします。

Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。 埋め込みMicrosoft Defender for Endpointは、LocalSystem アカウントを使用してシステム コンテキストで実行されます。 センサーは Microsoft Windows HTTP サービス (WinHTTP) を使用して、Microsoft Defender for Endpoint クラウド サービスとの通信を有効にします。 WinHTTP 構成設定は、Windows インターネット (WinINet) のインターネット閲覧プロキシ設定とは独立し、次の検出方法を使用してのみプロキシ サーバーを検出できます。

- **自動検出メソッド**:
  - 透過プロキシ
  - Web プロキシ自動発見プロトコル (WPAD)

  透過プロキシまたは WPAD がネットワーク トポロジに実装されている場合、特別な構成設定は不要です。 プロキシ内の Microsoft Defender for Endpoint URL の除外の詳細については、このドキュメントの「デバイス プロキシとインターネット接続の設定を構成する」の「URL 許可リスト」または「Configure device proxy and Internet [connectivity](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) settings」の「Proxy [Service](production-deployment.md#proxy-service-urls) URL」セクションを参照してください。

- **静的プロキシの手動構成**:
  - レジストリ ベースの構成
  - netsh コマンドを使用して構成された WinHTTP

    安定したトポロジ (たとえば、同じプロキシの背後にある企業ネットワーク内のデスクトップ) のデスクトップにのみ適しています。

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>レジストリ ベースの静的プロキシを使用して、プロキシ サーバーを手動で構成します。

コンピューターがインターネットへの接続を許可されていない場合、Microsoft Defender for Endpoint センサーだけが診断データを報告し、Microsoft Defender for Endpoint サービスと通信できるレジストリ ベースの静的プロキシを構成します。 静的プロキシは、グループ ポリシー (GP) を使用して構成できます。 グループ ポリシーは次の場所にあります。

- 管理用テンプレート \> Windows コンポーネント \> \> データ収集とプレビュー ビルド接続ユーザー エクスペリエンスとテレメトリ サービスの認証プロキシの使用を構成する
- [有効] に **設定し、[** 認証された **プロキシの使用を無効にする] を選択します。**

1. グループ ポリシー管理コンソールを開きます。
2. 組織のプラクティスに基づいてポリシーを作成するか、既存のポリシーを編集します。
3. サーバーをグループ ポリシー **\> \> \>** し、[管理用テンプレート] Windows コンポーネント のデータ収集とプレビュー ビルドに移動し、[接続されたユーザー エクスペリエンスとテレメトリ サービスの認証されたプロキシの使用状況を構成する] に移動します。

   :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="使用状況ポリシーの構成に関連するオプション" lightbox="images/atp-gpo-proxy1.png":::

4. **[有効]** を選択します。
5. [認証 **されたプロキシの使用を無効にする] を選択します**。
6. [管理 **用テンプレート] Windows \> コンポーネント \> データ\>** 収集とプレビュー ビルド 接続されたユーザー エクスペリエンスと利用統計情報を構成します。

   :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="接続されたユーザー エクスペリエンスと利用統計情報の構成に関連するオプション" lightbox="images/atp-gpo-proxy2.png":::

7. **[有効]** を選択します。
8. プロキシ サーバー **名を入力します**。

このポリシーは、レジストリ キー `HKLM\Software\Policies\Microsoft\Windows\DataCollection` の下に 2 つのレジストリ値 `TelemetryProxyServer` を REG_SZ として、`DisableEnterpriseAuthProxy` を REG_DWORD として設定します。

レジストリ値は、次 `TelemetryProxyServer` の文字列形式を取ります。

```text
<server name or ip>:<port>
```

例: 10.0.0.6:8080

レジストリ値 `DisableEnterpriseAuthProxy` を 1に設定する必要があります。

### <a name="configure-the-proxy-server-manually-using-netsh-command"></a>netsh コマンドを使用してプロキシ サーバーを手動で構成する

netsh を使用して、システム全体の静的プロキシを構成します。

> [!NOTE]
>
> - これは、既定のプロキシで WinHTTP を使用する Windows サービスを含むすべてのアプリケーションに影響します。
> - トポロジを変更しているラップトップ (たとえば、オフィスから自宅) は netsh に誤動作します。 レジストリ ベースの静的プロキシの構成を使用します。

1. 管理者特権でコマンド プロンプトを開きます。
    1. **[スタート]** をクリックし、「**cmd**」と入力します。
    1. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter** キーを押します。

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   例: netsh winhttp set proxy 10.0.0.6:8080

### <a name="proxy-configuration-for-down-level-devices"></a>ダウンレベル デバイスのプロキシ構成

Down-Level には、Windows 7 SP1 および Windows 8.1 ワークステーション、Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2、および Windows Server 2016 のバージョンが含Windows サーバー CB 1803。 これらのオペレーティング システムでは、エンドポイントから Azure への通信を処理するために、Microsoft 管理エージェントの一部としてプロキシが構成されます。 これらのデバイスでのプロキシの構成方法については、「Microsoft Management Agent Fast Deployment Guide」を参照してください。

### <a name="proxy-service-urls"></a>プロキシ サービスの URL

v20 を含む URL は、Windows 10バージョン 1803 または Windows 11です。 たとえば、デバイス`us-v20.events.data.microsoft.com`がバージョン 1803 またはバージョン 1803 上Windows 10場合にのみWindows 11。

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合Microsoft Defender for Endpointセンサーがシステム コンテキストから接続している場合は、リストされている URL で匿名トラフィックが許可されている必要があります。

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスと関連付けられている URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター ルールが存在しないか、許可ルールの作成が必要な場合があります。

<br>

****


|ドメインリストのスプレッドシート| 説明|
|---|---|
|Microsoft Defender for Endpointの URL リスト| 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Microsoft Defender for Endpoint/Gov/GCC/DoD の URL リスト | Gov/GCC/DoD のお客様向けサービスの場所、地理的な場所、OS の特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

## <a name="next-step"></a>次の手順

[![**Phase 3: Onboard**.](images/onboard.png#lightbox)] <br> [フェーズ 3: オンボード](onboarding.md): サービスにデバイスをオンボードし、Microsoft Defender for Endpointからセンサー データを取得できます。
