---
title: 保管担当者をケースにAdvanced eDiscoveryする
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
description: インポート ツール d を使用して、複数の保管担当者と関連付けられたデータ ソースをすばやくケースに追加Advanced eDiscovery。
ms.openlocfilehash: ccce04b5821eaff2d2ba65c846d58f3f474fb7277931da1d986f7b7ebe8beccb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53906108"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>保管担当者をケースにAdvanced eDiscoveryする

多Advanced eDiscoveryが関係する場合は、ケースに追加するために必要な情報を含む CSV ファイルを使用して、複数の保管担当者を一度にインポートできます。

## <a name="import-custodians"></a>保管担当者のインポート

1. [データ ソース] Advanced eDiscoveryを開き、[**データ ソース] タブを選択** します。

2. [データ **ソースのインポート**  >  **保管担当者の追加] をクリックします**。

3. [保管 **担当者のインポート] フライアウト** ページで、[空のテンプレートをダウンロードする] をクリックして、カストディアン テンプレートの CSV ファイルをダウンロードします。

   ![[保管担当者のインポート] フライアウト ページから CSV テンプレートをダウンロードする](../media/ImportCustodians1.png)

4. 保管情報を CSV ファイルに追加し、ローカル コンピューターに保存します。 CSV ファイルで [必要なプロパティの詳細については、「Custodian CSV](#custodian-csv-file) ファイル」セクションを参照してください。

5. 保管担当者情報を含む CSV ファイルを準備した後、[データ ソース] タブに戻り、[データ ソースのインポート 保管担当者の追加] を再度  >  **クリック** します。

6. [保管 **担当者のインポート] フライ** アウト ページで、[参照] をクリックし、保管担当者情報を含む CSV ファイルをアップロードします。

   CSV ファイルがアップロードされると **、BulkAddCustodian** という名前のジョブが作成され、[ジョブ] タブに **表示** されます。ジョブは、保管担当者と関連付けられたデータ ソースを検証し、ケースの **[** データ ソース] ページに追加します。

## <a name="custodian-csv-file"></a>カストディアン CSV ファイル

CSV カストディアン テンプレートをダウンロードした後、各行に保管担当者とそのデータ ソースを追加できます。 ヘッダー行の列名は必ず変更してください。 ワークロードの種類とワークロードの場所の列を使用して、他のデータ ソースを保管担当者に関連付ける。

| 列名|Description|
|:------- |:------------------------------------------------------------|
|**Custodian contactEmail**     |保管担当者の UPN メール アドレス。 たとえば、sarad@contoso.onmicrosoft.com。           |
|**Exchange有効** | 保管担当者のメールボックスを含めるか含めない場合の TRUE/FALSE 値。      |
|**OneDrive有効** | 保管担当者のアカウントを含めるか含めない場合は TRUE/FALSE OneDrive for Businessします。 |
|**Is OnHold**        | 保管担当者データ ソースを保留にするかどうかを示す TRUE/FALSE 値。 <sup>1</sup>     |
|**ワークロード 1 の種類**         |保管担当者に関連付けるデータ ソースの種類を示す文字列値。 次の値を指定できます。 <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**ワークロード 1 の場所**     | ワークロードの種類に応じて、これはデータ ソースの場所です。 たとえば、メールボックスの電子メール アドレスExchangeサイトの URL SharePointします。 |
|||

> [!NOTE]
> <sup>1</sup> 保管担当者のインポート プロセスと CSV ファイルを使用して、最大 1,000 のメールボックスと 100 のサイトを保留にできます。 このプロセスを使用して、ケースに 1,000 人を超える保管担当者を追加できますが、保留の制限は引き続き適用されます。 ホールド制限の詳細については、「制限」を参照[Advanced eDiscovery。](limits-ediscovery20.md#hold-limits)

保管担当者情報を含む CSV ファイルの例を次に示します。<br/><br/>

|Custodian contactEmail      | Exchange有効 | OneDrive有効 | Is OnHold | ワークロード 1 の種類 | ワークロード 1 の場所             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>保管担当者とデータ ソースの検証

保管担当者の CSV ファイルをアップロードした後、Advanced eDiscoveryを実行します。

1. 保管担当者とそのデータ ソースを検証します。

2. 各保管担当者のすべてのデータ ソースにインデックスを作成し、保持します (CSV ファイルの **Is OnHold** プロパティが TRUE に設定されている場合)。

### <a name="custodian-validation"></a>カストディアン検証

現時点では、組織の管理者 (Azure Azure Active Directory) に含まれるカストディアンAD。

保管担当者のインポート ツールは、CSV ファイルの **[Custodian contactEmail]** 列の UPN 値を使用して、保管担当者を検索して検証します。 検証された保管担当者は、ケースに自動的に追加され、ケースの [データ **ソース]** タブに表示されます。 保管担当者を検証できない場合は、ケースの [ジョブ] タブに表示される BulkAddCustodian ジョブのエラー ログに一覧表示されます。 未確認の保管担当者は、ケースに追加されないか、[データ ソース] タブ **に表示** されません。

### <a name="data-source-validation"></a>データ ソースの検証

保管担当者が検証され、ケースに追加された後、保管担当者に関連付けられている各プライマリ メールボックスと OneDrive アカウントが追加されます。

ただし、保管担当者に関連付けられた他のデータ ソース (SharePoint サイト、Microsoft Teams、Microsoft 365 グループ、Yammer グループなど) が見つからない場合、それらのデータ ソースはいずれも保管担当者に割り当てられていないので、[データ ソース] タブの [カストディアン]の横にある [状態] 列に値が表示されます。 

カストディアンの検証済みデータ ソースを追加するには、次の方法を実行します。

1. [データ **ソース] タブ** で、検証されていないデータ ソースを含む保管担当者を選択します。

2. カストディアン のフライアウト ページで、[保管場所] セクションまでスクロールして、カストディアンに関連付けられている検証済みデータ ソースと検証されていないデータ ソースの両方を表示します。

3. 無効 **なデータ** ソースを削除するか、新しいデータ ソースを追加するには、フライアウト ページの上部にある [編集] をクリックします。

4. 未評価のデータ ソースを削除するか、新しいデータ ソースを追加した後、[データソース] タブのカストディアンの [状態] 列に値 Active **が表示** されます。以前は無効と思ったソースを追加するには、以下の修復手順に従って手動で保管担当者に追加します。

### <a name="remediating-invalid-data-sources"></a>無効なデータ ソースの修復

以前は無効だったデータ ソースを手動で追加して関連付けるには、次の操作を行います。

1. [データ **ソース] タブで** 、以前は無効だったデータ ソースを手動で追加して関連付ける保管担当者を選択します。

2. フライ **アウト ページ** の上部にある [編集] をクリックして、メールボックス、サイト、Teams、Yammerグループをカストディアンに関連付ける。 これを行うには、適切なデータ **の場所** の種類の横にある [編集] をクリックします。

3. [ **次へ** ] をクリック **して [保留** 設定] ページを表示し、追加したデータ ソースの保留設定を構成します。

4. [ **次へ]** をクリック **して [保管担当者の確認] ページを表示** し、[ **送信** ] をクリックして変更を保存します。
