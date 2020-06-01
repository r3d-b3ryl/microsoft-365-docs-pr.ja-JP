---
title: 高度な電子情報開示ケースへの保管担当者の一括追加
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: 9331e45619f549ea31adcfdd9316eea20e43efef
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432440"
---
# <a name="bulk-add-custodians-to-an-advanced-ediscovery-case-preview"></a>高度な電子情報開示ケースへの一括追加保管担当者 (プレビュー)

保管担当者の高度な電子情報開示ケースでは、複数の保管担当者をケースに追加するために必要なすべての情報を含む CSV ファイルによって一度にインポートできます。

## <a name="bulk-add-custodians"></a>一括追加保管担当者

1. Case を入力し、[**ソース**] タブに移動します。

2. [ **Import 保管担当者**] をクリックします。

3. [ポップアップ] ページで、[**空のテンプレートをダウンロード**して CSV 保管担当者テンプレートファイルをダウンロード] をクリックします。

4. この CSV ファイルに custodial 情報を追加して、ローカルコンピューターに保存します。 CSV ファイルのプロパティに関する情報については、次のセクションを参照してください。

5. [**ソース**] タブで、[ **Import 保管担当者**] をもう一度クリックします。 
6. [ポップアップ] ページで、[**参照**] をクリックし、CSV ファイルをアップロードします。

   CSV ファイルをアップロードすると、BulkAddCustodian ジョブが作成され、[**ジョブ**] タブに表示されます。ジョブは保管担当者とそれに対応するデータソースを検証し、ケースの [**ソース**] ページの [**保管担当者**] タブに追加します。

## <a name="custodian-csv-file"></a>保管担当者 CSV ファイル

CSV テンプレートをダウンロードした後、保管担当者とそのデータソースを各行に追加できます。 見出し行の列名を変更しないようにしてください。

| 列名|説明|
|:------- |:------------------------------------------------------------|
|**保管担当者いる**     | 保管担当者の UPN 電子メール。 例: sarad@onmicrosoft.contoso.com           |
|**Exchange が有効** | 保管担当者のメールボックスを追加するかどうかを示す TRUE/FALSE 値。      |
|**OneDrive の有効化** | 保管担当者の OneDrive for Business アカウントを追加するかどうかを示す TRUE/FALSE 値。 |
|**OnHold**        | TRUE/FALSE 保管担当者を保留にするかどうかを指定します。       |
|**Workload1 の種類**         | 保管担当者に関連付けるデータソースの種類を示す文字列値。 <br />次の値を指定できます。 <br />ExchangeMailbox、SharePointSite、TeamsMailbox、Teamsmailbox、YammerMailbox、YammerSite |
|**Workload1 の場所**     | ワークロードの種類に応じて、ワークロードのデータの場所 (Exchange メールボックスの電子メールアドレスや SharePoint サイトの URL など) が使用されます。 |
|||

保管担当者情報を含む CSV ファイルの例を次に示します。  

| ContactEmail      | Exchange が有効 | OneDrive の有効化 | OnHold | Workload1 の種類 | Workload1 の場所             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|sarad@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>保管担当者とデータソースの検証

保管担当者 CSV ファイルをアップロードすると、Advanced eDiscovery は次の作業を行います。

1. 保管担当者とそのデータソースを検証します。 

2. 各保管担当者のすべてのデータソースのインデックスを付けて、保留中に配置します (Is OnHold プロパティが TRUE に設定されている場合)。

### <a name="custodian-validation"></a>保管担当者の検証

現時点では、Azure Active Directory (AAD) 内の保管担当者のインポートのみがサポートされています。

CSV ファイルの [**連絡先の電子メール**] 列にある UPN 値を使用して、保管担当者を検証し、検索します。 検証された保管担当者は、ケースに自動的に追加され、ケースの**ソース**ページの [**保管担当者**] タブに表示されます。 保管担当者を検証できない場合は、[**ジョブ**] タブに表示されている BulkAddCustodian ジョブのエラーログに、その場合はエラーログに表示されます。 Unvalidated 保管担当者はケースに追加されません。

### <a name="data-source-validation"></a>データソースの検証

保管担当者が検証され、ケースに追加されると、保管担当者に関連付けられている各データソースが検証されます。 保管担当者のデータソースが見つからない場合、**検証されていない**値は、その保管担当者の [**保管担当者**] タブの [**検証済み**] 列に表示されます。

### <a name="remediating-unvalidated-data-sources"></a>修復 unvalidated データソース

Unvalidated データソースで保管担当者を修復するには、次のようにします。 

1. [**保管担当者**] タブで、検証されていない保管担当者を選択します。

2. 保管担当者のポップアップページで、[**データソース**] セクションまでスクロールして、保管担当者に関連付けられているデータソースを表示します。 検証済みデータソースと unvalidated データソースの両方が表示されます。

3. [**データソース**] セクションで、[**編集**] をクリックします。

4. [ **Custodial 所在地の選択**] ページで、unvalidated データソースを削除します。

5. [**その他の場所の選択**] ページで、[**更新**] をクリックして、保管担当者の追加のデータソースを追加します。
