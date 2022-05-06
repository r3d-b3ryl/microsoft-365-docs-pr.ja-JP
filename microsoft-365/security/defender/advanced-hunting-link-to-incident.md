---
title: クエリ結果をインシデントにリンクする
description: クエリ結果をインシデントにリンクする
keywords: 高度な捜索, インシデント, ピボット, エンティティ, go hunt, 関連イベント, 脅威の捜索, サイバー脅威の捜索, 検索, クエリ, テレメトリ, Microsoft 365, Microsoft 365 Defender
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c81b0b0850686242c675629cf99fa2c4b3a18496
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755499"
---
# <a name="link-query-results-to-an-incident"></a>クエリ結果をインシデントにリンクする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

インシデントへのリンク機能を使用すると、調査中の新しいインシデントまたは既存のインシデントに高度なハンティング クエリの結果を追加できます。 この機能は、高度な捜索アクティビティからレコードを簡単にキャプチャするのに役立ちます。これにより、インシデントに関するより豊富なタイムラインやイベントコンテキストを作成できます。 

## <a name="link-results-to-new-or-existing-incidents"></a>新しいインシデントまたは既存のインシデントに結果をリンクする

1. 高度な検索クエリ ページで、最初に指定されたクエリ フィールドにクエリを入力し、[ **クエリの実行** ] を選択して結果を取得します。

    :::image type="content" source="../../media/link-to-incident-1.png" alt-text="Microsoft 365 Defender ポータルの [クエリ] ページ" lightbox="../../media/link-to-incident-1.png":::

2. [結果] ページで、作業中の新規または現在の調査に関連するイベントまたはレコードを選択し、[ **インシデントへのリンク**] を選択します。

    :::image type="content" source="../../media/link-to-incident-1b.png" alt-text="Microsoft 365 Defender ポータルの [結果] タブの [インシデントへのリンク] オプション" lightbox="../../media/link-to-incident-1b.png":::

3. [インシデントへのリンク] ウィンドウで **[アラートの詳細** ] セクションを見つけ、[ **新しいインシデントの作成** ] を選択してイベントをアラートに変換し、それらを新しいインシデントにグループ化します。

    :::image type="content" source="../../media/link-to-incident-3-create-new.png" alt-text="Microsoft 365 Defender ポータルの [インシデントへのリンク] ウィンドウの [アラートの詳細] セクション" lightbox="../../media/link-to-incident-3-create-new.png":::
    
    または、[ **既存のインシデントにリンク]** を選択して、選択したレコードを既存のインシデントに追加します。 既存のインシデントのドロップダウン リストから関連するインシデントを選択します。 インシデント名または ID の最初のいくつかの文字を入力して、既存のインシデントを検索することもできます。 

    :::image type="content" source="../../media/link-to-incident-3-link-to-existing.png" alt-text="Microsoft 365 Defender ポータルの [アラートの詳細] セクション" lightbox="../../media/link-to-incident-3-link-to-existing.png":::

4. どちらの選択でも、次の詳細を指定し、[ **次へ**] を選択します。
      - **アラート タイトル** - インシデント レスポンダーが理解できる結果のわかりやすいタイトルを指定します。 このわかりやすいタイトルがアラート タイトルになります。
      - **重大度** - アラートのグループに適用される重大度を選択します。
      - **カテゴリ** - アラートに適した脅威カテゴリを選択します。
      - **説明** - グループ化されたアラートに役立つ説明を入力します。
      - **推奨されるアクション** - 修復アクションを提供します。

5. [ **影響を受けるエンティティ** ] セクションで、影響を受けるメイン エンティティまたは影響を受けるエンティティを選択します。 このセクションには、クエリ結果に基づく該当するエンティティのみが表示されます。 この例では、クエリを使用して、電子メール流出インシデントに関連するイベントを検索しました。そのため、送信者は影響を受けるエンティティです。 たとえば、4 つの異なる送信者がある場合は、4 つのアラートが作成され、選択したインシデントにリンクされます。

     :::image type="content" source="../../media/link-to-incident-4-impacted-entities.png" alt-text="Microsoft 365 Defender ポータルの [インシデントへのリンク] セクションの影響を受けるエンティティ" lightbox="../../media/link-to-incident-4-impacted-entities.png":::

1. **[次へ]** を選択します。
1. [ **概要** ] セクションで指定した詳細を確認します。
   :::image type="content" source="../../media/link-to-incident-5-summary.png" alt-text="Microsoft 365 Defender ポータルの [インシデントへのリンク] セクションの結果ページ" lightbox="../../media/link-to-incident-5-summary.png":::
     
1. **[完了]** を選択します。

## <a name="view-linked-records-in-the-incident"></a>インシデント内のリンクされたレコードを表示する

インシデント名を選択すると、イベントがリンクされているインシデントを表示できます。
:::image type="content" source="../../media/link-to-incident-6-incident-pg.png" alt-text="Microsoft 365 Defender ポータルの [概要] タブの [イベントの詳細] 画面" lightbox="../../media/link-to-incident-6-incident-pg.png":::

この例では、選択した 4 つのイベントを表す 4 つのアラートが、新しいインシデントに正常にリンクされました。 

各アラート ページでは、イベントまたはイベントに関する完全な情報をタイムライン ビュー (使用可能な場合) とクエリ結果ビューで確認できます。
:::image type="content" source="../../media/link-to-incident-7-alert-story.png" alt-text="Microsoft 365 Defender ポータルの [タイムライン] タブのイベントの完全な詳細" lightbox="../../media/link-to-incident-7-alert-story.png":::

イベントを選択して、[ **レコードの検査** ] ウィンドウを開くこともできます。
:::image type="content" source="../../media/link-to-incident-7-inspect-record.png" alt-text="Microsoft 365 Defender ポータルの [タイムライン] タブのイベントの検査レコードの詳細" lightbox="../../media/link-to-incident-7-inspect-record.png":::

## <a name="filter-for-events-added-using-advanced-hunting"></a>高度なハンティングを使用して追加されたイベントのフィルター
**手動** 検出ソースでインシデント キューとアラート キューをフィルター処理することで、高度な捜索から生成されたアラートを表示できます。

:::image type="content" source="../../media/link-to-incident-8-filter.png" alt-text="Microsoft 365 Defender ポータルの [フィルター] ページの [インシデントとアラート] キューの手動フィルター処理" lightbox="../../media/link-to-incident-8-filter.png":::
