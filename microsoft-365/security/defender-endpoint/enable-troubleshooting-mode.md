---
title: Microsoft Defender for Endpointでのトラブルシューティング モードでの概要
description: Microsoft Defender for Endpointトラブルシューティング モードをオンにして、さまざまなウイルス対策の問題に対処します。
keywords: ウイルス対策, トラブルシューティング, トラブルシューティング モード, 改ざん防止, 互換性
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 07ebfc55df3a03d3447e12f540b7c200de16ae51
ms.sourcegitcommit: 872ab0b6a225c20274916e07ed4cc4944be9509a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65679016"
---
# <a name="get-started-with-troubleshooting-mode-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでのトラブルシューティング モードでの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
> [!NOTE]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

Microsoft Defender for Endpointトラブルシューティング モードを使用すると、組織のポリシーによって制御されている場合でも、デバイスから有効にし、さまざまなシナリオをテストすることで、さまざまな Microsoft Defender ウイルス対策機能のトラブルシューティングを行うことができます。 トラブルシューティング モードは既定で無効になっており、デバイス (またはデバイスのグループ) で一定の時間有効にする必要があります。 これは排他的にEnterprise専用の機能であり、Microsoft 365 Defenderアクセスが必要であることに注意してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- トラブルシューティング モードを使用して、改ざん防止設定を無効または変更して実行します。

  - Microsoft Defender ウイルス対策機能のトラブルシューティング/アプリケーションの互換性 (偽陽性のアプリケーション ブロック)。

  - トラブルシューティング モードを使用し、改ざん防止やその他のウイルス対策設定を操作することで、パフォーマンスのトラブルシューティングをMicrosoft Defender ウイルス対策します。

- 改ざんイベントが発生した場合 (たとえば、スナップショットが変更または削除された場合)、 `MpPreference` トラブルシューティング モードは終了し、改ざん保護はデバイスで有効になります。

- 適切なアクセス許可を持つローカル管理者は、通常ポリシーによってロックされている個々のエンドポイントの構成を変更できます。 デバイスをトラブルシューティング モードにすると、Microsoft Defender ウイルス対策パフォーマンスと互換性のシナリオを診断するときに役立ちます。

  - ローカル管理者は、Microsoft Defender ウイルス対策をオフにしたり、アンインストールしたりすることはできません。

  - ローカル管理者は、Microsoft Defender ウイルス対策 スイート内の他のすべてのセキュリティ設定 (クラウド保護、改ざん防止など) を構成できます。

- "セキュリティ設定の管理" アクセス許可を持つ管理者は、トラブルシューティング モードを有効にするためのアクセス権を持ちます。

