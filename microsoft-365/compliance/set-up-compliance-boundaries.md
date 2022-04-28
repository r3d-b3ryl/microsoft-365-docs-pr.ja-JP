---
title: 電子情報開示調査のコンプライアンス境界を設定する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: コンプライアンス境界を使用して、電子情報開示マネージャーがMicrosoft 365で検索できるユーザー コンテンツの場所を制御する論理境界を作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36a7f1e679f404a77b61c30b8efef7875558fee9
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65099193"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>電子情報開示調査のコンプライアンス境界を設定する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

この記事のガイダンスは、Microsoft Purview 電子情報開示 (Standard) または Microsoft Purview 電子情報開示 (プレミアム) を使用して調査を管理する場合に適用できます。

コンプライアンスの境界では、電子情報開示マネージャーが検索できるユーザー コンテンツの場所 (メールボックス、OneDrive アカウント、SharePoint サイトなど) を制御する組織内に論理的な境界を作成します。 また、コンプライアンス境界は、組織内の法的、人事、またはその他の調査を管理するために使用される電子情報開示ケースにアクセスできるユーザーを制御します。 コンプライアンスの境界の必要性は、多くの場合、地理的な役員や規制を尊重する必要がある複数の国内企業と、多くの場合、異なる機関に分かれている政府に必要です。 Microsoft 365では、コンプライアンスの境界は、コンテンツ検索を実行し、電子情報開示ケースで調査を管理するときに、これらの要件を満たすのに役立ちます。
  
次の図の例を使用して、コンプライアンス境界のしくみを説明します。
  
