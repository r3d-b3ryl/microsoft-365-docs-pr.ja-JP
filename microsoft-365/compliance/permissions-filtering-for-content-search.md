---
title: 電子情報開示のアクセス許可フィルターを構成する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: 検索アクセス許可フィルターを使用して、電子情報開示マネージャーが組織内のメールボックスとサイトのサブセットのみを検索できるようにします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 067e1a3c785d624579af80f92476d2641266f4dc
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66018055"
---
# <a name="configure-permissions-filtering-for-ediscovery"></a>電子情報開示のアクセス許可フィルターを構成する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

検索アクセス許可フィルターを使用して、電子情報開示マネージャーが組織内のメールボックスとサイトのサブセットのみを検索できるようにします。 また、アクセス許可のフィルター処理を使用して、同じ電子情報開示管理者に特定の検索条件を満たすメールボックスやサイトのコンテンツのみを検索させることができます。 たとえば、電子情報開示管理者に特定の場所または部門のユーザーのメールボックスのみを検索させるようにすることができます。 これを行うには、サポートされている受信者フィルターを使用して、特定のユーザーまたはユーザー グループが検索できるメールボックスを制限するフィルターを作成します。 また、ユーザーが検索できるメールボックス コンテンツを指定するフィルターを作成することもできます。 これは、検索可能なメッセージ プロパティを使用するフィルターを作成することで行います。 同様に、電子情報開示マネージャーが組織内の特定のSharePoint サイトのみを検索できるようにすることができます。 これは、検索可能なサイトを限定するフィルターを作成することで行います。 検索可能なサイトのコンテンツを指定するフィルターを作成することもできます。 これは、検索可能なサイト プロパティを使用するフィルターを作成することで行います。

検索アクセス許可フィルターは、Microsoft Purview コンプライアンス ポータルでコンテンツ検索、Microsoft Purview 電子情報開示 (Standard)、および Microsoft Purview 電子情報開示 (プレミアム) を使用してコンテンツを検索するときに適用されます。 検索アクセス許可フィルターが特定のユーザーに適用されている場合、そのユーザーは次の検索関連アクションを実行できます。

- コンテンツを検索する

- 検索結果のプレビュー

- 検索結果をエクスポートする

- 検索によって返されたアイテムを消去する

また、検索アクセス許可フィルターを使用して、特定の電子情報開示マネージャーが検索できるユーザー コンテンツの場所 (メールボックス、SharePoint サイト、OneDrive アカウントなど) を制御する組織内に論理境界 (*コンプライアンス境界* と呼ばれる) を作成することもできます。 詳細については、「 [電子情報開示調査のコンプライアンス境界を設定する](set-up-compliance-boundaries.md)」を参照してください。
  
Security & Compliance PowerShell の次の 4 つのコマンドレットを使用すると、検索アクセス許可フィルターを構成および管理できます。
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>アクセス許可フィルターを構成するための要件

- コンプライアンス セキュリティ フィルター コマンドレットを実行するには、コンプライアンス ポータルの組織管理役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)」を参照してください。

- コンプライアンス セキュリティ フィルター コマンドレットを使用するには、Exchange Online とセキュリティ &コンプライアンス PowerShell の両方に接続する必要があります。 これは、これらのコマンドレットがメールボックスのプロパティにアクセスする必要があるため、PowerShell Exchange Online接続する必要があるためです。 手順については、次のセクションを参照してください。

