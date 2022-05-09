---
title: Microsoft Defender for Endpoint 展開の設定
description: Microsoft Defender for Endpointのデプロイを設定する方法について説明します
keywords: デプロイ、セットアップ、ライセンス検証、テナント構成、ネットワーク構成
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
ms.openlocfilehash: bae66223494d8de98737516cef1a2c407d7d1a6a
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783537"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a>Microsoft Defender for Endpoint 展開の設定

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Defender for Endpoint のデプロイは、次の 3 フェーズのプロセスです。

|[![デプロイ フェーズ - 準備します。](images/phase-diagrams/prepare.png#lightbox)](prepare-deployment.md)<br>[フェーズ 1: 準備](prepare-deployment.md) | ![デプロイ フェーズ - セットアップ](images/phase-diagrams/setup.png#lightbox)<br>フェーズ 2: セットアップ | [![デプロイ フェーズ - オンボード](images/phase-diagrams/onboard.png#lightbox)](onboarding.md)<br>[フェーズ 3: オンボード](onboarding.md)|
|---|---|---|
||*お客様はここにいます。*||

現在、セットアップ フェーズ中です。

このデプロイ シナリオでは、次の手順について説明します。

- ライセンスの検証
- テナントの構成
- ネットワークの構成

> [!NOTE]
> 一般的なデプロイを案内する目的で、このシナリオではMicrosoft Endpoint Configuration Managerの使用のみを対象とします。 Defender for Endpoint では、他のオンボード ツールの使用がサポートされていますが、展開ガイドではこれらのシナリオについては説明しません。 詳細については、「[デバイスをMicrosoft Defender for Endpointにオンボードする」を](onboard-configure.md)参照してください。

## <a name="check-license-state"></a>ライセンスの状態を確認する

ライセンスの状態と、適切にプロビジョニングされたかどうかを確認するには、管理センターまたは **Microsoft Azure ポータル** を使用します。

1. ライセンスを表示するには、**Microsoft Azure ポータル** に移動し、[Microsoft Azure ポータルのライセンス セクション](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)に移動します。

   :::image type="content" source="images/atp-licensing-azure-portal.png" alt-text="[Azure ライセンス] ページ" lightbox="images/atp-licensing-azure-portal.png":::

1. または、管理センターで **[課金** \> **サブスクリプション]** に移動します。

    画面に、プロビジョニングされたすべてのライセンスとその現在の **状態** が表示されます。

    :::image type="content" source="images/atp-billing-subscriptions.png" alt-text="[課金ライセンス] ページ" lightbox="images/atp-billing-subscriptions.png":::

## <a name="cloud-service-provider-validation"></a>クラウド サービス プロバイダーの検証

会社にプロビジョニングされているライセンスにアクセスし、ライセンスの状態を確認するには、管理センターに移動します。

1. **パートナー ポータル** で、[**サービスの管理] > Office 365** を選択します。

2. **パートナー ポータル** のリンクをクリックすると、[**代理管理者] オプションが** 開き、顧客管理センターにアクセスできるようになります。

   :::image type="content" source="images/atp-O365-admin-portal-customer.png" alt-text="Office 365管理ポータル" lightbox="images/atp-O365-admin-portal-customer.png":::

## <a name="tenant-configuration"></a>テナント構成

Microsoft Defender for Endpointへのオンボードは簡単です。 ナビゲーション メニューから、[エンドポイント] セクションの下にある任意の項目、またはインシデント、ハンティング、アクション センター、脅威分析などのMicrosoft 365 Defender機能を選択して、オンボード プロセスを開始します。

Web ブラウザーから<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">、Microsoft 365 Defender ポータル</a>に移動します。

## <a name="data-center-location"></a>データ センターの場所
Microsoft Defender for Endpointは、[Microsoft 365 Defenderが使用するのと同じ場所](/microsoft-365/security/defender/m365d-enable)にデータを格納して処理します。 Microsoft 365 Defenderがまだオンになっていない場合は、Microsoft Defender for EndpointへのオンボードもMicrosoft 365 Defenderオンになり、アクティブなMicrosoft 365の場所に基づいて新しいデータ センターの場所が自動的に選択されます。 セキュリティ サービス。 選択したデータ センターの場所が画面に表示されます。

## <a name="network-configuration"></a>ネットワークの構成

組織がインターネットにアクセスするためにプロキシを使用するエンドポイントを必要としない場合は、このセクションをスキップします。

Microsoft Defender ATP センサーでは、センサー データをレポートし、Microsoft Defender for Endpoint service サービスと通信するために、Microsoft Windows HTTP (WinHTTP) が必要になります。 埋め込みMicrosoft Defender for Endpointセンサーは、LocalSystem アカウントを使用してシステム コンテキストで実行されます。 センサーは Microsoft Windows HTTP サービス (WinHTTP) を使用して、Microsoft Defender for Endpoint クラウド サービスとの通信を有効にします。 WinHTTP 構成設定は、Windows インターネット (WinINet) インターネット閲覧プロキシ設定とは無関係であり、次の検出方法を使用してのみプロキシ サーバーを検出できます。

- **自動検出メソッド**:
  - 透過プロキシ
  - Web プロキシ自動発見プロトコル (WPAD)

  透過プロキシまたは WPAD がネットワーク トポロジに実装されている場合、特別な構成設定は必要ありません。 プロキシでの URL の除外のMicrosoft Defender for Endpointの詳細については、このドキュメントの「[プロキシ サービス URL」](production-deployment.md#proxy-service-urls)セクションで、URL 許可の一覧または[デバイス プロキシとインターネット接続の設定の構成](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)に関するセクションを参照してください。

- **手動の静的プロキシ構成**:
  - レジストリ ベースの構成
  - netsh コマンドを使用して構成された WinHTTP

    安定したトポロジ内のデスクトップにのみ適しています (たとえば、同じプロキシの背後にある企業ネットワーク内のデスクトップ)。

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a>レジストリ ベースの静的プロキシを使用して、プロキシ サーバーを手動で構成します。

コンピューターがインターネットへの接続を許可されていない場合は、Microsoft Defender for Endpoint センサーのみが診断データを報告し、Microsoft Defender for Endpoint サービスと通信できるようにレジストリ ベースの静的プロキシを構成します。 静的プロキシは、グループ ポリシー (GP) を使用して構成できます。 グループ ポリシーは次の場所にあります。

- コンポーネント \> データ収集とプレビュー ビルド\>Windows管理テンプレート\>接続ユーザー エクスペリエンスとテレメトリ サービスの認証プロキシの使用を構成する
- **[有効]** に設定し、[**認証されたプロキシの使用を無効にする**] を選択します。

1. グループ ポリシー管理コンソールを開きます。
2. 組織のプラクティスに基づいて、ポリシーを作成するか、既存のポリシーを編集します。
3. グループ ポリシーを編集し、**コンポーネント \> データ収集とプレビュー ビルド\>Windows管理用テンプレート\>に移動して、接続ユーザー エクスペリエンスとテレメトリ サービスの認証プロキシの使用を構成します**。

   :::image type="content" source="images/atp-gpo-proxy1.png" alt-text="使用ポリシーの構成に関連するオプション" lightbox="images/atp-gpo-proxy1.png":::

4. **[有効]** を選択します。
5. [ **認証されたプロキシの使用を無効にする]** を選択します。
6. **[管理用テンプレート\>] Windowsコンポーネント \> データ収集とプレビュー ビルド\>に移動して、接続されたユーザー エクスペリエンスとテレメトリを構成します**。

   :::image type="content" source="images/atp-gpo-proxy2.png" alt-text="接続されたユーザー エクスペリエンスとテレメトリの構成に関連するオプション" lightbox="images/atp-gpo-proxy2.png":::

7. **[有効]** を選択します。
8. **プロキシ サーバー名** を入力します。

このポリシーは、レジストリ キー `HKLM\Software\Policies\Microsoft\Windows\DataCollection` の下に 2 つのレジストリ値 `TelemetryProxyServer` を REG_SZ として、`DisableEnterpriseAuthProxy` を REG_DWORD として設定します。

レジストリ値 `TelemetryProxyServer` は、次の文字列形式を取ります:

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
> - トポロジを変更しているノート PC (たとえば、自宅からオフィスへ) は、netsh で誤動作します。 レジストリ ベースの静的プロキシの構成を使用します。

1. 管理者特権でコマンド プロンプトを開きます。
    1. **[スタート]** をクリックし、「**cmd**」と入力します。
    1. **[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドを入力して、**Enter** キーを押します。

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   例: netsh winhttp set proxy 10.0.0.6:8080

### <a name="proxy-configuration-for-down-level-devices"></a>下位レベルのデバイスのプロキシ構成

Down-Level デバイスには、Windows 7 台の SP1 ワークステーションとWindows 8.1 ワークステーション、Windows Server 2008 R2、およびMicrosoft Monitoring Agentを使用して以前にオンボードされたその他のサーバー オペレーティング システムが含まれます。 これらのオペレーティング システムには、エンドポイントから Azure への通信を処理するために、Microsoft 管理エージェントの一部としてプロキシが構成されます。 これらのデバイスでプロキシを構成する方法については、Microsoft 管理エージェントの高速展開ガイドを参照してください。

### <a name="proxy-service-urls"></a>プロキシ サービスの URL

v20 を含む URL は、Windows 10バージョン 1803 または Windows 11 デバイスがある場合にのみ必要です。 たとえば、`us-v20.events.data.microsoft.com`デバイスがWindows 10バージョン 1803 またはWindows 11の場合にのみ必要です。

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、Microsoft Defender for Endpoint センサーがシステム コンテキストから接続されているため、一覧の URL で匿名トラフィックが許可されていることを確認します。

次のダウンロード可能なスプレッドシートには、ネットワークが接続できる必要があるサービスとその関連 URL が一覧表示されます。 これらの URL へのアクセスを拒否するファイアウォールまたはネットワーク フィルター規則がないことを確認するか、それらに対して特別に *許可* 規則を作成する必要がある場合があります。

<br>

****


|ドメイン リストのスプレッドシート| 説明|
|---|---|
|商用顧客向けの Microsoft Defender for Endpoint の URL リスト| 商用顧客向けサービスの場所、地理的な場所、OS に関する特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/b/f/6bfff670-47c3-4e45-b01b-64a2610eaefa/mde-urls-commercial.xlsx)
| Gov/GCC/DoD 向けの Microsoft Defender for Endpoint の URL リスト | Gov/GCC/DoD のお客様向けのサービスの場所、地理的な場所、OS の特定の DNS レコードのスプレッドシート。 <p> [ここにスプレッドシートをダウンロードします。](https://download.microsoft.com/download/6/a/0/6a041da5-c43b-4f17-8167-79dfdc10507f/mde-urls-gov.xlsx)

## <a name="next-step"></a>次の手順

[![**フェーズ 3: オンボード**.](images/onboard.png#lightbox)] <br> [フェーズ 3: オンボード:](onboarding.md) Microsoft Defender for Endpoint サービスがセンサー データを取得できるように、デバイスをサービスにオンボードします。
