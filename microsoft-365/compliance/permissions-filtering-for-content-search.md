---
title: コンテンツ検索のアクセス許可フィルターを構成する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: コンテンツ検索のアクセス許可フィルターを使用して、電子情報開示マネージャーが組織内のメールボックスとサイトのサブセットのみを検索できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82e5ce9be5e2f26c1863b0951d3476a6aa31458d
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58508132"
---
# <a name="configure-permissions-filtering-for-content-search"></a>コンテンツ検索のアクセス許可フィルターを構成する

検索アクセス許可フィルターを使用すると、電子情報開示マネージャーが組織内のメールボックスとサイトのサブセットのみを検索できます。 また、アクセス許可のフィルター処理を使用して、同じ電子情報開示管理者に特定の検索条件を満たすメールボックスやサイトのコンテンツのみを検索させることができます。 たとえば、電子情報開示管理者に特定の場所または部門のユーザーのメールボックスのみを検索させるようにすることができます。 これを行うには、サポートされている受信者フィルターを使用して、特定のユーザーまたはユーザー グループが検索できるメールボックスを制限するフィルターを作成します。 ユーザーが検索できるメールボックス コンテンツを指定するフィルターを作成できます。 これは、検索可能なメッセージ プロパティを使用するフィルターを作成することで行います。 同様に、電子情報開示マネージャーが組織内の特定のSharePointのみを検索できます。 これは、検索可能なサイトを限定するフィルターを作成することで行います。 検索可能なサイトのコンテンツを指定するフィルターを作成することもできます。 これは、検索可能なサイト プロパティを使用するフィルターを作成することで行います。

検索アクセス許可フィルターを使用して、特定の電子情報開示マネージャーが検索できるユーザーコンテンツの場所 (メールボックス、SharePoint サイト、OneDrive アカウントなど) を制御する組織内に論理境界 (コンプライアンス境界と呼ばれる) を作成することもできます。 詳細については、「[Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する](tagging-and-assessment-in-advanced-ediscovery.md)」を参照してください。
  
検索アクセス許可のフィルター処理は、ページ内のコンテンツ検索機能でMicrosoft 365 コンプライアンス センター。 これらの 4 つのコマンドレットを使用すると、検索アクセス許可フィルターを構成および管理できます。
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>アクセス許可フィルターを構成するための要件

- コンプライアンス セキュリティ フィルターコマンドレットを実行するには、組織の管理役割グループのメンバーである必要Microsoft 365 コンプライアンス センター。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)」を参照してください。

- コンプライアンス セキュリティ フィルターコマンドレットを使用するにはExchange Onlineとセキュリティ &コンプライアンス センター PowerShell の両方に接続する必要があります。 これらのコマンドレットではメールボックスプロパティへのアクセスが必要なので、PowerShell に接続する必要Exchange Onlineです。 手順については、次のセクションを参照してください。

