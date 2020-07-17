---
title: FCI または他のプロパティが使用されているドキュメントを保護する DLP ポリシーを作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: データ損失防止 (DLP) ポリシーを使用して、サードパーティ製システムのプロパティを持つドキュメントを保護する方法について説明します。
ms.openlocfilehash: 4db6844c6f00856de5893631058c774210344454
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818722"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>FCI または他のプロパティを使用したドキュメントを保護する DLP ポリシーを作成する

Microsoft 365 では、データ損失防止 (DLP) ポリシーを使用して機密情報を特定、監視、保護することができます。 多くの組織では、Windows Server ファイル分類インフラストラクチャ (FCI) の分類プロパティ、SharePoint のドキュメントプロパティ、またはサードパーティシステムによって適用されるドキュメントプロパティを使用して、機密情報を識別して分類するプロセスが既にあります。 これが組織を説明している場合は、Windows Server FCI または他のシステムによってドキュメントに適用されたプロパティを認識する DLP ポリシーを作成して、特定の FCI またはその他のプロパティ値を持つ Office ドキュメントに DLP ポリシーを適用できるようにすることができます。
  
![Office 365 と外部の分類システムを示す図](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)
  
たとえば、組織において、Windows Server FCI を使用して社会保障番号などの個人情報 (PII) が含まれるドキュメントを識別し、ドキュメント内で検出された個人情報の種類と検出回数に基づいて [**個人情報**] プロパティを [**高**]、[**中**]、[**低**]、[**公開**]、または [**個人情報ではない**] に設定することによってドキュメントの分類を行っている場合があります。 Microsoft 365 では、このプロパティが設定されているドキュメントを特定の値 (**高**、**中**など) に識別する DLP ポリシーを作成し、それらのファイルへのアクセスをブロックするなどの処理を実行できます。 プロパティが [**低**] に設定されている場合には (電子メールの通知送信などの) 異なるアクションを実行する別のルールを同じポリシーに含めることができます。 このようにして、DLP は Windows Server FCI と統合され、Windows Server ベースのファイルサーバーから Microsoft 365 にアップロードまたは共有される Office ドキュメントを保護するのに役立ちます。
  
DLP ポリシーは、特定のプロパティの名前と値のペアを探すだけです。対象プロパティに SharePoint 検索の対応する管理プロパティが含まれる場合には、任意のドキュメント プロパティを使用できます。たとえば、SharePoint のサイト コレクションが [**旅行レポート**] という名前のコンテンツの種類を使用し、[**顧客**] という必須フィールドが指定されているとします。ユーザーが旅行レポートを作成するたびに、顧客名を入力する必要が生じます。このプロパティの名前と値のペアを DLP ポリシーでも使用できます。たとえば、[**顧客**] フィールドに [**Contoso**] が含まれるときに外部ユーザーによるドキュメントへのアクセスをブロックするルールを作成できます。
  
特定の Microsoft 365 ラベルを含むコンテンツに DLP ポリシーを適用する場合は、ここに記載されている手順に従ってはいけないことに注意してください。 代わりに、 [DLP ポリシーの条件として保持ラベルを使用](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)する方法について説明します。
  
## <a name="before-you-create-the-dlp-policy"></a>DLP ポリシーを作成する前に

DLP ポリシーで Windows Server FCI プロパティまたは他のプロパティを使用するには、その前に、SharePoint 管理センターで管理プロパティを作成する必要があります。 理由は次のとおりです。
  
例
  
DLP は検索クローラーを使用してサイト上の機密情報を識別および分類し、その機密情報を検索インデックスのセキュリティで保護された部分に保存するため、これは重要です。 Office 365 にドキュメントをアップロードすると、SharePoint は、ドキュメントプロパティに基づいて、クロールされたプロパティを自動的に作成します。 ただし、DLP ポリシーで FCI またはその他のプロパティを使用するには、クロールされたプロパティを管理プロパティにマッピングして、そのプロパティを持つコンテンツがインデックスに保持されるようにする必要があります。
  
