---
title: Microsoft Defender for Endpointでの Web 閲覧のセキュリティの監視
description: Microsoft Defender for Endpointで Web 保護を使用して Web 閲覧のセキュリティを監視する
keywords: Web 保護, Web 脅威保護, Web 閲覧, 監視, レポート, カード, ドメインリスト, セキュリティ, フィッシング, マルウェア, エクスプロイト, Web サイト, ネットワーク保護, Edge, Internet Explorer, Chrome, Firefox, Web ブラウザー
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cf702dbcbec1bf9141827610c1304a0f19e13b90
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475875"
---
# <a name="monitor-web-browsing-security"></a>Web 閲覧のセキュリティを監視する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web 保護を使用すると、Microsoft 365 Defender ポータルの **[レポート] > [Web 保護**] の下にあるレポートを使用して、組織の Web 閲覧セキュリティを監視できます。 レポートには、Web 脅威検出の統計情報を提供するカードが含まれています。

- **時間の経過と共に Web 脅威保護の検出** - この傾向カードには、選択した期間中に種類別に検出された Web 脅威の数が表示されます (過去 30 日間、過去 3 か月間、過去 6 か月間)

  :::image type="content" source="images/wtp-blocks-over-time.png" alt-text="Web 脅威保護の検出を時間の経過と共に示すカード" lightbox="images/wtp-blocks-over-time.png":::

- **Web 脅威保護の概要** - このカードには、過去 30 日間の Web 脅威検出の合計が表示され、さまざまな種類の Web 脅威に分散が表示されます。 スライスを選択すると、悪意のある Web サイトまたは不要な Web サイトで検出されたドメインの一覧が開きます。

  :::image type="content" source="images/wtp-summary.png" alt-text="Web 脅威保護の概要を示すカード"  lightbox="images/wtp-summary.png":::

> [!NOTE]
> カードまたはドメイン リストにブロックが反映されるまでには、最大で 12 時間かかる場合があります。

## <a name="types-of-web-threats"></a>Web 脅威の種類

Web 保護は、悪意のある Web サイトと望ましくない Web サイトを次のように分類します。

- **フィッシング** - ユーザーをだまして資格情報やその他の機密情報を漏らすために設計されたスプーフィングされた Web フォームやその他のフィッシング メカニズムを含む Web サイト
- **悪意のある** - マルウェアをホストし、コードを悪用する Web サイト
- **カスタム インジケーター** - ブロック用の [カスタム インジケーター リスト](manage-indicators.md) に追加した URL またはドメインを持つ Web サイト

## <a name="view-the-domain-list"></a>ドメイン一覧を表示する

Web 脅威 **保護の概要** カードで特定の Web 脅威カテゴリを選択して、[ **ドメイン] ページを** 開きます。 このページには、その脅威カテゴリの下にあるドメインの一覧が表示されます。 このページでは、ドメインごとに次の情報が提供されます。

- **アクセス数** - ドメイン内の URL に対する要求の数
- **ブロック** - 要求がブロックされた回数
- **アクセスの傾向** - アクセス試行回数の変化
- **脅威カテゴリ** - Web 脅威の種類
- **デバイス** - アクセス試行があるデバイスの数

ドメインを選択すると、そのドメイン内の URL にアクセスしようとしたデバイスの一覧と URL の一覧が表示されます。

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web コンテンツ フィルタリング](web-content-filtering.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web の脅威への対応](web-protection-response.md)