- アクセス許可の検索フィルターの詳細については、「[More information](#more-information)」セクションを参照してください。

- 検索アクセス許可のフィルター処理は、非アクティブなメールボックスに適用されます。つまり、メールボックスとメールボックス コンテンツのフィルター処理を使用して、非アクティブなメールボックスを検索できるユーザーを制限することができます。 アクセス許可のフィルター処理と非アクティブなメールボックスの詳細については、「[詳細情報](#more-information)」のセクションを参照してください。

- 検索アクセス許可のフィルター処理は、Exchange のパブリック フォルダーを検索できるユーザーを制限するのに使用することができません。

- 組織で作成できる検索アクセス許可フィルターの数に制限はありません。 ただし、検索クエリには最大 100 個の条件を指定できます。 この場合、条件は、ブール演算子 ( **AND**、 **OR**、 **NEAR** など) によってクエリに接続されているものとして定義されます。 条件の数の制限には、検索クエリ自体と、検索を実行するユーザーに適用されるすべての検索アクセス許可フィルターが含まれます。 そのため、(特にこれらのフィルターが同じユーザーまたはユーザーのグループに適用されている場合) 検索アクセス許可フィルターが多いほど、検索の条件の最大数を超える可能性が高くなります。 組織が条件の制限に達するのを防ぐには、組織の検索アクセス許可フィルターの数を、ビジネス要件を満たすためにできるだけ少なくしてください。 詳細については、「 [電子情報開示調査のコンプライアンス境界を設定する](set-up-compliance-boundaries.md#frequently-asked-questions)」を参照してください。

## <a name="connect-to-exchange-online-and-security--compliance-powershell-in-a-single-session"></a>Exchange Onlineとセキュリティ&コンプライアンス PowerShell を 1 回のセッションでConnectする

このセクションでスクリプトを正常に実行するには、Exchange Online PowerShell V2 モジュールをダウンロードしてインストールする必要があります。 詳細については、「[PowerShell V2 モジュールExchange Onlineについて](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)」を参照してください。

1. .ps1のファイル名サフィックスを使用して、次のテキストをWindows PowerShell スクリプト ファイル **に** 保存します。 たとえば、 **ConnectEXO-SCC.ps1という名前** のファイルに保存できます。

    ```powershell
    Import-Module ExchangeOnlineManagement
    $UserCredential = Get-Credential
    Connect-ExchangeOnline -Credential $UserCredential -ShowBanner:$false
    Connect-IPPSSession -Credential $UserCredential
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. ローカル コンピューター上で、Windows PowerShell を開き、前の手順で作成したスクリプトが配置されているフォルダーに移動し、スクリプトを実行します。例:

    ```powershell
    .\ConnectEXO-SCC.ps1
    ```

これが機能したかどうかを知る方法 スクリプトを実行すると、powerShell と Security & Compliance PowerShell Exchange Onlineのコマンドレットを使用できます。 何もエラーが表示されなければ、正常に接続されています。 クイック テストでは、PowerShell コマンドレットと Security & Compliance PowerShell コマンドレットExchange Online実行します。 たとえば、 **Get-Mailbox** と **Get-ComplianceSearch** を実行して実行できます。

PowerShell 接続エラーのトラブルシューティングについては、次を参照してください。

- [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [セキュリティ/コンプライアンス PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-ComplianceSecurityFilter** は、検索アクセス許可フィルターを作成するために使用されます。 このコマンドレットの基本的な構文を次に示します。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <user or role group> -Filters <filter>
```

次のセクションでは、このコマンドレットのパラメーターについて説明します。 検索アクセス許可フィルターを作成するには、すべてのパラメーターが必要です。

### <a name="filtername"></a>*FilterName*

_FilterName_ パラメーターは、アクセス許可フィルターの名前を指定します。 この名前は、**Get ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter**、および **Remove-ComplianceSecurityFilter** コマンドレットを使用する際に、フィルターを特定するために使用されます。

### <a name="filters"></a>*Filters*

_Filters_ パラメーターはコンプライアンス セキュリティ フィルターの検索条件を指定します。 次の 3 つの異なる種類のフィルターを作成できます。  

- **メールボックスまたはOneDriveフィルター:** この種類のフィルターは、メールボックスを指定し、割り当てられたユーザー (_Users_ パラメーターで指定) が検索できるアカウントをOneDriveします。 この種類のフィルターは、ユーザーが検索できるコンテンツの場所を定義するため、 *コンテンツの場所* フィルターと呼ばれます。 この種類のフィルターの構文は _MailboxPropertyName_ **Mailbox_** です。_MailboxPropertyName_ は、検索できるメールボックスとOneDrive アカウントのスコープに使用されるメールボックス プロパティを指定します。 たとえば、メールボックス フィルター`"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"`を使用すると、このフィルターを割り当てたユーザーは、CustomAttribute10 プロパティの値 "の 付きユーザー" を持つメールボックスとOneDrive アカウントのみを検索できます。

  メールボックスまたはOneDrive フィルターの _MailboxPropertyName_ プロパティには、サポートされているフィルター可能な受信者プロパティを使用できます。 次の表に、メールボックスまたはOneDriveフィルターの作成に使用される 4 つの一般的な受信者プロパティを示します。 この表には、フィルターでプロパティを使用する例も含まれています。

  |プロパティ名  |例  |
  |---------|---------|
  |Alias    |`"Mailbox_Alias -like 'v-'"`         |
  |会社名  |`"Mailbox_Company -eq 'Contoso'"`        |
  |CountryOrRegion |`"Mailbox_CountryOrRegion -eq 'United States'"`         |
  |部署 |`"Mailbox_Department -eq 'Finance'"`        |
  |||

- **メールボックスコンテンツのフィルター処理:** この種類のフィルターは、検索できるコンテンツに適用されます。 この種類のフィルターは、割り当てられたユーザーが検索できるメールボックスのコンテンツまたは検索可能な電子メール プロパティを指定するため、 *コンテンツ フィルター* と呼ばれます。 この種類のフィルターの構文は **MailboxContent_** _SearchablePropertyNameで、_SearchablePropertyName_ は検索で指定できるキーワード クエリ言語 (KQL) プロパティを指定します。 たとえば、メールボックス コンテンツ フィルター `"MailboxContent_Recipients  -like 'contoso.com'"` を使用すると、このフィルターを割り当てたユーザーは、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索できます。 検索可能な電子メール プロパティの一覧については、「 [電子情報開示のキーワード クエリと検索条件」を](keyword-queries-and-search-conditions.md#searchable-email-properties)参照してください。

  > [!IMPORTANT]
  > 1 つの検索フィルターにメールボックス フィルターとメールボックス コンテンツ フィルターを含めることはできません。 これらを 1 つのフィルターで結合するには、 [フィルターリスト](#using-a-filters-list-to-combine-filter-types)を使用する必要があります。  ただし、フィルターには、同じ型のより複雑なクエリを含めることができます。 たとえば、`"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"` のように指定します。

- **サイトとサイトのコンテンツ のフィルター処理:** 割り当てられたユーザーが検索できるサイトまたはサイトのコンテンツを指定するために使用できる、SharePointおよびOneDrive関連のフィルターが 2 つあります。

  - **Site_**_SearchableSiteProperty_
  
  - **SiteContent_**_SearchableSiteProperty_
  
   これら 2 つのフィルターは交換可能です。 たとえば、 `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors'"`  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors'"` 同じ結果を返します。 検索可能なサイト プロパティの一覧については、「[電子情報開示のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md#searchable-site-properties)」を参照してください。詳細な一覧については、「[SharePointのクロールされたプロパティと管理プロパティの概要](/SharePoint/technical-reference/crawled-and-managed-properties-overview)」を参照してください。 [**クエリ可能**] 列で [**はい**] とマークされているプロパティを使用して、サイトまたはサイトのコンテンツ フィルターを作成できます。  

  > [!IMPORTANT]
  > サポートされているプロパティのいずれかを使用してサイト フィルターを設定しても、フィルター内のサイト プロパティがそのサイト上のすべてのドキュメントに反映されるわけではありません。 つまり、サイト フィルターが機能し、適切なコンテンツをキャプチャするために、そのサイト上のドキュメントに関連付けられている特定のプロパティ フィールドをユーザーが引き続き設定する必要があります。 たとえば、ユーザーにセキュリティ フィルター "Site_RefineableString00 -eq 'abc' が適用され、ユーザーがキーワード クエリ "xyz" を使用して検索を実行した場合です。 セキュリティ フィルターがクエリに追加され、実行されている実際のクエリは "xyz **AND RefineableString0:'abc'** になります。 ユーザーは、サイト上のドキュメントが実際に [RefineableString00] フィールドの値を "abc" として持っていることを確認する必要があります。 そうでない場合、検索クエリは結果を返しません。

検索アクセス許可フィルターの *Filters* パラメーターを構成する場合は、次の点に注意してください。

- メールボックスとは異なり、サイト フィルターが場所フィルターのように見えても、 *サイト* のコンテンツの場所フィルターはありません。 SharePointとOneDriveのすべてのフィルターはコンテンツ フィルターです (また、*パス* などのサイト関連のプロパティがドキュメントに直接スタンプされるため、*Site_* フィルターと *SiteContent_* フィルターが交換可能な理由でもあります)。 これはなぜですか? これは、SharePointの設計方法の結果です。 SharePointでは、Exchangeメールボックスなど、プロパティを持つ "サイト オブジェクト" はありません。 そのため、 *Path* プロパティはドキュメントにスタンプされ、ドキュメントが配置されているサイトの URL が含まれます。 このため、 *サイト* フィルターはコンテンツ の場所フィルターではなく、コンテンツ フィルターと見なされます。

- 検索アクセス許可フィルターを作成して、ユーザーが特定のサービス内のコンテンツの場所を明示的に検索できないようにする必要があります (ユーザーがExchangeメールボックスやSharePoint サイトを検索できないようにするなど)。 つまり、組織内のすべての SharePoint サイトをユーザーが検索できるようにする検索権限フィルターを作成しても、そのユーザーはメールボックスを検索できてしまいます。 たとえば、SharePoint管理者がSharePoint サイトのみを検索できるようにするには、メールボックスを検索できないようにするフィルターを作成する必要があります。 同様に、Exchange管理者がメールボックスのみを検索できるようにするには、サイトを検索できないようにするフィルターを作成する必要があります。

### <a name="users"></a>*Users*

_Users_ パラメーターは、このフィルターを検索に適用するユーザーを指定します。 ユーザーのエイリアスまたはプライマリ SMTP アドレスでユーザーを特定します。 カンマで区切って複数の値を指定することも、値 **All** を使用してすべてのユーザーにフィルターを割り当てることもできます。

_Users_ パラメーターを使用して、コンプライアンス ポータルの役割グループを指定することもできます。 これにより、カスタムの役割グループを作成して、その役割グループに検索アクセス許可フィルターを割り当てることができます。 たとえば、多国籍企業の米国支社の電子情報開示管理者向けのカスタムの役割グループがあるとします。 _Users_ パラメーターを使用してこの役割グループを指定してから (役割グループの Name プロパティを使用)、_Filter_ パラメーターを使用して米国内のメールボックスのみを検索できるようにできます。 このパラメーターを使用して配布グループを指定することはできません。|

### <a name="using-a-filters-list-to-combine-filter-types"></a>フィルターリストを使用してフィルターの種類を結合する

*フィルターリスト* は、メールボックス フィルターとサイト フィルターをコンマで区切って含むフィルターです。 このコンマは **、OR** 演算子としても機能します。 フィルターリストを使用することは、さまざまな種類のフィルターを組み合わせるためにサポートされている唯一の方法です。 次の例では、 **コンマでメールボックス** フィルターと **サイト** フィルターが区切られています。

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors'"
```

フィルターリストを含むフィルターが検索の実行中に処理されると、フィルターリストから 2 つの検索アクセス許可フィルターが作成されます。コンマで区切られたフィルターごとに 1 つずつです。 そのため、前の例では、1 つのメールボックス検索アクセス許可フィルターと 1 つのサイト検索アクセス許可フィルターが作成されます。 これらのフィルターは **、OR** 演算子によって接続されます。

フィルター リストを使用する代わりに、2 つの個別の検索アクセス許可フィルターを作成します。 そのため、前の例では、メールボックス属性用に 1 つのフィルターを作成し、サイト属性に 1 つのフィルターを作成します。 どちらの場合も、結果は同じです。 フィルターリストを使用するか、個別の検索アクセス許可フィルターを作成することは好みの問題です。

フィルターリストの使用については、次の点に注意してください。

- メールボックス フィルターと **MailboxContent** フィルターを含むフィルターを作成 **するには、フィルター** リストを使用する必要があります。

- フィルターリストの各コンポーネントには、複雑なフィルター構文を含めることができます。 たとえば、メールボックスフィルターとサイト フィルターには、 **-or** 演算子で区切られた複数のフィルターを含めることができます。

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>検索アクセス許可フィルターの作成例

以下に、**New-ComplianceSecurityFilter** コマンドレットを使用して検索アクセス許可フィルターを作成する例を示します。

この例では、"US Discovery Managers" 役割グループのメンバーが、米国内のメールボックスとOneDrive アカウントのみを検索できるようにします。
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryOrRegion  -eq 'United States'"
```
  
この例では、ユーザー annb@contoso.com がカナダのメールボックスとOneDrive アカウントに対してのみ検索アクションを実行できるようにします。 このフィルターには、ISO 3166 1 からカナダの 3 桁の数値の国コードが含まれています。

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'"
```

この例では、ユーザーは、CustomAttribute1 メールボックス プロパティの値 "Marketing" を持つメールボックスとOneDrive アカウントのみを検索できます。

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'"
```

この例では、"Fourth Coffee 電子情報開示マネージャー" 役割グループのメンバーが、Department メールボックス プロパティの値 "FourthCoffee" を持つメールボックスとOneDrive アカウントのみを検索できるようにします。 このフィルターを使用すると、役割グループのメンバーは、Fourth Coffee SharePoint サイト内のドキュメントを検索することもできます。

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

> [!NOTE]
> 前の例では、役割グループメンバーがOneDrive アカウント内のドキュメントを検索できるように、追加のサイト コンテンツ フィルター (`SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'`) を含める必要があります。 このフィルターが含まれていない場合、フィルターでは、役割グループのメンバー `https://contoso.sharepoint.com/sites/FourthCoffee`が 、 .

この例では、電子情報開示マネージャーの役割グループのメンバーが、Discovery Users 配布グループのメンバーのメールボックスとOneDrive アカウントのみを検索できるようにします。 Exchange Online PowerShell のGet-DistributionGroup コマンドレットは、のユーザー グループのメンバーを検索するために使用されます。
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"
```

この例では、すべてのユーザーが、エグゼクティブ チーム配布グループのメンバーのメールボックスとOneDrive アカウントに対して検索アクションを実行できないようにします。 つまり、ユーザーはこれらのメールボックスからコンテンツを削除できます。 Exchange Online PowerShell のGet-DistributionGroup コマンドレットは、エグゼクティブ チーム グループのメンバーを検索するために使用されます。

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" 
```

この例では、OneDrive電子情報開示マネージャーのカスタム役割グループのメンバーが、組織内のOneDrive アカウント内のコンテンツのみを検索できるようにします。

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```
  
この例では、2015 年の暦年に送信されたメール メッセージに対してのみ検索アクションを実行するようにユーザーを制限します。

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'"
```

前の例と同様に、この例では、2015 年に最後に変更されたドキュメントに対してのみ検索アクションを実行するようにユーザーを制限します。

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" 
```

この例では、"OneDrive探索マネージャー" 役割グループのメンバーが組織内の任意のメールボックスで検索アクションを実行できないようにします。

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"
```

この例では、組織内のすべてのユーザーが、janets または sarad によって送受信された電子メール メッセージに対して検索アクションを実行できないようにします。

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'"
```

この例では、フィルター リストを使用して、メールボックスフィルターとサイト フィルターを組み合わせます。 この例では、メールボックス フィルターはコンテンツの場所フィルターであり、サイト フィルターはコンテンツ フィルターです。

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery'"
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** はアクセス許可の検索フィルターの一覧を返すために使用します。 _FilterName_ パラメーターを使用して、特定の検索フィルターの情報を返します。
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter** は既存のアクセス許可の検索フィルターを変更する場合に使用します。 次のセクションでは、このコマンドレットのパラメーターについて説明します。 唯一の必須パラメーターは _FilterName_ です。
  
### <a name="filtername"></a>*FilterName*

_FilterName_ パラメーターは、アクセス許可フィルターの名前を指定します。

### <a name="users"></a>*Users*

_Users_ パラメーターは、このフィルターを検索に適用するユーザーを指定します。 これは複数値プロパティであるため、このパラメーターを使用してユーザーまたはユーザーのグループを指定すると、既存のユーザーの一覧が上書きされます。 選択したユーザーを追加および削除する構文については、次の例を参照してください。

_Users_ パラメーターを使用して、コンプライアンス ポータルの役割グループを指定することもできます。 これにより、カスタムの役割グループを作成して、その役割グループに検索アクセス許可フィルターを割り当てることができます。 たとえば、多国籍企業の米国支社の電子情報開示管理者向けのカスタムの役割グループがあるとします。 _Users_ パラメーターを使用してこの役割グループを指定してから (役割グループの Name プロパティを使用)、_Filter_ パラメーターを使用して米国内のメールボックスのみを検索できるようにできます。 このパラメーターでは、配布グループを指定することはできません。

### <a name="filters"></a>*Filters*

_Filters_ パラメーターはコンプライアンス セキュリティ フィルターの検索条件を指定します。 次の 3 つの異なる種類のフィルターを作成できます。

- **メールボックスとOneDriveのフィルター処理:** この種類のフィルターは、メールボックスを指定し、割り当てられたユーザー (_Users_ パラメーターで指定) が検索できるアカウントをOneDriveします。 この種類のフィルターの構文は、**Mailbox_** _MailboxPropertyName_ です。_MailboxPropertyName_ は、検索できるメールボックスの範囲を指定するために使用されるメールボックス プロパティを指定します。 たとえば、メールボックス フィルター  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` を使用すると、このフィルターを割り当てたユーザーは、CustomAttribute10 プロパティの値 "付きユーザー" を持つメールボックスのみを検索できます。  _MailboxPropertyName_ プロパティには、サポートされているフィルター可能な受信者プロパティであればどれでも使用できます。 サポートされているプロパティの一覧については、「[-RecipientFilter パラメーターのフィルター可能なプロパティ](/powershell/exchange/recipientfilter-properties)」を参照してください。

- **メールボックスコンテンツのフィルター処理:** この種類のフィルターは、検索できるコンテンツに適用されます。 これは、割り当てられたユーザーが検索できるメールボックス コンテンツを指定します。 この種類のフィルターの構文は **MailboxContent_**_SearchablePropertyName_ です。_SearchablePropertyName_ は、検索で指定できるキーワード クエリ言語 (KQL) プロパティを指定します。 たとえば、メールボックス コンテンツ フィルター `"MailboxContent_Recipients  -like 'contoso.com'"` を使用すると、このフィルターを割り当てたユーザーは、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索できます。  検索可能な電子メール プロパティの一覧については、「 [電子情報開示のキーワード クエリと検索条件」を](keyword-queries-and-search-conditions.md)参照してください。

- **サイトとサイトのコンテンツ のフィルター処理:** 割り当てられたユーザーが検索できるサイトまたはサイトのコンテンツを指定するために使用できるサイト関連のフィルターには、次の 2 つのSharePointとOneDrive for Businessがあります。

  - **Site_** *SearchableSiteProperty* 
  - **SiteContent** _ *SearchableSiteProperty*
  
  これら 2 つのフィルターは交換可能です。 たとえば、  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 同じ結果を返します。 検索可能なサイト プロパティの一覧については、「[ロールされたプロパティと管理プロパティの概要](/SharePoint/technical-reference/crawled-and-managed-properties-overview)」を参照してください。 [**クエリ可能**] 列で [**はい**] とマークされているプロパティを使用して、サイトまたはサイトのコンテンツ フィルターを作成できます。

### <a name="examples-of-changing-search-permissions-filters"></a>検索アクセス許可フィルターの変更例

以下の例では、**Get-ComplianceSecurityFilter** コマンドレットと **Set-ComplianceSecurityFilter** コマンドレットを使用して、フィルターが割り当てられている既存のユーザーの一覧でユーザーを追加または削除する方法について説明します。 ユーザーをフィルターに追加またはフィルターから削除する場合は、SMTP アドレスを使用してユーザーを指定します。
  
この例では、フィルターにユーザーを追加します。

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.add("pilarp@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

以下の例では、フィルターからユーザーを削除します。

```powershell
$filterusers = Get-ComplianceSecurityFilter -FilterName OttawaUsersFilter
```

```powershell
$filterusers.users.remove("annb@contoso.com")
```

```powershell
Set-ComplianceSecurityFilter -FilterName OttawaUsersFilter -Users $filterusers.users
```

## <a name="remove-compliancesecurityfilter"></a>Remove-ComplianceSecurityFilter

**Remove-ComplianceSecurityFilter** は検索フィルターを削除する場合に使用します。 _FilterName_ パラメーターを使用して、削除するフィルターを指定します。
  
## <a name="more-information"></a>詳細情報

- **検索アクセス許可のフィルター処理のしくみ。** 検索の実行時に、アクセス許可フィルターが検索クエリに追加されます。 アクセス許可フィルターは、 **AND** ブール演算子によって検索クエリに結合されます。 検索クエリとアクセス許可フィルターのクエリ ロジックは次のようになります。

  ```text
  <SearchQuery> AND <PermissionsFilter>
  ```

  たとえば、Bob が Workers 配布グループのメンバーのメールボックスに対してすべての検索アクションを実行できるようにするアクセス許可フィルターがあるとします。 次に、Bob は、組織内のすべてのメールボックスに対して検索クエリを使用して検索を実行します  `sender:jerry@adatum.com`。 アクセス許可フィルターと検索クエリは **AND** 演算子によって論理的に結合されるため、検索では jerry@adatum.com によって Workers 配布グループの任意のメンバーに送信されたすべてのメッセージが返されます。 

- **複数の検索アクセス許可フィルターがある場合。** 検索クエリでは、複数のアクセス許可フィルターが **OR** ブール演算子によって結合されます。 したがって、フィルターのいずれかに該当する場合に結果が返されます。 検索では、すべてのフィルター ( **OR** 演算子で結合) が **AND** 演算子によって検索クエリと結合されます。

  ```text
  <SearchQuery> AND  (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>)
  ```

  前の例を見てみましょう。検索フィルターを使用すると、Bob は Workers 配布グループのメンバーのメールボックスのみを検索できます。 次に、Bob が Phil のメールボックスを検索することを防止する別のフィルターを作成します ("Mailbox_Alias -ne 'Phil'")。 また、Phil が Workers グループのメンバーであると仮定してみましょう。 Bob が組織内のすべてのメールボックスで (前の例の) 検索を実行すると、Bob が Phil のメールボックスを検索できないようにフィルターを適用した場合でも、検索結果が Phil のメールボックスに対して返されます。 これは、Bob に Workers グループを検索することを許可する最初のフィルターに該当しているからです。 また、Phil が Workers グループのメンバーであるため、Bob は Phil のメールボックスを検索できます。

- **非アクティブなメールボックスで検索アクセス許可のフィルター処理は動作しますか。** はい、メールボックスとメールボックス コンテンツのフィルター処理を使用して、組織の非アクティブなメールボックスを検索できるユーザーを制限することができます。 通常のメールボックスのように、非アクティブなメールボックスは、アクセス許可のフィルターを作成するのに使用される受信者プロパティで設定する必要があります。 必要に応じて、**Get-Mailbox -InactiveMailboxOnly** コマンドを使用して非アクティブなメールボックスのプロパティを表示することができます。 詳細については、「 [非アクティブなメールボックスの作成と管理](create-and-manage-inactive-mailboxes.md)」を参照してください。
  
- **パブリック フォルダーで検索アクセス許可のフィルター処理は動作しますか。** いいえ。 上で説明したように、検索アクセス許可のフィルター処理は、Exchange のパブリック フォルダーを検索できるユーザーを制限する目的には使用できません。 たとえば、パブリック フォルダーの場所にあるアイテムは、アクセス許可のフィルターによって、検索結果から除外することができません。

- **特定のサービスのすべてのコンテンツの場所をユーザーが検索できるようにした場合、ユーザーは他のサービスのコンテンツの場所を検索できないようになりますか。** いいえ。 前に説明したように、検索アクセス許可フィルターを作成して、ユーザーが特定のサービス内のコンテンツの場所を検索できないようにする必要があります (ユーザーがExchangeメールボックスやSharePoint サイトを検索できないようにするなど)。 つまり、組織内のすべての SharePoint サイトをユーザーが検索できるようにする検索権限フィルターを作成しても、そのユーザーはメールボックスを検索できてしまいます。 たとえば、SharePoint管理者がSharePoint サイトのみを検索できるようにするには、メールボックスを検索できないようにするフィルターを作成する必要があります。 同様に、Exchange管理者がメールボックスのみを検索できるようにするには、サイトを検索できないようにするフィルターを作成する必要があります。

- **検索アクセス許可フィルターは、検索クエリ文字の制限に対してカウントされますか?** はい。 検索アクセス許可フィルターは、検索クエリの文字制限に対してカウントされます。 詳細については、「[電子情報開示の制限 (プレミアム)」](limits-ediscovery20.md)を参照してください。

**組織内で作成できる検索アクセス許可フィルターの最大数は何ですか?**
  
組織で作成できる検索アクセス許可フィルターの数に制限はありません。 ただし、検索クエリには最大 100 個の条件を指定できます。 この場合、条件は、ブール演算子 ( **AND**、 **OR**、 **NEAR** など) によってクエリに接続されているものとして定義されます。 条件の数の制限には、検索クエリ自体と、検索を実行するユーザーに適用されるすべての検索アクセス許可フィルターが含まれます。 そのため、(特にこれらのフィルターが同じユーザーまたはユーザーのグループに適用されている場合) 検索アクセス許可フィルターが多いほど、検索の条件の最大数を超える可能性が高くなります。

この制限のしくみを理解するには、検索の実行時に検索アクセス許可フィルターが検索クエリに追加されることを理解する必要があります。 検索アクセス許可フィルターは、 **AND** ブール演算子によって検索クエリに結合されます。 検索クエリのクエリ ロジックと 1 つの検索アクセス許可フィルターは、次のようになります。

```text
<SearchQuery> AND <PermissionsFilter>
```

複数の検索アクセス許可フィルターは **OR** ブール演算子によって結合され、それらの条件は **AND** 演算子によって検索クエリに接続されます。

検索クエリと複数の検索アクセス許可フィルターのクエリ ロジックは次のようになります。

```text
<SearchQuery> AND (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>...)
```

検索クエリ自体が、ブール演算子によって接続された複数の条件で構成される可能性があります。 検索クエリの各条件も、100 条件の制限に対してカウントされます。

また、クエリに追加される検索アクセス許可フィルターの数は、検索を実行しているユーザーによって異なります。 特定のユーザーが検索を実行すると、ユーザーに適用される検索アクセス許可フィルター (フィルターの *Users* パラメーターによって定義されます) がクエリに追加されます。 組織には何百もの検索アクセス許可フィルターを設定できますが、同じユーザーに 100 を超えるフィルターが適用されている場合、それらのユーザーが検索を実行すると、100 条件の制限を超える可能性があります。

条件の制限については、もう 1 つ注意する必要があります。 検索クエリまたは検索アクセス許可フィルターに含まれる特定のSharePoint サイトの数も、この制限に対してカウントされます。 

組織が条件の制限に達するのを防ぐには、組織の検索アクセス許可フィルターの数を、ビジネス要件を満たすためにできるだけ少なくしてください。