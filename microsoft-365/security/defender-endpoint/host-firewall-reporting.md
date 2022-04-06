---
title: Microsoft Defender for Endpoint でのホスト ファイアウォール レポート
description: ポータルでファイアウォール レポートをホストMicrosoft 365 Defenderします。
keywords: Windows Defender, ファイアウォール
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.openlocfilehash: e5bbdd77226f8649f2a781866fef614706e8a789
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475281"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint でのホスト ファイアウォール レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

管理者の場合は、ファイアウォールレポートをポータルにホストMicrosoft 365 Defender[できます](https://security.microsoft.com)。 この機能を使用すると、Windows 10、Windows 11、Windows Server 2019、Windows Server 2022 ファイアウォール レポートを一元的な場所から表示できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- サーバー 11 または Windows 10サーバー 2019 Windowsサーバー 2019 または Windowsサーバー 2022 Windowsする必要があります。
- デバイスを Microsoft Defender for Endpoint サービスにオンボードするには、こちらを参照 [してください](onboard-configure.md)。
- ポータル <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderデータ</a>の受信を開始するには、Advanced **Security** を使用してファイアウォールの監査イベントWindows Defender有効にする必要があります。
  - [監査フィルター プラットフォーム のパケット ドロップ](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
  - [監査フィルター プラットフォーム接続](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
- グループ ポリシー オブジェクト エディター、ローカル セキュリティ ポリシー、またはグループ ポリシー コマンドを使用して、これらのイベントauditpol.exeします。 詳細については、こちらを参照 [してください](/windows/win32/fwp/auditing-and-logging)。
  - 2 つの PowerShell コマンドは次のとおりです。
    - **auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**
    - **auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**

## <a name="the-process"></a>プロセス

> [!NOTE]
> 上記のセクションの指示に従い、早期プレビュー参加のためにデバイスを適切に構成してください。

- イベントを有効にすると、Microsoft 365 Defenderの監視が開始されます。
  - リモート IP、リモート ポート、ローカル ポート、ローカル IP、コンピューター名、受信接続と送信接続間のプロセス。
- 管理者は、ここでホストWindowsを確認[できます](https://security.microsoft.com/firewall)。
  - カスタム レポート スクリプトをダウンロードして、カスタム レポート[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)を使用してファイアウォールのWindows Defenderを監視することで、Power BI。
  - データが反映されるまで最大 12 時間かかる場合があります。

## <a name="supported-scenarios"></a>サポートされるシナリオ

Ring0 Preview では、次のシナリオがサポートされています。

### <a name="firewall-reporting"></a>ファイアウォールレポート

ファイアウォール レポート ページの例を次に示します。 ここでは、受信、送信、およびアプリケーションアクティビティの概要を示します。 に移動すると、このページに直接アクセスできます <https://security.microsoft.com/firewall>。

> [!div class="mx-imgBorder"]
> :::image type="content" source="\images\host-firewall-reporting-page.png" alt-text="[ホスト ファイアウォールレポート] ページ" lightbox="\images\host-firewall-reporting-page.png":::

これらのレポートには、ファイアウォールブロックされた受信接続カードの下部にある **ReportsSecurity** >  **ReportDevices** >  (セクション) に **アクセスすることもできます。**

### <a name="from-computers-with-a-blocked-connection-to-device"></a>"接続がブロックされているコンピューター" からデバイスへ

カードは対話型オブジェクトをサポートします。 デバイスのアクティビティをドリル インするには、デバイス名をクリックして、新しいタブで Microsoft 365 Defender ポータルを起動し、[デバイス タイムライン] タブに直接 **移動** します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="\images\firewall-reporting-blocked-connection.png" alt-text="[接続がブロックされているコンピューター] ページ" lightbox="\images\firewall-reporting-blocked-connection.png":::

[タイムライン] タブ **を選択** すると、そのデバイスに関連付けられたイベントの一覧が表示されます。

表示ウィンドウの右上隅にある **[フィルター** ] ボタンをクリックした後、目的のイベントの種類を選択します。 この場合、[ファイアウォール イベント] **を選択** すると、ウィンドウはファイアウォール イベントにフィルター処理されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="\images\firewall-reporting-filters-button.png" alt-text="[フィルター] ボタン" lightbox="\images\firewall-reporting-filters-button.png":::

### <a name="drill-into-advanced-hunting-preview-refresh"></a>高度な検索 (プレビュー更新) の詳細を確認する

ファイアウォール レポートでは、[高度な検索を開く] ボタンをクリックして、カードから高度なハンティングに直接 **ドリルを実行** できます。 クエリは事前に設定されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="\images\firewall-reporting-advanced-hunting.png" alt-text="[高度な検索を開く] ボタン" lightbox="\images\firewall-reporting-advanced-hunting.png":::

クエリを実行し、過去 30 日間のすべての関連ファイアウォール イベントを確認できます。

追加のレポートやカスタムの変更については、クエリをエクスポートして、Power BI分析できます。 カスタム レポートは、カスタム レポート スクリプトをダウンロード[](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)して、カスタム レポートを使用してファイアウォールWindows Defender監視することでPower BI。
