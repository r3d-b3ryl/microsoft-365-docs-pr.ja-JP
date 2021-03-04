---
title: 電子情報開示調査のコンプライアンス境界を設定する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
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
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: コンプライアンス境界を使用して、電子情報開示マネージャーが Microsoft 365 で検索できるユーザー コンテンツの場所を制御する論理境界を作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: df582d46472bc7ca6d6e99e823ab94c0884d60a0
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423898"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>電子情報開示調査のコンプライアンス境界を設定する

この記事のガイダンスは、Core eDiscovery または Advanced eDiscovery を使用して調査を管理する場合に適用できます。

コンプライアンスの境界は、電子情報開示管理者が検索できるユーザー コンテンツの場所 (メールボックス、OneDrive アカウント、SharePoint サイトなど) を制御する組織内に論理的な境界を作成します。 また、コンプライアンスの境界は、組織内の法的、人事、その他の調査を管理するために使用される電子情報開示ケースにアクセスできるユーザーを制御します。 多くの場合、地理的な役員や規制を尊重する必要がある多国籍企業や、異なる機関に分かれている政府では、コンプライアンスの境界の必要性が必要です。 Microsoft 365 では、コンプライアンスの境界は、コンテンツ検索を実行し、電子情報開示ケースを使用して調査を管理する際に、これらの要件を満たすのに役立ちます。
  
次の図の例を使用して、コンプライアンスの境界がどのように機能するのか説明します。
  