![コンプライアンスの境界は、機関へのアクセスを制御する検索アクセス許可フィルターと、電子情報開示ケースへのアクセスを制御する管理者の役割グループで構成されています。](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
この例では、Contoso LTD は、Fourth Coffee と Coho Makery という 2 つの子会社で構成される組織です。 このビジネスでは、電子情報開示マネージャーと調査担当者が、Exchangeメールボックス、OneDrive アカウント、SharePoint サイトのみを検索できる必要があります。 また、電子情報開示マネージャーと調査担当者は、自分の代理で電子情報開示ケースのみを表示でき、自分がメンバーであるケースにのみアクセスできます。 さらに、このシナリオでは、調査担当者はコンテンツの場所を保留にしたり、ケースからコンテンツをエクスポートしたりすることはできません。 コンプライアンスの境界がこれらの要件を満たす方法を次に示します。
  
- 電子情報開示の検索アクセス許可フィルター機能は、電子情報開示マネージャーと調査担当者が検索できるコンテンツの場所を制御します。 つまり、Fourth Coffee 代理店の情報開示マネージャーと調査担当者は、Fourth Coffee の子会社のコンテンツの場所のみ検索できます。 同じ制限が Coho Winery の子会社にも適用されます。

- [ロール グループ](assign-ediscovery-permissions.md#rbac-roles-related-to-ediscovery) は、コンプライアンス境界に対して次の機能を提供します。

  - Microsoft Purview コンプライアンス ポータルで電子情報開示ケースを表示できるユーザーを制御します。 つまり、電子情報開示マネージャーと調査担当者には、その機関の電子情報開示ケースのみが表示されます。

  - 電子情報開示ケースにメンバーを割り当てることができるユーザーを制御します。 つまり、電子情報開示マネージャーと調査担当者は、自分がメンバーになっているケースにのみメンバーを割り当てることができます。

  - 特定のアクセス許可を割り当てるロールを追加または削除して、メンバーが実行できる電子情報開示関連のタスクを制御します。

- 検索アクセス許可フィルターが役割グループに適用されている場合、アクションを実行するアクセス許可がロール グループに割り当てられている限り、役割グループのメンバーは次の検索関連アクションを実行できます。

  - コンテンツを検索する

  - 検索結果のプレビュー

  - 検索結果をエクスポートする

  - 検索によって返されたアイテムを消去する

コンプライアンス境界を設定するプロセスを次に示します。
  
[手順 1: 代理店を定義するユーザー属性を特定する](#step-1-identify-a-user-attribute-to-define-your-agencies)

[手順 2: 各機関の役割グループを作成する](#step-2-create-a-role-group-for-each-agency)

[手順 3: コンプライアンス境界を適用する検索アクセス許可フィルターを作成する](#step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[手順 4: 機関内調査用の電子情報開示ケースを作成する](#step-4-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>コンプライアンス境界を設定する前に

- ユーザーには、Exchange Online ライセンスが割り当てられている必要があります。 これを確認するには、PowerShell の [Get-User](/powershell/module/exchange/get-user) コマンドレットExchange Online使用します。

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>手順 1: 代理店を定義するユーザー属性を特定する

最初の手順では、代理店を定義する属性を選択します。 この属性は、この属性に特定の値が割り当てられているユーザーのコンテンツの場所のみを検索するように電子情報開示マネージャーを制限する検索アクセス許可フィルターを作成するために使用されます。 たとえば、Contoso が **Department** 属性を使用することを決定したとします。 4 番目のコーヒー子会社のユーザーに対するこの属性の値は次のようになります  `FourthCoffee`  。Coho Portfolioy 子会社のユーザーの値は `CohoWinery`. 手順 3 では、この  `attribute:value`  ペア ( *Department:FourthCoffee* など) を使用して、電子情報開示マネージャーが検索できるユーザー コンテンツの場所を制限します。 
  
コンプライアンス境界に使用できるユーザー属性の例を次に示します。
  
- Company

- CustomAttribute1 - CustomAttribute15

- 部署

- 事業所

- CountryOrRegion (2 文字の国コード)

完全な一覧については、サポートされている [メールボックス フィルター](/powershell/exchange/recipientfilter-properties#filterable-recipient-properties)の完全な一覧を参照してください。

## <a name="step-2-create-a-role-group-for-each-agency"></a>手順 2: 各機関の役割グループを作成する

次の手順では、コンプライアンス ポータルで役割グループを作成し、代理店に合わせます。 役割グループを作成するには、組み込みの電子情報開示マネージャー グループをコピーし、適切なメンバーを追加し、ニーズに当てはまらない可能性がある役割を削除することをお勧めします。 電子情報開示関連のロールの詳細については、「電子情報開示 [アクセス許可の割り当て](assign-ediscovery-permissions.md)」を参照してください。
  
役割グループを作成するには、コンプライアンス ポータルの **[アクセス許可]** ページに移動し、コンプライアンスの境界と電子情報開示ケースを使用して調査を管理する各機関の各チームの役割グループを作成します。
  
Contoso コンプライアンス境界シナリオを使用して、4 つのロール グループを作成し、それぞれに適切なメンバーを追加する必要があります。
  
- Fourth Coffee の電子情報開示マネージャー

- Fourth Coffee の調査担当者

- Coho Winery の電子情報開示マネージャー

- Coho Winery の調査担当者
  
Contoso コンプライアンス境界シナリオの要件を満たすために、調査担当者がコンテンツの場所に **保留** を配置し、ケースからコンテンツをエクスポートできないようにするために、調査担当者ロール グループからホールド ロールと **エクスポート** ロールを削除します。

> [!IMPORTANT]
> ケースのメンバーとして追加した役割グループにロールが追加または削除された場合、ロール グループはケースのメンバー (またはロール グループがメンバーである場合) として自動的に削除されます。 その理由は、ケースのメンバーに追加のアクセス許可を誤って提供しないように組織を保護するためです。 同様に、役割グループが削除された場合は、そのロール グループがメンバーであったすべてのケースから削除されます。

## <a name="step-3-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>手順 3: コンプライアンス境界を適用する検索アクセス許可フィルターを作成する

各機関の役割グループを作成したら、次の手順では、各役割グループを特定の機関に関連付け、コンプライアンス境界自体を定義する検索アクセス許可フィルターを作成します。 各機関に対して 1 つの検索アクセス許可フィルターを作成する必要があります。 セキュリティアクセス許可フィルターの作成の詳細については、「 [コンテンツ検索のアクセス許可フィルターを構成する](permissions-filtering-for-content-search.md)」を参照してください。
  
この記事のシナリオのコンプライアンス境界に使用される検索アクセス許可フィルターを作成するために使用される構文を次に示します。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "SiteContent_Path -like '<SharePointURL>' -or SiteContent_Path -like '<OneDriveURL>'"
```

コマンドの各パラメーターの説明を次に示します。
  
- `FilterName`: フィルターの名前を指定します。 フィルターが使用されている機関を記述または識別する名前を使用します。

- `Users`: このフィルターを実行する検索アクションに適用されるユーザーまたはグループを指定します。 コンプライアンス境界の場合、このパラメーターは、フィルターを作成する機関の役割グループ (手順 3 で作成した) を指定します。 これは複数値パラメーターであるため、コンマで区切って 1 つ以上のロール グループを含めることができます。

- `Filters`: フィルターの検索条件を指定します。 コンプライアンス境界の場合は、次のフィルターを定義します。 それぞれが異なるコンテンツの場所に適用されます。

  - `Mailbox`: パラメーターで定義されている役割グループが検索できるメールボックスまたはOneDrive アカウントを`Users`指定します。 このフィルターを使用すると、役割グループのメンバーは、特定の機関のメールボックスまたはOneDriveアカウントのみを検索できます。たとえば、 `"Mailbox_Department -eq 'FourthCoffee'"`

  - `SiteContent`: このフィルターには、2 つの個別のフィルターが含まれます。 1 つ目`SiteContent_Path`は、パラメーターで定義されたロール グループが検索できる、代理店内のSharePoint サイトを`Users`指定します。 たとえば、「 `SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee'` 」のように入力します。 2 番目`SiteContent_Path`のフィルター (オペレーターによって`or`最初`SiteContent_Path`のフィルターに接続) は、機関のOneDrive ドメイン (*MySite* ドメインとも呼ばれます) を指定します。 たとえば、「 `SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'` 」のように入力します。 フィルターの `Site_Path` 代わりにフィルターを `SiteContent` 使用することもできます。 フィルターと`SiteContent`フィルターは`Site`交換可能であり、この記事で説明する検索アクセス許可フィルターには影響しません。

    > [!IMPORTANT]
    > OneDriveの`SiteContent`フィルターが前の検索アクセス許可フィルターに含まれるのはなぜですか? フィルターは`Mailbox`メールボックスとOneDriveアカウントの *両方* に適用されますが、OneDrive フィルターも含めなかった場合、SharePoint フィルターを含めるとOneDrive`Site`アカウントが除外されます。 検索アクセス許可フィルターにSharePointフィルターが含まれていない場合は、メールボックス フィルターにコンプライアンス境界のスコープにOneDriveアカウントが含まれるため、別のOneDrive フィルターを含める必要はありません。 つまり、フィルターのみを`Mailbox`含む検索アクセス許可フィルターには、メールボックスとOneDriveアカウントの両方が含まれます。

Contoso のコンプライアンスの境界シナリオをサポートするために作成される2つの検索アクセス許可フィルターの例を示します。 これらの例にはいずれもコンマ区切りのフィルター リストが含まれています。メールボックスとサイトのフィルターが同じ検索アクセス許可フィルターに含まれており、コンマで区切られています。
  
### <a name="fourth-coffee"></a>4 番目のコーヒー

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

### <a name="coho-winery"></a>Coho のワイン工場

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'"
```

> [!NOTE]
> 前の例のパラメーターの `Filters` 構文には、 *フィルターの一覧* が含まれています。 フィルターリストは、メールボックス フィルターとサイト パス フィルターをコンマで区切って含むフィルターです。 前の例では、コンマが区切 `Mailbox` られ `SiteContent` 、フィルターが適用 `-Filters "Mailbox_<MailboxPropertyName>  -eq '<Value> '", "SiteContent_Path -like '<SharePointURL>' -or SiteContent_Path -like '<OneDriveURL>'"`されていることに注意してください。 電子情報開示検索の実行中にこのフィルターが処理されると、1 つのメールボックス フィルターと 1 つのSharePoint/OneDrive フィルターという 2 つの検索アクセス許可フィルターがフィルター一覧から作成されます。 フィルター リストを使用する代わりに、各機関に対して 2 つの個別の検索アクセス許可フィルターを作成します。メールボックス属性の検索アクセス許可フィルターと、SharePoint属性とサイト属性のOneDrive フィルターの 1 つ。 どちらの場合も、結果は同じになります。 フィルターリストを使用するか、個別の検索アクセス許可フィルターを作成することは好みの問題です。

### <a name="how-do-the-search-permissions-filters-work-in-this-scenario"></a>このシナリオでは、検索アクセス許可フィルターはどのように機能しますか?

このシナリオでは、各機関に対して検索アクセス許可フィルターを適用する方法を次に示します。

1. フィルターは `Mailbox` 、電子情報開示マネージャーが検索できるコンテンツの場所を定義するために最初に適用されます。 この場合、Coho Managersy 電子情報開示マネージャーは、*Department* mailbox プロパティが **FourthCoffee** の値を持つユーザーのメールボックスとOneDrive アカウントのみを検索できます。Coho Marketplace 電子情報開示マネージャーは、*Department* メールボックス プロパティに **CohoWinery** の値を持つユーザーのメールボックスとOneDrive アカウントのみを検索できます。 フィルターは `Mailbox` 、電子情報開示マネージャーが検索できるコンテンツの場所を指定するため、コンテンツの *場所フィルター* です。 どちらのフィルターでも、電子情報開示マネージャーは特定のメールボックス プロパティ値を持つコンテンツの場所のみを検索できます。

2. 検索できるコンテンツの場所が定義されると、フィルターの次の部分で電子情報開示マネージャーが検索できるコンテンツが定義されます。 最初 `SiteContent` のフィルターを使用すると、第 4 のコーヒー電子情報開示マネージャーは、サイト パス プロパティを含む (または最初から始まる) `https://contoso.sharepoint.com/sites/FourthCoffee`ドキュメントのみを検索できます。Coho Winery 電子情報開示マネージャーは、サイト パス プロパティを含む (または最初から始まる) `https://contoso.sharepoint.com/sites/CohoWinery`ドキュメントのみを検索できます。 そのため、2 つの `SiteContent` フィルターは、検索可能なコンテンツを定義するため、 *コンテンツ フィルター* です。 どちらのフィルターでも、電子情報開示マネージャーは特定のドキュメント プロパティ値を持つドキュメントのみを検索できます。 検索可能なサイト プロパティはすべてのドキュメントにスタンプされるため、SharePoint関連のすべてのフィルターはコンテンツ フィルターです。 詳細については、「 [電子情報開示のアクセス許可フィルターを構成する」を参照](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)してください。

   > [!NOTE]
   > この記事のシナリオでは使用しませんが、メールボックス コンテンツ フィルターを使用して、電子情報開示マネージャーが検索できるコンテンツを指定することもできます。 メールボックス コンテンツ フィルターの構文は次のとおりです `"MailboxContent_<property> -<comparison operator> '<value>'"`。 日付範囲、受信者、ドメイン、または検索可能な電子メール プロパティに基づいてコンテンツ フィルターを作成できます。 たとえば、このフィルターを使用すると、電子情報開示マネージャーは、contoso.com ドメイン `"MailboxContent_Participants -like 'contoso.com'"`内のユーザーが送受信したメール アイテムのみを検索できます。 メールボックス コンテンツ フィルターの詳細については、「 [検索アクセス許可フィルターの構成](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)」を参照してください。

3. 検索アクセス許可フィルターは、 **AND** ブール演算子によって検索クエリに結合されます。 つまり、いずれかの機関の電子情報開示マネージャーが電子情報開示検索を実行する場合、検索によって返されるアイテムは、検索クエリと検索アクセス許可フィルターで定義されている条件と一致する必要があります。

## <a name="step-4-create-an-ediscovery-case-for-intra-agency-investigations"></a>手順 4: 機関内調査用の電子情報開示ケースを作成する

最後の手順では、コンプライアンス ポータルで電子情報開示 (Standard) ケースまたは電子情報開示 (プレミアム) ケースを作成し、手順 2 で作成した役割グループをケースのメンバーとして追加します。 これにより、コンプライアンス境界を使用する 2 つの重要な特性が得られます。
  
- ケースに追加されたロール グループのメンバーのみが、コンプライアンス ポータルでケースを表示してアクセスできます。 たとえば、4 番目のコーヒー調査担当者の役割グループがケースの唯一のメンバーである場合、4 番目のコーヒー電子情報開示マネージャーの役割グループ (または他の役割グループのメンバー) のメンバーは、ケースを表示またはアクセスできません。

- ケースに割り当てられた役割グループのメンバーがケースに関連付けられた検索を実行すると、そのエージェント内のコンテンツの場所のみを検索できます (これは、手順 3. で作成した検索アクセス許可フィルターによって定義されます)。

ケースを作成してメンバーを割り当てるには:

1. コンプライアンス ポータルの **電子情報開示 (Standard)** または **電子情報開示 (プレミアム)** ページに移動し、ケースを作成します。

2. ケースの一覧で、作成したケースの名前をクリックします。

3. ロール グループをメンバーとしてケースに追加します。 手順については、次のいずれかの記事を参照してください。

   - [電子情報開示 (Standard) ケースにメンバーを追加する](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-ediscovery-standard-case)

   - [電子情報開示 (プレミアム) ケースにメンバーを追加する](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

> [!NOTE]
> ケースに役割グループを追加する場合は、自分がメンバーである役割グループのみを追加できます。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>複数地域環境でのコンテンツの検索とエクスポート

また、検索アクセス許可フィルターを使用すると、コンテンツをエクスポート用にルーティングする場所と、[SharePoint Multi-Geo環境](../enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)内のコンテンツの場所を検索するときにどのデータセンターを検索できるかを制御することもできます。
  
- **検索結果をエクスポートする:** 特定のデータセンターから、Exchangeメールボックス、SharePoint サイト、OneDrive アカウントから検索結果をエクスポートできます。 つまり、検索結果のエクスポート元となるデータセンターの場所を指定できます。

    **New-ComplianceSecurityFilter** コマンドレットまたは **Set-ComplianceSecurityFilter** コマンドレットの *リージョン* パラメーターを使用して、エクスポートをルーティングするデータセンターを作成または変更します。
  
    |**パラメーターの値**|**データセンターの場所**|
    |:-----|:-----|
    |NAM  <br/> |北米 (データセンターは米国内)  <br/> |
    |EUR  <br/> |ヨーロッパ  <br/> |
    |APC  <br/> |アジア太平洋  <br/> |
    |CAN <br/> |カナダ|
    |||

- **ルート コンテンツ検索:** SharePoint サイトとOneDrive アカウントのコンテンツ検索をサテライト データセンターにルーティングできます。 つまり、検索を実行するデータセンターの場所を指定できます。

    *Region* パラメーターには、次のいずれかの値を使用して、SharePoint サイトとOneDrive アカウントを検索するときに検索を実行するデータセンターの場所を制御します。
  
    |**パラメーターの値**|**SharePointのデータセンター ルーティングの場所**|
    |:-----|:-----|
    |NAM  <br/> |US  <br/> |
    |EUR  <br/> |ヨーロッパ  <br/> |
    |APC  <br/> |アジア太平洋  <br/> |
    |CAN  <br/> |US  <br/> |
    |AUS  <br/> |アジア太平洋  <br/> |
    |KOR  <br/> |組織の既定のデータセンター  <br/> |
    |GBR  <br/> |ヨーロッパ  <br/> |
    |JPN  <br/> |アジア太平洋  <br/> |
    |IND  <br/> |アジア太平洋  <br/> |
    |ラム  <br/> |US  <br/> |
    |も  <br/> |ヨーロッパ |
    |ブラジャー  <br/> |北米のデータセンター |
    |||

   検索アクセス許可フィルターの *[リージョン*] パラメーターを指定しないと、組織のプライマリ SharePoint リージョンが検索されます。 検索結果は、最も近いデータセンターにエクスポートされます。

   概念を簡略化するために、*Region* パラメーターは、SharePointおよびOneDrive内のコンテンツの検索に使用されるデータセンターを制御します。 これは、Exchange コンテンツ検索がデータセンターの地理的な場所に制限されていないため、Exchange内のコンテンツの検索には適用されません。 また、同じ *リージョン* パラメーター値によって、エクスポートのルーティング先となるデータセンターも指定される場合があります。 これは、多くの場合、地理的なボード間でのデータの移動を制御するために必要です。

> [!NOTE]
> 電子情報開示 (プレミアム) を使用している場合、*Region* パラメーターはデータのエクスポート元のリージョンを制御しません。 データは、組織の中央の場所からエクスポートされます。 また、SharePointとOneDrive内のコンテンツの検索は、データセンターの地理的な場所に制限されません。 すべてのデータセンターが検索されます。 電子情報開示 (プレミアム) の詳細については、Microsoft 365[の電子情報開示 (プレミアム) ソリューションの概要に関するページを](overview-ediscovery-20.md)参照してください。

コンプライアンス境界の検索アクセス許可フィルターを作成するときに *、Region* パラメーターを使用する例を次に示します。 これは、4 番目のコーヒー子会社が北米にあり、Coho Makery がヨーロッパにあることを前提としています。
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'" -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "SiteContent_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery' -or SiteContent_Path -like 'https://contoso-my.sharepoint.com/personal'" -Region EUR
```

複数地域環境でコンテンツを検索およびエクスポートする場合は、次の点に注意してください。
  
- Exchange メールボックスの検索は、*Region* パラメーターにより制御されません。 メールボックスを検索すると、すべてのデータセンターが検索されます。 Exchangeメールボックスの検索範囲を制限するには、検索アクセス許可フィルターを作成または変更するときに *フィルター* パラメーターを使用します。

- 電子情報開示マネージャーが複数のSharePointリージョン間で検索する必要がある場合は、その電子情報開示マネージャーが検索アクセス許可フィルターで使用する別のユーザー アカウントを作成して、SharePoint サイトまたはOneDrive アカウントが配置されているリージョンを指定する必要があります。 この設定の詳細については、[Content Search](content-search-reference.md#searching-for-content-in-a-sharepoint-multi-geo-environment) の「SharePoint Multi-Geo環境でのコンテンツの検索」セクションを参照してください。

- SharePointおよびOneDriveでコンテンツを検索する場合、*Region* パラメーターは、電子情報開示マネージャーが電子情報開示調査を行うプライマリまたはサテライトの場所に検索を指示します。 電子情報開示マネージャーが、検索アクセス許可フィルターで指定されたリージョン外のSharePointサイトとOneDrive サイトを検索する場合、検索結果は返されません。

- 電子情報開示 (Standard) から検索結果をエクスポートすると、すべてのコンテンツの場所 (Exchange、Skype for Business、SharePoint、OneDrive、コンテンツ検索ツールを使用して検索できるその他のサービスを含む) のコンテンツがAzure Storageにアップロードされます。 *Region* パラメーターで指定されたデータセンター内の場所を指定します。 これにより、組織は、制御された境界を越えてコンテンツをエクスポートできないことで、コンプライアンスを維持できます。 検索アクセス許可フィルターにリージョンが指定されていない場合、コンテンツは組織のプライマリ データセンターにアップロードされます。

  電子情報開示 (プレミアム) からコンテンツをエクスポートする場合、*Region* パラメーターを使用してコンテンツをアップロードする場所を制御することはできません。 コンテンツは、組織の中央の場所にあるデータセンター内のAzure Storageの場所にアップロードされます。 中央の場所に基づく地理的な場所の一覧については、「[複数地域の電子情報開示の構成Microsoft 365](../enterprise/multi-geo-ediscovery-configuration.md)参照してください。

- 次のコマンドを実行して、既存の検索アクセス許可フィルターを編集してリージョンを追加または変更できます。

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>SharePoint ハブ サイトのコンプライアンス境界の使用

[SharePoint ハブ サイト](/sharepoint/dev/features/hub-site/hub-site-overview)は、多くの場合、電子情報開示コンプライアンスの境界が従うのと同じ地理的または機関の境界に合わせて配置されます。 つまり、ハブ サイトのサイト ID プロパティを使用して、コンプライアンス境界を作成できます。 これを行うには、SharePoint Online PowerShell の [Get-SPOHubSite](/powershell/module/sharepoint-online/get-spohubsite#examples) コマンドレットを使用してハブ サイトの SiteId を取得し、部門 ID プロパティのこの値を使用して検索アクセス許可フィルターを作成します。

次の構文を使用して、SharePoint ハブ サイトの検索アクセス許可フィルターを作成します。

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'"
```

Coho Winery エージェンシーのハブ サイトの検索アクセス許可フィルターを作成する例を次に示します。

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'"
```

## <a name="compliance-boundary-limitations"></a>コンプライアンス境界の制限事項

コンプライアンス境界を使用する電子情報開示のケースと調査を管理する場合は、次の制限事項に留意してください。
  
- 検索を作成して実行するときに、機関以外のコンテンツの場所を選択することができます。 ただし、検索のアクセス許可フィルターがあるため、これらの場所からのコンテンツは、検索結果に含まれません。

- コンプライアンスの境界は、電子情報開示ケースの保留には適用されません。 つまり、ある機関の電子情報開示マネージャーが、保留中の別の機関にユーザーを配置することができます。 ただし、電子情報開示マネージャーが保留にされているユーザーのコンテンツの場所を検索する場合は、コンプライアンスの境界が適用されます。 つまり、電子情報開示マネージャーは、ユーザーを保留にすることはできても、ユーザーのコンテンツの場所を検索することはできません。

    また、保留リストは、機関のコンテンツの場所にのみ適用されます。

- 検索アクセス許可フィルター (メールボックスまたはサイト フィルター) が割り当てられ、組織内のすべてのSharePoint サイトを含む検索のインデックスのないアイテムをエクスポートしようとすると、次のエラー メッセージが表示`Unable to execute the task. Reason: The scope options UnindexedItemsOnly or BothIndexedandUnindexedItems are not allowed when the executing user has a compliance security filter applied`されます。 検索アクセス許可フィルターが割り当てられ、インデックスのないアイテムをSharePointからエクスポートする場合は、検索を再実行し、検索する特定のSharePoint サイトを含める必要があります。 それ以外の場合は、すべてのSharePointサイトを含む検索からインデックス付きアイテムのみをエクスポートできます。 検索結果をエクスポートするときのオプションの詳細については、「コンテンツ検索結果の [エクスポート](export-search-results.md#step-1-prepare-search-results-for-export)」を参照してください。

- 検索アクセス許可のフィルターは、Exchange のパブリックフォルダーには適用されません。

## <a name="more-information"></a>詳細

- メールボックスのライセンス解除または論理的な削除が行われると、ユーザーはコンプライアンス境界内では考慮されなくなります。 削除時にメールボックスに保留が配置された場合でも、メールボックスに保持されているコンテンツは、コンプライアンス境界または検索アクセス許可フィルターの対象となります。

- ユーザーに対してコンプライアンス境界と検索アクセス許可フィルターが実装されている場合は、ユーザーのメールボックスを削除せず、OneDrive アカウントを削除しないことをお勧めします。 つまり、ユーザーのメールボックスを削除する場合は、OneDriveの検索アクセス許可フィルターを適用するためにmailbox_RecipientFilterが使用されるため、ユーザーのOneDrive アカウントも削除する必要があります。

- コンプライアンスの境界と検索アクセス許可フィルターは、Exchange、OneDrive、SharePointのコンテンツにスタンプされている属性と、このスタンプされたコンテンツの後続のインデックス作成によって異なります。

- コンテンツ ベースのコンプライアンス境界に対して除外フィルター (検索アクセス許可フィルターでの使用など) を使用 `-not()` することはお勧めしません。 最近更新された属性を含むコンテンツにインデックスが作成されていない場合、除外フィルターを使用すると予期しない結果になることがあります。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Who (New-ComplianceSecurityFilter コマンドレットとSet-ComplianceSecurityFilter コマンドレットを使用して) 検索アクセス許可フィルターを作成および管理できますか?**
  
検索アクセス許可フィルターを作成、表示、変更するには、コンプライアンス ポータルの組織管理役割グループのメンバーである必要があります。
  
**電子情報開示マネージャーが複数の機関にまたがる複数の役割グループに割り当てられている場合、一方の機関または他の機関でコンテンツを検索するにはどうすればよいですか?**
  
電子情報開示マネージャーは、検索を特定の機関に制限するパラメーターを検索クエリに追加できます。 たとえば、組織が **CustomAttribute10** プロパティを指定して代理店を区別した場合、検索クエリに次を追加して、特定の`CustomAttribute10:<value>`機関のメールボックスとOneDrive アカウントを検索できます。
  
**検索アクセス許可フィルターのコンプライアンス属性として使用される属性の値が変更された場合はどうなりますか?**
  
フィルターで使用される属性の値が変更された場合、検索アクセス許可フィルターでコンプライアンス境界を適用するには、最大で 3 日かかります。 たとえば、Contoso のシナリオでは、4 番目のコーヒー代理店のユーザーが Coho Makery エージェンシーに転送されるとします。 その結果、ユーザー オブジェクトの **Department** 属性の値が *FourthCoffee* から *CohoWinery* に変更されます。 この状況では、4 番目のコーヒー電子情報開示と投資家は、属性が変更された後、最大 3 日間、そのユーザーの検索結果を取得します。 同様に、Coho Marketplace の電子情報開示マネージャーと調査担当者がユーザーの検索結果を取得するまでには、最大で 3 日かかります。
  
**電子情報開示マネージャーは、2 つの個別のコンプライアンス境界からコンテンツを表示できますか?**
  
はい。これは、両方の機関に対して可視性を持つ役割グループに電子情報開示マネージャーを追加することで、メールボックスExchange検索するときに実行できます。 ただし、SharePoint サイトとOneDrive アカウントを検索する場合、電子情報開示マネージャーは、機関が同じリージョンまたは地域の場所にある場合にのみ、異なるコンプライアンス境界内のコンテンツを検索できます。 **メモ：** サイトのこの制限は、電子情報開示 (プレミアム) では適用されません。これは、SharePointおよびOneDrive内のコンテンツの検索が地理的な場所によって制限されないためです。
  
**検索アクセス許可フィルターは、電子情報開示ケースホールド、Microsoft 365アイテム保持ポリシー、DLP に対して機能しますか?**
  
いいえ。現時点では不可能です。
  
**コンテンツをエクスポートする場所を制御するリージョンを指定したが、そのリージョンにSharePoint組織がない場合でも、SharePoint検索できますか?**
  
検索アクセス許可フィルターで指定されたリージョンが組織に存在しない場合は、既定のリージョンが検索されます。
  
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
