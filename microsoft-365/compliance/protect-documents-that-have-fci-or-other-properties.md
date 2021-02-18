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
description: データ損失防止 (DLP) ポリシーを使用して、サードパーティ システムのプロパティを持つドキュメントを保護する方法について学習します。
ms.openlocfilehash: cf026e447ad1f0da3486a36dd5e36c52c09998cb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288230"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>FCI または他のプロパティを使用したドキュメントを保護する DLP ポリシーを作成する

Microsoft 365 データ損失防止 (DLP) ポリシーでは、分類プロパティまたはアイテム プロパティを使用して機密アイテムを識別できます。 たとえば、次のコマンドを使用できます。

- Windows Server ファイル分類インフラストラクチャ (FCI) のプロパティ
- SharePoint ドキュメント プロパティ
- サード パーティ製のシステム ドキュメント プロパティ

![Office 365 と外部の分類システムを示す図](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

たとえば、組織では、Windows Server FCI を使用して社会保障番号などの個人データを持つアイテムを識別し、ドキュメント内で検出された個人データの種類と出現回数に基づいて **、Personally Identifiable Information** プロパティをHigh、Moderate、Low、Public、**または** **Not PII** に設定してドキュメントを分類できます。  

Microsoft 365 では、そのプロパティが [高] や [中] などの特定の値に設定されているドキュメントを識別する DLP ポリシーを作成し、それらのファイルへのアクセスをブロックするなどのアクションを実行できます。 プロパティが [**低**] に設定されている場合には (電子メールの通知送信などの) 異なるアクションを実行する別のルールを同じポリシーに含めることができます。 これにより、DLP は Windows Server FCI と統合され、Windows Server ベースのファイル サーバーから Microsoft 365 にアップロードまたは共有された Office ドキュメントを保護できます。

DLP ポリシーは、単に特定のプロパティ名と値のペアを検索します。 プロパティに SharePoint 検索用の対応する管理プロパティがある限り、任意のドキュメント プロパティを使用できます。 たとえば、SharePoint サイト コレクションでは **、Customer** という必須フィールドを持つ Trip Report という名前のコンテンツ タイプを使用 **できます**。 旅行レポートを作成するたびに、顧客名を入力する必要があります。 このプロパティ名と値のペアは、DLP ポリシーでも使用できます。たとえば、[顧客] フィールドに **Contoso** が含まれている場合にゲストのドキュメントへのアクセスをブロックするルールが必要な場合です。

DLP ポリシーを特定の Microsoft 365 ラベルを持つコンテンツに適用する場合は、ここでの手順に従う必要はありません。 代わりに、DLP ポリシーで [保持ラベルを条件として使用する方法について学習します](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。

## <a name="before-you-create-the-dlp-policy"></a>DLP ポリシーを作成する前に

DLP ポリシーで Windows Server FCI プロパティまたは他のプロパティを使用するには、その前に、SharePoint 管理センターで管理プロパティを作成する必要があります。 その理由を次に示します。

例

> [!NOTE]
> 条件を使用して DLP ルールを作成する場合は、クロールされたプロパティ名ではなく、管理プロパティ名を使用 `ContentPropertyContainsWords` してください。

DLP は検索クローラーを使用してサイトの機密情報を識別および分類し、その機密情報を検索インデックスのセキュリティで保護された部分に格納するために重要です。 ドキュメントを Office 365 にアップロードすると、SharePoint はドキュメントプロパティに基づいてクロールされたプロパティを自動的に作成します。 ただし、DLP ポリシーで FCI または他のプロパティを使用するには、クロールされたプロパティを管理プロパティにマップして、そのプロパティを持つコンテンツがインデックスに保持される必要があります。

検索および管理プロパティの詳細については [、「SharePoint Online で検索スキーマを管理する」を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=627454)。

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする

最初に、DLP ポリシーで参照するプロパティが含まれるドキュメントをアップロードする必要があります。 Microsoft 365 はプロパティを検出し、クロールされたプロパティを自動的に作成します。 次の手順では、管理プロパティを作成し、管理プロパティをこのクロールされたプロパティにマップします。

### <a name="step-2-create-a-managed-property"></a>手順 2: 管理プロパティを作成する

1. Microsoft 365 管理センターにサインインします。

2. 左側のナビゲーションで **、[管理センター** \> **] を選択します。** SharePoint 管理センターが表示されます。

3. 左側のナビゲーションで **、[検索管理**] \> ページの [検索スキーマ **の管理** ] で \> **検索を選択します**。

   ![SharePoint 管理センターの検索管理ページ](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. [管理 **プロパティ] ページの** \> **[新しい管理プロパティ] をクリックします**。

   ![[新しい管理プロパティ] ボタンが強調表示されている[プロパティ管理] ページ](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。

6. [**型**] で [**テキスト**] を選択します。

7. [**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。

8. [ **クロールされたプロパティへのマッピング] でマッピング** \> **を追加します**。

9. [クロールされた **プロパティ** の選択] ダイアログ ボックスで、DLP ポリシー OK で使用する Windows Server FCI プロパティまたは他のプロパティに対応するクロールされたプロパティを検索して \> 選択 \> **します**。

   ![[クロールされたプロパティの選択] ダイアログ ボックス](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. At the bottom of the page \> **OK**.

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する

この例では、組織は Windows Server ベースのファイル サーバーで FCI を使用しています。具体的には、"高"、"中"、"低"、"パブリック"、および **"Not PII"** の値を持つ個人を特定できる情報という名前の FCI 分類プロパティを使用しています。    次に、既存の FCI 分類を 365 の DLP ポリシーで使用Officeしています。

まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。

次に、条件 Document プロパティに次の値が含まれる 2 つのルールを持つ DLP **ポリシーを作成します**。

- **FCI PII コンテンツ - 高、中** 最初のルールは、FCI 分類プロパティ **の個人** を特定できる情報が High または **Moderate** に等しく、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメントへのアクセスを制限します。

- **FCI PII コンテンツ - 低** 2 番目のルールは、FCI 分類プロパティの個人を特定できる情報が低で、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメント所有者に通知を送信します。

### <a name="create-the-dlp-policy-by-using-powershell"></a>PowerShell を使用して DLP ポリシーを作成する

条件 **ドキュメント プロパティ** にこれらの値が含まれている場合、セキュリティ コンプライアンス センターの UI では一時的に使用できませんが、PowerShell を使用してこの条件を &amp; 使用できます。 コマンドレットを使用して DLP ポリシーを操作し、パラメーターを指定してコマンドレットを使用して、条件 Document プロパティに次の値が含まれる条件を  `New\Set\Get-DlpCompliancePolicy`  `New\Set\Get-DlpComplianceRule`  `ContentPropertyContainsWords` **追加できます**。

これらのコマンドレットの詳細については、セキュリティ コンプライアンス センター [のコマンドレット &amp; を参照してください](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)。

1. [リモート &amp; PowerShell を使用してセキュリティ コンプライアンス センターに接続する](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. 使用してポリシーを作成します  `New-DlpCompliancePolicy` 。

この PowerShell は、すべての場所に適用される DLP ポリシーを作成します。

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. 前述の 2 つのルールを作成するには、"低" の値に対するルールと "高" と "中" の値を指定するルールを `New-DlpComplianceRule` **使用** します。  

   この 2 つのルールを作成する PowerShell の例を次に示します。 プロパティ名と値のペアは引用符で囲み、プロパティ名ではスペースを含めずに複数の値をコンマで区切って指定できます。  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Windows Server FCI には、この例で使用されている個人を特定できる情報を含む **多くの組** み込みプロパティが含まれています。 各プロパティに指定できる値は、組織ごとに異なる場合があります。 ここで **使用する高****、中**、**および低** の値は、一例にしか示されません。 組織では、Windows Server ベースのファイル サーバー上のサーバー リソース マネージャーで、Windows Server FCI 分類プロパティの値を使用して表示できます。 詳細については、「分類プロパティを [作成する」を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=627456)。

終了すると、両方とも Document プロパティを使用する 2 つの新しいルールにこれらの値の条件 **が含まれている必要** があります。 この条件は UI には表示されませんが、他の条件、アクション、設定が表示されます。

1 つのルールは、[**個人情報**] プロパティが [**高**] または [**中**] の場合にコンテンツへのアクセスをブロックします。 2 番目のルールは、[**個人情報**] プロパティが [**低**] の場合にコンテンツについて通知を送信します。

![2 つのルールが作成されたことを示す[新しい DLP ポリシー] ダイアログ ボックス](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>DLP ポリシーを作成した後に

前のセクションの手順を実行すると、そのプロパティを持つコンテンツをすばやく検出する DLP ポリシーが作成されます。ただし、そのコンテンツが新しくアップロードされた場合 (コンテンツのインデックスが作成される)、またはコンテンツが古く、編集したばかりの場合 (コンテンツのインデックスが再作成される場合のみ)。

対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。

> [!CAUTION]
> サイトを再インデックス付けすると、検索システムで多大な負荷が発生することがあります。 シナリオで本当に必要としない限り、サイトのインデックスを再作成しません。

詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](https://go.microsoft.com/fwlink/p/?LinkID=627457)」を参照してください。

### <a name="reindex-a-site-optional"></a>サイトのインデックスを再作成する (オプション)

1. On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.

2. [検索 **] で**、[検索と **オフラインの可用性] を選択します** \> **。サイトのインデックスを再作成します**。

## <a name="more-information"></a>詳細情報

- [データ損失防止ポリシーの概要](data-loss-prevention-policies.md)

- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)

- [通知を送信して、DLP ポリシーのポリシーのヒントを表示する](use-notifications-and-policy-tips.md)

- [DLP ポリシー テンプレートに含まれるもの](what-the-dlp-policy-templates-include.md)

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
