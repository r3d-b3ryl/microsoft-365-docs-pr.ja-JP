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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkSPO
description: データ損失防止 (DLP) ポリシーを使用して、プロパティを持つドキュメントをサード パーティ製システムから保護する方法について学習します。
ms.openlocfilehash: 0bfb520119717d952a803e0f37fef0a1499ff0da
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312155"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>FCI または他のプロパティを使用したドキュメントを保護する DLP ポリシーを作成する

Microsoft 365データ損失防止 (DLP) ポリシーでは、分類プロパティまたはアイテム プロパティを使用して機密アイテムを識別できます。 たとえば、次のコマンドを使用できます。

- Windowsファイル分類インフラストラクチャ (FCI) プロパティ
- SharePointのプロパティ
- サード パーティ製のシステム ドキュメントのプロパティ

![外部分類システムOffice 365を示す図。](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

たとえば、Windows Server FCI を使用して、社会保障番号などの個人データを含むアイテムを識別し、ドキュメント内で見つかった個人データの種類と発生数に基づいて、個人を特定できる情報プロパティを High、**Moderate**、**Low**、**Public**、Not **PII** に設定してドキュメントを分類できます。

このMicrosoft 365、そのプロパティが High や **Medium** などの特定の値に設定されているドキュメントを識別する DLP ポリシーを作成し、それらのファイルへのアクセスをブロックするなどのアクションを実行できます。 プロパティが [**低**] に設定されている場合には (電子メールの通知送信などの) 異なるアクションを実行する別のルールを同じポリシーに含めることができます。 この方法で、DLP は Windows Server FCI と統合され、Office サーバー ベースのファイル サーバーから Microsoft 365 にアップロードまたは共有Windowsドキュメントを保護できます。

DLP ポリシーは、単に特定のプロパティ名と値のペアを検索します。 検索に対応する管理プロパティがある限り、任意の document プロパティをSharePointできます。 たとえば、サイト コレクションSharePoint、顧客という名前の必須フィールドを持つ **Trip Report** という名前のコンテンツ タイプを使用 **する場合があります**。 ユーザーが旅行レポートを作成するたびに、顧客名を入力する必要があります。 このプロパティ名と値のペアは、DLP ポリシーでも使用できます 。たとえば、[顧客] フィールドに **Contoso** が含まれている場合にゲストのドキュメントへのアクセスをブロックするルールが必要な場合などです。

DLP ポリシーを特定のラベル付きコンテンツに適用する場合Microsoft 365手順に従う必要はありません。 代わりに、DLP ポリシーでアイテム保持ラベルを条件として使用 [する方法について学習します](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。

## <a name="before-you-create-the-dlp-policy"></a>DLP ポリシーを作成する前に

DLP ポリシーで Windows Server FCI プロパティまたは他のプロパティを使用する前に、管理センターで管理プロパティをSharePoint<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">する必要があります</a>。 その理由を次に示します。

例

> [!NOTE]
> 条件を使用して DLP ルールを作成する場合は、クロールされたプロパティ名ではなく、管理プロパティ名を使用してください `ContentPropertyContainsWords` 。

DLP は検索クローラーを使用してサイトの機密情報を識別および分類し、その機密情報を検索インデックスの安全な部分に格納するために重要です。 ドキュメントをドキュメントにアップロードすると、Office 365 SharePointに基づいてクロールされたプロパティが自動的に作成されます。 ただし、DLP ポリシーで FCI または他のプロパティを使用するには、クロールされたプロパティを管理プロパティにマップして、そのプロパティを持つコンテンツをインデックスに保持する必要があります。

検索および管理プロパティの詳細については、「オンラインで検索スキーマを管理する[」をSharePointしてください](/sharepoint/manage-search-schema)。

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする

最初に、DLP ポリシーで参照するプロパティが含まれるドキュメントをアップロードする必要があります。 Microsoft 365を検出し、クロールされたプロパティを自動的に作成します。 次の手順では、管理プロパティを作成し、管理プロパティをこのクロールされたプロパティにマップします。

### <a name="step-2-create-a-managed-property"></a>手順 2: 管理プロパティを作成する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>にサインインします。

2. 左側のナビゲーションで、[管理センター **] を選択SharePoint**\>。 これで、管理センター SharePoint<a href="https://go.microsoft.com/fwlink/?linkid=2185219" target="_blank">されます</a>。

3. 左側のナビゲーションで、[検索管理] **ページ**\>の [検索スキーマ **の** 管理 **] で [**\>検索] を選択します。

   ![管理センターのSharePointページを開きます。](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. [管理プロパティ **] ページの** [新\>**しい管理プロパティ] をクリックします**。

   ![[新しい管理プロパティ] ボタンが強調表示された [管理プロパティ] ページ。](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。

6. [**型**] で [**テキスト**] を選択します。

7. [**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。

8. [ **クロールされたプロパティへのマッピング] マッピング** \> **を追加します**。

9. [クロール **されたプロパティの**\>選択] ダイアログ ボックスで、DLP ポリシー **OK** で使用する Windows Server FCI プロパティまたは他のプロパティに対応するクロールされたプロパティを検索して選択\>します。

   ![クロールされたプロパティの選択ダイアログ ボックス。](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. ページの下部で [OK] を\>**クリックします**。

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する

この例では、組織は Windows Server ベースのファイル サーバーで FCI を使用しています。具体的には、高、中、低、パブリック、および NOT **PII** の値を使用して、個人を特定できる情報という名前の FCI 分類プロパティを使用しています。  次に、既存の FCI 分類を、既存の DLP ポリシーで使用Office 365。

まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。

次に、次の 2 つのルールを使用して DLP ポリシーを作成し、 **両方とも条件 Document プロパティに次の値が含まれます**。

- **FCI PII コンテンツ - 高、中程度** 最初のルールは、FCI 分類プロパティ **[** 個人識別可能な情報] が [高] または [中程度] に等しく、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメントへのアクセスを制限します。

- **FCI PII コンテンツ - 低** 2 番目のルールは、FCI 分類プロパティ **[** 個人識別可能な情報] が **Low** に等しく、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメント所有者に通知を送信します。

### <a name="create-the-dlp-policy-by-using-powershell"></a>PowerShell を使用して DLP ポリシーを作成する

Document プロパティ **にこれらの** 値が含まれている条件は、セキュリティ コンプライアンス センターの UI &amp; では一時的に使用できませんが、PowerShell を使用してこの条件を使用できます。 コマンドレットを使用して  `New\Set\Get-DlpCompliancePolicy` DLP  `New\Set\Get-DlpComplianceRule`  `ContentPropertyContainsWords` ポリシーを操作し、パラメーターと一緒にコマンドレットを使用して、Document プロパティにこれらの値が含まれる条件 **を追加できます**。

これらのコマンドレットの詳細については、「セキュリティ コンプライアンス センター [のコマンドレット」 &amp; を参照してください](/powershell/exchange/exchange-online-powershell)。

1. [Connectセキュリティへのアクセス&amp;リモート PowerShell を使用したコンプライアンス センター](/powershell/exchange/connect-to-scc-powershell)

2. を使用してポリシーを作成します  `New-DlpCompliancePolicy`。

この PowerShell は、すべての場所に適用される DLP ポリシーを作成します。

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. 上記の 2 つのルール`New-DlpComplianceRule`を作成するには、Low 値に対して 1  つのルールを使用し、別のルールは高値と中程度の **値を****指定** します。

   これら 2 つのルールを作成する PowerShell の例を次に示します。 プロパティ名と値のペアは二重引用符で囲み、プロパティ名はスペースを使用しないコンマで区切られた複数の値を指定できます。  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Windowsサーバー FCI には、この例で使用される個人を特定できる情報を含む多くの組み込みプロパティが含まれています。 プロパティごとに使用できる値は、組織ごとに異なる場合があります。 ここで **使用する高****値、中** 程度値、および **低** 値は、一例です。 組織では、Windows Server ベースのファイル サーバー上のファイル Windows サーバー リソース マネージャーで、Windows Server FCI 分類プロパティを表示できます。 詳細については、「分類プロパティを [作成する」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759215(v=ws.11))。

完了したら、両方とも Document プロパティを使用する 2 つの新しいルールにこれらの値 **の条件が含まれている必要** があります。 この条件は UI には表示されませんが、他の条件、アクション、および設定が表示されます。

1 つのルールは、[**個人情報**] プロパティが [**高**] または [**中**] の場合にコンテンツへのアクセスをブロックします。 2 番目のルールは、[**個人情報**] プロパティが [**低**] の場合にコンテンツについて通知を送信します。

![2 つのルールが作成され、新しい DLP ポリシー ダイアログが表示されます。](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>DLP ポリシーを作成した後に

前のセクションの手順を実行すると、そのプロパティを持つコンテンツをすばやく検出する DLP ポリシーが作成されますが、そのコンテンツが新しくアップロードされた場合 (コンテンツのインデックスが作成される) 場合、またはコンテンツが古いが編集済みである場合 (コンテンツの再インデックスが作成される場合) だけです。

対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。

> [!CAUTION]
> サイトを再インデックス付けすると、検索システムで多大な負荷が発生することがあります。 シナリオで絶対に必要な場合を限り、サイトのインデックスを再設定しない。

詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](/sharepoint/crawl-site-content)」を参照してください。

### <a name="reindex-a-site-optional"></a>サイトのインデックスを再作成する (オプション)

1. サイトで、[サイト] **設定** (右上の歯車アイコン) \> **を選択設定**。

2. [検索 **] で**、[ **検索とオフラインの可用性の** \> **再インデックス サイト] を選択します**。

## <a name="more-information"></a>詳細情報

- [データ損失防止について](dlp-learn-about-dlp.md)

- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)

- [通知を送信して、DLP ポリシーのポリシーのヒントを表示する](use-notifications-and-policy-tips.md)

- [DLP ポリシー テンプレートに含まれるもの](what-the-dlp-policy-templates-include.md)

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)