---
title: Microsoft Defender for Endpoint でのホスト ファイアウォール レポート
description: ポータルでファイアウォール レポートをホストして表示Microsoft 365 Defender。
keywords: Windows Defender,ファイアウォール
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
ms.openlocfilehash: 41fa5aece6f8c18ef16dbf624f90a1ead25b45f5
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65174934"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint でのホスト ファイアウォール レポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

グローバル管理者またはセキュリティ管理者の場合は、[Microsoft 365 Defender ポータル](https://security.microsoft.com)にファイアウォール レポートをホストできるようになりました。 この機能を使用すると、Windows 10、Windows 11、Windows Server 2019、Windows Server 2022 ファイアウォールレポートを一元的な場所から表示できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Windows 10またはWindows 11、または Server 2019 または Windows Server 2022 Windows実行している必要があります。
- Microsoft Defender for Endpoint サービスにデバイスをオンボードするには、[こちらを参照してください](onboard-configure.md)。
- <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータルMicrosoft 365 Defender</a>データの受信を開始するには、高度なセキュリティを備えたWindows Defenderファイアウォールの **監査イベント** を有効にする必要があります。
  - [フィルター プラットフォームのパケット ドロップの監査](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
  - [プラットフォーム接続のフィルター処理の監査](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
- グループ ポリシー オブジェクト エディター、ローカル セキュリティ ポリシー、またはauditpol.exe コマンドを使用して、これらのイベントを有効にします。 詳細については、「[こちら](/windows/win32/fwp/auditing-and-logging)」をご覧ください。
  - 2 つの PowerShell コマンドは次のとおりです。
    - **auditpol /set /サブカテゴリ:"Filtering Platform Packet Drop" /failure:enable**
    - **auditpol /set /サブカテゴリ:"Filtering Platform Connection" /failure:enable**

## <a name="the-process"></a>プロセス

> [!NOTE]
> 上記のセクションの手順に従い、早期プレビュー参加のためにデバイスを適切に構成してください。

- イベントを有効にすると、Microsoft 365 Defenderはデータの監視を開始します。
  - リモート IP、リモート ポート、ローカル ポート、ローカル IP、コンピューター名、受信接続と送信接続間のプロセス。
- 管理者は、[ここで](https://security.microsoft.com/firewall)Windowsホスト ファイアウォール アクティビティを確認できるようになりました。
  - [カスタム レポート スクリプト](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)をダウンロードして、Power BIを使用してWindows Defenderファイアウォールアクティビティを監視することで、追加のレポートを容易にすることができます。
  - データが反映されるまでに最大で 12 時間かかる場合があります。

## <a name="supported-scenarios"></a>サポートされるシナリオ

Ring0 プレビューでは、次のシナリオがサポートされます。

### <a name="firewall-reporting"></a>ファイアウォールレポート

ファイアウォール レポート ページの例をいくつか次に示します。 ここでは、受信、送信、およびアプリケーション のアクティビティの概要を示します。 に移動すると、このページに <https://security.microsoft.com/firewall>直接アクセスできます。

:::image type="content" source="images/host-firewall-reporting-page.png" alt-text="[ホスト ファイアウォール] レポート ページ" lightbox="\images\host-firewall-reporting-page.png":::

これらのレポートには、**ファイアウォールブロック受信接続** カードの下部にある **ReportsSecurity** >  **ReportDevices** >  (セクション) に移動してアクセスすることもできます。

### <a name="from-computers-with-a-blocked-connection-to-device"></a>"接続がブロックされたコンピューター" からデバイスへ

カードは対話型オブジェクトをサポートします。 デバイス名をクリックすると、新しいタブでMicrosoft 365 Defender ポータルが起動し、[**デバイス タイムライン**] タブに直接移動して、デバイスのアクティビティを詳細に確認できます。

:::image type="content" source="images/firewall-reporting-blocked-connection.png" alt-text="[接続がブロックされたコンピューター] ページ" lightbox="\images\firewall-reporting-blocked-connection.png":::

[ **タイムライン** ] タブを選択できるようになりました。これにより、そのデバイスに関連付けられているイベントの一覧が表示されます。

表示ウィンドウの右上隅にある **[フィルター** ] ボタンをクリックした後、目的のイベントの種類を選択します。 この場合、 **ファイアウォール イベント** を選択すると、ウィンドウはファイアウォール イベントにフィルター処理されます。

:::image type="content" source="images/firewall-reporting-filters-button.png" alt-text="[フィルター] ボタン" lightbox="\images\firewall-reporting-filters-button.png":::

### <a name="drill-into-advanced-hunting-preview-refresh"></a>高度なハンティングにドリルインする (プレビュー更新)

ファイアウォール レポートでは、[高度な **検索を開く**] ボタンをクリックして、カードから **直接高度なハンティング** へのドリルがサポートされます。 クエリは事前に設定されます。

:::image type="content" source="images/firewall-reporting-advanced-hunting.png" alt-text="[高度なハンティングを開く] ボタン" lightbox="\images\firewall-reporting-advanced-hunting.png":::

クエリを実行できるようになり、過去 30 日間のすべての関連ファイアウォール イベントを調べることができます。

追加のレポートやカスタム変更を行う場合は、クエリをPower BIにエクスポートして詳細な分析を行うことができます。 カスタム レポートは、[カスタム レポート スクリプト](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall)をダウンロードして、Power BIを使用してWindows Defenderファイアウォール アクティビティを監視することで容易に行うことができます。
