---
title: デバイスコントロールを使用して組織のデータを保護する
description: デバイス制御レポートを使用して組織のデータ セキュリティを監視します。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 8d9a853309c03b635896dc124c86787ae07ddafe
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490179"
---
# <a name="protect-your-organizations-data-with-device-control"></a>デバイスコントロールを使用して組織のデータを保護する

**適用対象:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpoint デバイスコントロールは、リムーバブル ストレージ デバイスや USB ドライブの使用など、組織内のデバイスによるメディアの使用を監視および制御することで、データ損失から保護します。

デバイス制御レポートでは、次のようなメディアの使用状況に関連するイベントを表示できます。

- **監査イベント:** 外部メディアが接続されている場合に発生する監査イベントの数を示します。
- **ポリシー イベント:** デバイス制御ポリシーがトリガーされた場合に発生するポリシー イベントの数を示します。

> [!NOTE]
> メディアの使用状況を追跡する監査イベントは、Microsoft Defender for Endpoint にオンボードされているデバイスに対して既定で有効になっています。

## <a name="understanding-the-audit-events"></a>監査イベントについて

監査イベントには、次のものが含まれます。

- **USB ドライブのマウントとマウント解除:** USB ドライブのマウントまたはマウント解除時に生成される監査イベント。
- **PnP:** プラグ アンド プレイ監査イベントは、リムーバブル 記憶域、プリンター、またはメディアが接続Bluetooth生成されます。

## <a name="monitor-device-control-security"></a>デバイス制御のセキュリティを監視する

Microsoft Defender for Endpoint のデバイス制御により、セキュリティ管理者は、レポートを通じて組織のデバイス制御セキュリティを追跡できるツールを使用できます。 [デバイスの保護のレポート] にアクセスして、Microsoft 365セキュリティ センターでデバイス **制御レポート>確認できます**。

[レポート] ダッシュボードの **[** デバイス保護] カードには、過去 180 日間にメディアの種類によって生成された監査イベントの数が表示されます。

> [!div class="mx-imgBorder"]
> ![DeviceControlReportCard](images/devicecontrolcard.png)

[ **詳細の表示]** ボタンには、デバイスコントロールレポートページにメディア使用状況 **データが表示** されます。

このページには、種類ごとのイベントの集計数とイベントの一覧を示すダッシュボードが表示されます。 管理者は、時間範囲、メディア クラス名、およびデバイス ID をフィルター処理できます。

> [!div class="mx-imgBorder"]
> ![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)

イベントを選択すると、詳細を示すフライアウトが表示されます。

- **一般的な詳細:** 日付、アクション モード、およびこのイベントのポリシー。
- **メディア情報:** メディア情報には、メディア名、クラス名、クラス GUID、デバイス ID、ベンダー ID、ボリューム、シリアル番号、バスの種類が含まれます。
- **場所の詳細:** デバイス名と MDATP デバイス ID。

> [!div class="mx-imgBorder"]
> ![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)

組織全体でこのメディアのリアルタイム アクティビティを表示するには、[高度な検索を開く] **ボタンを選択** します。 これには、事前に定義された埋め込みクエリが含まれます。

> [!div class="mx-imgBorder"]
> ![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)

デバイスのセキュリティを確認するには、フライアウトの [デバイス ページを **開く** ] ボタンを選択します。 このボタンをクリックすると、デバイス エンティティ ページが開きます。

> [!div class="mx-imgBorder"]
> ![DeviceEntityPage](images/Devicesecuritypage.png)

## <a name="reporting-delays"></a>レポートの遅延

デバイス制御レポートには、メディア接続が発生した時刻から、イベントがカードまたはドメイン リストに反映されるまで、12 時間の遅延が発生する可能性があります。