- アクセス許可の検索フィルターの詳細については、「[More information](#more-information)」セクションを参照してください。

- 検索アクセス許可のフィルター処理は、非アクティブなメールボックスに適用されます。つまり、メールボックスとメールボックス コンテンツのフィルター処理を使用して、非アクティブなメールボックスを検索できるユーザーを制限することができます。 アクセス許可のフィルター処理と非アクティブなメールボックスの詳細については、「[詳細情報](#more-information)」のセクションを参照してください。

- 検索アクセス許可のフィルター処理は、Exchange のパブリック フォルダーを検索できるユーザーを制限するのに使用することができません。

- 組織で作成できる検索アクセス許可フィルターの数に制限はありません。 ただし、検索アクセス許可フィルターが 100 を超える場合は、検索のパフォーマンスに影響します。 検索の検索アクセス許可フィルターの数を出来るだけ少なくするために、可能な限り、Exchange、SharePoint、および OneDrive のルールを 1 つのフィルターに統合するフィルターを作成するようにします。

## <a name="connect-to-exchange-online-and-security--compliance-center-powershell-in-a-single-session"></a>Connect 1 Exchange Onlineでコンプライアンス & PowerShell のセキュリティ とセキュリティを管理する方法

このセクションでスクリプトを正常に実行する前に、PowerShell V2 モジュールをダウンロードしてインストールExchange Onlineする必要があります。 詳細については[、「PowerShell V2 モジュールExchange Onlineについて」を参照してください](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)。

1. ファイル名のサフィックスを使用してWindows PowerShellスクリプト ファイルに次のテキスト **を保存**.ps1。 たとえば、このファイルを "ConnectEXO-SCC.ps1" という名前 **のファイルに保存ConnectEXO-SCC.ps1。**

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

これが機能したかどうかを知る方法 スクリプトを実行すると、コンプライアンス PowerShell Exchange Onlineセキュリティ &のコマンドレットがローカル のユーザー セッションにWindows PowerShellされます。 何もエラーが表示されなければ、正常に接続されています。 クイック テストでは、コンプライアンス センター powerShell コマンドレットExchange Onlineセキュリティ &を実行します。 たとえば、Get-Mailbox と **Get-ComplianceSearch** **を実行して実行できます**。

PowerShell 接続エラーのトラブルシューティングについては、以下を参照してください。

- [Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell#how-do-you-know-this-worked)

- [セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell#how-do-you-know-this-worked)

## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-ComplianceSecurityFilter を** 使用して、検索アクセス許可フィルターを作成します。 次の表では、このコマンドレットのパラメーターについて説明します。 コンプライアンス セキュリティ フィルターを作成するには、すべてのパラメーターが必要です。
  
| パラメーター | 説明 |
|:-----|:-----|
| _Action_ <br/> | _Action_ パラメーターは、フィルターに適用する検索操作の種類を指定します。 可能なコンテンツ検索アクションは次のとおりです。  <br/><br/> **エクスポート:** 検索結果のエクスポート時にフィルターが適用されます。  <br/> **プレビュー:** 検索結果のプレビュー時にフィルターが適用されます。  <br/> **削除:** フィルターは、検索結果を削除するときに適用されます。  <br/> **検索:** フィルターは、検索の実行中に適用されます。  <br/> **すべて:** フィルターは、すべての検索アクションに適用されます。  <br/> |
| _FilterName_ <br/> |_FilterName_ パラメーターは、アクセス許可フィルターの名前を指定します。 この名前は、**Get ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter**、および **Remove-ComplianceSecurityFilter** コマンドレットを使用する際に、フィルターを特定するために使用されます。  <br/> |
| _Filters_ <br/> | _Filters_ パラメーターはコンプライアンス セキュリティ フィルターの検索条件を指定します。 次の 3 つの異なる種類のフィルターを作成できます。  <br/><br/> **メールボックスまたはOneDriveフィルター:** この種類のフィルターは、割り当OneDriveユーザー _(Users_ パラメーターで指定) が検索できるメールボックスとアカウントを指定します。 この種類のフィルターの構文は **Mailbox_** _MailboxPropertyName です。MailboxPropertyName_ は、検索できるメールボックスと OneDrive アカウントのスコープに使用されるメールボックス プロパティを指定します。  たとえば、メールボックス フィルターを使用すると、このフィルターを割り当てられたユーザーは `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` 、CustomAttribute10 プロパティの "OttawaUsers" という値を持つメールボックスと OneDrive アカウントのみを検索できます。  <br/>  _MailboxPropertyName_ プロパティには、サポートされているフィルター可能な受信者プロパティであればどれでも使用できます。 サポートされているプロパティの一覧については、「[-RecipientFilter パラメーターのフィルター可能なプロパティ](/powershell/exchange/recipientfilter-properties)」を参照してください。  <br/><br/> **メールボックス のコンテンツ フィルター:** この種類のフィルターは、検索できるコンテンツに適用されます。 これは、割り当てられたユーザーが検索できるメールボックス コンテンツを指定します。 この種類のフィルターの構文は **MailboxContent_** _SearchablePropertyName: value_ で  _、SearchablePropertyName_ はコンテンツ検索で指定できるキーワード クエリ言語 (KQL) プロパティを指定します。 たとえば、メールボックスのコンテンツ フィルター `MailboxContent_recipients:contoso.com` は、このフィルターが割り当てられたユーザーに、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索することを許可します。  <br/>  検索可能なメッセージ プロパティの一覧については、「コンテンツ検索のキーワード クエリ [と検索条件」を参照してください](keyword-queries-and-search-conditions.md)。 <br/> <br/> **重要:**  1 つの検索フィルターにメールボックス フィルターとメールボックス コンテンツ フィルターを含めすることはできません。 これらを 1 つのフィルターに組み合わせるには、フィルター リストを [使用する必要があります](#using-a-filters-list-to-combine-filter-types)。  ただし、フィルターには、同じ種類のより複雑なクエリを含めできます。 例: `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **サイトとサイトのコンテンツ フィルター:** サイト関連のSharePointとOneDrive for Business、割り当てられたユーザーが検索できるサイトまたはサイト コンテンツを指定するために使用できる 2 つのフィルターがあります。  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  これら 2 つのフィルターは交換可能です。 たとえば、同  `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` じ  `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 結果を返します。 しかし、フィルターの役割を理解するため、`Site_` を使用してサイト関連のプロパティ (サイト URL など) を指定し、`SiteContent_` を使用してコンテンツ関連のプロパティ (ドキュメントの種類など) を指定できます。 たとえば、フィルター `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` は、このフィルターが割り当てられたユーザーが、https://contoso.sharepoint.com/sites/doctors サイト コレクション内のコンテンツのみを検索することを許可します。 フィルター `"SiteContent_FileExtension -eq 'docx'"` は、このフィルターが割り当てられたユーザーに、Word 文書 (Word 2007 以降) のみを検索することを許可します。  <br/><br/>  検索可能なサイト プロパティの一覧については、「[ロールされたプロパティと管理プロパティの概要](/SharePoint/technical-reference/crawled-and-managed-properties-overview)」を参照してください。 [**クエリ可能**] 列で [**はい**] とマークされているプロパティを使用して、サイトまたはサイトのコンテンツ フィルターを作成できます。  <br/><br/> **重要:** <br/><br/> - サポートされているプロパティのいずれかを使用してサイト フィルターを設定しても、フィルター内のサイト プロパティが、そのサイトのすべてのファイルに伝達されるという意味ではありません。 つまり、サイト フィルターが機能し、適切なコンテンツをキャプチャするために、ユーザーは引き続きそのサイト上のファイルに関連付けられている特定のプロパティ フィールドにデータを設定する必要があります。 たとえば、ユーザーにセキュリティ フィルター "Site_RefineableString00 -eq 'abc' が適用されている場合、ユーザーはキーワード クエリ "xyz" を使用して検索を実行します。 セキュリティ フィルターがクエリに追加され、実際に実行されているクエリは "xyz **AND RefineableString0:'abc'**" になります。 ユーザーは、サイト上のファイルが実際に RefineableString00 フィールドに abc として値を持つ必要があります。 指定しない場合、この検索クエリは結果を返します。 <br/><br/>- ユーザーが特定のサービス内のコンテンツの場所を明示的に検索する (ユーザーが Exchange メールボックスや SharePoint サイトを検索しないなど) には、検索アクセス許可フィルターを作成する必要があります。 つまり、組織内のすべての SharePoint サイトをユーザーが検索できるようにする検索権限フィルターを作成しても、そのユーザーはメールボックスを検索できてしまいます。 たとえば、管理者SharePointサイトのみをSharePointするには、メールボックスの検索を妨げるフィルターを作成する必要があります。 同様に、管理者Exchangeメールボックスのみを検索するには、サイトの検索を妨げるフィルターを作成する必要があります。           |
| _Users_ <br/> |_Users パラメーター_ は、コンテンツ検索に適用されるこのフィルターを取得するユーザーを指定します。 ユーザーのエイリアスまたはプライマリ SMTP アドレスでユーザーを特定します。 カンマで区切って複数の値を指定することも、値 **All** を使用してすべてのユーザーにフィルターを割り当てることもできます。  <br/> また、Users パラメーターを _使用して_、役割グループMicrosoft 365 コンプライアンス センター指定することもできます。 これにより、カスタムの役割グループを作成して、その役割グループに検索アクセス許可フィルターを割り当てることができます。 たとえば、多国籍企業の米国支社の電子情報開示管理者向けのカスタムの役割グループがあるとします。 _Users_ パラメーターを使用してこの役割グループを指定してから (役割グループの Name プロパティを使用)、_Filter_ パラメーターを使用して米国内のメールボックスのみを検索できるようにできます。  <br/> このパラメーターでは、配布グループを指定することはできません。  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>フィルター リストを使用してフィルターの種類を組み合わせる

フィルター *リストは* 、メールボックス フィルターとコンマで区切られたサイト フィルターを含むフィルターです。 フィルター リストの使用は、さまざまな種類のフィルターを組み合わせる唯一のサポートされる方法です。 次の例では、メールボックス フィルターとサイト フィルターをコンマで区切 **ります**。

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

コンテンツ検索の実行中にフィルター リストを含むフィルターが処理されると、2 つの検索アクセス許可フィルターがフィルター リストから作成されます。1 つはコンマで区切られたフィルターごとに 1 つです。 したがって、前の例では、1 つのメールボックス検索アクセス許可フィルターと 1 つのサイト検索アクセス許可フィルターが作成されます。 

フィルター リストを使用する代わりに、2 つの個別の検索アクセス許可フィルターを作成します。 したがって、前の例では、メールボックス属性用に 1 つのフィルターを作成し、サイト属性に対して 1 つのフィルターを作成します。 どちらの場合も、結果は同じです。 フィルター リストを使用するか、個別の検索アクセス許可フィルターを作成することは、優先的な問題です。

フィルター リストの使用に関して、次のことを念頭に置いておきます。

- メールボックス フィルターと MailboxContent フィルターを含むフィルターを作成するには、フィルター リスト **を使用する必要** があります。

- フィルター リストの各コンポーネントには、複雑なフィルター構文を含めできます。 たとえば、メールボックスフィルターとサイト フィルターには、-or 演算子で区切られた **複数のフィルターを含** めできます。

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>検索アクセス許可フィルターの作成例

以下に、**New-ComplianceSecurityFilter** コマンドレットを使用して検索アクセス許可フィルターを作成する例を示します。 
  
この例では、ユーザーがカナダ annb@contoso.com メールボックスに対してのみすべてのコンテンツ検索アクションを実行できます。 このフィルターには、ISO 3166 1 からカナダの 3 桁の数値の国コードが含まれています。

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

この例では、ユーザー donh および suzanf は、CustomAttribute1 メールボックス プロパティの値が 'Marketing' であるメールボックスのみを検索できます。

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

この例では、"US Discovery Managers" 役割グループのメンバーが、米国内のメールボックスに対してのみすべてのコンテンツ検索アクションを実行できます。 このフィルターには、ISO 3166-1 で米国を表す 3 桁の数値の国コードが含まれています。
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

この例では、電子情報開示マネージャー役割グループのメンバーが、Ottawa Users 配布グループのメンバーのメールボックスのみを検索できます。 PowerShell Get-DistributionGroupのExchange Onlineコマンドレットを使用して、Ottawa Users グループのメンバーを検索します。
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

この例では、すべてのユーザーが Executive Team 配布グループのメンバーのメールボックスからコンテンツを削除することを禁止します。 PowerShell Get-DistributionGroupのExchange Onlineコマンドレットを使用して、エグゼクティブ チーム グループのメンバーを検索します。

```powershell
$DG = Get-DistributionGroup "Executive Team"
```

```powershell
New-ComplianceSecurityFilter -FilterName NoExecutivesPreview  -Users All -Filters "Mailbox_MemberOfGroup -ne '$($DG.DistinguishedName)'" -Action Purge
```

この例では、OneDrive 電子情報開示管理者のカスタム役割グループのメンバーは、組織内の OneDrive for Business の場所にあるコンテンツのみを検索できます。

```powershell
New-ComplianceSecurityFilter -FilterName OneDriveOnly  -Users "OneDrive eDiscovery Managers" -Filters "Site_Path -like 'https://contoso-my.sharepoint.com/personal*'" -Action Search
```

> [!NOTE]
> ユーザーが検索できるサイトを特定のサイトに制限する場合、上記の例で示すように、フィルター `Site_Path` を使用します。 `Site_Site` を使用することはできません。 
  
次の使用例は、2015 年の暦年に送信された電子メール メッセージに対してのみ、すべてのコンテンツ検索アクションを実行するユーザーを制限します。

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

前の例と同様に、この例では、2015 年の暦年に最後に変更されたドキュメントに対してすべてのコンテンツ検索アクションを実行するユーザーを制限します。

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

この例では、"OneDrive Discovery Managers" 役割グループのメンバーが組織のメールボックスでコンテンツ検索アクションを実施できないようにしています。 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

この例では、組織内の誰もが、ジャネットまたはサラドによって送信または受信された電子メール メッセージを検索しません。

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

この例では、フィルター リストを使用してメールボックスフィルターとサイト フィルターを組み合わせます。

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** はアクセス許可の検索フィルターの一覧を返すために使用します。 _FilterName_ パラメーターを使用して、特定の検索フィルターの情報を返します。 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter** は既存のアクセス許可の検索フィルターを変更する場合に使用します。 唯一の必須パラメーターは _FilterName_ です。 
  
| パラメーター | 説明 |
|:-----|:-----|
| _Action_| _Action_ パラメーターは、フィルターに適用する検索操作の種類を指定します。 可能なコンテンツ検索アクションは次のとおりです。 <br/><br/> **エクスポート:** 検索結果のエクスポート時にフィルターが適用されます。  <br/> **プレビュー:** 検索結果のプレビュー時にフィルターが適用されます。  <br/> **削除:** フィルターは、検索結果を削除するときに適用されます。  <br/> **検索:** フィルターは、検索の実行中に適用されます。  <br/> **すべて:** フィルターは、すべての検索アクションに適用されます。  <br/> |
| _FilterName_|_FilterName_ パラメーターは、アクセス許可フィルターの名前を指定します。 |
| _Filters_| _Filters_ パラメーターはコンプライアンス セキュリティ フィルターの検索条件を指定します。 次の 2 種類のフィルターを作成できます。 <br/><br/>**メールボックスとOneDriveフィルター:** この種類のフィルターは、割り当OneDriveユーザー _(Users_ パラメーターで指定) が検索できるメールボックスとアカウントを指定します。 この種類のフィルターの構文は、**Mailbox_** _MailboxPropertyName_ です。_MailboxPropertyName_ は、検索できるメールボックスの範囲を指定するために使用されるメールボックス プロパティを指定します。 たとえば、メールボックス フィルターを使用すると、このフィルターを割り当てられたユーザーは  `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` 、CustomAttribute10 プロパティの値 "OttawaUsers" を持つメールボックスのみを検索できます。  _MailboxPropertyName_ プロパティには、サポートされているフィルター可能な受信者プロパティであればどれでも使用できます。 サポートされているプロパティの一覧については、「[-RecipientFilter パラメーターのフィルター可能なプロパティ](/powershell/exchange/recipientfilter-properties)」を参照してください。 <br/><br/>**メールボックス のコンテンツ フィルター:** この種類のフィルターは、検索できるコンテンツに適用されます。 これは、割り当てられたユーザーが検索できるメールボックス コンテンツを指定します。 この種類のフィルターの構文は **MailboxContent_** _SearchablePropertyName:value_ です  _。SearchablePropertyName_ は、コンテンツ検索で指定できるキーワード クエリ言語 (KQL) プロパティを指定します。 たとえば、メールボックスのコンテンツ フィルター `MailboxContent_recipients:contoso.com` は、このフィルターが割り当てられたユーザーに、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索することを許可します。  検索可能なメッセージ プロパティの一覧については、「 [コンテンツ検索のキーワード クエリ」を参照してください](keyword-queries-and-search-conditions.md)。 <br/><br/>**サイトとサイトのコンテンツ フィルター:** サイト関連のSharePointとOneDrive for Business、割り当てられたユーザーが検索できるサイトまたはサイト コンテンツを指定するために使用できる 2 つのフィルターがあります。 <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent** _ *SearchableSiteProperty*<br/><br/>これら 2 つのフィルターは交換可能です。 たとえば、同  `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"`  `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` じ結果を返します。 しかし、フィルターの役割を理解するため、`Site_` を使用してサイト関連のプロパティ (サイト URL など) を指定し、`SiteContent_` を使用してコンテンツ関連のプロパティ (ドキュメントの種類など) を指定できます。 たとえば、フィルター `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` は、このフィルターが割り当てられたユーザーが、https://contoso.spoppe.com/sites/doctors サイト コレクション内のコンテンツのみを検索することを許可します。 フィルター `"SiteContent_FileExtension -eq 'docx'"` は、このフィルターが割り当てられたユーザーに、Word 文書 (Word 2007 以降) のみを検索することを許可します。  <br/><br/>検索可能なサイト プロパティの一覧については、「[ロールされたプロパティと管理プロパティの概要](/SharePoint/technical-reference/crawled-and-managed-properties-overview)」を参照してください。 [**クエリ可能**] 列で [**はい**] とマークされているプロパティを使用して、サイトまたはサイトのコンテンツ フィルターを作成できます。 <br/><br/>          |
| _Users_|_Users パラメーター_ は、コンテンツ検索に適用されるこのフィルターを取得するユーザーを指定します。 これは複数値プロパティなので、このパラメーターを使用してユーザーまたはユーザーのグループを指定すると、既存のユーザーの一覧が上書きされます。 選択したユーザーを追加および削除する構文については、次の例を参照してください。 <br/><br/>また、Users パラメーターを _使用して_、役割グループMicrosoft 365 コンプライアンス センター指定することもできます。 これにより、カスタムの役割グループを作成して、その役割グループに検索アクセス許可フィルターを割り当てることができます。 たとえば、多国籍企業の米国支社の電子情報開示管理者向けのカスタムの役割グループがあるとします。 _Users_ パラメーターを使用してこの役割グループを指定してから (役割グループの Name プロパティを使用)、_Filter_ パラメーターを使用して米国内のメールボックスのみを検索できるようにできます。 <br/><br/>このパラメーターでは、配布グループを指定することはできません。 |

## <a name="examples-of-changing-search-permissions-filters"></a>検索アクセス許可フィルターの変更例

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

- **検索アクセス許可のフィルター処理のしくみ。** コンテンツ検索を実行すると、アクセス許可フィルターが検索クエリに追加されます。 アクセス許可フィルターは、AND Boolean 演算子によって検索 **クエリに** 結合されます。 検索クエリとアクセス許可フィルターのクエリ ロジックは次のように表示されます。

  ```text
  <SearchQuery> AND <PermissionsFilter>
  ```

  たとえば、Bob が Workers 配布グループのメンバーのメールボックスに対してすべての検索アクションを実行できるアクセス許可フィルターがあります。 次に、Bob は、検索クエリを使用して組織内のすべてのメールボックスでコンテンツ検索を実行します  `sender:jerry@adatum.com` 。 アクセス許可フィルターと検索クエリは **AND** 演算子によって論理的に組み合わされるので、検索は jerry@adatum.com によってワーカー配布グループのメンバーに送信されたメッセージを返します。 

- **複数の検索アクセス許可フィルターがある場合。** コンテンツ検索クエリでは、OR ブール演算子によって複数のアクセス許可 **フィルターが組み** 合わされます。 したがって、フィルターのいずれかに該当する場合に結果が返されます。 コンテンツ検索では、すべてのフィルター **(OR** 演算子を組み合わせたもの) が **AND** 演算子によって検索クエリと組み合わされます。 

  ```text
  <SearchQuery> AND  (<PermissionsFilter1> OR <PermissionsFilter2> OR <PermissionsFilter3>)
  ```

  前の例を見て、検索フィルターを使用すると、Bob は Workers 配布グループのメンバーのメールボックスのみを検索できます。 次に、Bob が Phil のメールボックスを検索することを防止する別のフィルターを作成します ("Mailbox_Alias -ne 'Phil'")。 また、Phil が Workers グループのメンバーであると仮定してみましょう。 Bob が組織内のすべてのメールボックスで (前の例の) コンテンツ検索を実行すると、Bob がフィルのメールボックスを検索しなからせないフィルターを適用した場合でも、フィルのメールボックスの検索結果が返されます。 これは、Bob に Workers グループを検索することを許可する最初のフィルターに該当しているからです。 また、Phil が Workers グループのメンバーであるため、Bob は Phil のメールボックスを検索できます。 

- **非アクティブなメールボックスで検索アクセス許可のフィルター処理は動作しますか。** はい、メールボックスとメールボックス コンテンツのフィルター処理を使用して、組織の非アクティブなメールボックスを検索できるユーザーを制限することができます。 通常のメールボックスのように、非アクティブなメールボックスは、アクセス許可のフィルターを作成するのに使用される受信者プロパティで設定する必要があります。 必要に応じて、**Get-Mailbox -InactiveMailboxOnly** コマンドを使用して非アクティブなメールボックスのプロパティを表示することができます。 詳細については、「[Office 365 の非アクティブなメールボックスの作成と管理](create-and-manage-inactive-mailboxes.md)」を参照してください。
    
- **パブリック フォルダーで検索アクセス許可のフィルター処理は動作しますか。** いいえ。 上で説明したように、検索アクセス許可のフィルター処理は、Exchange のパブリック フォルダーを検索できるユーザーを制限する目的には使用できません。 たとえば、パブリック フォルダーの場所にあるアイテムは、アクセス許可のフィルターによって、検索結果から除外することができません。 

- **特定のサービスのすべてのコンテンツの場所をユーザーが検索できるようにした場合、ユーザーは他のサービスのコンテンツの場所を検索できないようになりますか。** いいえ。 前に説明したように、検索アクセス許可フィルターを作成して、ユーザーが特定のサービス内のコンテンツの場所を明示的に検索する (ユーザーが Exchange メールボックスや SharePoint サイトを検索しないなど) のを防ぐ必要があります。 つまり、組織内のすべての SharePoint サイトをユーザーが検索できるようにする検索権限フィルターを作成しても、そのユーザーはメールボックスを検索できてしまいます。 たとえば、管理者SharePointサイトのみをSharePointするには、メールボックスの検索を妨げるフィルターを作成する必要があります。 同様に、管理者Exchangeメールボックスのみを検索するには、サイトの検索を妨げるフィルターを作成する必要があります。

- **検索アクセス許可フィルターは、検索クエリの文字制限に対してカウントされますか?** はい。 検索アクセス許可フィルターは、検索クエリの文字制限に対してカウントされます。 詳細については、「制限」[を参照Advanced eDiscovery。](limits-ediscovery20.md)