検索および管理プロパティの詳細については、「 [SharePoint Online で検索スキーマを管理する](https://go.microsoft.com/fwlink/p/?LinkID=627454)」を参照してください。
  
### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする

最初に、DLP ポリシーで参照するプロパティが含まれるドキュメントをアップロードする必要があります。 Microsoft 365 はプロパティを検出し、クロールされたプロパティを自動的に作成します。 次の手順では、管理プロパティを作成し、管理プロパティをこのクロールされたプロパティにマップします。
  
### <a name="step-2-create-a-managed-property"></a>手順 2: 管理プロパティを作成する

1. Microsoft 365 管理センターにサインインします。
    
2. 左側のナビゲーションで、[**管理センター** SharePoint] を選択し \> **SharePoint**ます。 SharePoint 管理センターが表示されます。
    
3. 左側のナビゲーションで、[検索管理] ページの [**検索] を選択し** \> **search administration** \> ます。**検索スキーマを管理**します。
    
    ![SharePoint 管理センターの検索管理ページ](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)
  
4. [**管理プロパティ**] ページで、 \> **新しい管理プロパティを追加**します。
    
    ![[新しい管理プロパティ] ボタンが強調表示されている[プロパティ管理] ページ](../media/b161c764-414c-4037-83ed-503a49fb4410.png)
  
5. プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。
    
6. [**型**] で [**テキスト**] を選択します。 
    
7. [**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。
    
8. [クロールされた**プロパティへのマッピング**] で \> **マッピングを追加**します。
    
9. [クロールされた**プロパティの選択**] ダイアログボックスで、 \> DLP ポリシーで使用する Windows Server fci プロパティまたはその他のプロパティに対応するクロールされたプロパティを検索して選択し \> **OK**ます。
    
    ![[クロールされたプロパティの選択] ダイアログ ボックス](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)
  
10. ページの下部にある \> **[OK] をクリック**します。
    
## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する

この例では、組織が Windows Server ベースのファイルサーバー上で FCI を使用しています。具体的には、[**高** **]、[中**]、[**低**]、[**パブリック**]、および [PII] で**はなく**、可能な値を持つ、"**個人識別情報**" という名前の fci 分類プロパティを使用しています。 ここで、Office 365 の DLP ポリシーで既存の FCI 分類を活用することを希望しています。
  
まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。
  
次に、2つのルールを使用する DLP ポリシーを作成します。両方のプロパティには、条件**ドキュメントプロパティに次のいずれかの値が含まれ**ています。
  
- **Fci PII コンテンツ-高、** 中最初のルールは、FCI 分類プロパティの個人を特定できる**情報**が**高**または**モデレート**で、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメントへのアクセスを制限します。 
    
- **Fci PII コンテンツ-低**2番目のルールは、FCI 分類プロパティの個人を特定できる**情報**が**少なく**、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメント所有者に通知を送信します。 
    
### <a name="create-the-dlp-policy-by-using-powershell"></a>PowerShell を使用して DLP ポリシーを作成する

Condition**ドキュメントプロパティにこれらの値のいずれかが含ま**れていることに注意してください。これらの値は、セキュリティコンプライアンスセンターの UI では一時的に使用できません &amp; が、PowerShell を使用してこの条件を引き続き使用することができます。 コマンドレットを使用して `New\Set\Get-DlpCompliancePolicy` DLP ポリシーを操作し、パラメーターを指定したコマンドレットを使用して、 `New\Set\Get-DlpComplianceRule` `ContentPropertyContainsWords` 条件**ドキュメントプロパティにこれらの値のいずれかを含める**ことができます。
  
これらのコマンドレットの詳細については、「[セキュリティ &amp; コンプライアンスセンターのコマンドレット](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)」を参照してください。
  
1. [&amp;リモート PowerShell を使用してセキュリティコンプライアンスセンターに接続する](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. を使用してポリシーを作成し `New-DlpCompliancePolicy` ます。

すべての場所に適用する DLP ポリシーを作成する PowerShell の例を次に示します。

```powershell
New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
```

3. 上記の2つのルールを使用して `New-DlpComplianceRule` 、1つのルールを**低**値に、もう1つは**高**および中**程度**のルールを作成します。 
    
    これら2つのルールを作成する PowerShell の例を次に示します。 プロパティ名と値のペアは二重引用符で囲まれており、プロパティ名でコンマで区切って複数の値を指定する場合は、次のようにスペースを含めません。`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

```powershell
New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
```

    Note that Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example. The possible values for each property can be different for every organization. The **High**, **Moderate**, and **Low** values used here are only an example. For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server. For more information, see [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).
    
完了したら、ドキュメントプロパティを使用する2つの新しいルールに**これらの値の条件が含まれ**ている必要があります。 この条件は UI には表示されませんが、他の条件、アクション、設定が表示されることに注意してください。
  
1 つのルールは、[**個人情報**] プロパティが [**高**] または [**中**] の場合にコンテンツへのアクセスをブロックします。 2 番目のルールは、[**個人情報**] プロパティが [**低**] の場合にコンテンツについて通知を送信します。
  
![2 つのルールが作成されたことを示す[新しい DLP ポリシー] ダイアログ ボックス](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)
  
## <a name="after-you-create-the-dlp-policy"></a>DLP ポリシーを作成した後に

前のセクションの手順を実行すると、そのプロパティを使用してコンテンツを迅速に検出する DLP ポリシーが作成されます。ただし、そのコンテンツが新しくアップロードされた場合 (コンテンツのインデックスが作成されます)、またはそのコンテンツが古く、編集された (コンテンツの再インデックスが作成される) 場合のみです。
  
対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。
  
> [!CAUTION]
> サイトを再インデックス付けすると、検索システムで多大な負荷が発生することがあります。 シナリオで絶対に必要でない限り、サイトを再インデックス化しないでください。 
  
詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](https://go.microsoft.com/fwlink/p/?LinkID=627457)」を参照してください。
  
### <a name="re-index-a-site-optional"></a>サイトを再インデックス付けする (省略可能)

1. サイトで、[**設定**] (右上にある歯車アイコン) [サイトの設定] を選択し \> **Site Settings**ます。
    
2. [**検索**] で、[**検索とオフライン可用性**インデックス作成サイト] を選択し \> **Reindex site**ます。
    
## <a name="more-information"></a>詳細情報

- [データ損失防止ポリシーの概要](data-loss-prevention-policies.md)
    
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)
    
- [通知を送信して、DLP ポリシーのポリシーのヒントを表示する](use-notifications-and-policy-tips.md)
    
- [DLP ポリシー テンプレートに含まれるもの](what-the-dlp-policy-templates-include.md)
    
- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
