---
title: データ移行をリクエストする方法
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5bb64310-36fc-473d-b791-a0176f21707f
f1.keywords:
- NOCSH
description: 既存の Office 365 のお客様は、お住まいの国が新しい geo に Microsoft 365 サービスデータを移動する前に、要求を提出する必要があります。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f7ca333ca12faab84df54582ecd3212842d26e1a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949800"
---
# <a name="how-to-request-your-data-move"></a>データ移行をリクエストする方法

> [!NOTE]
> このページの情報は、geo で新しいデータセンターを開始する前に、既存の Microsoft 365 テナントを持っているお客様にのみ適用されます。 移行の適格性は、特定のワークロードプロビジョニングの日付にも依存しているため、テナントの作成日は常に重要な1つの日付になるとは限りません。
  
既存の Microsoft 365 お客様は、組織の主要な顧客データ全体の移行を要求することができます。  
  
## <a name="when-can-i-request-a-move"></a>いつ移行をリクエストできますか?

|**国がサインアップしているお客様**|**リクエスト期間の開始**|**リクエストの期限**|
|:-----|:-----|:-----|
|日本  <br/> |2020年1月1日  <br/> |2020 年 6 月 30 日  <br/> |
|オーストラリア、ニュージーランド、フィジー  <br/> |2020年1月1日  <br/> |2020 年 6 月 30 日  <br/> |
|インド  <br/> |2020年1月1日  <br/> |2020 年 6 月 30 日  <br/> |
|カナダ  <br/> |2020年1月1日  <br/> |2020 年 6 月 30 日  <br/> |
|英国  <br/> |2020年1月1日  <br/> |2020 年 6 月 30 日  <br/> |
|韓国  <br/> |2020年1月1日  <br/> |2020 年 6 月 30 日  <br/> |
|フランス  <br/> |2020年1月1日  <br/> |2020 年 6 月 30 日  <br/> |
|アラブ首長国連邦  <br/> |2019 年 7 月 15 日  <br/> |2020 年 6 月 30 日  <br/> |
|南アフリカ  <br/> |2019 年 7 月 25 日  <br/> |2020 年 6 月 30 日  <br/> |
|スイス、リヒテンシュタイン  <br/> |2019 年 12 月 10 日  <br/> |2020 年 6 月 30 日  <br/> |
|ノルウェー  <br/> |2020 年 4 月 15 日  <br/> |2020年10月31日  <br/> |
|ドイツ  <br/> |計画  <br/> |計画  <br/> |

## <a name="how-to-request-a-move"></a>移行をリクエストする方法

対象となるお客様には、 [Microsoft 365 管理センター](https://aka.ms/365admin)にページが表示されます。これにより、お客様は自社のコア顧客データを新しいデータセンターリージョンに移動するよう要求できます。  
  
Microsoft 365 管理センターのページにアクセスするには、左側のナビゲーションウィンドウで [ **設定**] を展開し、[ **組織の設定**] をクリックします。
Tab **組織プロファイル**を選択して、[ **Data レジデンシー**] オプションを選択します。
  
このセクションは、テナントが Microsoft 365 引っ越しプログラムの対象外である場合には表示されません。  データ常駐の要件があり、移行を要求する必要がある組織の場合は、チェックボックスをオンにして、 **保存**します。
  
![データセンターのオプトイン操作画面](../media/dataresidencyflyoutae.jpg)
  
「 **Data レジデンシー** 」セクションのテキストが、組織が適切な国および日付に **データを移動するように要求** したことを示すように変化することを確認する必要があります。 メッセージ センターにも確認メッセージが届きます。 これにより、移行が正常にリクエストされたことを確認できます。 


  
## <a name="what-happens-after-requesting-a-move"></a>移行をリクエストした後はどうなりますか?

移行をリクエストした後、運用上の制約が許容されるように、をすばやく移行することを計画します。 予測不可能な性質の制約が数多くあるため、移行が実施される特定の日付や時間帯を共有することはできません。 お客様のテナントの管理者は、各サービスの移行が完了した後で、メッセージセンターに通知が表示されます。
  
移行を完了するには、お住まいの国のリクエストの期限から最大 24 か月かかる場合があります。
  
## <a name="microsoft-teams"></a>Microsoft Teams

2020年1月の間、対象となる Office 365 諸国のお客様は、Microsoft Teams chat service データの移行をオプトインできます。  オプトインタイムラインは、対象となるすべての国に対して再オープンまたは拡張されています。これにより、お客様は、範囲内の Microsoft Teams で移行プログラムを検討する機会を得ることができます。 データ常駐移行のために以前にオプトインされていたお客様は、Teams をローカルデータセンター geo に移行することもできます。これらのお客様には、追加の作業は必要ありません。

## <a name="related-topics"></a>関連項目

[コア データを新しい Office 365 データ センター geo に移行する](moving-data-to-new-datacenter-geos.md)

[データ移行についての一般的な FAQ](data-move-faq.md)

[Microsoft Dynamics CRM Online の新しいデータ センター geo](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure のリージョン](https://azure.microsoft.com/regions/)
  

