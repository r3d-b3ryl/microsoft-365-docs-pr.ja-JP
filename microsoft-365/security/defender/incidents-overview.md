---
title: Microsoft 365 Defender でのインシデント
description: デバイス、ユーザー、メールボックス全体で発生したインシデントを調査します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861625"
---
# <a name="incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender でのインシデント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。
>

Microsoft 365 Defender のインシデントは、関連付けられたアラートと、攻撃のストーリーを構成する関連データのコレクションです。 

Microsoft 365 サービスとアプリは、疑わしいイベントや悪意のあるイベントやアクティビティを検出すると、アラートを作成します。 個々のアラートは、完了または継続的な攻撃に関する貴重な手がかりを提供します。 ただし、攻撃は通常、デバイス、ユーザー、メールボックスなど、さまざまな種類のエンティティに対してさまざまな手法を採用します。 結果は、テナント内の複数のエンティティに対する複数の通知になります。 

個々のアラートを組み合わせて攻撃に関する洞察を得る場合は、困難で時間がかかる場合があります。Microsoft 365 Defender は自動的にアラートと関連情報をインシデントに集約します。

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender がエンティティからのイベントをインシデントに関連付ける方法":::

Microsoft 365 Defender でのインシデントのこの短い概要 (4 分) をご覧ください。

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

関連するアラートをインシデントにグループ化すると、攻撃の包括的なビューが得されます。 たとえば、次の情報を表示できます。

- 攻撃が開始された場所。
- どのような戦術が使用されたのか。
- 攻撃がテナントにどれくらいまで入ったか。
- 攻撃の範囲 (影響を受けたデバイス、ユーザー、メールボックスの数など)。 
- 攻撃に関連付けられているすべてのデータ。

有効 [にすると、Microsoft](m365d-enable.md)365 Defender は自動化と人工知能を通じて自動的にアラートを調査および解決できます。 また、追加の修復手順を実行して攻撃を解決することもできます。 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Microsoft 365 セキュリティ センターのインシデントとアラート

Microsoft 365 セキュリティ センター (& >) のクイック 起動時に、インシデント とアラートのインシデントを[管理 security.microsoft.com。](https://security.microsoft.com)  次に例を示します。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 セキュリティ センターの [インシデント] ページ":::

インシデント名を選択すると、インシデントの概要が表示され、追加情報を含むタブにアクセスできます。

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 セキュリティ センターのインシデントの概要ページの例":::

インシデントの追加タブは次のとおりです。

- アラート 

  インシデントとその情報に関連するすべてのアラート。

- デバイス

  インシデントの一部または関連付けとして識別されたすべてのデバイス。

- ユーザー

  インシデントの一部または関連付けとして識別されたすべてのユーザー。

- メールボックス

  インシデントの一部または関連付けとして識別されたすべてのメールボックス。

- 調査

  インシデント内のアラートによってトリガーされる、すべての自動調査。

- 証拠と対応

  インシデント内のアラートでサポートされているイベントと疑わしいエンティティすべて。

Microsoft 365 セキュリティ センターのインシデントとそのデータとインシデントのタブの関係を次に示します。

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="インシデントとそのデータと Microsoft 365 セキュリティ センターのインシデントのタブとの関係":::

## <a name="next-step"></a>次の手順

[インシデント] ページの **インシデント キュー** には、最新のインシデントが一覧表示されます。 ここから、以下の操作を行うことができます。

- 重大度などの要因に基 [づいて優先順位](incident-queue.md) を付ける必要があるインシデントを確認します。 
- インシデントの [調査](investigate-incidents.md) を実行します。
- [インシデントの名前の変更](manage-incidents.md)、割り当て、分類、インシデント管理ワークフローのタグの追加など、インシデントを管理します。
