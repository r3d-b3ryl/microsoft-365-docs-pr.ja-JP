---
title: Microsoft Defender for Endpoint ファイルを調査する
description: 調査オプションを使用して、アラート、動作、またはイベントに関連付けられているファイルの詳細を取得します。
keywords: 調査, 調査, ファイル, 悪意のあるアクティビティ, 攻撃の動機, ディープ分析, 詳細分析レポート
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 642fc9b8f38b0687a27d73a47324dc3b3f70269e
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388190"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Microsoft Defender for Endpointアラートに関連付けられているファイルを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatefiles-abovefoldlink)

特定のアラート、動作、またはイベントに関連付けられているファイルの詳細を調査し、ファイルが悪意のあるアクティビティを示しているかどうかを判断し、攻撃の動機を特定し、侵害の潜在的な範囲を理解するのに役立ちます。

特定のファイルの詳細なプロファイル ページにアクセスするには、さまざまな方法があります。 たとえば、検索機能を使用したり、 **アラート プロセス ツリー**、 **インシデント グラフ**、 **成果物タイムライン** からリンクをクリックしたり、 **デバイス タイムライン** に一覧表示されているイベントを選択したりできます。

詳細なプロファイル ページで、新しいファイル ページを切り替えることで、 **新しい** ページレイアウトと古いページ レイアウトを切り替えることができます。 この記事の残りの部分では、新しいページ レイアウトについて説明します。

ファイル ビューの次のセクションから情報を取得できます。

- ファイルの詳細、マルウェアの検出、ファイルの普及率
- ファイル PE メタデータ (存在する場合)
- 詳細分析
- アラート
- 組織内で観察される
- 詳細分析
- ファイル名

このページからファイルに対してアクションを実行することもできます。

## <a name="file-actions"></a>ファイル操作

プロファイル ページの上部にあるファイル情報カードの上。 ここで実行できるアクションは次のとおりです。

- 停止と検疫
- インジケーターの追加/編集
- ファイルをダウンロードする
- 脅威のエキスパートに相談する
- アクション センター

これらのアクションの詳細については、「 [ファイルに対する応答アクションの実行」を](respond-file-alerts.md)参照してください。

## <a name="file-details-malware-detection-and-file-prevalence"></a>ファイルの詳細、マルウェア検出、ファイルの普及率

ファイルの詳細、インシデント、マルウェア検出、ファイルの普及率カードには、ファイルに関するさまざまな属性が表示されます。

ファイルの MD5、ウイルス合計検出率、Microsoft Defender ウイルス対策検出 (使用可能な場合)、ファイルの普及率などの詳細が表示されます。

ファイルの普及率カードには、組織内および世界中のデバイスでファイルが表示された場所が表示されます。 ファイルが表示された最初のデバイスと最後のデバイスに簡単にピボットし、デバイスタイムラインで調査を続行できます。 

> [!NOTE]
> ファイルの普及率カードの *組織セクションのデバイスには* 、異なるユーザーが異なる値を表示する場合があります。 これは、ユーザーが持つ RBAC スコープに基づいてカードに情報が表示されるためです。 つまり、特定のデバイス セットに対する可視性がユーザーに付与されている場合、それらのデバイスに対するファイルの組織の普及率のみが表示されます。

:::image type="content" source="images/atp-file-information.png" alt-text="ファイル情報" lightbox="images/atp-file-information.png":::

## <a name="alerts"></a>アラート

[ **アラート]** タブには、ファイルに関連付けられているアラートの一覧と、アラートがリンクされているインシデントが表示されます。 この一覧には、影響を受けるデバイスが属しているデバイス グループがある場合を除き、アラート キューと同じ情報の多くが含まれます。 列ヘッダーの上にあるツール バーから **[列のカスタマイズ** ] を選択すると、表示される情報の種類を選択できます。

:::image type="content" source="images/atp-alerts-related-to-file.png" alt-text="ファイル セクションに関連するアラート" lightbox="images/atp-alerts-related-to-file.png":::

## <a name="observed-in-organization"></a>組織内で観察される

[ **組織の監視** ] タブでは、ファイルで監視されたデバイスを確認する日付範囲を指定できます。

> [!NOTE]
> このタブには、最大 100 台のデバイスが表示されます。 ファイル _を含むすべての_ デバイスを表示するには、タブの列ヘッダーの上にあるアクション メニューから **[エクスポート** ] を選択して、タブを CSV ファイルにエクスポートします。

:::image type="content" source="images/atp-observed-machines.png" alt-text="ファイルで観察された最新のデバイス" lightbox="images/atp-observed-machines.png":::

スライダーまたは範囲セレクターを使用して、ファイルに関連するイベントを確認する期間をすばやく指定します。 範囲に対するアラートの表示によって支援を受けることができます。 タイム ウィンドウは、1 日に限り小さく指定できます。 これにより、その時点でその IP アドレスと通信したファイルのみが表示され、不要なスクロールと検索が大幅に減ります。

## <a name="deep-analysis"></a>詳細分析

[ **ディープ分析** ] タブでは、 [詳細な分析のためにファイルを送信](respond-file-alerts.md#deep-analysis)し、ファイルの動作に関する詳細と組織内での影響を明らかにすることができます。 ファイルを送信すると、結果が使用可能になると、詳細分析レポートがこのタブに表示されます。 詳細な分析で何も見つからなかった場合、レポートは空になり、結果の領域は空白のままになります。

:::image type="content" source="images/submit-file.png" alt-text="[ディープ分析] タブ" lightbox="images/submit-file.png":::

## <a name="file-names"></a>ファイル名

[ **ファイル名** ] タブには、組織内で使用するために観察されたすべての名前が一覧表示されます。

:::image type="content" source="images/atp-file-names.png" alt-text="[ファイル名] タブ" lightbox="images/atp-file-names.png":::

## <a name="action-center"></a>アクション センター

**アクション センター** には、特定のファイルでフィルター処理されたアクション センターが表示されるため、保留中のアクションとファイルに対して実行されたアクションの履歴を確認できます。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender for Endpoint キューを表示および整理する](alerts-queue.md)
- [Microsoft Defender for Endpoint アラートを管理する](manage-alerts.md)
- [Microsoft Defender for Endpointアラートを調査する](investigate-alerts.md)
- [Microsoft Defender for Endpoint デバイスの一覧のデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Microsoft Defender for Endpointでユーザー アカウントを調査する](investigate-user.md)
- [ファイルの対応措置を講じる](respond-file-alerts.md)
