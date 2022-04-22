---
title: オンプレミス ユーザーの Teams チャット データを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 管理者は、Microsoft 365 の電子情報開示ツールを使用して、Exchange ハイブリッド展開のオンプレミス ユーザーの Teams チャット データを検索してエクスポートできます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e1f15922e84a68538e20ccb3ad0030bd5c2bd5f1
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64995362"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a>オンプレミス ユーザーの Teams チャット データを検索する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

組織に Exchange ハイブリッド展開がある場合 (または、組織がオンプレミス Exchange 組織を Office 365 と同期している場合)、Microsoft Teams を有効にしている場合、オンプレミス ユーザーは Teams チャット アプリケーションを使用してインスタント メッセージングを利用できます。 クラウドベースのユーザーの場合、Teams チャット データ (*1x1 または 1xN チャット* とも呼ばれます) は、プライマリ クラウドベースのメールボックスに保存されます。 オンプレミス ユーザーが Teams チャット アプリケーションを使用する場合、そのチャット メッセージはオンプレミスにあるプライマリ メールボックスに保存できません。 この制限を回避するために、Microsoft は、クラウドベースのストレージ領域を作成する新機能をリリースしました。これにより、電子情報開示ツールを使用して、オンプレミス ユーザーの Teams チャット データを検索およびエクスポートできます。
  
オンプレミス ユーザーがクラウドベースのストレージを有効にするための要件と制限は次のとおりです。
  
- オンプレミスのディレクトリ サービス (Active Directory など) のユーザー アカウントは、Microsoft 365 のディレクトリ サービスである Azure Active Directory と同期する必要があります。 つまり、メール ユーザー アカウントは、Microsoft 365 で作成され、プライマリ メールボックスがオンプレミスの組織に存在するユーザーに関連付けられます。

- プライマリ メールボックスがオンプレミスの組織にあるユーザーには、Microsoft Teams ライセンスと Exchange Online Plan 1 の最小ライセンスが割り当てられている必要があります。

- 組織に Exchange ハイブリッド展開がない場合は、オンプレミスの Exchange スキーマを Azure Active Directory に同期する必要があります。 これを行わないと、オンプレミスの Exchange 組織にメール ボックスを持つユーザーのために Exchange Online で重複するクラウド ベースのメール ボックスを作成するリスクがあります。

- オンプレミス ユーザーに関連付けられた Teams チャット データのみがクラウドベースのストレージ領域に保存されます。 オンプレミス ユーザーは、このストレージ領域にアクセスすることはできません。

> [!NOTE]
> Teams チャネルに含まれる会話は、チームに関連付けられているクラウドベースのメールボックスに常に保存されます。つまり、チャネルの会話を検索できます。 Teams チャネルの会話の検索の詳細については、「[Microsoft Teams と Microsoft 365 グループの検索」](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups)を参照してください。
  
## <a name="how-it-works"></a>メカニズム

Microsoft Teams 対応のユーザーがオンプレミスのメールボックスを持っていて、そのユーザー アカウント/ID がクラウドに同期されている場合、Microsoft は、オンプレミス ユーザーの 1xN Teams チャット データを関連付けるクラウドベースのストレージを作成します。 オンプレミス ユーザーの Teams チャット データは、検索用にインデックス化されます。 これにより、コンテンツ検索 (および Microsoft Purview 電子情報開示 (標準) と Microsoft Purview 電子情報開示 (プレミアム) ケースに関連する検索) を使用して、オンプレミス ユーザーの Teams チャット データを検索、プレビュー、エクスポートできます。 また、セキュリティ/コンプライアンス センター PowerShell の **\*ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザー向け Teams チャット データを検索することもできます。
  
次の図は、オンプレミス ユーザー向け Teams チャット データの検索、プレビュー、エクスポートを行う方法を示しています。
  
![Microsoft Teams のオンプレミスユーザー向けのクラウドベース ストレージ。](../media/EHAMShard1.png)
  
この機能に加えて、電子情報開示ツールを使用して、クラウドベースの SharePoint サイトの Teams コンテンツ、各 Microsoft チームに関連付けられた Exchange メールボックス、クラウドベースのユーザーの Exchange Online メールボックスの 1xN Teams チャット データを検索、プレビュー、エクスポートすることもできます。

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a>オンプレミス ユーザーの Teams チャット コンテンツの検索

Microsoft Purview コンプライアンス ポータルのコンテンツ検索を使用して、オンプレミス ユーザーの Teams チャット データを検索する方法について示します。 電子情報開示 (標準) の検索ツールを使用して、オンプレミス ユーザーのチャット データを検索することもできます。
  
1. コンプライアンス ポータルで、[**コンテンツ検索**] に移動します。

2. [**検索**] タブで [**新しい検索**] をクリックし、新しい検索に名前を付けます。

3. [**場所**] ページで、[Exchange メールボックス] トグルを [**オン**] に設定します。

4. 特定のユーザー (オンプレミス ユーザーを含む) の Teams コンテンツを検索するには、[**ユーザー、グループ、チームを選択**] を選択し、検索に含める特定のユーザーを選択します。 特定のユーザーを一覧表示しない場合、オンプレミス ユーザーを含むすべてのユーザーが検索に含まれます。

