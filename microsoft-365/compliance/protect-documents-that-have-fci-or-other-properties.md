---
title: ドキュメントを保護する DLP ポリシーを作成する
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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkSPO
description: データ損失防止 (DLP) ポリシーを使用して、サード パーティのシステムからプロパティを持つドキュメントを保護する方法について説明します。
ms.openlocfilehash: 1b73f1441909c49534c17cef47804021ca2824dd
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66007264"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>FCI または他のプロパティを使用したドキュメントを保護する DLP ポリシーを作成する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview データ損失防止 (DLP) ポリシーでは、分類プロパティまたはアイテム プロパティを使用して機密アイテムを識別できます。 たとえば、次を使用できます。

- Windows サーバー ファイル分類インフラストラクチャ (FCI) プロパティ
- ドキュメント プロパティをSharePointする
- サード パーティのシステム ドキュメント プロパティ

![Office 365および外部分類システムを示す図。](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

たとえば、組織では、Windows Server FCI を使用して社会保障番号などの個人データを持つアイテムを識別し、ドキュメント内で見つかった個人データの種類と発生回数に基づいて、[**個人を特定できる情報**] プロパティを **[高**]、[**中]**、[**低**]、[**パブリック****]、または [NOT PII**] に設定してドキュメントを分類できます。

Microsoft 365では、そのプロパティが特定の値 (**High** や **Medium** など) に設定されているドキュメントを識別し、それらのファイルへのアクセスをブロックするなどのアクションを実行する DLP ポリシーを作成できます。 プロパティが [**低**] に設定されている場合には (電子メールの通知送信などの) 異なるアクションを実行する別のルールを同じポリシーに含めることができます。 このように、DLP は Windows Server FCI と統合され、Windows サーバー ベースのファイル サーバーからMicrosoft 365にアップロードまたは共有されるOfficeドキュメントを保護するのに役立ちます。

DLP ポリシーは、単に特定のプロパティ名と値のペアを検索します。 プロパティにSharePoint検索用の対応する管理プロパティがある限り、任意のドキュメント プロパティを使用できます。 たとえば、SharePoint サイト コレクションでは、**Trip Report** という名前のコンテンツ タイプと **、Customer** という名前の必須フィールドを使用する場合があります。 ユーザーが旅行レポートを作成するたびに、顧客名を入力する必要があります。 このプロパティ名と値のペアは、DLP ポリシーでも使用できます。たとえば、 **Customer** フィールドに **Contoso** が含まれている場合にゲストのドキュメントへのアクセスをブロックするルールが必要な場合などです。

特定のMicrosoft 365 ラベルを含むコンテンツに DLP ポリシーを適用する場合は、ここでの手順に従う必要はありません。 代わりに、 [DLP ポリシーでアイテム保持ラベルを条件として使用する](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)方法について説明します。

## <a name="before-you-create-the-dlp-policy"></a>DLP ポリシーを作成する前に

DLP ポリシーで Windows Server FCI プロパティまたはその他のプロパティを使用するには、<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">SharePoint管理センター</a>で管理プロパティを作成する必要があります。 その理由を次に示します。

例

> [!NOTE]
> 条件を使用して DLP ルールを作成するときは、クロールされたプロパティ名ではなく、管理プロパティ名を `ContentPropertyContainsWords` 使用してください。

DLP は検索クローラーを使用してサイト上の機密情報を識別して分類し、その機密情報を検索インデックスの安全な部分に格納するため、これは重要です。 ドキュメントをOffice 365にアップロードすると、SharePointドキュメントのプロパティに基づいてクロールされたプロパティが自動的に作成されます。 ただし、DLP ポリシーで FCI またはその他のプロパティを使用するには、そのプロパティを持つコンテンツがインデックスに保持されるように、クロールされたプロパティをマネージド プロパティにマップする必要があります。

検索プロパティと管理プロパティの詳細については、「[SharePoint Online での検索スキーマの管理](/sharepoint/manage-search-schema)」を参照してください。

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする

最初に、DLP ポリシーで参照するプロパティが含まれるドキュメントをアップロードする必要があります。 Microsoft 365はプロパティを検出し、そこからクロールされたプロパティを自動的に作成します。 次の手順では、マネージド プロパティを作成し、マネージド プロパティをこのクロールされたプロパティにマップします。

### <a name="step-2-create-a-managed-property"></a>手順 2: 管理プロパティを作成する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>にサインインします。

2. 左側のナビゲーションで、[**管理センター** \> **] SharePoint** を選択します。 これで<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">、SharePoint管理センター</a>に入るようになりました。

3. 左側のナビゲーションで、**検索管理** ページ\>の **[検索**\>スキーマの管理] で **[検索**] を選択します。

   ![管理センターの検索管理ページSharePoint表示されます。](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. [**管理プロパティ]** ページの **[新しい管理プロパティ]** を\>クリックします。

   ![[新しい管理プロパティ] ボタンが強調表示された [管理プロパティ] ページ。](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。

6. [**型**] で [**テキスト**] を選択します。

7. [**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。

8. [**クロールされたプロパティ**\>へのマッピング **] で、マッピングを追加します**。

9. [**クロールされたプロパティの選択**] ダイアログ ボックス\>で、DLP ポリシー \> OK で使用する Windows Server FCI プロパティまたはその他のプロパティに対応するクロールされたプロパティを見つけて選択 **します**。

   ![[クロールされたプロパティの選択] ダイアログ ボックス。](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. ページ \>の下部に **[OK] をクリックします**。

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する

この例では、組織は、Windows サーバー ベースのファイル サーバーで FCI を使用しています。具体的には、高、**中、****低****、****パブリック**、**および PII 以外** の可能な値を持つ **Personally Identifiable Information** という FCI 分類プロパティを使用しています。 次に、Office 365の DLP ポリシーで既存の FCI 分類を使用したいと考えています。

まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。

次に、 **ドキュメント プロパティに次のいずれかの値が含まれている** 条件を両方とも使用する 2 つのルールを持つ DLP ポリシーを作成します。

- **FCI PII コンテンツ - 高、中** 最初の規則は、FCI 分類プロパティ **[個人用識別可能な情報** ] が **[高** ] または **[中]** に等しく、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメントへのアクセスを制限します。

- **FCI PII コンテンツ - 低** 2 番目の規則は、FCI 分類プロパティ **Personally Identifiable Information** が **Low** に等しく、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメント所有者に通知を送信します。

### <a name="create-the-dlp-policy-by-using-security--compliance-powershell"></a>Security & Compliance PowerShell を使用して DLP ポリシーを作成する

**ドキュメント プロパティにこれらの値のいずれかが含まれている** 条件は、Microsoft Purview コンプライアンス ポータルでは一時的に使用できませんが、セキュリティ & コンプライアンス PowerShell では引き続きこの条件を使用できます。 コマンドレットを`New\Set\Get-DlpCompliancePolicy`使用して DLP ポリシーを操作し、パラメーターと共にコマンドレットを`New\Set\Get-DlpComplianceRule``ContentPropertyContainsWords`使用して **、ドキュメントプロパティにこれらの値のいずれかが含まれている** という条件を追加できます。

1. [セキュリティ & コンプライアンス PowerShell へのConnect](/powershell/exchange/connect-to-scc-powershell)

2. を使用してポリシーを `New-DlpCompliancePolicy`作成します。

   この PowerShell では、すべての場所に適用される DLP ポリシーが作成されます。

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. 上で説明した 2 つのルールを作成します `New-DlpComplianceRule`。ここで、1 つのルールは **Low** 値用で、もう 1 つのルールは **高** 値と **中値** 用です。

   これら 2 つのルールを作成する PowerShell の例を次に示します。 プロパティ名と値のペアは引用符で囲まれており、プロパティ名では、スペースを含まないコンマで区切られた複数の値を指定できます。たとえば、 `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Windows Server FCI には、この例で使用される **個人を特定できる情報** など、多くの組み込みプロパティが含まれています。 各プロパティで使用できる値は、組織ごとに異なる場合があります。 ここで使用する **高**、 **中**、 **低** の値は例にすぎません。 組織では、Windows サーバー FCI 分類プロパティを、Windows サーバー ベースのファイル サーバー上のファイル サーバー Resource Managerで使用可能な値で表示できます。 詳細については、「 [分類プロパティの作成](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759215(v=ws.11))」を参照してください。

完了したら、両方とも Document プロパティを使用する 2 つの新しいルールに **これらの値条件のいずれかが含まれている** ポリシーが必要です。 この条件は UI には表示されませんが、他の条件、アクション、および設定は表示されます。

1 つのルールは、[**個人情報**] プロパティが [**高**] または [**中**] の場合にコンテンツへのアクセスをブロックします。 2 番目のルールは、[**個人情報**] プロパティが [**低**] の場合にコンテンツについて通知を送信します。

![作成した 2 つのルールを示す [新しい DLP ポリシー] ダイアログ。](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>DLP ポリシーを作成した後に

前のセクションの手順を実行すると、そのプロパティを持つコンテンツを迅速に検出する DLP ポリシーが作成されます。ただし、そのコンテンツが新しくアップロードされた場合 (コンテンツのインデックスが作成されるように)、またはコンテンツが古いが編集された場合 (コンテンツのインデックスが再作成されるようにする) 場合に限られます。

対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。

> [!CAUTION]
> サイトを再インデックス付けすると、検索システムで多大な負荷が発生することがあります。 シナリオで絶対に必要な場合を除き、サイトのインデックスを再作成しないでください。

詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](/sharepoint/crawl-site-content)」を参照してください。

### <a name="reindex-a-site-optional"></a>サイトのインデックスを再作成する (省略可能)

1. サイトで、**設定** (右上の歯車アイコン) \> **サイト 設定** を選択します。

2. [ **検索**] で、[ **検索とオフライン可用性** \> **のインデックスの再作成サイト**] を選択します。

## <a name="more-information"></a>詳細情報

- [データ損失防止について](dlp-learn-about-dlp.md)

- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)

- [通知を送信して、DLP ポリシーのポリシーのヒントを表示する](use-notifications-and-policy-tips.md)

- [DLP ポリシー テンプレートに含まれるもの](what-the-dlp-policy-templates-include.md)

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
