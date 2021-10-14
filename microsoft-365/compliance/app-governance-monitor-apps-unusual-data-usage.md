---
title: 異常なデータ使用量のアプリを監視して対応する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 異常なデータ使用量のアプリを監視して対応します。
ms.openlocfilehash: eae71e61d3dede705c034c802841451a599cb971
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335697"
---
# <a name="monitor-and-respond-to-apps-with-unusual-data-usage"></a>異常なデータ使用量のアプリを監視して対応する

アプリ ガバナンスは、不要で潜在的に悪意のあるアプリ アクティビティを特定するのに役立つデータ使用情報を提供します。 この情報は、ポータルの次のセクションから利用できます。

- データ使用量カード - 時間の経過に伴う合計データ使用量を提供し、Microsoft 365 のすべてのアプリの合計アップロードおよびダウンロード アクティビティの突然の急増を強調表示します。 このカードは、ファイルやメールなどのさまざまなリソースの使用情報も個別に提供するため、アプリが悪用している可能性のあるリソースを特定できます。
- アプリの詳細ウィンドウ - [アプリ] ページでアプリを選択すると、ポップアップ ウィンドウにアプリに関する詳細情報が表示されます。 ウィンドウで、リソースの種類ごとのアプリ固有のデータ使用情報を取得し、時間の経過に伴うアップロードとダウンロードのパターンも取得します。
- ポリシー条件 - データ使用量が次の条件に一致するアプリに自動的にフラグを付けて非アクティブ化するポリシーを作成できます。
  - データ使用量 - ダウンロードとアップロードの合計量が指定されたしきい値を超えています
  - データ使用傾向 - 前日と比較したダウンロードとアップロードの合計量の増加率が指定されたしきい値に達しています
