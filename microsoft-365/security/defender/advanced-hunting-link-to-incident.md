---
title: クエリ結果をインシデントにリンクする
description: クエリ結果をインシデントにリンクする
keywords: 高度な狩猟、インシデント、ピボット、エンティティ、go hunt、関連イベント、脅威ハンティング、サイバー脅威ハンティング、検索、クエリ、テレメトリ、Microsoft 365、Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5302c078da3ded781007412a2807fc20fa77319e
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2021
ms.locfileid: "61220898"
---
# <a name="link-query-results-to-an-incident"></a>クエリ結果をインシデントにリンクする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

インシデント機能へのリンクを使用すると、調査中の新規または既存のインシデントに高度な検索クエリ結果を追加できます。 この機能を使用すると、高度な狩猟アクティビティからレコードを簡単にキャプチャし、インシデントに関するイベントのより豊富なタイムラインまたはコンテキストを作成できます。 

## <a name="link-results-to-new-or-existing-incidents"></a>結果を新規または既存のインシデントにリンクする

1. 高度な検索クエリ ページで、まずクエリ フィールドにクエリを入力し、[クエリの実行] を選択して結果を取得します。

    :::image type="content" source="../../media/link-to-incident-1.png" alt-text="ポータル内の **Query** ページのMicrosoft 365 Defender例" lightbox="../../media/link-to-incident-1.png":::

2. [結果] ページで、作業している新しい調査または現在の調査に関連するイベントまたはレコードを選択し、[インシデントにリンク] **を選択します**。

    :::image type="content" source="../../media/link-to-incident-1b.png" alt-text="ポータルの **Results** タブの **インシデントへのリンク** オプションMicrosoft 365 Defenderします。" lightbox="../../media/link-to-incident-1b.png":::

3. [インシデント **へのリンク]** ウィンドウで [アラートの詳細]セクションを見つけ、[新しいインシデントの作成] を選択してイベントをアラートに変換し、新しいインシデントにグループ化します。

    :::image type="content" source="../../media/link-to-incident-3-create-new.png" alt-text="ポータルの **インシデントへのリンク** ウィンドウの **Alert details** セクションのMicrosoft 365 Defender例" lightbox="../../media/link-to-incident-3-create-new.png":::
    
    または、[ **既存のインシデントへのリンク] を選択して** 、選択したレコードを既存のインシデントに追加します。 既存のインシデントのドロップダウン リストから関連するインシデントを選択します。 インシデント名または ID の最初の数文字を入力して、既存のインシデントを検索できます。 

    :::image type="content" source="../../media/link-to-incident-3-link-to-existing.png" alt-text="ポータルの **インシデントへのリンク** ウィンドウの **Alert details** セクションのMicrosoft 365 Defender例":::

4. どちらの選択でも、次の詳細を入力し、[次へ] を **選択します**。
      - **アラート タイトル** - インシデントレスポンダーが理解できる結果の説明的なタイトルを提供します。 これは、アラート タイトルになります。
      - **重大度** - アラートのグループに適用される重大度を選択します。
      - **[カテゴリ** ] - アラートの適切な脅威カテゴリを選択します。
      - **説明** - グループ化されたアラートに役立つ説明を提供します。
      - **推奨されるアクション** - 修復アクションを提供します。

5. [影響を **受けるエンティティ] セクション** で、影響を受ける主なエンティティまたは影響を受けるエンティティを選択します。 このセクションには、クエリ結果に基づく適用可能なエンティティだけが表示されます。 この例では、クエリを使用して、可能性がある電子メールのexfiltrationインシデントに関連するイベントを検索しました。したがって、Sender は影響を受けたエンティティです。 たとえば、4 つの異なる送信者がある場合、4 つのアラートが作成され、選択したインシデントにリンクされます。

     :::image type="content" source="../../media/link-to-incident-4-impacted-entities.png" alt-text="ポータルの **インシデントへのリンク** セクションの影響を受けたエンティティMicrosoft 365 Defender例" lightbox="../../media/link-to-incident-4-impacted-entities.png":::

1. **[次へ]** を選択します。
1. [概要] セクションで指定した詳細 **を確認** します。
     :::image type="content" source="../../media/link-to-incident-5-summary.png" alt-text="ポータルの **インシデントへのリンク** セクションの結果ページMicrosoft 365 Defender例" lightbox="../../media/link-to-incident-5-summary.png":::
     
1. [**完了**] を選択します。

## <a name="view-linked-records-in-the-incident"></a>インシデント内のリンクされたレコードを表示する

インシデント名を選択すると、イベントがリンクされているインシデントを表示できます。
     :::image type="content" source="../../media/link-to-incident-6-incident-pg.png" alt-text="ポータルの **Summary** タブのイベントの詳細画面Microsoft 365 Defender例" lightbox="../../media/link-to-incident-6-incident-pg.png":::

この例では、選択した 4 つのイベントを表す 4 つのアラートが、新しいインシデントに正常にリンクされました。 

各アラート ページで、タイムライン ビュー (利用可能な場合) およびクエリ結果ビューでイベントまたはイベントに関する完全な情報を見ることができます。
     :::image type="content" source="../../media/link-to-incident-7-alert-story.png" alt-text="ポータルの **Timeline** タブのイベントの完全な詳細のMicrosoft 365 Defender例" lightbox="../../media/link-to-incident-7-alert-story.png":::

イベントを選択して、[レコードの検査] ウィンドウ **を開** くすることもできます。
:::image type="content" source="../../media/link-to-incident-7-inspect-record.png" alt-text="イベントのレコードの詳細を、ポータルの **Timeline** タブで調Microsoft 365 Defender例" lightbox="../../media/link-to-incident-7-inspect-record.png":::

## <a name="filter-for-events-added-using-advanced-hunting"></a>高度な検索を使用して追加されたイベントのフィルター
インシデント キューとアラート キューを手動検出ソースでフィルター処理することで、高度な検索から生成されたアラート **を** 表示できます。

:::image type="content" source="../../media/link-to-incident-8-filter.png" alt-text="イベント ポータルの **Filters** ページのインシデントキューとアラート キューの手動フィルター Microsoft 365 Defender例" lightbox="../../media/link-to-incident-8-filter.png":::