- Microsoft Defender for Endpointは、トラブルシューティング プロセス全体を通じてログと調査データを収集します。

  - `MpPreference`のスナップショットは、トラブルシューティング モードが開始される前に作成されます。

  - 2 つ目のスナップショットは、トラブルシューティング モードの有効期限が切れる直前に作成されます。

  - トラブルシューティング モード中の操作ログも収集されます。

  - 上記のすべてのログとスナップショットが収集され、デバイス ページの [[調査パッケージ](respond-machine-alerts.md#collect-investigation-package-from-devices) の収集] 機能を使用して管理者が収集できるようになります。 管理者がデータを収集するまで、Microsoft はデバイスからこのデータを削除しません。

- 管理者は、デバイス ページでイベント ビューアーのトラブルシューティング モード中に行われる **設定の変更** を確認することもできます。

- トラブルシューティング モードは、有効期限 (3 時間) に達すると自動的にオフになります。 有効期限が切れた後、すべてのポリシー管理構成は再び読み取り専用になり、トラブルシューティング モードをオンに設定する前の状態に戻ります。

- コマンドがMicrosoft 365 Defenderからデバイスでアクティブになるまでに、最大で 15 分かかる場合があります。

- トラブルシューティング モードが開始され、トラブルシューティング モードが終了すると、エンド ユーザーに通知が送信されます。 また、まもなく終了することを通知する警告も送信されます。

- トラブルシューティング モードの開始と終了は、デバイス ページの **デバイス タイムライン** で識別されます。

- 高度な捜索では、すべてのトラブルシューティング モード イベントに対してクエリを実行できます。

> [!NOTE]
> ポリシー管理の変更は、コンピューターがトラブルシューティング モードでアクティブになっている場合に適用されます。 ただし、トラブルシューティング モードの有効期限が切れるまで、変更は有効になりません。 さらに、Microsoft Defender ウイルス対策 プラットフォームの更新プログラムは、トラブルシューティング モードでは適用されません。 トラブルシューティング モードがWindows更新プログラムで終了すると、プラットフォームの更新プログラムが適用されます。

## <a name="prerequisites"></a>前提条件

- Windows 10 (バージョン 19044.1618 以降)、Windows 11、Windows Server 2019、または Windows Server 2022 を実行しているデバイス。

  半期/Redstone|OS のバージョン|Release
  :---|:---|:---
  21H2/SV1|>=22000.593|[KB5011563: Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011563)
  20H1/20H2/21H1|>=19042.1620<br/> >=19041.1620<br/> >=19043.1620|[KB5011543: Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011543)
  Windows Server 2022|>=20348.617|[KB5011558: Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011558)
  Windows Server 2019 (RS5)|>=17763.2746|[KB5011551: Microsoft Update Catalog](https://www.catalog.update.microsoft.com/Search.aspx?q=KB5011551)

- トラブルシューティング モードを適用するには、Microsoft Defender for Endpointがテナント登録され、デバイスでアクティブになっている必要があります。

- デバイスは、Microsoft Defender ウイルス対策バージョン 4.18.2203 以降をアクティブに実行している必要があります。

## <a name="enable-the-troubleshooting-mode"></a>トラブルシューティング モードを有効にする

1. Microsoft 365 Defender ポータル (<https://security.microsoft.com>) に移動し、サインインします。

2. トラブルシューティング モードを有効にするデバイスのデバイス ページ/コンピューター ページに移動します。 **[トラブルシューティング モードを有効にする]** を選択します。 これには、Microsoft Defender for Endpointの "セキュリティ センターでセキュリティ設定を管理する" アクセス許可が必要であることに注意してください。

   :::image type="content" source="../../media/ts-mode-menu.png" alt-text="トラブルシューティング モードを有効にする" lightbox="../../media/ts-mode-menu.png":::

3. デバイスのトラブルシューティング モードを有効にすることを確認します。

   :::image type="content" source="../../media/ts-mode-conf-flyout.png" alt-text="構成ポップアップ" lightbox="../../media/ts-mode-conf-flyout.png":::

4. デバイス ページには、デバイスがトラブルシューティング モードになっていると表示されます。

   :::image type="content" source="../../media/ts-mode-option-greyed-out.png" alt-text="デバイスがトラブルシューティング モードになりました" lightbox="../../media/ts-mode-option-greyed-out.png":::

## <a name="advanced-hunting-queries"></a>高度なハンティング クエリ

環境で発生しているトラブルシューティング イベントを把握できるように、事前に構築された高度なハンティング クエリを次に示します。 また、これらのクエリを使用して、デバイスがトラブルシューティング モードのときにアラートを表示する [検出ルールを作成](/defender/custom-detection-rules.md#create-a-custom-detection-rule) することもできます。

### <a name="get-troubleshooting-events-for-a-particular-device"></a>特定のデバイスのトラブルシューティング イベントを取得する

```kusto
let deviceName = "<device name>";   // update with device name
let deviceId = "<device id>";   // update with device id
search in (DeviceEvents)
(DeviceName == deviceName
) and ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| project $table, Timestamp,DeviceId, DeviceName, _tsmodeproperties,
 _tsmodeproperties.TroubleshootingState, _tsmodeproperties.TroubleshootingPreviousState, _tsmodeproperties.TroubleshootingStartTime,
 _tsmodeproperties.TroubleshootingStateExpiry, _tsmodeproperties.TroubleshootingStateRemainingMinutes,
 _tsmodeproperties.TroubleshootingStateChangeReason, _tsmodeproperties.TroubleshootingStateChangeSource
```

### <a name="devices-currently-in-troubleshooting-mode"></a>現在トラブルシューティング モードのデバイス

```kusto
search in (DeviceEvents)
ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where Timestamp > ago(3h)
| where _tsmodeproperties.TroubleshootingStateChangeReason == "Troubleshooting mode started"
|summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
```

### <a name="count-of-troubleshooting-mode-instances-by-device"></a>デバイス別のトラブルシューティング モード インスタンスの数

```kusto
search in (DeviceEvents)
ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where Timestamp > ago(30d)  // choose the date range you want
| where _tsmodeproperties.TroubleshootingStateChangeReason == "Troubleshooting mode started"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| sort by count_
```

### <a name="total-count"></a>総件数

```kusto
search in (DeviceEvents)
ActionType == "AntivirusTroubleshootModeEvent"
| extend _tsmodeproperties = parse_json(AdditionalFields)
| where Timestamp > ago(2d) //beginning of time range
| where Timestamp < ago(1d) //end of time range
| where _tsmodeproperties.TroubleshootingStateChangeReason == "Troubleshooting mode started"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count()
| where count_ > 5          // choose your max # of TS mode instances for your time range
```

## <a name="related-topic"></a>関連トピック

- [トラブルシューティング モードがオンです](troubleshooting-mode-scenarios.md)
- [改ざん防止機能を使用してセキュリティ設定を保護する](prevent-changes-to-security-settings-with-tamper-protection.md)
