---
title: Microsoft Defender for Endpointでアラートを確認する
description: 視覚化されたアラート ストーリーやチェーンの各ステップの詳細など、アラート情報を確認します。
keywords: インシデント, インシデント, マシン, デバイス, ユーザー, アラート, アラート, 調査, グラフ, 証拠
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: 91cd06188a8337f3d0df0b9c67d7c98e389e4351
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64466772"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpointでアラートを確認する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-managealerts-abovefoldlink)

Microsoft Defender for Endpointのアラート ページでは、選択したアラートに関連する攻撃信号とアラートを組み合わせて、アラートに完全なコンテキストを提供し、詳細なアラート ストーリーを作成します。

組織に影響を与えるアラートを迅速にトリアージし、調査し、効果的なアクションを実行します。 トリガーされた理由と、1 つの場所からの影響について理解します。 詳細については、この概要を参照してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a>アラートの概要

Defender for Endpoint でアラートの名前を選択すると、アラート ページに移動します。 アラート ページでは、選択したアラートのコンテキストですべての情報が表示されます。 各アラート ページは、次の 4 つのセクションで構成されます。

1. **アラート のタイトルには** アラートの名前が表示され、ページで選択した内容に関係なく、現在の調査が開始されたアラートを通知します。
2. [**影響を受ける資産**](#review-affected-assets) には、このアラートの影響を受けるデバイスとユーザーのカードが一覧表示され、詳細な情報やアクションをクリックできます。
3. **アラート ストーリー** には、アラートに関連するすべてのエンティティがツリー ビューによって相互接続されて表示されます。 タイトルのアラートは、選択したアラートのページに最初に移動したときにフォーカスが設定されます。 アラート ストーリーのエンティティは展開可能でクリック可能であり、追加情報を提供し、アラート ページのコンテキストで適切なアクションを実行できるようにすることで対応を迅速化します。 アラート ストーリーを使用して調査を開始します。 [Microsoft Defender for Endpointのアラートを調査する方法](/microsoft-365/security/defender-endpoint/investigate-alerts)について説明します。
4. **詳細ウィンドウ** には、最初に選択したアラートの詳細と、このアラートに関連する詳細とアクションが表示されます。 アラート ストーリーで影響を受ける資産またはエンティティのいずれかを選択すると、詳細ウィンドウが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。

アラートの検出状態をメモします。

- 禁止: 試行された疑わしいアクションは回避されました。 たとえば、ファイルがディスクに書き込まれていないか、実行されていません。

  :::image type="content" source="images/detstat-prevented.png" alt-text="脅威の防止を示すページ" lightbox="images/detstat-prevented.png":::

- ブロック: 疑わしい動作が実行され、ブロックされました。 たとえば、プロセスが実行されましたが、その後疑わしい動作が発生したため、プロセスは終了しました。

  :::image type="content" source="images/detstat-blocked.png" alt-text="脅威のブロックを示すページ" lightbox="images/detstat-blocked.png":::

- 検出済み: 攻撃が検出され、まだアクティブな可能性があります。

  :::image type="content" source="images/detstat-detected.png" alt-text="脅威の検出を示すページ" lightbox="images/detstat-detected.png":::

その後、アラートの詳細ウィンドウで *自動調査の詳細* を確認して、既に実行されているアクションを確認したり、推奨されるアクションに関するアラートの説明を読み取ることもできます。

:::image type="content" source="images/alert-air-and-alert-description.png" alt-text="アラートの説明と自動調査セクションが強調表示された詳細ウィンドウ" lightbox="images/alert-air-and-alert-description.png":::

アラートが開いたときに詳細ウィンドウで使用できるその他の情報には、MITRE の手法、ソース、その他のコンテキストの詳細が含まれます。

## <a name="review-affected-assets"></a>影響を受ける資産を確認する

影響を受ける資産セクションでデバイスまたはユーザー カードを選択すると、詳細ウィンドウでデバイスまたはユーザーの詳細に切り替わります。

- **デバイスの場合**、詳細ウィンドウには、デバイス自体に関する情報 (ドメイン、オペレーティング システム、IP など) が表示されます。 アクティブなアラートと、そのデバイスにログオンしているユーザーも利用できます。 デバイスを分離したり、アプリの実行を制限したり、ウイルス対策スキャンを実行したりすることで、すぐにアクションを実行できます。 または、調査パッケージを収集したり、自動調査を開始したり、デバイス ページに移動してデバイスの観点から調査したりできます。

   :::image type="content" source="images/device-page-details.png" alt-text="デバイスが選択されている場合の詳細ウィンドウ" lightbox="images/device-page-details.png":::

- **ユーザーの場合**、詳細ウィンドウには、ユーザーの SAM 名や SID などの詳細なユーザー情報のほか、このユーザーによって実行されるログオンの種類、およびそれに関連するすべてのアラートとインシデントが表示されます。 [ *ユーザー ページを開く* ] を選択すると、そのユーザーの視点から調査を続行できます。

   :::image type="content" source="images/user-page-details.png" alt-text="ユーザーが選択されている場合の詳細ウィンドウ" lightbox="images/user-page-details.png":::

## <a name="related-topics"></a>関連項目

- [インシデント キューを表示して整理する](view-incidents-queue.md)
- [インシデントの調査](investigate-incidents.md)
- [インシデントの管理](manage-incidents.md)