![コンプライアンスの境界は、電子情報開示ケースへのアクセスを制御する機関および管理者役割グループへのアクセスを制御する検索アクセス許可フィルターで構成されます。](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
この例では、Contoso LTD は、2 つの子会社である Fourth Coffee と Coho Winery で構成される組織です。 このビジネスでは、電子情報開示の管理人と調査担当者が Exchange メールボックス、OneDrive アカウント、および SharePoint サイトのみを自分の代理店で検索できる必要があります。 また、電子情報開示マネージャーと調査担当者は、自分の代理店で電子情報開示ケースのみを表示し、自分がメンバーであるケースにのみアクセスできます。 また、このシナリオでは、調査担当者はコンテンツの場所を保留にしたり、ケースからコンテンツをエクスポートしたりすることはできません。 コンプライアンスの境界がこれらの要件を満たす方法を次に示します。
  
- コンテンツ検索の検索アクセス許可フィルター機能は、電子情報開示管理者と調査担当者が検索できるコンテンツの場所を制御します。 つまり、Fourth Coffee 代理店の情報開示マネージャーと調査担当者は、Fourth Coffee の子会社のコンテンツの場所のみ検索できます。 同じ制限が Coho Winery の子会社にも適用されます。

- 役割グループは、コンプライアンスの境界に対して次の機能を提供します。

  - セキュリティ コンプライアンス センターで電子情報開示ケースを表示できる&制御します。 つまり、電子情報開示マネージャーと調査担当者には、その機関の電子情報開示ケースのみが表示されます。

  - 電子情報開示ケースにメンバーを割り当てできるユーザーを制御します。 つまり、電子情報開示マネージャーと調査担当者は、自分がメンバーになっているケースにのみメンバーを割り当てることができます。

  - 特定のアクセス許可を割り当てる役割を追加または削除することで、メンバーが実行できる電子情報開示関連のタスクを制御します。

コンプライアンスの境界を設定するプロセスを次に示します。
  
[手順 1: 代理店を定義するユーザー属性を特定する](#step-1-identify-a-user-attribute-to-define-your-agencies)

[手順 2: Microsoft サポートに要求を送信して、ユーザー属性を OneDrive アカウントに同期させる](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[手順 3: 各機関の役割グループを作成する](#step-3-create-a-role-group-for-each-agency)

[手順 4: コンプライアンス境界を適用するための検索アクセス許可フィルターを作成する](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[手順 5: 代理店内調査用の電子情報開示ケースを作成する](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>コンプライアンスの境界を設定する前に

(手順 1) で ID である Azure Active Directory (Azure AD) 属性をユーザーの OneDrive アカウントに正常に同期する前に、次の前提条件を満たす必要があります (手順 2 で)。

- ユーザーには、Exchange Online ライセンスと SharePoint Online ライセンスが割り当てられている必要があります。

- ユーザー メールボックスのサイズは 10 MB 以上である必要があります。 ユーザーのメールボックスが 10 MB 未満の場合、代理店を定義するために使用される属性は、ユーザーの OneDrive アカウントに同期されません。

- コンプライアンスの境界と検索アクセス許可フィルターの作成に使用される属性では、Azure Active Directory (Azure AD) 属性をユーザー のメールボックスに同期する必要があります。 使用する属性が同期された状態を確認するには、Exchange Online PowerShell で [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) コマンドレットを実行します。 このコマンドレットの出力には、Exchange Online に同期された Azure AD属性が表示されます。

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>手順 1: 代理店を定義するユーザー属性を特定する

最初の手順は、代理店を定義する azure AD属性を選択します。 この属性は、この属性に特定の値が割り当てられているユーザーのコンテンツの場所のみを検索する電子情報開示マネージャーを制限する検索アクセス許可フィルターを作成するために使用されます。 たとえば、Contoso が Department 属性を使用すると **します** 。 第 4 コーヒー子会社のユーザーのこの属性の値は、Coho Winery 子会社のユーザーの値  `FourthCoffee`  になります `CohoWinery` 。 手順 4 では、このペア  `attribute:value`  ( *たとえば、Department:FourthCoffee)* を使用して、電子情報開示マネージャーが検索できるユーザー コンテンツの場所を制限します。 
  
コンプライアンスの境界に使用できる Azure ADユーザー属性の一覧を次に示します。
  
- Company

- CustomAttribute1 - CustomAttribute15

- 部署

- 事業所

- C (2 文字の国コード) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> この属性は、Exchange Online PowerShell で **Get-User** コマンドレットを実行して返される CountryOrRegion プロパティにマップされます。 このコマンドレットはローカライズされた国名を返します。これは 2 文字の国コードから翻訳されます。 詳細については [、Set-User](https://docs.microsoft.com/powershell/module/exchange/set-user) コマンドレットリファレンス記事の CountryOrRegion パラメーターの説明を参照してください。

特に Exchange メールボックスでは、より多くのユーザー属性を使用することができますが、OneDrive で現在サポートされている属性は上記の属性のみです。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>手順 2: Microsoft サポートに要求を送信して、ユーザー属性を OneDrive アカウントに同期させる

次の手順では、Microsoft サポートに要求を送信して、手順 1 で選択した Azure AD 属性を組織内のすべての OneDrive アカウントに同期します。 この同期が行われると、手順 1 で選択した属性 (とその値) は、 という名前の非表示の管理プロパティにマップされます `ComplianceAttribute` 。 この属性を使用して、手順 4 で OneDrive の検索アクセス許可フィルターを作成します。
  
Microsoft サポートに要求を送信する場合は、次の情報を含める必要があります。
  
- 組織の既定のドメイン名

- Azure AD属性の名前 (手順 1 から)

- サポート要求の目的に関する次のタイトルまたは説明: "コンプライアンス セキュリティ フィルターに対して Azure AD OneDrive for Business 同期を有効にする"。 これにより、要求を実装する電子情報開示エンジニアリング チームに要求をルーティングできます。

エンジニアリングの変更が行われた後、属性が OneDrive に同期された後、Microsoft サポートは、変更が行われたビルド番号と推定展開日を送信します。 通常、展開プロセスには、サポート要求を送信した後、4 ~ 6 週間かかります。
  
> [!IMPORTANT]
> この属性の変更を展開する前に、手順 3 ~ 手順 5 を完了できます。 ただし、コンテンツ検索を実行しても、属性の同期が展開されるまで、検索アクセス許可フィルターで指定された OneDrive アカウントのドキュメントは返されません。
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>手順 3: 各機関の役割グループを作成する

次の手順では、セキュリティ コンプライアンス センターに役割グループ&を作成し、そのグループを代理店に合わせて作成します。 役割グループを作成するには、組み込みの電子情報開示マネージャー グループをコピーし、適切なメンバーを追加し、ニーズに当てはまらない可能性がある役割を削除することをお勧めします。 電子情報開示関連の役割の詳細については、「コンプライアンス センター」の「Office [365 Security &」を参照してください](assign-ediscovery-permissions.md)。
  
役割グループを作成するには、[セキュリティ/コンプライアンス センター] の [**アクセス許可**] ページに移動し、コンプライアンスの境界と電子情報開示ケースを使用して調査を管理する各機関のチームそれぞれの役割グループを作成します。
  
Contoso コンプライアンスの境界シナリオを使用して、4 つの役割グループを作成し、それぞれに適切なメンバーを追加する必要があります。
  
- Fourth Coffee の電子情報開示マネージャー

- Fourth Coffee の調査担当者

- Coho Winery の電子情報開示マネージャー

- Coho Winery の調査担当者
  
Contoso コンプライアンス境界シナリオの要件を満たすために、調査担当者がコンテンツの場所を保留にしたり、ケースからコンテンツをエクスポートしたりするのを防ぐために、調査担当者の役割グループから保留とエクスポートの役割も削除します。

## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>手順 4: コンプライアンス境界を適用するための検索アクセス許可フィルターを作成する

各機関の役割グループを作成した後、次の手順では、各役割グループを特定の機関に関連付け、コンプライアンス境界自体を定義する検索アクセス許可フィルターを作成します。 各機関に対して 1 つの検索アクセス許可フィルターを作成する必要があります。 セキュリティアクセス許可フィルターの作成の詳細については、「コンテンツ検索のアクセス許可フィルター [の構成」を参照してください](permissions-filtering-for-content-search.md)。
  
コンプライアンスの境界に使用される検索アクセス許可フィルターの作成に使用される構文を次に示します。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

コマンドの各パラメーターの説明を次に示します。
  
- `FilterName`: フィルターの名前を指定します。 フィルターを使用する機関を説明または識別する名前を使用します。

- `Users`: このフィルターを実行するコンテンツ検索アクションに適用されるユーザーまたはグループを指定します。 コンプライアンス境界の場合、このパラメーターは、フィルターを作成する代理店の役割グループ (手順 3 で作成した) を指定します。 これは複数値パラメーターなので、1 つ以上の役割グループをコンマで区切って含めることができます。

- `Filters`: フィルターの検索条件を指定します。 コンプライアンスの境界では、次のフィルターを定義します。 それぞれがコンテンツの場所に適用されます。 

    - `Mailbox`: パラメーターで定義されている役割グループが検索できるメールボックス  `Users` を指定します。 コンプライアンス境界の場合  *、ComplianceAttribute*  は手順 1 で識別した属性と同じ属性であり  *、AttributeValue*  は代理店を指定します。 このフィルターを使用すると、役割グループのメンバーは、特定の機関のメールボックスのみを検索できます。たとえば、 `"Mailbox_Department -eq 'FourthCoffee'"` . 

    - `Site`: パラメーターで定義されている役割グループが検索できる OneDrive アカウント `Users` を指定します。 OneDrive フィルターの場合は、実際の文字列を使用します  `ComplianceAttribute` 。 これは、手順 1 で識別した属性と同じ属性にマップされ、手順 2 で送信したサポート要求の結果として OneDrive アカウントに同期されます。 *AttributeValue は*  、エージェンシーを指定します。 このフィルターを使用すると、役割グループのメンバーは、特定の機関の OneDrive アカウントのみを検索できます。たとえば、  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` .

    - `Site_Path`: パラメーターで定義されている役割グループが検索できる SharePoint  `Users` サイトを指定します。 *SharePointURL は*、役割グループのメンバーが検索できる機関内のサイトを指定します。 例: `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。 フィルターが `Site` `Site_Path` -or 演算子によって接続されていることを **確認** します。

     > [!NOTE]
     > パラメーターの構文には `Filters` 、フィルター リストが *含まれます*。 フィルター リストは、メールボックス フィルターとコンマで区切られたサイト フィルターを含むフィルターです。 前の例では、コンマが次の値と **Mailbox_ComplianceAttribute区切Site_ComplianceAttribute** 注意 **してください** `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` 。 コンテンツ検索の実行中にこのフィルターが処理されると、フィルター 一覧から 2 つの検索アクセス許可フィルター (メールボックス フィルターとサイト フィルター 1 つ) が作成されます。 フィルター リストを使用する代わりに、各機関に対して 2 つの個別の検索アクセス許可フィルターを作成します。メールボックス属性の検索アクセス許可フィルターとサイト属性のフィルターを 1 つ作成します。 どちらの場合も、結果は同じです。 フィルター リストを使用するか、個別の検索アクセス許可フィルターを作成することは、優先的な問題です。

- `Action`: フィルターが適用されるコンプライアンス検索アクションの種類を指定します。 たとえば、パラメーターで定義されている役割グループのメンバーがコンテンツ検索を実行する場合にのみ、フィルター  `-Action Search` `Users` が適用されます。 この場合、検索結果をエクスポートするときにフィルターは適用されません。 コンプライアンスの境界では、フィルター  `-Action All` がすべての検索アクションに適用されます。 

    コンテンツ検索アクションの一覧については、「コンテンツ検索のアクセス許可フィルターの構成」の「New-ComplianceSecurityFilter」 [セクションを参照してください](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)。

Contoso のコンプライアンスの境界シナリオをサポートするために作成される2つの検索アクセス許可フィルターの例を示します。 これらの例にはいずれもコンマ区切りのフィルター リストが含まれています。メールボックスとサイトのフィルターが同じ検索アクセス許可フィルターに含まれており、コンマで区切られています。
  
### <a name="fourth-coffee"></a>4 番目のコーヒー

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>Coho Winery

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>手順 5: 代理店内調査用の電子情報開示ケースを作成する

最後の手順では、Microsoft 365 コンプライアンス センターにコア電子情報開示ケースまたは Advanced eDiscovery ケースを作成し、手順 3 で作成した役割グループをケースのメンバーとして追加します。 これにより、コンプライアンスの境界を使用する 2 つの重要な特性が得られます。
  
- ケースに追加された役割グループのメンバーだけが、セキュリティ コンプライアンス センターでケースを表示&できます。 たとえば、4 番目の Coffee Investigators 役割グループがケースの唯一のメンバーである場合、4 番目のコーヒー電子情報開示マネージャー役割グループのメンバー (または他の役割グループのメンバー) はケースを表示またはアクセスできます。

- ケースに割り当てられた役割グループのメンバーがケースに関連付けられた検索を実行すると、そのユーザーは、その代理店内のコンテンツの場所のみを検索できます (手順 4 で作成した検索アクセス許可フィルターによって定義されます)。

ケースを作成してメンバーを割り当てるには、次の方法を使用します。

1. Microsoft 365 コンプライアンス センターの [コア電子 **情報開示****]** または [高度な電子情報開示] ページに移動し、ケースを作成します。

2. ケースの一覧で、作成したケースの名前をクリックします。

3. [このケース **の管理]** フライアウト ページの [ **役割グループの** 管理] で、[追加] アイコン [追加] ![ を ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **クリックします**。

    ![電子情報開示ケースのメンバーとして役割グループを追加する](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 役割グループの一覧で、手順 3 で作成した役割グループのいずれかを選択し、[追加] を **クリックします**。

5. [ **このケースの** 管理] **フライアウトで** [保存] をクリックして変更を保存します。

> [!NOTE]
> 役割グループをケースに追加する場合は、自分がメンバーである役割グループのみを追加できます。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>複数地域環境でのコンテンツの検索とエクスポート

また、検索アクセス許可フィルターを使用すると、コンテンツをエクスポート用にルーティングする場所と [、SharePoint](https://go.microsoft.com/fwlink/?linkid=860840)複数地域環境でコンテンツの場所を検索するときに検索できるデータセンターを制御することもできます。
  
- **検索結果のエクスポート:** 特定のデータセンターから、Exchange メールボックス、SharePoint サイト、および OneDrive アカウントから検索結果をエクスポートできます。 つまり、検索結果をエクスポートするデータセンターの場所を指定できます。

    エクスポートを **ルーティングする** データセンターを作成または変更するには **、New-ComplianceSecurityFilter** コマンドレットまたは **Set-ComplianceSecurityFilter** コマンドレットの Region パラメーターを使用します。
  
    |**パラメーターの値**|**データセンターの場所**|
    |:-----|:-----|
    |NAM  <br/> |北アメリカ (データセンターは米国内)  <br/> |
    |EUR  <br/> |ヨーロッパ  <br/> |
    |APC  <br/> |アジア太平洋  <br/> |
    |CAN <br/> |カナダ|
    |||

- **コンテンツ検索のルーティング:** SharePoint サイトと OneDrive アカウントのコンテンツ検索をサテライト データセンターにルーティングできます。 つまり、検索を実行するデータセンターの場所を指定できます。

    Region パラメーターには、 **次** のいずれかの値を使用して、SharePoint サイトと OneDrive アカウントの検索時に検索が実行されるデータセンターの場所を制御します。 
  
    |**パラメーターの値**|**SharePoint のデータセンタールーティングの場所**|
    |:-----|:-----|
    |NAM  <br/> |米国  <br/> |
    |EUR  <br/> |ヨーロッパ  <br/> |
    |APC  <br/> |アジア太平洋  <br/> |
    |CAN  <br/> |米国  <br/> |
    |AUS  <br/> |アジア太平洋  <br/> |
    |KOR  <br/> |組織の既定のデータセンター  <br/> |
    |GBR  <br/> |ヨーロッパ  <br/> |
    |JPN  <br/> |アジア太平洋  <br/> |
    |IND  <br/> |アジア太平洋  <br/> |
    |LAM  <br/> |米国  <br/> |
    |NOR  <br/> |ヨーロッパ |
    |BRA  <br/> |北米のデータセンター |
    |||

   検索アクセス許可フィルターに **Region** パラメーターを指定しない場合、組織のプライマリ SharePoint 領域が検索されます。 検索結果は、最も近いデータセンターにエクスポートされます。

   概念を簡略化するために **、Region** パラメーターは、SharePoint および OneDrive のコンテンツの検索に使用されるデータセンターを制御します。 Exchange コンテンツ検索はデータセンターの地理的な場所にバインドされないので、これは Exchange でのコンテンツの検索には適用されません。 また、同じ **Region** パラメーター値によって、エクスポートがルーティングされるデータセンターが決まる場合もあります。 これは、地理的なボードをまたがってデータの動きを制御するために必要な場合が多い。

> [!NOTE]
> 高度な電子情報開示を使用している場合 **、Region** パラメーターはデータのエクスポート地域を制御できません。 データは、組織のプライマリ データセンターからエクスポートされます。 また、SharePoint と OneDrive でコンテンツを検索する場合は、データセンターの地理的な場所にバインドされる必要があります。 すべてのデータセンターが検索されます。 高度な電子情報開示の詳細については [、「Microsoft 365](overview-ediscovery-20.md)の高度な電子情報開示ソリューションの概要」を参照してください。

コンプライアンス境界の検索アクセス許可フィルターを作成 **するときに Region** パラメーターを使用する例を次に示します。 これは、4 番目のコーヒー子会社が北アメリカにあり、Coho Winery がヨーロッパにあると仮定します。 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

複数地域環境でコンテンツを検索およびエクスポートする場合は、次のことを念頭に置いておきます。
  
- Exchange メールボックスの検索は、**Region** パラメーターにより制御されません。 メールボックスを検索すると、すべてのデータセンターが検索されます。 検索対象の Exchange メールボックスの範囲を制限するには、検索アクセス許可フィルターを作成または変更するときに **Filters** パラメーターを使用します。 

- 電子情報開示マネージャーが複数の SharePoint 地域間で検索する必要がある場合は、その電子情報開示マネージャーが検索アクセス許可フィルターで使用する別のユーザー アカウントを作成して、SharePoint サイトまたは OneDrive アカウントがある地域を指定する必要があります。 この設定の詳細については、「コンテンツ検索」の「SharePoint 複数地域環境でコンテンツを検索する」セクション [を参照してください](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)。

- SharePoint および OneDrive でコンテンツを検索する場合 **、Region** パラメーターは、電子情報開示マネージャーが電子情報開示調査を行うプライマリまたはサテライトの場所に検索を指示します。 電子情報開示マネージャーが、検索アクセス許可フィルターで指定されている地域外の SharePoint サイトと OneDrive サイトを検索した場合、検索結果は返されません。

- 検索結果をエクスポートする場合、すべてのコンテンツの場所 (Exchange、Skype for Business、SharePoint、OneDrive、およびコンテンツ検索ツールを使用して検索できるその他のサービスを含む) のコンテンツが **、Region** パラメーターで指定されたデータセンター内の Azure Storage の場所にアップロードされます。 これにより、組織は、管理された境界を越えてコンテンツをエクスポートすることを許可しない方法でコンプライアンスを遵守できます。 検索アクセス許可フィルターで地域が指定されていない場合、コンテンツは組織のプライマリ データセンターにアップロードされます。

- 次のコマンドを実行して、既存の検索アクセス許可フィルターを編集して地域を追加または変更できます。

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>SharePoint ハブ サイトのコンプライアンス境界の使用

[SharePoint ハブ サイトは、](https://docs.microsoft.com/sharepoint/dev/features/hub-site/hub-site-overview) 多くの場合、電子情報開示のコンプライアンスの境界に従うのと同じ地理的または機関の境界と一致します。 つまり、ハブ サイトのサイト ID プロパティを使用してコンプライアンス境界を作成できます。 これを行うには、SharePoint Online PowerShell の [Get-SPOHubSite](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spohubsite#examples) コマンドレットを使用してハブ サイトの SiteId を取得し、部門 ID プロパティにこの値を使用して検索アクセス許可フィルターを作成します。

SharePoint ハブ サイトの検索アクセス許可フィルターを作成するには、次の構文を使用します。

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

Coho ワイナリー代理店のハブ サイトの検索アクセス許可フィルターを作成する例を次に示します。

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>コンプライアンス境界の制限

コンプライアンスの境界を使用する電子情報開示ケースと調査を管理する場合は、次の制限事項に注意してください。
  
- 検索を作成して実行するときに、機関以外のコンテンツの場所を選択することができます。 ただし、検索のアクセス許可フィルターがあるため、これらの場所からのコンテンツは、検索結果に含まれません。

- コンプライアンスの境界は、電子情報開示ケースのホールドには適用されません。 つまり、ある機関の電子情報開示マネージャーが、保留中の別の機関にユーザーを配置することができます。 ただし、電子情報開示マネージャーが保留にされているユーザーのコンテンツの場所を検索する場合は、コンプライアンスの境界が適用されます。 つまり、電子情報開示マネージャーは、ユーザーを保留にすることはできても、ユーザーのコンテンツの場所を検索することはできません。

    また、保留リストは、機関のコンテンツの場所にのみ適用されます。

- 検索アクセス許可のフィルターは、Exchange のパブリックフォルダーには適用されません。

## <a name="more-information"></a>詳細情報

- メールボックスのライセンスが無効または削除された場合、Azure AD属性はメールボックスに同期されなくなりました。 メールボックスが削除された際に保持がメールボックスに配置された場合でも、メールボックスに保持されているコンテンツは、メールボックスが削除される前に Azure AD 属性が最後に同期された時刻に基づいて、コンプライアンス境界または検索アクセス許可フィルターの対象になります。 

    さらに、ユーザーのメールボックスと OneDrive アカウントの間の同期は、メールボックスのライセンスが削除またはソフト削除された場合に停止します。 OneDrive アカウントのコンプライアンス属性の最後のスタンプ値は有効なままです。

- コンプライアンス属性は、ユーザーの Exchange メールボックスから OneDrive アカウントに 7 日ごとに同期されます。 前に述べたように、この同期は、ユーザーが Exchange Online ライセンスと SharePoint Online ライセンスの両方を割り当て、ユーザーのメールボックスが 10 MB 以上である場合にのみ発生します。

- ユーザーのメールボックスと OneDrive アカウントの両方に対してコンプライアンスの境界と検索アクセス許可フィルターが実装されている場合は、OneDrive アカウントではなく、ユーザーのメールボックスを削除することをお勧めします。 つまり、ユーザーのメールボックスを削除する場合は、ユーザーの OneDrive アカウントも削除する必要があります。

- ユーザーが 2 つ以上の OneDrive アカウントを持つ可能性がある状況 (戻り従業員など) があります。 このような場合、Azure アカウントのユーザーに関連付けられたプライマリ OneDrive アカウントAD同期されます。

- コンプライアンスの境界と検索アクセス許可フィルターは、Exchange、OneDrive、および SharePoint のコンテンツにスタンプされる属性と、このスタンプされたコンテンツの後続のインデックスによって異なっています。 

- コンテンツ ベースのコンプライアンス境界に除外フィルター (検索アクセス許可フィルターでの使用など) を使用することは `-not()` お勧めしません。 最近更新された属性を持つコンテンツにインデックスが作成されていない場合、除外フィルターを使用すると予期しない結果になる可能性があります。 

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**検索アクセス許可フィルターを作成および管理できるユーザー (New-ComplianceSecurityFilterコマンドレットSet-ComplianceSecurityFilter)**
  
検索アクセス許可フィルターを作成、表示、および変更するには、セキュリティ コンプライアンス センターの組織の管理役割グループの&必要があります。
  
**複数の機関にまたがる複数の役割グループに電子情報開示マネージャーが割り当てられている場合、ある機関または他の機関のコンテンツを検索する方法を説明します。**
  
電子情報開示マネージャーは、検索を特定の機関に制限するパラメーターを検索クエリに追加できます。 たとえば、組織が代理店を区別するために **CustomAttribute10** プロパティを指定した場合、検索クエリに次の情報を追加して、特定の機関のメールボックスと OneDrive アカウントを検索できます。 `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`
  
**検索アクセス許可フィルターでコンプライアンス属性として使用される属性の値が変更された場合は、どうなるでしょうか。**
  
フィルターで使用される属性の値が変更された場合、検索アクセス許可フィルターがコンプライアンス境界を適用するのに最大 3 日かかる。 たとえば、Contoso のシナリオでは、第 4 コーヒー機関のユーザーが Coho ワイナリー代理店に転送されたとします。 その結果、ユーザー オブジェクトの **Department** 属性の値が *FourthCoffee* から *CohoWinery に変更されます*。 この状況では、属性が変更された後、4 番目のコーヒー電子情報開示と投資家は、そのユーザーの検索結果を最大 3 日間取得します。 同様に、Coho Winery の電子情報開示マネージャーと調査担当者がユーザーの検索結果を取得するには、最大 3 日かかる。
  
**電子情報開示マネージャーは、2 つの個別のコンプライアンス境界からのコンテンツを表示できますか?**
  
はい、これは、両方の機関に対して可視性を持つ役割グループに電子情報開示マネージャーを追加することで、Exchange メールボックスを検索するときに実行できます。 ただし、SharePoint サイトと OneDrive アカウントを検索する場合、電子情報開示マネージャーは、機関が同じ地域または地理的な場所にある場合にのみ、異なるコンプライアンス境界内のコンテンツを検索できます。 **注:** SharePoint と OneDrive でコンテンツを検索しても地理的な場所にバインドされないので、サイトのこの制限は Advanced eDiscovery では適用されません。
  
**検索アクセス許可フィルターは、電子情報開示ケースホールド、Microsoft 365 アイテム保持ポリシー、または DLP で機能しますか?**
  
いいえ、現時点ではそうではありません。
  
**コンテンツのエクスポート先を制御する領域を指定したが、その地域に SharePoint 組織が存在しない場合でも、SharePoint を検索できますか?**
  
検索アクセス許可フィルターで指定された地域が組織に存在しない場合、既定の地域が検索されます。
  
**組織で作成できる検索アクセス許可フィルターの最大数は何ですか?**
  
組織で作成できる検索アクセス許可フィルターの数に制限はありません。 ただし、検索アクセス許可フィルターが 100 個以上ある場合、検索のパフォーマンスに影響を与えます。 組織内の検索アクセス許可フィルターの数を可能な限り小さくするには、Exchange、SharePoint、および OneDrive のルールを組み合わせて、可能な限り 1 つの検索アクセス許可フィルターにフィルターを作成します。
