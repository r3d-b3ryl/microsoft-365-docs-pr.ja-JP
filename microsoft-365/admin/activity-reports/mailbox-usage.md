---
title: メールボックス使用状況レポートをMicrosoft 365 管理センターする
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: メールボックスの使用状況レポートを取得して、ユーザー メールボックスを持つユーザーのアクティビティ レベルと、それぞれのストレージとクォータの情報について確認する方法について説明します。
ms.openlocfilehash: 4df0859930d2fe8a11623a775c96454fd3c9aaa7
ms.sourcegitcommit: af6c13d7ab1fe440dd45ce8cd3940774cdda66ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2022
ms.locfileid: "67004288"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>管理センターの Microsoft 365 レポート - メールボックスの使用状況

**メールボックス使用状況レポート** は、電子メール送信、読み取り、予定の作成、会議の送信、会議の承諾、会議の辞退、会議の取り消しに基づいて、ユーザー メールボックスを持つユーザーに関する情報と各アクティビティのレベルを提供します。 また、各ユーザーのメールボックスが使用している記憶域の容量と、憶域のクォータに近づいているメールボックスの数についても表示されます。 メールボックス使用状況レポートには、ユーザー間で共有されているメールボックスに関する情報も含まれており、共有メールボックスのストレージとクォータ データが提供されます。
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>メールボックスの使用状況レポートを取得する方法

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。
2. **Email アクティビティ** の下にある **[その他の表示**] を選択します。 
3. **[Email アクティビティ**] ドロップダウン リストから、[**Exchange** \> **メールボックスの使用状況**] を選択します。

## <a name="interpret-the-mailbox-usage-report"></a>メールボックス使用状況レポートを解釈する

メールボックス、**ストレージ**、**クォータ** のグラフを見ると、組織の **メールボックス** の使用状況を確認できます。

共有メールボックス情報にアクセスするには、グラフの右上にあるドロップダウンの選択を **[共有**] に変更します。  テナントに共有メールボックスがない場合は、共有メールボックス情報を表示できません。  また、共有グラフを表示することを選択した場合、現在、グラフ情報をエクスポートすることはできません。 これは既知の問題であり、今後のイテレーションで修正される予定です。
  
:::image type="content" alt-text="メールボックスの使用状況レポート。" source="../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png" lightbox="../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png":::

[ **メールボックスの使用状況**] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択した場合、テーブルには現在の日付から最大 28 日間のデータが表示されます (レポートが生成された日付ではありません)。 各レポートのデータは、通常、過去 24 - 48 時間まで表示されます。

### <a name="the-mailbox-chart"></a>メールボックス グラフ

**メールボックス** グラフには、組織内のユーザーまたは共有メールボックスの合計数と、レポート期間の任意の日にアクティブになっている合計数が表示されます。 ユーザーまたは共有メールボックスは、電子メールの送信、読み取り、予定の作成、会議の送信、会議の承諾、会議の辞退、会議アクティビティの取り消しを行った場合、アクティブと見なされます。

メールボックス グラフで次の処理を行います。
- Y 軸は、ユーザーまたは共有メールボックスの数です。 
- X 軸は、この特定のレポートで選択された日付範囲です。

### <a name="the-storage-chart"></a>ストレージ グラフ

**[ストレージ]** グラフには、メールボックスの種類別に組織内で使用されているストレージの量が表示されます。 ストレージ グラフには、アーカイブ メールボックスは含まれません。 自動拡張アーカイブの詳細については、「 [Microsoft 365 での自動拡張アーカイブの概要」を](../../compliance/autoexpanding-archiving.md)参照してください。

ストレージ チャートで次の手順を実行します。
- Y 軸は、組織内のユーザーまたは共有メールボックスによって使用されるストレージの量です。
- X 軸は、この特定のレポートで選択された日付範囲です。

### <a name="the-quota-chart"></a>クォータ グラフ

**クォータ** グラフには、各クォータ カテゴリのユーザーまたは共有メールボックスの数が表示されます。 クォータには 4 つのカテゴリがあります。 
- 適切: 使用されるストレージが "問題の警告" クォータを下回っているユーザーまたは共有メールボックスの数。
- 警告: 使用されているストレージが "問題の警告" クォータ以上で、"送信禁止" クォータを下回っているユーザーまたは共有メールボックスの数。
- 送信できない: 使用されるストレージが送信禁止クォータ以上で、送受信禁止クォータ以下のユーザーまたは共有メールボックスの数。
- 送受信できない: 使用されるストレージが "送受信禁止" クォータ以上のユーザーまたは共有メールボックスの数。

クォータ グラフで次の手順を実行します。
- Y 軸は、各ストレージ クォータ内のユーザーまたは共有メールボックスの数です。
- X 軸はクォータ カテゴリです。

凡例の項目を選択すると、表示されるグラフをフィルター処理できます。

## <a name="mailbox-usage-per-mailbox-table"></a>メールボックス テーブルあたりのメールボックス使用量

次の表に、メールボックスごとのレベルでのメールボックス使用量の内訳を示します。 テーブルには列を追加することができます。 

|アイテム|説明|
|:-----|:-----|
|受信者の種類 |共有またはユーザー。 |
|ユーザー名 |ユーザーの電子メール アドレス。 |
|表示名  |ユーザーの完全な名前。 |
|Deleted |現在の状態が削除されたが、レポートのレポート期間中にアクティブであったメールボックス。|
|削除された日付 |メールボックスが削除された日付。 |
|作成日 | メールボックスが作成された日付。  |
|最終アクティビティの日付 | メールボックスが最後に電子メールの送信または読み取りアクティビティを行った日付。   |
|アイテム数|メールボックス内のアイテムの合計数。 |
|使用されるストレージ (MB)|使用されたストレージの合計。 |
|削除済みのアイテム数|メールボックス内の削除済みアイテムの合計数。 |
|削除されたアイテム サイズ (MB)|メールボックス内のすべての削除済みアイテムの合計サイズ。 |
|問題の警告クォータ (MB)|メールボックス所有者がストレージ クォータに達しようとしているという警告を受け取る場合のストレージ制限。  |
|送信クォータを禁止する (MB)|メールボックスが電子メールを送信できなくなった場合のストレージの制限。 |
|送信受信クォータを禁止する (MB)|メールボックスで電子メールの送受信ができなくなった場合のストレージの制限。 |
|回復可能なアイテム クォータ (MB)|メールボックスでメールを削除できなくなった場合の、メールボックス内の回復可能な (削除された) アイテムのストレージ制限。 |
|アーカイブあり|メールボックスでオンライン アーカイブが有効になっているかどうかを示します。 |


組織のポリシーにより、ユーザー情報を特定できるレポートを表示できない場合は、これらすべてのレポートのプライバシー設定を変更できます。 Microsoft 365 管理センターのアクティビティ **レポートの [レポート**] セクションの [ユーザー [の詳細を](activity-reports.md)非表示にする] を確認します。

[ **列の選択] を選択** して、レポートに列を追加または削除します。  <br/> :::image type="content" alt-text="メールボックス使用状況レポート - 列を選択します。" source="../../media/ea3d0b18-6ac6-41b0-9bb9-4844f040ea75.png":::

[エクスポート] リンクを選択して、レポート データを Excel .csv ファイルに **エクスポート** することもできます。 