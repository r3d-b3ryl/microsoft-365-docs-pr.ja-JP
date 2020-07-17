---
title: コンテンツ検索用にアクセス許可フィルターを設定する
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1adffc35-38e5-4f7d-8495-8e0e8721f377
description: コンテンツ検索のアクセス許可フィルターを使用して、電子情報開示マネージャーが組織内のメールボックスとサイトのサブセットのみを検索できるようにします。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06fabfd1132166e2439c9790b50b0dbcb5bdca2c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818776"
---
# <a name="configure-permissions-filtering-for-content-search"></a>コンテンツ検索用にアクセス許可フィルターを設定する

検索アクセス許可フィルターを使用して、電子情報開示マネージャーが組織内のメールボックスとサイトのサブセットのみを検索できるようにすることができます。 また、アクセス許可のフィルター処理を使用して、同じ電子情報開示管理者に特定の検索条件を満たすメールボックスやサイトのコンテンツのみを検索させることができます。 たとえば、電子情報開示管理者に特定の場所または部門のユーザーのメールボックスのみを検索させるようにすることができます。 これを行うには、サポートされている受信者フィルターを使用して、特定のユーザーまたはユーザーグループが検索できるメールボックスを制限するフィルターを作成します。 また、ユーザーが検索できるメールボックスの内容を指定するフィルターを作成することもできます。 これは、検索可能なメッセージ プロパティを使用するフィルターを作成することで行います。 同様に、電子情報開示マネージャーが組織内の特定の SharePoint サイトのみを検索できるようにすることもできます。 これは、検索可能なサイトを限定するフィルターを作成することで行います。 検索可能なサイトのコンテンツを指定するフィルターを作成することもできます。 これは、検索可能なサイト プロパティを使用するフィルターを作成することで行います。

また、検索アクセス許可フィルターを使用して、特定の電子情報開示マネージャーが検索できるユーザーコンテンツの場所 (メールボックス、SharePoint サイト、OneDrive アカウントなど) を制御する、組織内の論理的な境界 (*コンプライアンス境界*と呼ばれる) を作成することもできます。 詳細については、「[Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する](tagging-and-assessment-in-advanced-ediscovery.md)」を参照してください。
  
検索アクセス許可フィルターは、セキュリティ/コンプライアンス センターのコンテンツ検索機能によりサポートされています。 次の4つのコマンドレットを使用すると、検索アクセス許可のフィルターを構成および管理できます。
  
