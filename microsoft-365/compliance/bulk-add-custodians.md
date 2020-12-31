---
title: 保管担当者を Advanced eDiscovery ケースにインポートする
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
description: インポート ツールを使用して、Advanced eDiscovery のケースに複数の保管担当者と関連するデータ ソースをすばやく追加します。
ms.openlocfilehash: 65ae932fac759896690e5fa65ec1d4173439ccb6
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740304"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a>保管担当者を Advanced eDiscovery ケースにインポートする

多くの保管担当者が関係する Advanced eDiscovery ケースでは、ケースに追加するために必要な情報を含む CSV ファイルを使用して、一度に複数の保管担当者をインポートできます。

## <a name="import-custodians"></a>保管担当者をインポートする

1. Advanced eDiscovery ケースを開き、[データ ソース **] タブを選択** します。

2. [データ **ソースのインポート 保管担当者の**  >  **追加] をクリックします**。

3. [カ **ストディアンのインポート]** フライアウトページで、空のテンプレートをダウンロードしてカストディアン テンプレート CSV ファイルをダウンロードします。

   ![[カストディアンのインポート] フライアウト ページから CSV テンプレートをダウンロードする](../media/ImportCustodians1.png)

4. CSV ファイルに保管情報を追加し、ローカル コンピューターに保存します。 CSV ファイル [で必要なプロパティの](#custodian-csv-file) 詳細については、保管担当者の CSV ファイルセクションを参照してください。

5. 保管担当者の情報を含む CSV ファイルを準備した後、[データソース] タブに戻り、[データ ソースのインポート 保管担当者の追加] を再度クリック  >  します。

6. [カ **ストディアンのインポート]** フライアウト ページで、[参照] **をクリックし** 、保管担当者の情報を含む CSV ファイルをアップロードします。

   CSV ファイルをアップロードすると **、BulkAddCusto読** み取りという名前のジョブが作成され、[ジョブ] タブに **表示** されます。ジョブは、保管担当者と関連するデータ ソースを検証し、ケースの [データ ソース] **ページに** 追加します。

## <a name="custodian-csv-file"></a>保管担当者 CSV ファイル

CSV カストディアン テンプレートをダウンロードした後、各行にカストディアンとそのデータ ソースを追加できます。 ヘッダー行の列名は必ず変更してください。 ワークロードの種類とワークロードの場所の列を使用して、他のデータ ソースを保管担当者に関連付ける。

| 列名|説明|
|:------- |:------------------------------------------------------------|
|**Custodian contactEmail**     |保管担当者の UPN メール アドレス。 たとえば、sarad@contoso.onmicrosoft.com。           |
|**Exchange Enabled** | 保管担当者のメールボックスを含めるか含めるか含めない場合の TRUE/FALSE 値。      |
|**OneDrive の有効化** | 保管担当者の OneDrive for Business アカウントを含めるか含めない場合の TRUE/FALSE 値。 |
|**Is OnHold**        | 保管担当者のデータ ソースを保留にするかどうかを示す TRUE または FALSE の値。       |
|**Workload1 の種類**         |保管担当者に関連付けるデータ ソースの種類を示す文字列値。 次の値を指定できます。 <br/>- ExchangeMailbox<br/> - SharePointSite<br/>- TeamsMailbox<br/>- TeamsSite<br/> - YammerMailbox<br/>- YammerSite |
|**Workload1 の場所**     | ワークロードの種類に応じて、これはデータ ソースの場所です。 たとえば、Exchange メールボックスの電子メール アドレスや SharePoint サイトの URL などです。 |
|||

カストディアン情報を含む CSV ファイルの例を次に示します。<br/><br/>

|Custodian contactEmail      | Exchange Enabled | OneDrive の有効化 | Is OnHold | Workload1 の種類 | Workload1 の場所             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|robinc@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | SharePointSite | https://contoso.sharepoint.com |
|pillarp@onmicrosoft.contoso.com | TRUE             | TRUE             | TRUE      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a>保管担当者とデータ ソースの検証

保管担当者の CSV ファイルをアップロードすると、Advanced eDiscovery は次の手順を実行します。

1. 保管担当者とそのデータ ソースを検証します。

2. 各保管担当者のすべてのデータ ソースのインデックスを作成し、保留します (CSV ファイルの **Is OnHold** プロパティが TRUE に設定されている場合)。

### <a name="custodian-validation"></a>カストディアンの検証

現時点では、組織の Azure Active Directory (Azure Active Directory) に含まれるカストディアンのインポートのみをサポートAD。

保管担当者インポート ツールは、CSV ファイルの **Custodian contactEmail** 列の UPN 値を使用して、カストディアンを検索して検証します。 検証された保管担当者は、ケースに自動的に追加され、ケースの [データ ソース] **タブに** 一覧表示されます。 カストディアンを検証できない場合は、ケースの [ジョブ] タブに表示される BulkAddCustoian ジョブのエラー ログに一覧表示されます。 未確認のカストディアンは、ケースに追加されないか、[データ ソース] タブ **に表示** されません。

### <a name="data-source-validation"></a>データ ソースの検証

カストディアンが検証され、ケースに追加された後、カストディアンに関連付けられている各プライマリ メールボックスと OneDrive アカウントが追加されます。

ただし、保管担当者に関連付けられている他のデータ ソース (SharePoint サイト、Microsoft Teams、Microsoft 365 グループ、Yammer グループなど) が見つからない場合は、保管担当者に割り当てられていないデータ ソースが見つかり、[データ ソース] タブの [状態]列に [検証されていない] の値が表示されます。 

カストディアンの検証済みデータ ソースを追加するには:

1. [ **データ ソース] タブ** で、検証されていないデータ ソースを含む保管担当者を選択します。

2. カストディアンのフライアウト ページで、[ **保管** 場所] セクションまでスクロールして、カストディアンに関連付けられている検証済みデータ ソースと検証されていないデータ ソースの両方を表示します。

3. 無効 **な** データ ソースを削除するか、新しいデータ ソースを追加するには、フライアウト ページの上部にある [編集] をクリックします。

4. 未確認のデータ ソースを削除するか、新しいデータ ソースを追加すると、[データ ソース] タブの保管担当者の [状態] 列に値 **Active** **が表示** されます。以前は無効と思だったソースを追加するには、次の修復手順に従って手動でカストディアンに追加します。

### <a name="remediating-invalid-data-sources"></a>無効なデータ ソースの修復

以前に無効だったデータ ソースを手動で追加して関連付けるには、次の操作を行います。

1. [データ ソース **] タブで** 、以前は無効だったデータ ソースを手動で追加して関連付けるカストディアンを選択します。

2. フライ **アウト** ページの上部にある [編集] をクリックして、メールボックス、サイト、Teams、または Yammerグループをカストディアンに関連付ける。 これを行うには、適切なデータ **の場所** の種類の横にある [編集] をクリックします。

3. [ **次へ** ] を **クリックして保留設定** ページを表示し、追加したデータ ソースの保留設定を構成します。

4. [**次へ]** をクリックして **[保管担当者の** 確認] ページを表示し、[送信] をクリックして変更を保存します。
