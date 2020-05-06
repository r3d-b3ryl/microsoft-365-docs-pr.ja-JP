---
title: オンプレミス ユーザーのクラウドベース メールボックスの検索
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
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: セキュリティ/コンプライアンス センターのコンテンツ検索ツールを使用して、Exchange ハイブリッド展開のオンプレミス ユーザーが使用している Microsoft Teams チャット データ (1xN チャットと呼ばれます) を検索してエクスポートします。
ms.openlocfilehash: 7b05460bb41ff97c8571a96b38a8eebd50a206fd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034574"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users"></a>オンプレミス ユーザーのクラウドベース メールボックスの検索

組織に Exchange ハイブリッド展開がある場合 (または、組織がオンプレミス Exchange 組織を Office 365 と同期している場合)、Microsoft Teams を有効にしている場合、ユーザーは Teams チャット アプリケーションを使用してインスタント メッセージングを利用できます。 クラウドベースのユーザーの場合、Teams チャット データ (*1xN チャット*とも呼ばれます) は、プライマリ クラウドベースのメールボックスに保存されます。 オンプレミスのユーザーが Teams チャット アプリケーションを使用する場合、そのユーザーのプライマリ メールボックスはオンプレミスに配置されます。 この制限を回避するために、Microsoft は、オンプレミス ユーザーの Teams チャットデータを格納するために、クラウドベースのストレージ領域 (オンプレミス ユーザーのクラウドベースのメールボックスと呼ばれます) を作成する新機能をリリースしました。 これにより、セキュリティ/コンプライアンス センターのコンテンツ検索ツールを使用して、オンプレミス ユーザー向け Teams チャットデータを検索してエクスポートできます。 
  
オンプレミス ユーザーに対してクラウドベースのメールボックスを設定するための要件と制限について説明します。
  
- オンプレミスのディレクトリ サービス (Active Directory など) のユーザー アカウントは、Microsoft 365 のディレクトリ サービスである Azure Active Directory と同期する必要があります。 つまり、メール ユーザー アカウントは、Microsoft 365 で作成され、プライマリ メールボックスがオンプレミスの組織に存在するユーザーに関連付けられます。

- プライマリ メールボックスがオンプレミスの組織にあるユーザーには、Microsoft Teams ライセンスと Exchange Online Plan 1 の最小ライセンスが割り当てられている必要があります。

- オンプレミス ユーザーのクラウドベースのメールボックスには、Teams チャット データのみが保存されます。 オンプレミス ユーザーは、クラウドベースのメールボックスにサインインしたり、何らかの方法でアクセスしたりすることはできません。 メール メッセージの送受信には使用できません。 

