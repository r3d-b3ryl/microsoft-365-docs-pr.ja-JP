---
title: デバイス制御を使用して組織のデータを保護する
description: デバイス制御レポートを使用して組織のデータ セキュリティを監視します。
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 6fe93be2ec244628f2bf2195eb453307235ea06f
ms.sourcegitcommit: 997eb64f80da99b1099daba62994c722bbb25d72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2022
ms.locfileid: "66129187"
---
# <a name="device-control-report"></a>デバイス制御レポート

**適用対象:** 
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for Endpointデバイス制御は、リムーバブル ストレージ デバイスや USB ドライブなど、組織内のデバイスによるメディアの使用を監視および制御することで、データ損失から保護します。

デバイス制御レポートを使用すると、メディアの使用状況に関連するイベントを表示できます。 このようなイベントは次のとおりです。

- **監査イベント:** 外部メディアが接続されたときに発生する監査イベントの数を示します。
- **ポリシー イベント:** デバイス制御ポリシーがトリガーされたときに発生するポリシー イベントの数を示します。

> [!NOTE]
> メディアの使用状況を追跡する監査イベントは、Microsoft Defender for Endpointにオンボードされたデバイスに対して既定で有効になっています。

## <a name="understanding-the-audit-events"></a>監査イベントについて

監査イベントには、次のものが含まれます。

- **USB ドライブのマウントとマウント解除:** USB ドライブがマウントまたはマウント解除されたときに生成されるイベントを監査します。
- **PnP:** リムーバブル ストレージ、プリンター、またはBluetooth メディアが接続されると、プラグ アンド プレイ監査イベントが生成されます。
- **リムーバブル ストレージ のアクセス制御:** リムーバブル ストレージ アクセス制御ポリシーがトリガーされると、イベントが生成されます。 監査、ブロック、または許可を指定できます。

## <a name="monitor-device-control-security"></a>デバイス制御のセキュリティを監視する

Defender for Endpoint のデバイス制御により、セキュリティ管理者は、レポートを使用して組織のデバイス制御セキュリティを追跡できるツールを使用できます。 デバイス制御レポートは、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) で確認できます。 **[レポート****全般** > セキュリティ]  >  レポートに移動 **します**。 **デバイス コントロール カードを** 探し、リンクを選択してレポートを開きます。 

**レポート** ダッシュボードのデバイス保護カードには、過去 180 日間にメディアの種類別に生成された監査イベントの数が表示されます。

[ **詳細の表示]** ボタンには、 **デバイス コントロール レポート** ページに、その他のメディア使用状況データが表示されます。

このページには、種類ごとのイベントの集計数とイベントの一覧が含まれるダッシュボードが提供され、ページごとに 500 イベントが表示されますが、管理者は下にスクロールして、より多くのイベントを表示し、時間範囲、メディア クラス名、デバイス ID でフィルター処理できます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Detaileddevicecontrolreport.png" alt-text="Microsoft 365 Defender ポータルの [デバイス制御レポートの詳細] ページ" lightbox="images/Detaileddevicecontrolreport.png":::

イベントを選択すると、詳細情報を示すポップアップが表示されます。

- **一般的な詳細:** 日付、アクション モード、ポリシー、およびこのイベントのアクセス。
- **メディア情報:** メディア情報には、メディア名、クラス名、クラス GUID、デバイス ID、ベンダー ID、シリアル番号、およびバスの種類が含まれます。
- **場所の詳細:** デバイス名、ユーザー、および MDATP デバイス ID。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/devicecontrolreportfilter.png" alt-text="[デバイスコントロールレポートのフィルター] ページ" lightbox="images/devicecontrolreportfilter.png":::

組織全体でこのメディアのリアルタイム アクティビティを表示するには、[ **高度なハンティングを開く** ] ボタンを選択します。 これには、定義済みの埋め込みクエリが含まれます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Devicecontrolreportquery.png" alt-text="[デバイスコントロールレポートのクエリ] ページ" lightbox="images/Devicecontrolreportquery.png":::

デバイスのセキュリティを確認するには、ポップアップで [ **デバイスを開く] ページ** ボタンを選択します。 このボタンをクリックすると、デバイス エンティティ ページが開きます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/Devicesecuritypage.png" alt-text="[デバイス エンティティ] ページ" lightbox="images/Devicesecuritypage.png":::

## <a name="reporting-delays"></a>レポートの遅延

メディア接続が発生した時点から、イベントがカードまたはドメイン リストに反映されるまでに最大 12 時間の遅延が発生する可能性があります。