5. [**オンプレミスのユーザー用にアプリ コンテンツを追加する**] チェック ボックスがオンになっていることを確認します。 これにより、オンプレミス ユーザーのクラウド ベース ストレージが検索されます。

    ![[場所] ウィザード ページの [オンプレミスのユーザー用に Office アプリ コンテンツを追加する] チェック ボックスをオンにします。](../media/EHAMShardCheckBox.png)

6. [**検索条件の定義**] ページで、キーワード クエリを作成し、必要に応じて検索クエリに条件を追加します。 Team チャット データのみを検索するには、[**キーワード**] ボックスに次のクエリを追加します。

    ```text
    kind:im AND kind:microsoftteams
    ```

6. 検索を送信して実行します。 オンプレミス ユーザーの検索結果は、他の検索結果と同様にプレビューできます。 検索結果 (Teams チャット データを含む) を PST ファイルにエクスポートすることもできます。 詳細については、以下を参照してください。

    - [検索を作成する](content-search.md)

    - [検索結果をプレビューする](preview-ediscovery-search-results.md)

    - [検索結果をエクスポートする](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a>PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索する

セキュリティ/コンプライアンス センター PowerShell の **New-ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザーの Teams チャット データを検索することもできます。 前に説明したように、PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索するために、サポート要求を送信する必要はありません。
  
1. [セキュリティ/コンプライアンス センター PowerShell に接続します](/powershell/exchange/connect-to-scc-powershell)。

2. 次の PowerShell コマンドを実行して、オンプレミス ユーザーの Teams チャット データを検索するコンテンツ検索を作成します。

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    *IncludeUserAppContent* パラメーターを使用して、*ExchangeLocation* パラメーターで指定されたユーザーのクラウドベースのストレージを指定します。 *AllowNotFoundExchangeLocationsEnabled* を使用すると、オンプレミス ユーザーのクラウドベースのストレージを検索できます。 このパラメーターに `$true` 値を使用すると、検索はメールボックスの存在を検証してから実行されます。 このクラウドベースのストレージは通常のクラウドベースのメールボックスとして解決されないため、これはオンプレミス ユーザーのクラウドベースのストレージを検索するために必要です。

    次の例では、Contoso 組織のオンプレミス ユーザーである Sara Davis のクラウドベースのストレージで、キーワード "redstone" を含む Teams チャットを検索します。
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   検索を作成したら、必ず **Get-compliancesearch** コマンドレットを使用して、検索を実行してください。
  
これらのコマンドレットの詳細については、以下を参照してください。
  
- [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch)

- [Start-ComplianceSearch](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a>既知の問題

- 現在、オンプレミス ユーザーの Teams チャット データを検索、プレビュー、およびエクスポートできます。 また、オンプレミス ユーザーの Teams チャット データをコアまたは電子情報開示 (プレミアム) ケースに関連付けられた状態で保留に設定し、オンプレミス ユーザーの Teams チャットまたはチャネル メッセージに保持ポリシーを適用することもできます。 ただし、現時点では、オンプレミス ユーザーの他のコンテンツの場所 (Exchange メールボックスや SharePoint サイトなど) に保持ポリシーを適用することはできません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**オンプレミス ユーザーのチャット メッセージの検索にサポート リクエストを送信する必要がありますか?**

いいえ。 すべての組織で、この機能は既定で有効になっています。 以前は Microsoft サポートに連絡する必要がありましたが、現在は必要ありません。
  
 **すべての組織でこの機能が既定で有効になる前の、オンプレミス ユーザーの古い Teams チャット データを、電子情報開示ツールで検索できますか?**
  
Microsoft では 2018 年 1 月 31 日よりオンプレミス ユーザーの Teams チャット データの保存を開始しました。そのため、オンプレミスの Teams ユーザーの ID が、この日付以降に Microsoft 365 のオンプレミスの Active Directory と Azure Active Directory 間で同期されている場合、Teams チャット データはクラウドに保存されており、電子情報開示ツールを使用して検索することができます。

 **オンプレミス ユーザーは、クラウドに Teams チャット データを保存するためにライセンスが必要ですか?**
  
はい。クラウドベースのストレージにオンプレミス ユーザーの Teams チャット データを保存するには、そのユーザーに Office 365 (または Microsoft 365) の Microsoft Teams ライセンスと Exchange Online プランのライセンスが割り当てられている必要があります。

**オンプレミス ユーザー向けのクラウドベースのストレージはどこにありますか?**
  
Teams のチャット データは、オンプレミスのユーザーのデータの既定の場所 (PDL) に保存されます。 PDL は、Single-Geo 環境と Multi-Geo 環境の両方で適用されます。 詳細については、「[Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)」を参照してください。

**ユーザーのオンプレミス メールボックスがクラウドに移行された場合、Teams チャット データが失われるリスクはありますか?**
  
いいえ。オンプレミス ユーザーのプライマリ メールボックスをクラウドに移行すると、そのユーザーの Teams チャット データは、新しいクラウドベースのプライマリ メールボックスに移行されます。
  
 **電子情報開示の保留ポリシーまたはアイテム保持ポリシーをオンプレミス ユーザーに適用することはできますか?**
  
はい。 オンプレミス ユーザーの Teams チャットおよびチャネル メッセージに電子情報開示の保留または保持ポリシーを適用できます。 ただし、オンプレミス ユーザーの Teams コンテンツを保留または保持するには、オンプレミス ユーザーに Exchange Online のプラン 2 のライセンスが割り当てられている必要があります。
