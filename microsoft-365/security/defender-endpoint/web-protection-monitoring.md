---
title: Microsoft Defender for Endpoint での Web 閲覧セキュリティの監視
description: Microsoft Defender for Endpoint の Web 保護を使用して Web 閲覧のセキュリティを監視する
keywords: Web 保護、Web 脅威保護、Web 閲覧、監視、レポート、カード、ドメイン リスト、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 384ea6f07a1b84421e8961d43bb97fd589c0c39a
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53656189"
---
# <a name="monitor-web-browsing-security"></a>Web 閲覧のセキュリティを監視する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web 保護を使用すると、組織の Web 閲覧のセキュリティを監視するために、>ポータルの **[レポート** と Web 保護Microsoft 365 Defenderできます。 レポートには、Web 脅威検出の統計情報を提供するカードが含まれます。

- **Web 脅威保護の** 検出時間の推移 - この傾向カードには、選択した期間中に種類別に検出された Web 脅威の数が表示されます (過去 30 日間、過去 3 か月、過去 6 か月)

  :::image type="content" alt-text="Web 脅威の保護検出を時間の間に示すカードの画像" source="images/wtp-blocks-over-time.png" lightbox="images/wtp-blocks-over-time.png":::

- **Web 脅威保護の** 概要 - このカードには、過去 30 日間の Web 脅威検出の合計が表示され、さまざまな種類の Web 脅威に対する配布が表示されます。 スライスを選択すると、悪意のある Web サイトや望ましくない Web サイトで見つかったドメインの一覧が開きます。

  :::image type="content" alt-text="Web 脅威保護の概要を示すカードの画像" source="images/wtp-summary.png" lightbox="images/wtp-summary.png":::

> [!NOTE]
> ブロックがカードまたはドメイン リストに反映されるまで最大 12 時間かかる場合があります。

## <a name="types-of-web-threats"></a>Web の脅威の種類

Web 保護は、悪意のある Web サイトと望ましくない Web サイトを次のように分類します。

- **フィッシング -** スプーフィングされた Web フォームや、ユーザーをだまして資格情報などの機密情報を取得するように設計された他のフィッシング メカニズムを含む Web サイト
- **悪意** のある - マルウェアをホストし、コードを悪用する Web サイト
- **カスタム インジケーター** - ブロック用にカスタム インジケーター リストに追加した URL またはドメインを持つ [Web](manage-indicators.md) サイト

## <a name="view-the-domain-list"></a>ドメイン リストの表示

Web 脅威保護の概要カードで特定の Web 脅威カテゴリを **選択して** 、[ドメイン] ページ **を開** きます。 このページには、その脅威カテゴリの下のドメインの一覧が表示されます。 このページには、ドメインごとに次の情報が表示されます。

- **アクセス数** - ドメイン内の URL に対する要求の数
- **ブロック** - 要求がブロックされた回数
- **アクセスの傾向** - アクセス試行回数の変更
- **脅威カテゴリ** - Web 脅威の種類
- **デバイス** - アクセス試行を行うデバイスの数

ドメインを選択して、そのドメイン内の URL にアクセスしようとしたデバイスの一覧と URL の一覧を表示します。

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web コンテンツ フィルタリング](web-content-filtering.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web の脅威への対応](web-protection-response.md)