[New-ComplianceSecurityFilter](#new-compliancesecurityfilter)

[Get-ComplianceSecurityFilter](#get-compliancesecurityfilter)

[Set-ComplianceSecurityFilter](#set-compliancesecurityfilter)

[Remove-ComplianceSecurityFilter](#remove-compliancesecurityfilter)

## <a name="requirements-to-configure-permissions-filtering"></a>アクセス許可のフィルターを構成するための要件

- コンプライアンス セキュリティ フィルターのコマンドレットを実行するには、セキュリティ/コンプライアンス センターの組織管理の役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)」を参照してください。
    
- コンプライアンス セキュリティ フィルターのコマンドレットを使用するには、Windows PowerShell をセキュリティ/コンプライアンス センターとお客様の Exchange Online 組織の両方に接続する必要があります。 これらのコマンドレットはメールボックスのプロパティへのアクセスを必要とするため、Exchange Online に接続する必要があります。 手順については、次のセクションを参照してください。 
    
- アクセス許可の検索フィルターの詳細については、「[More information](#more-information)」セクションを参照してください。 
    
- 検索アクセス許可のフィルター処理は、非アクティブなメールボックスに適用されます。つまり、メールボックスとメールボックス コンテンツのフィルター処理を使用して、非アクティブなメールボックスを検索できるユーザーを制限することができます。 アクセス許可のフィルター処理と非アクティブなメールボックスの詳細については、「[詳細情報](#more-information)」のセクションを参照してください。 
    
-  検索アクセス許可のフィルター処理は、Exchange のパブリック フォルダーを検索できるユーザーを制限するのに使用することができません。 
    
- 組織で作成できる検索アクセス許可フィルターの数に制限はありません。 しかし、100を超える検索アクセス許可のフィルターがある場合は、検索のパフォーマンスが影響を受けます。 検索の検索アクセス許可フィルターの数を出来るだけ少なくするために、可能な限り、Exchange、SharePoint、および OneDrive のルールを 1 つのフィルターに統合するフィルターを作成するようにします。
    
## <a name="connect-to-the-security--compliance-center-and-exchange-online-in-a-single-remote-powershell-session"></a>1 つのリモート PowerShell セッションで、セキュリティ/コンプライアンス センターと Exchange Online に接続する

1. ファイル名サフィックス **. ps1**を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。 たとえば、 **ConnectEXO-CC.ps1**という名前のファイルに保存することができます。
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -AllowClobber -DisableNameChecking
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Exchange Online + Compliance Center)"
    ```

2. ローカル コンピューター上で、Windows PowerShell を開き、前の手順で作成したスクリプトが配置されているフォルダーに移動し、スクリプトを実行します。例:
    
    ```powershell
    .\ConnectEXO-CC.ps1
    ```

これが機能したかどうかを知る方法 スクリプトの実行後に、セキュリティ/コンプライアンス センターと Exchange Online からのコマンドレットは、ローカルの Windows PowerShell セッションにインポートされます。 何もエラーが表示されなければ、正常に接続されています。 クイックテストでは、セキュリティ & コンプライアンスセンターのコマンドレットと Exchange Online コマンドレットを実行します。 たとえば、 **UnifiedCompliancePrerequisite**を実行して、**メールボックスを取得**することができます。 
  
エラーが表示された場合は、次の要件を確認します。
  
- よく起きる問題がパスワードの入力ミスです。もう一度 2 つのステップを実行します。特に、ステップ 1 ではユーザー名とパスワードを慎重に入力します。
    
- 使用するアカウントに、セキュリティ/コンプライアンス センターにアクセスする権限があることを確認してください。 詳細については、｢[セキュリティ/コンプライアンス センターへのアクセス権をユーザーに付与する](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)」を参照してください。
    
- サービス拒否 (DoS) 攻撃を防止するため、セキュリティ/コンプライアンス センターに対して開かれるリモート PowerShell 接続は 3 つまでに制限されます。
    
- スクリプトを実行するには、Windows PowerShell が構成されている必要があります。 これは、接続するたびにではなく、一度だけ実行する必要があります。 Windows PowerShell で署名されたスクリプトの実行を有効にするには、管理者特権の Windows PowerShell ウィンドウ ( **[管理者として実行]** を選択すると開く Windows PowerShell ウィンドウ) で次のコマンドを実行します。

    ```powershell
    Set-ExecutionPolicy RemoteSigned
    ```

- ローカル コンピューターと Office 365 の間に TCP ポート 80 のトラフィックを開く必要があります。 このポートは多くの場合開いているはずですが、組織で厳格なインターネット アクセス ポリシーが使用されている場合は、念のために確認する必要があります。

  
## <a name="new-compliancesecurityfilter"></a>New-ComplianceSecurityFilter

**New-compliancesecurityfilter**を使用して、検索アクセス許可フィルターを作成します。 次の表では、このコマンドレットのパラメーターについて説明します。 コンプライアンス セキュリティ フィルターを作成するには、すべてのパラメーターが必要です。 
  
|**パラメーター**|**説明**|
|:-----|:-----|
| _Action_ <br/> | _Action_ パラメーターは、フィルターに適用する検索操作の種類を指定します。 可能なコンテンツ検索操作は次のとおりです。  <br/><br/> **エクスポート:** フィルターは、検索結果をエクスポートするときに適用されます。  <br/> **プレビュー:** フィルターは、検索結果をプレビューするときに適用されます。  <br/> **削除:** フィルターは、検索結果を削除するときに適用されます。  <br/> **検索:** フィルターは、検索を実行するときに適用されます。  <br/> **すべて:** フィルターは、すべての検索操作に適用されます。  <br/> |
| _FilterName_ <br/> |_FilterName_ パラメーターは、アクセス許可フィルターの名前を指定します。 この名前は、**Get ComplianceSecurityFilter**、**Set-ComplianceSecurityFilter**、および**Remove-ComplianceSecurityFilter** コマンドレットを使用する際に、フィルターを特定するために使用されます。  <br/> |
| _Filters_ <br/> | _Filters_ パラメーターはコンプライアンス セキュリティ フィルターの検索条件を指定します。 次の 3 つの異なる種類のフィルターを作成できます。  <br/><br/> **メールボックスフィルター処理:** この種類のフィルターでは、( _users_パラメーターで指定された) 割り当てられたユーザーが検索できるメールボックスを指定します。 この種類のフィルターの構文は、**Mailbox_** _MailboxPropertyName_ です。_MailboxPropertyName_ は、検索できるメールボックスの範囲を指定するために使用されるメールボックス プロパティを指定します。 たとえば、メールボックスフィルターでは、 `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` このフィルターを割り当てられたユーザーが、CustomAttribute10 プロパティに "OttawaUsers" という値を持つメールボックスのみを検索できるようにします。  <br/>  _MailboxPropertyName_ プロパティには、サポートされているフィルター可能な受信者プロパティであればどれでも使用できます。 サポートされているプロパティの一覧については、「[-RecipientFilter パラメーターのフィルター可能なプロパティ](https://go.microsoft.com/fwlink/p/?LinkId=784903)」を参照してください。  <br/><br/> **メールボックスコンテンツフィルター:** この種類のフィルターは、検索可能なコンテンツに適用されます。 これは、割り当てられたユーザーが検索できるメールボックス コンテンツを指定します。 この種類のフィルターの構文は**MailboxContent_** _searchablepropertyname: value_です。ここで、 _Searchablepropertyname_は、コンテンツ検索で指定できるキーワードクエリ言語 (kql) プロパティを指定します。 たとえば、メールボックスのコンテンツ フィルター `MailboxContent_recipients:contoso.com` は、このフィルターが割り当てられたユーザーに、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索することを許可します。  <br/>  検索可能なメッセージ プロパティの一覧は、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。 <br/> <br/> **重要:** 1つの検索フィルターに、メールボックスフィルターとメールボックスコンテンツフィルターを含めることはできません。 これらを1つのフィルターで結合するには、[フィルタリスト](#using-a-filters-list-to-combine-filter-types)を使用する必要があります。  ただし、フィルターには同じ種類のより複雑なクエリを含めることができます。 例: `"Mailbox_CustomAttribute10 -eq 'FTE' -and Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'"`  <br/><br/> **サイトおよびサイトコンテンツのフィルター処理:** 割り当てられたユーザーが検索できるサイトまたはサイトコンテンツを指定するには、次の2つの SharePoint および OneDrive for Business のサイト関連フィルターを使用できます。  <br/><br/> - **Site_** _SearchableSiteProperty_ <br/> - **SiteContent_** _SearchableSiteProperty_ <br/><br/>  これらの2つのフィルターは、互いに交換可能です。 たとえば、 `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` と `"SiteContent_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` 同じ結果が返されます。 しかし、フィルターの役割を理解するため、`Site_` を使用してサイト関連のプロパティ (サイト URL など) を指定し、`SiteContent_` を使用してコンテンツ関連のプロパティ (ドキュメントの種類など) を指定できます。 たとえば、フィルター `"Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"` は、このフィルターが割り当てられたユーザーが、https://contoso.sharepoint.com/sites/doctors サイト コレクション内のコンテンツのみを検索することを許可します。 フィルター `"SiteContent_FileExtension -eq 'docx'"` は、このフィルターが割り当てられたユーザーに、Word 文書 (Word 2007 以降) のみを検索することを許可します。  <br/><br/>  検索可能なサイト プロパティの一覧については、「[ロールされたプロパティと管理プロパティの概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)」を参照してください。 [**クエリ可能**] 列で [**はい**] とマークされているプロパティを使用して、サイトまたはサイトのコンテンツ フィルターを作成できます。  <br/><br/> **重要:** ユーザーが特定のサービスでコンテンツの場所を検索するのを明示的に禁止するには、検索アクセス許可フィルターを作成する必要があります (ユーザーが Exchange メールボックスまたは任意の SharePoint サイトを検索することを禁止するなど)。 つまり、組織内のすべての SharePoint サイトをユーザーが検索できるようにする検索権限フィルターを作成しても、そのユーザーはメールボックスを検索できてしまいます。 たとえば、sharepoint 管理者のみが SharePoint サイトを検索できるようにするには、メールボックスの検索を禁止するフィルターを作成する必要があります。 同様に、Exchange 管理者がメールボックスのみを検索できるようにするには、サイトの検索を禁止するフィルターを作成する必要があります。           |
| _Users_ <br/> |_Users_ パラメーターは、コンテンツ検索にこのフィルターを適用するユーザーを指定します。 ユーザーのエイリアスまたはプライマリ SMTP アドレスでユーザーを特定します。 カンマで区切って複数の値を指定することも、値 **All** を使用してすべてのユーザーにフィルターを割り当てることもできます。  <br/> _Users_ パラメーターを使用して、セキュリティ/コンプライアンス センターの役割グループを指定することもできます。 これにより、カスタムの役割グループを作成して、その役割グループに検索アクセス許可フィルターを割り当てることができます。 たとえば、多国籍企業の米国支社の電子情報開示管理者向けのカスタムの役割グループがあるとします。 _Users_ パラメーターを使用してこの役割グループを指定してから (役割グループの Name プロパティを使用)、_Filter_ パラメーターを使用して米国内のメールボックスのみを検索できるようにできます。  <br/> このパラメーターでは、配布グループを指定することはできません。  <br/> |
   
### <a name="using-a-filters-list-to-combine-filter-types"></a>フィルターの種類を結合するためのフィルターリストの使用

*フィルターリスト*は、メールボックスフィルターと、コンマで区切られたサイトフィルターを含むフィルターです。 フィルターリストの使用は、さまざまな種類のフィルターを組み合わせるためにサポートされている唯一の方法です。 次の例では、コンマが**メールボックス**フィルターと**サイト**フィルターを分割している点に注意してください。

```powershell
-Filters "Mailbox_CustomAttribute10 -eq 'OttawaUsers'", "Site_Path -like 'https://contoso.sharepoint.com/sites/doctors*'"
```

コンテンツ検索の実行中にフィルターリストを含むフィルターが処理されると、フィルターリストから、コンマで区切られた各フィルターに対して1つずつ、2つの検索アクセス許可フィルターが作成されます。 そのため、前の例では、1つのメールボックス検索アクセス許可フィルターと1つのサイト検索アクセス許可フィルターを作成します。 

フィルターリストを使用する代わりに、2つの個別の検索アクセス許可フィルターを作成することもできます。 そのため、前の例では、mailbox 属性に1つのフィルターを作成し、サイト属性に1つのフィルターを作成します。 どちらの場合でも、結果は同じです。 フィルターリストを使用するか、別の検索アクセス許可のフィルターを作成することは、優先度の高いものです。

フィルターリストの使用については、次の点に注意してください。

- **メールボックス**フィルターと**MailboxContent**フィルターを含むフィルターを作成するには、フィルターリストを使用する必要があります。 

- 前述したように、1つの検索権限フィルターに**サイト**と**sitecontent**内容フィルターを含めるために、フィルタリストを使用する必要はありません。 たとえば、 **-or**演算子を使用して**サイト**と**sitecontent**各フィルターを組み合わせることができます。

   ```powershell
   -Filters "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"
   ```

- フィルターリストの各コンポーネントには、複雑なフィルター構文を含めることができます。 たとえば、メールボックスフィルターとサイトフィルターに**は、-or**演算子で区切られた複数のフィルターを含めることができます。

   ```powershell
   -Filters "Mailbox_Department -eq 'CohoWinery' -or Mailbox_CustomAttribute10 -eq 'CohoUsers'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'"
   ```

## <a name="examples-of-creating-search-permissions-filters"></a>検索アクセス許可フィルターの作成例

以下に、**New-ComplianceSecurityFilter** コマンドレットを使用して検索アクセス許可フィルターを作成する例を示します。 
  
この例では、annb@contoso.com のユーザーはカナダでのメールボックスにのみ、すべてのコンテンツ検索アクションを実行できます。 このフィルターには、ISO 3166 1 からカナダの 3 桁の数値の国コードが含まれています。

```powershell
New-ComplianceSecurityFilter -FilterName CountryFilter  -Users annb@contoso.com -Filters "Mailbox_CountryCode  -eq '124'" -Action All
```

この例では、ユーザーの donh および suzanf が、CustomAttribute1 mailbox プロパティの値が ' Marketing ' であるメールボックスのみを検索できるようにします。

```powershell
New-ComplianceSecurityFilter -FilterName MarketingFilter  -Users donh,suzanf -Filters "Mailbox_CustomAttribute1  -eq 'Marketing'" -Action Search
```

この例では、"US Discovery Managers" 役割グループのメンバーが、米国内のメールボックスにのみ、すべてのコンテンツ検索アクションを実行できます。このフィルターには、ISO 3166-1 で米国を表す 3 桁の数値の国コードが含まれています。
  
```powershell
New-ComplianceSecurityFilter -FilterName USDiscoveryManagers  -Users "US Discovery Managers" -Filters "Mailbox_CountryCode  -eq '840'" -Action All
```

この例では、電子情報開示マネージャーの役割グループのメンバーが、Ottawa Users 配布グループのメンバーのメールボックスのみを検索できるようにします。 Exchange Online PowerShell の Ottawa コマンドレットは、ユーザーグループのメンバーを検索するために使用されます。
  
```powershell
$DG = Get-DistributionGroup "Ottawa Users"
```

```powershell
New-ComplianceSecurityFilter -FilterName DGFilter  -Users eDiscoveryManager -Filters "Mailbox_MemberOfGroup -eq '$($DG.DistinguishedName)'" -Action Search
```

この例では、すべてのユーザーが Executive Team 配布グループのメンバーのメールボックスからコンテンツを削除することを禁止します。 Exchange Online の PowerShell コマンドレットは、Executive チームグループのメンバーを検索するために使用されます。

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
  
この例では、2015 年中に送信されるメール メッセージに対してのみ、すべてのコンテンツ検索アクションを実行するようにユーザーを制限します。

```powershell
New-ComplianceSecurityFilter -FilterName EmailDateRestrictionFilter -Users donh@contoso.com -Filters "MailboxContent_Received -ge '01-01-2015' -and MailboxContent_Received -le '12-31-2015'" -Action All
```

前の例と同様に、この例では、ユーザーがすべてのコンテンツ検索の操作を行うことを、2015 年中のいずれかの時点で最後に変更されたドキュメントに制限しています。

```powershell
New-ComplianceSecurityFilter -FilterName DocumentDateRestrictionFilter -Users donh@contoso.com -Filters "SiteContent_LastModifiedTime -ge '01-01-2015' -and SiteContent_LastModifiedTime -le '12-31-2015'" -Action All
```

この例では、"OneDrive Discovery Managers" 役割グループのメンバーが組織のメールボックスでコンテンツ検索アクションを実施できないようにしています。 

```powershell
New-ComplianceSecurityFilter -FilterName NoEXO -Users "OneDrive Discovery Managers" -Filters "Mailbox_Alias -notlike '*'"  -Action All
```

この例では、janets または sarad で送受信された電子メールメッセージを組織内のすべてのユーザーが検索できないようにします。

```powershell
New-ComplianceSecurityFilter -FilterName NoSaraJanet -Users All -Filters "MailboxContent_Participants -notlike 'janets@contoso.onmicrosoft.com' -and MailboxContent_Participants -notlike 'sarad@contoso.onmicrosoft.com'" -Action Search
```

この例では、フィルターリストを使用して、メールボックスフィルターとサイトフィルターを結合します。

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="get-compliancesecurityfilter"></a>Get-ComplianceSecurityFilter

**Get-ComplianceSecurityFilter** はアクセス許可の検索フィルターの一覧を返すために使用します。 _FilterName_ パラメーターを使用して、特定の検索フィルターの情報を返します。 
  
## <a name="set-compliancesecurityfilter"></a>Set-ComplianceSecurityFilter

**Set-ComplianceSecurityFilter** は既存のアクセス許可の検索フィルターを変更する場合に使用します。 唯一の必須パラメーターは _FilterName_ です。 
  
|**パラメーター**|**説明**|
|:-----|:-----|
| _Action_| _Action_ パラメーターは、フィルターに適用する検索操作の種類を指定します。 可能なコンテンツ検索操作は次のとおりです。 <br/><br/> **エクスポート:** フィルターは、検索結果をエクスポートするときに適用されます。  <br/> **プレビュー:** フィルターは、検索結果をプレビューするときに適用されます。  <br/> **削除:** フィルターは、検索結果を削除するときに適用されます。  <br/> **検索:** フィルターは、検索を実行するときに適用されます。  <br/> **すべて:** フィルターは、すべての検索操作に適用されます。  <br/> |
| _FilterName_|_FilterName_ パラメーターは、アクセス許可フィルターの名前を指定します。 |
| _Filters_| _Filters_ パラメーターはコンプライアンス セキュリティ フィルターの検索条件を指定します。 2つの異なる種類のフィルターを作成できます。 <br/><br/>**メールボックスフィルター処理:** この種類のフィルターでは、( _users_パラメーターで指定された) 割り当てられたユーザーが検索できるメールボックスを指定します。 この種類のフィルターの構文は、**Mailbox_** _MailboxPropertyName_ です。_MailboxPropertyName_ は、検索できるメールボックスの範囲を指定するために使用されるメールボックス プロパティを指定します。 たとえば、メールボックスフィルターでは、 `"Mailbox_CustomAttribute10 -eq 'OttawaUsers'"` このフィルターを割り当てられたユーザーが、CustomAttribute10 プロパティに "OttawaUsers" という値を持つメールボックスのみを検索できるようにします。  _MailboxPropertyName_ プロパティには、サポートされているフィルター可能な受信者プロパティであればどれでも使用できます。 サポートされているプロパティの一覧については、「[-RecipientFilter パラメーターのフィルター可能なプロパティ](https://go.microsoft.com/fwlink/p/?LinkId=784903)」を参照してください。 <br/><br/>**メールボックスコンテンツフィルター:** この種類のフィルターは、検索可能なコンテンツに適用されます。 これは、割り当てられたユーザーが検索できるメールボックス コンテンツを指定します。 この種類のフィルターの構文は、**MailboxContent_** _SearchablePropertyName:value_ です。_SearchablePropertyName_ は、コンテンツ検索で指定できるキーワード クエリ言語 (KQL) のプロパティを指定します。 たとえば、メールボックスのコンテンツ フィルター `MailboxContent_recipients:contoso.com` は、このフィルターが割り当てられたユーザーに、contoso.com ドメイン内の受信者に送信されたメッセージのみを検索することを許可します。  検索可能なメッセージ プロパティの一覧は、「[コンテンツ検索のキーワード クエリ](keyword-queries-and-search-conditions.md)」を参照してください。 <br/><br/>**サイトおよびサイトコンテンツのフィルター処理:** 割り当てられたユーザーが検索できるサイトまたはサイトコンテンツを指定するには、次の2つの SharePoint および OneDrive for Business のサイト関連フィルターを使用できます。 <br/><br/>- **Site_** *SearchableSiteProperty* <br/>- **SiteContent**_*SearchableSiteProperty*<br/><br/>これらの2つのフィルターは、互いに交換可能です。 たとえば、 `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` と `"SiteContent_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` 同じ結果が返されます。 しかし、フィルターの役割を理解するため、`Site_` を使用してサイト関連のプロパティ (サイト URL など) を指定し、`SiteContent_` を使用してコンテンツ関連のプロパティ (ドキュメントの種類など) を指定できます。 たとえば、フィルター `"Site_Path -like 'https://contoso.spoppe.com/sites/doctors*'"` は、このフィルターが割り当てられたユーザーが、https://contoso.spoppe.com/sites/doctors サイト コレクション内のコンテンツのみを検索することを許可します。 フィルター `"SiteContent_FileExtension -eq 'docx'"` は、このフィルターが割り当てられたユーザーに、Word 文書 (Word 2007 以降) のみを検索することを許可します。  <br/><br/>検索可能なサイト プロパティの一覧については、「[ロールされたプロパティと管理プロパティの概要](https://go.microsoft.com/fwlink/p/?LinkId=331599)」を参照してください。 [**クエリ可能**] 列で [**はい**] とマークされているプロパティを使用して、サイトまたはサイトのコンテンツ フィルターを作成できます。 <br/><br/>          |
| _Users_|_Users_ パラメーターは、コンテンツ検索にこのフィルターを適用するユーザーを指定します。 これは複数値のプロパティであるため、このパラメーターを使用してユーザーまたはユーザーのグループを指定すると、既存のユーザーのリストが上書きされます。 選択したユーザーを追加および削除する構文については、次の例を参照してください。 <br/><br/>_Users_ パラメーターを使用して、セキュリティ/コンプライアンス センターの役割グループを指定することもできます。 これにより、カスタムの役割グループを作成して、その役割グループに検索アクセス許可フィルターを割り当てることができます。 たとえば、多国籍企業の米国支社の電子情報開示管理者向けのカスタムの役割グループがあるとします。 _Users_ パラメーターを使用してこの役割グループを指定してから (役割グループの Name プロパティを使用)、_Filter_ パラメーターを使用して米国内のメールボックスのみを検索できるようにできます。 <br/><br/>このパラメーターでは、配布グループを指定することはできません。 |

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

- **検索アクセス許可のフィルター処理のしくみ。** アクセス許可のフィルターは、コンテンツ検索が実行されると、検索クエリに追加されます。 アクセス許可フィルターは、 **and**ブール演算子によって検索クエリに結合されます。 たとえば、アクセス許可フィルターを使用して、Bob がワーカー配布グループのメンバーのメールボックスに対してすべての検索操作を実行できるようにします。 Bob は、検索クエリ `sender:jerry@adatum.com` を使用して、組織内のすべてのメールボックスでコンテンツ検索を実行したとします。 アクセス許可フィルターと検索クエリは論理的に**and**演算子で組み合わされているため、この検索では、jerry@adatum.com によって送信されたすべてのメッセージが、ワーカー配布グループのメンバーに返されます。 
    
- **複数の検索アクセス許可フィルターがある場合。** コンテンツ検索クエリでは、複数のアクセス許可フィルターは **OR** ブール演算子によって結合されます。 したがって、フィルターのいずれかに該当する場合に結果が返されます。 コンテンツ検索では、(**OR** 演算子によって結合された) すべてのフィルターが、**AND** 演算子によって検索クエリと結合されます。 この例では、検索フィルターを使用して、仕事仲間配布グループのメンバーのメールボックスのみを検索することができるようになります。 次に、Bob が Phil のメールボックスを検索することを防止する別のフィルターを作成します ("Mailbox_Alias -ne 'Phil'")。 また、Phil が Workers グループのメンバーであると仮定してみましょう。 Bob が組織内のすべてのメールボックスでコンテンツ検索 (前の例の) を実行すると、フィルターを適用して、Bob が Phil のメールボックスを検索できないようにした場合でも、Phil のメールボックスに対して検索結果が返されます。 これは、Bob に Workers グループを検索することを許可する最初のフィルターに該当しているからです。 また、Phil が Workers グループのメンバーであるため、Bob は Phil のメールボックスを検索できます。 
    
- **非アクティブなメールボックスで検索アクセス許可のフィルター処理は動作しますか。** はい、メールボックスとメールボックス コンテンツのフィルター処理を使用して、組織の非アクティブなメールボックスを検索できるユーザーを制限することができます。 通常のメールボックスのように、非アクティブなメールボックスは、アクセス許可のフィルターを作成するのに使用される受信者プロパティで設定する必要があります。 必要に応じて、**Get-Mailbox -InactiveMailboxOnly** コマンドを使用して非アクティブなメールボックスのプロパティを表示することができます。 詳細については、「[Office 365 の非アクティブなメールボックスの作成と管理](create-and-manage-inactive-mailboxes.md)」を参照してください。
    
- **パブリック フォルダーで検索アクセス許可のフィルター処理は動作しますか。** いいえ。 上で説明したように、検索アクセス許可のフィルター処理は、Exchange のパブリック フォルダーを検索できるユーザーを制限する目的には使用できません。 たとえば、パブリック フォルダーの場所にあるアイテムは、アクセス許可のフィルターによって、検索結果から除外することができません。 
    
- **特定のサービスのすべてのコンテンツの場所をユーザーが検索できるようにした場合、ユーザーは他のサービスのコンテンツの場所を検索できないようになりますか。** いいえ。 前述したように、検索アクセス許可フィルターを作成して、ユーザーが特定のサービスでコンテンツの場所を検索できないようにする (たとえば、ユーザーが Exchange メールボックスまたは任意の SharePoint サイトを検索するのを防ぐ) 必要があります。 つまり、組織内のすべての SharePoint サイトをユーザーが検索できるようにする検索権限フィルターを作成しても、そのユーザーはメールボックスを検索できてしまいます。 たとえば、sharepoint 管理者のみが SharePoint サイトを検索できるようにするには、メールボックスの検索を禁止するフィルターを作成する必要があります。 同様に、Exchange 管理者がメールボックスのみを検索できるようにするには、サイトの検索を禁止するフィルターを作成する必要があります。
