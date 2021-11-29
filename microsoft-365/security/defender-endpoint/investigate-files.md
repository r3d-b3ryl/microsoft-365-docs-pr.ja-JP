---
title: Microsoft Defender for Endpoint ファイルの調査
description: 調査オプションを使用して、アラート、動作、またはイベントに関連付けられたファイルの詳細を取得します。
keywords: 調査、調査、ファイル、悪意のあるアクティビティ、攻撃の動機、深い分析、深い分析レポート
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 704510b6b31e47b1a68ab90ffbf5e6e7353d0969
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217940"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatefiles-abovefoldlink)

特定のアラート、動作、またはイベントに関連付けられたファイルの詳細を調査して、ファイルに悪意のあるアクティビティが発生したかどうかを判断し、攻撃の動機を特定し、侵害の潜在的な範囲を理解します。

特定のファイルの詳細なプロファイル ページにアクセスするには、さまざまな方法があります。 たとえば、検索機能を使用したり、アラート プロセス ツリー 、**インシデント** グラフ、アーティファクト タイムラインからのリンクをクリックしたり、デバイス タイムラインに一覧表示されているイベント **を選択できます**。 

詳細なプロファイル ページに移動したら、新しい [ファイル] ページを切り替えて、新しいページ レイアウトと古いページ レイアウト **を切り替えることができます**。 この記事の残りの部分では、新しいページ レイアウトについて説明します。

ファイル ビューでは、次のセクションから情報を取得できます。

- ファイルの詳細, マルウェアの検出, ファイルの普及率
- 詳細分析
- アラート
- 組織内で観察される
- 詳細分析
- ファイル名

このページからファイルに対してアクションを実行することもできます。

## <a name="file-actions"></a>ファイル操作

プロファイル ページの上部、ファイル情報カードの上。 ここで実行できるアクションは次のとおりです。

- 停止と検疫
- インジケーターの追加および編集
- ファイルをダウンロードする
- 脅威のエキスパートに相談する
- アクション センター

これらのアクションの詳細については、「ファイルに [対して応答アクションを実行する」を参照してください](respond-file-alerts.md)。

## <a name="file-details-malware-detection-and-file-prevalence"></a>ファイルの詳細、マルウェア検出、ファイルの普及率

ファイルの詳細、インシデント、マルウェア検出、およびファイル普及率カードには、ファイルに関するさまざまな属性が表示されます。

ファイルの MD5、ウイルスの合計検出率、使用可能な場合は Microsoft Defender AV 検出、ファイルの普及率などの詳細が表示されます。

ファイルの有病率カードは、組織内および世界中のデバイスでファイルが見られた場所を示します。

> [!NOTE]
> 異なるユーザーは、ファイル普及カードの組織セクションのデバイスに異なる値を表示する場合があります。 これは、ユーザーが持つ RBAC スコープに基づいて情報がカードに表示されるためです。 つまり、ユーザーが特定のデバイス セットで表示を許可されている場合、それらのデバイスに対するファイル組織の普及率だけが表示されます。

![ファイル情報のイメージ。](images/atp-file-information.png)

## <a name="alerts"></a>アラート

[ **アラート]** タブには、ファイルに関連付けられているアラートの一覧が表示されます。 このリストには、影響を受けるデバイスが属するデバイス グループがある場合を除き、アラート キューと同じ情報の多くが含まれる。 列ヘッダーの上にあるツールバーから [列のカスタマイズ] を選択すると、表示される情報の種類を選択できます。

![ファイル セクションに関連するアラートのイメージ。](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a>組織内で観察される

[ **組織で観察]** タブを使用すると、日付範囲を指定して、ファイルで観察されたデバイスを確認できます。

> [!NOTE]
> このタブには、最大 100 台のデバイスが表示されます。 ファイルを _含む_ すべてのデバイスを表示するには、タブの列ヘッダーの上にあるアクションメニューから [エクスポート] を選択して、タブを CSV ファイルにエクスポートします。

![ファイルを含む最新の観測デバイスのイメージ。](images/atp-observed-machines.png)

スライダーまたは範囲セレクターを使用して、ファイルに関連するイベントを確認する期間をすばやく指定します。 タイム ウィンドウは、1 日に限り小さく指定できます。 これにより、その時点でその IP アドレスと通信したファイルだけが表示され、不要なスクロールと検索が大幅に削減されます。

## <a name="deep-analysis"></a>詳細分析

[**深い分析**] タブ [](respond-file-alerts.md#deep-analysis)を使用すると、ファイルを詳細に分析するためにファイルを提出し、ファイルの動作の詳細と、ファイルが組織に与える影響を明らかにできます。 ファイルを送信すると、結果が得られたら、このタブに詳細分析レポートが表示されます。 深い分析で何も見つからなかった場合、レポートは空で、結果領域は空白のままです。

![[詳細な分析] タブのイメージ。](images/submit-file.png)

## <a name="file-names"></a>ファイル名

[ **ファイル名] タブ** には、組織でファイルが使用されているすべての名前が一覧表示されます。

![[ファイル名] タブのイメージ。](images/atp-file-names.png)

## <a name="related-topics"></a>関連トピック

- [Microsoft Defender for Endpoint キューの表示と整理](alerts-queue.md)
- [エンドポイント通知の Microsoft Defender の管理](manage-alerts.md)
- [Microsoft Defender for Endpoint アラートの調査](investigate-alerts.md)
- [Microsoft Defender for Endpoint Devices リストのデバイスを調査する](investigate-machines.md)
- [Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する](investigate-ip.md)
- [Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する](investigate-domain.md)
- [Microsoft Defender for Endpoint のユーザー アカウントを調査する](investigate-user.md)
- [ファイルの対応措置を講じる](respond-file-alerts.md)