- 組織がオンプレミス ユーザーに対してクラウドベースのメールボックスで Teams チャット データを検索できるようにするには、Microsoft サポートに要求を送信する必要があります。 この記事の「[Microsoft サポートに要求を送信してこの機能有効にする](#filing-a-request-with-microsoft-support-to-enable-this-feature)」を参照してください。 

> [!NOTE]
> Teams チャネルに含まれる会話は、チームに関連付けられているクラウドベースのメールボックスに常に保存されます。 つまり、コンテンツ検索を使用して、サポート要求を提出せずにチャネル会話を検索できます。 Teams チャネルの会話の検索の詳細については、「[Microsoft Teams と Microsoft 365 グループの検索」](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)を参照してください。
  
## <a name="how-it-works"></a>動作のしくみ

Microsoft Teams 対応ユーザーがオンプレミス メールボックスを持ち、ユーザー アカウント/ ID がクラウドに同期されている場合、Microsoft は 1xN Teams チャット データを保存するクラウドベースのメールボックスを作成します。 Teams チャット データがクラウドベースのメールボックスに保存されると、検索用にインデックスが作成されます。 これにより、コンテンツ検索 (および電子情報開示ケースに関連付けられている検索) を使用して、オンプレミス ユーザーのために Teams チャット データを検索、プレビュー、エクスポートできます。 また、セキュリティ/コンプライアンス センター PowerShell の **\*ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザー向け Teams チャット データを検索することもできます。 
  
次の図は、オンプレミス ユーザー向け Teams チャット データの検索、プレビュー、エクスポートを行う方法を示しています。
  
![Microsoft Teams のオンプレミスユーザー向けのクラウドベース ストレージ](../media/EHAMShard1.png)
  
この新しい機能に加えて、コンテンツ検索を使用して、クラウドベースの SharePoint サイトの Teams コンテンツ、各 Microsoft Team に関連付けられた Exchange メールボックス、クラウドベースのユーザーの Exchange Online メールボックスの 1xN Teams チャット データを検索、プレビュー、エクスポートできます。

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a>Microsoft サポートに要求を送信してこの機能有効にする

組織がセキュリティ/コンプライアンス センターのグラフィカル ユーザー インターフェイスを使用して、オンプレミスユーザー向けクラウドベースのメールボックスで Teams チャット データを検索できるようにするには、Microsoft サポートに要求を提出する必要があります。 この機能は、セキュリティ/ コンプライアンス センターの PowerShell で使用できます。 PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索するために、サポート要求を送信する必要はありません。
  
Microsoft サポートに要求を送信するときには、次の情報を含めてください。
  
- 組織の既定のドメイン名。

- 組織のテナント名とテナント ID。 これらは、Azure Active Directory ポータル (**管理** \> **プロパティ**の下) にあります。 「[Microsoft 365 テナント ID を見つける](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)」をご覧ください。

- サポート要求の目的に関する次のタイトルまたは説明：「オンプレミス ユーザーのアプリケーション コンテンツ検索を有効にする」。 これにより、要求を実装する電子情報開示エンジニアリング チームが要求をルーティングできます。

技術的な変更が行われた後、Microsoft サポートは、展開予定日を送信します。 通常、サポート要求の送信後、展開プロセスには 2 ~ 3 週間かかります。
  
### <a name="what-happens-after-this-feature-is-enabled"></a>この機能を有効にするとどうなりますか?

組織にこの機能が展開されると、コンテンツ検索およびセキュリティ/コンプライアンス センターの電子情報開示ケースに関連付けられた検索で次の変更が行われます。
  
- [**オンプレミス ユーザー向けの Office アプリ コンテンツの追加**] チェックボックスが、コンテンツ 検索の[**場所**] の下に追加されます。

    ![[オンプレミス ユーザー向けの Office アプリ コンテンツの追加] チェックボックスが、コンテンツ 検索 UI に追加されます。](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- オンプレミス ユーザーは、検索するユーザー メールボックスを選択するために使用するコンテンツの場所選択ツールに表示されます。

## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a>オンプレミス ユーザー向けクラウドベース メールボックスで Teams チャット コンテンツを検索する

この機能を有効にすると、セキュリティ/コンプライアンス センターのコンテンツ検索を使用して、オンプレミス ユーザー向けクラウドベースのメールボックスで Teams チャット データを検索できます。
  
1. セキュリティ/コンプライアンス センターで、[**検索**] \> [**コンテンツ検索**] に移動します。

2. [**検索**] ページで、[![追加アイコン](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **新しい検索**] をクリックします。

    前に説明したように、[**オンプレミス ユーザー向けの Office アプリ コンテンツの追加**] チェックボックスが、[**場所**] の下に表示されます。 既定では、オンになっています。

3. キーワード クエリを作成し、必要に応じて検索クエリに条件を追加します。 Team チャット データのみを検索するには、[**キーワード]** ボックスに次のクエリを追加します。

    ```text
    kind:im
    ```

4. この時点で、[**場所**] の下で、次のいずれかのオプションを選択できます。

    - **[すべての場所]:** 組織内のすべてのユーザーのメールボックスを検索するには、このオプションを選択します。 チェックボックスを選択すると、オンプレミス ユーザーのクラウドベースのすべてのメールボックスも検索対象となります。

    - **特定の場所:** このオプションを選択し、[**変更**\>] をクリックし、ユーザー、グループ、チームを選択して、特定のメールボックスを検索します。 前に説明したように、場所の選択ツールを使用して、オンプレミス ユーザーを検索できます。

5. 検索を保存して実行します。 オンプレミス ユーザー向けクラウドベースのメールボックスからの検索結果は、他の検索結果と同様にプレビューできます。 検索結果 (Teams チャット データを含む) を PST ファイルにエクスポートすることもできます。 詳細については、以下を参照してください。 

    - [検索を作成する](content-search.md#create-a-search)

    - [検索結果をプレビューする](content-search.md#preview-search-results)

    - [コンテンツ検索の結果をエクスポートする](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a>PowerShell を使用して、オンプレミス ユーザー向けクラウド ベースのメールボックスで Teams チャット データを検索する

セキュリティ/コンプライアンス センター PowerShell で、**New-ComplianceSearch** および **Set-ComplianceSearch** コマンドレットを使用して、オンプレミス ユーザー向けクラウドベース メールボックスを検索できます。 前に説明したように、PowerShell を使用してオンプレミス ユーザーの Teams チャット データを検索するために、サポート要求を送信する必要はありません。 
  
1. [セキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。

2. 次の PowerShell コマンドを実行して、オンプレミスユーザーのクラウドベースのメールボックスを検索するコンテンツ検索を作成します。

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    *IncludeUserAppContent* パラメーターを使用して、*ExchangeLocation* パラメーターで指定されたユーザーのクラウドベースのメールボックスを指定します。 *AllowNotFoundExchangeLocationsEnabled* により、オンプレミス ユーザーがクラウドベースのメールボックスを使用できます。 このパラメーターに `$true` 値を使用すると、検索はメールボックスの存在を検証してから実行されます。 これらの種類のメールボックスは通常のメールボックスとして解決されないため、これはオンプレミ スユーザーのクラウドベースのメールボックスを検索するために必要です。

    次の例では、Contoso 組織のオンプレミス ユーザーである Sara Davis のクラウドベースのメールボックスで、キーワード "redstone" を含む Teams チャット (インスタント メッセージ) を検索します。
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   検索を作成したら、必ず **Get-compliancesearch** コマンドレットを使用して、検索を実行してください。 
  
これらのコマンドレットの詳細については、以下を参照してください。
  
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

- [Set-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)

- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

## <a name="known-issues"></a>既知の問題

- 現在、オンプレミス ユーザー向けクラウドベースのメールボックスのコンテンツを検索、プレビュー、エクスポートできます。 また、オンプレミス ユーザー向けクラウドベースのメールボックスを電子情報開示ケースに関連付けられた状態で保留にし、オンプレミスユーザー向けクラウドベースのメールボックスに Teams チャットまたはチャネル メッセージの保持ポリシーを適用することもできます。 ただし、現時点では、他のコンテンツの場所 (Exchange メールボックス、SharePoint サイトなど) の保持ポリシーをオンプレミス ユーザー向けクラウドベースのメールボックスに適用することはできません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

 **オンプレミスユーザー向けクラウドベースのメールボックスはどこにありますか?**
  
クラウドベースのメールボックスが作成され、組織と同じデータ センターに格納されます。
  
 **サポート要求を送信する以外の要件はありますか?**
  
 前に説明したように、オンプレミス メールボックスを持つユーザーの ID は、クラウドベースの組織と同期して、Office 365 の各オンプレミス ユーザー アカウントに対応するメール ユーザー アカウントが作成されるようにする必要があります。 また、組織には、Office 365 Enterprise E1、E3、E5 などの Office 365 Enterprise サブスクリプションも必要です。
  
 **ユーザーのオンプレミス メールボックスがクラウドに移行された場合、Teams チャット データが失われるリスクはありますか?**
  
いいえ。 オンプレミス ユーザーのプライマリ メールボックスをクラウドに移行すると、そのユーザーの Teams チャット データは、新しいクラウドベースのプライマリ メールボックスに移行されます。
  
 **電子情報開示の保留ポリシーまたはアイテム保持ポリシーをオンプレミス ユーザーに適用することはできますか?**
  
はい。 Teams チャットとチャネル メッセージの電子情報開示保留リストまたは保持ポリシーを、オンプレミス ユーザー向けクラウドベースのメールボックスに適用できます。
  
 **この機能を有効にするように組織が要求を送信する前に、コンテンツ検索で、オンプレミスユーザー向けの古い Teams チャットを検索できますか?**
  
Microsoft は、2018年1月31日にオンプレミスユーザー向け Teams チャット データの保存を開始しました。 そのため、オンプレミスの Teams ユーザーの ID が、この日付以降に Active Directory と Azure Active Directory の間で同期されている場合、Teams チャット データはクラウドベースのメールボックスに保存され、コンテンツ検索を使用して検索できます。 Microsoft は、2018年1月31日より前の Teams チャット データをオンプレミスのメールボックスに保存する作業も行っています。 これに関する詳細については、間もなく利用可能になります。

 **オンプレミス ユーザーは、クラウドベース メールボックスに Teams チャット データを保存するためにライセンスが必要ですか?**
  
はい。 クラウドベースのメールボックスにオンプレミスユーザーの Teams チャット データを保存するには、そのユーザーに Office 365 (または Microsoft 365) の Microsoft Teams ライセンスと Exchange Online Plan ライセンスが割り当てられている必要があります。
