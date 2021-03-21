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
description: データ損失防止 (DLP) ポリシーを使用して、プロパティを持つドキュメントをサード パーティ製システムから保護する方法について学習します。
ms.openlocfilehash: 2d66a0a863b2076044a5c1d1cb9c3d4e8c29a186
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925563"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="dc809-103">FCI または他のプロパティを使用したドキュメントを保護する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="dc809-103">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="dc809-104">Microsoft 365 データ損失防止 (DLP) ポリシーでは、分類プロパティまたはアイテム プロパティを使用して機密アイテムを識別できます。</span><span class="sxs-lookup"><span data-stu-id="dc809-104">Microsoft 365 data loss prevention (DLP) policies can use classification properties or item properties to identify sensitive items.</span></span> <span data-ttu-id="dc809-105">たとえば、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc809-105">For example you can use:</span></span>

- <span data-ttu-id="dc809-106">Windows Server ファイル分類インフラストラクチャ (FCI) プロパティ</span><span class="sxs-lookup"><span data-stu-id="dc809-106">Windows Server File Classification infrastructure (FCI) properties</span></span>
- <span data-ttu-id="dc809-107">SharePoint ドキュメントのプロパティ</span><span class="sxs-lookup"><span data-stu-id="dc809-107">SharePoint document properties</span></span>
- <span data-ttu-id="dc809-108">サード パーティ製のシステム ドキュメントのプロパティ</span><span class="sxs-lookup"><span data-stu-id="dc809-108">third-party system document properties</span></span>

![Office 365 と外部の分類システムを示す図](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

<span data-ttu-id="dc809-110">たとえば、組織では、Windows Server FCI を使用して社会保障番号などの個人データを含むアイテムを識別し、ドキュメント内で見つかった個人データの種類と発生数に基づいて、個人を特定できる情報プロパティを High、Moderate、Low、Public、または Not **PII** に設定してドキュメントを分類できます。   </span><span class="sxs-lookup"><span data-stu-id="dc809-110">For example, your organization might use Windows Server FCI to identify items with personal data such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of personal data found in the document.</span></span>

<span data-ttu-id="dc809-111">Microsoft 365 では、そのプロパティが High や **Medium** などの特定の値に設定されているドキュメントを識別する DLP ポリシーを作成し、それらのファイルへのアクセスをブロックするなどのアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc809-111">In Microsoft 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="dc809-112">プロパティが [**低**] に設定されている場合には (電子メールの通知送信などの) 異なるアクションを実行する別のルールを同じポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="dc809-112">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="dc809-113">これにより、DLP は Windows Server FCI と統合され、Windows Server ベースのファイル サーバーから Microsoft 365 にアップロードまたは共有された Office ドキュメントを保護できます。</span><span class="sxs-lookup"><span data-stu-id="dc809-113">In this way, DLP integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Microsoft 365 from Windows Server-based file servers.</span></span>

<span data-ttu-id="dc809-114">DLP ポリシーは、単に特定のプロパティ名と値のペアを検索します。</span><span class="sxs-lookup"><span data-stu-id="dc809-114">A DLP policy simply looks for a specific property name/value pair.</span></span> <span data-ttu-id="dc809-115">SharePoint 検索に対応する管理プロパティがある限り、任意の document プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc809-115">Any document property can be used, as long as the property has a corresponding managed property for SharePoint search.</span></span> <span data-ttu-id="dc809-116">たとえば、SharePoint サイト コレクションは、Customer という名前の必須フィールドを持つ **Trip Report** という名前のコンテンツ タイプを使用 **する場合があります**。</span><span class="sxs-lookup"><span data-stu-id="dc809-116">For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**.</span></span> <span data-ttu-id="dc809-117">ユーザーが旅行レポートを作成するたびに、顧客名を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc809-117">Whenever a person creates a trip report, they must enter the customer name.</span></span> <span data-ttu-id="dc809-118">このプロパティ名と値のペアは、DLP ポリシーでも使用できます。たとえば、[顧客] フィールドに Contoso が含まれている場合にゲストのドキュメントへのアクセスをブロックするルールが必要な場合 **など** です。</span><span class="sxs-lookup"><span data-stu-id="dc809-118">This property name/value pair can also be used in a DLP policy—for example, if you want a rule that blocks access to the document for guests when the **Customer** field contains **Contoso**.</span></span>

<span data-ttu-id="dc809-119">特定の Microsoft 365 ラベルを持つコンテンツに DLP ポリシーを適用する場合は、ここでの手順に従う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dc809-119">If you want to apply your DLP policy to content with specific Microsoft 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="dc809-120">代わりに、DLP ポリシーで [アイテム保持ラベルを条件として使用する方法について学習します](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)。</span><span class="sxs-lookup"><span data-stu-id="dc809-120">Instead, learn how to [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="dc809-121">DLP ポリシーを作成する前に</span><span class="sxs-lookup"><span data-stu-id="dc809-121">Before you create the DLP policy</span></span>

<span data-ttu-id="dc809-122">DLP ポリシーで Windows Server FCI プロパティまたは他のプロパティを使用するには、その前に、SharePoint 管理センターで管理プロパティを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc809-122">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="dc809-123">その理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc809-123">Here's why.</span></span>

<span data-ttu-id="dc809-p106">例</span><span class="sxs-lookup"><span data-stu-id="dc809-p106">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>

> [!NOTE]
> <span data-ttu-id="dc809-131">条件を使用して DLP ルールを作成する場合は、クロールされたプロパティ名ではなく、管理プロパティ名を使用 `ContentPropertyContainsWords` してください。</span><span class="sxs-lookup"><span data-stu-id="dc809-131">Be sure to use a managed property name and not a crawled property name when creating DLP rules using the `ContentPropertyContainsWords` condition.</span></span>

<span data-ttu-id="dc809-132">DLP は検索クローラーを使用してサイトの機密情報を識別および分類し、その機密情報を検索インデックスの安全な部分に格納するために重要です。</span><span class="sxs-lookup"><span data-stu-id="dc809-132">This is important because DLP uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index.</span></span> <span data-ttu-id="dc809-133">ドキュメントを 365 から 365 にアップロードOffice SharePoint は、ドキュメントのプロパティに基づいてクロールされたプロパティを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="dc809-133">When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties.</span></span> <span data-ttu-id="dc809-134">ただし、DLP ポリシーで FCI または他のプロパティを使用するには、クロールされたプロパティを管理プロパティにマップして、そのプロパティを持つコンテンツをインデックスに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc809-134">But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>

<span data-ttu-id="dc809-135">検索プロパティと管理プロパティの詳細については [、「SharePoint Online で検索スキーマを管理する」を参照してください](/sharepoint/manage-search-schema)。</span><span class="sxs-lookup"><span data-stu-id="dc809-135">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](/sharepoint/manage-search-schema).</span></span>

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="dc809-136">手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする</span><span class="sxs-lookup"><span data-stu-id="dc809-136">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="dc809-137">最初に、DLP ポリシーで参照するプロパティが含まれるドキュメントをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc809-137">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="dc809-138">Microsoft 365 はプロパティを検出し、クロールされたプロパティを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="dc809-138">Microsoft 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="dc809-139">次の手順では、管理プロパティを作成し、管理プロパティをこのクロールされたプロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="dc809-139">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>

### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="dc809-140">手順 2: 管理プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="dc809-140">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="dc809-141">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="dc809-141">Sign in to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="dc809-142">左側のナビゲーションで、[管理センター \> **SharePoint] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc809-142">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="dc809-143">SharePoint 管理センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc809-143">You're now in the SharePoint admin center.</span></span>

3. <span data-ttu-id="dc809-144">左側のナビゲーションで、[検索管理] **ページ** \> の [ **検索スキーマの** 管理 \> **] で [検索] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc809-144">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>

   ![SharePoint 管理センターの検索管理ページ](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. <span data-ttu-id="dc809-146">[管理プロパティ **] ページの** [ \> **新しい管理プロパティ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc809-146">On the **Managed Properties** page \> **New Managed Property**.</span></span>

   ![[新しい管理プロパティ] ボタンが強調表示されている[プロパティ管理] ページ](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. <span data-ttu-id="dc809-p110">プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc809-p110">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>

6. <span data-ttu-id="dc809-150">[**型**] で [**テキスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc809-150">For **Type**, choose **Text**.</span></span>

7. <span data-ttu-id="dc809-151">[**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dc809-151">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>

8. <span data-ttu-id="dc809-152">[ **クロールされたプロパティへのマッピング] マッピング** \> **を追加します**。</span><span class="sxs-lookup"><span data-stu-id="dc809-152">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>

9. <span data-ttu-id="dc809-153">[クロール **されたプロパティの選択**] ダイアログ ボックスで、DLP ポリシーで使用する Windows Server FCI プロパティまたは他のプロパティに対応するクロールされたプロパティを検索して \> 選択 \> **します。**</span><span class="sxs-lookup"><span data-stu-id="dc809-153">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>

   ![[クロールされたプロパティの選択] ダイアログ ボックス](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. <span data-ttu-id="dc809-155">ページの下部で \> **[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dc809-155">At the bottom of the page \> **OK**.</span></span>

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="dc809-156">FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="dc809-156">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="dc809-157">この例では、組織は Windows Server ベースのファイル サーバーで FCI を使用しています。具体的には、高、中程度、低、パブリック、およびNOT PII の可能な値を持つ、個人を特定できる情報という名前の FCI 分類プロパティを **使用しています**。  </span><span class="sxs-lookup"><span data-stu-id="dc809-157">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="dc809-158">次に、365 の DLP ポリシーで既存の FCI 分類Officeしています。</span><span class="sxs-lookup"><span data-stu-id="dc809-158">Now they want to use their existing FCI classification in their DLP policies in Office 365.</span></span>

<span data-ttu-id="dc809-159">まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="dc809-159">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>

<span data-ttu-id="dc809-160">次に、次の 2 つのルールを使用して DLP ポリシーを作成し、 **両方とも条件 Document プロパティに次の値が含まれます**。</span><span class="sxs-lookup"><span data-stu-id="dc809-160">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>

- <span data-ttu-id="dc809-161">**FCI PII コンテンツ - 高、中程度** 最初のルールは、FCI 分類プロパティ **[** 個人識別可能な情報] が [高]または [中程度] に等しく、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="dc809-161">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span>

- <span data-ttu-id="dc809-162">**FCI PII コンテンツ - 低** 2 番目のルールは、FCI 分類プロパティ **[** 個人識別可能な情報] が **Low** に等しく、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメント所有者に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="dc809-162">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span>

### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="dc809-163">PowerShell を使用して DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="dc809-163">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="dc809-164">Document プロパティ **にこれらの** 値が含まれている条件は、セキュリティ コンプライアンス センターの UI では一時的に使用できませんが、PowerShell を使用してこの条件 &amp; を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc809-164">The condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="dc809-165">コマンドレットを使用して DLP ポリシーを操作し、パラメーターと一緒にコマンドレットを使用して、Document プロパティにこれらの値が含まれる条件  `New\Set\Get-DlpCompliancePolicy`  `New\Set\Get-DlpComplianceRule`  `ContentPropertyContainsWords` **を追加できます**。</span><span class="sxs-lookup"><span data-stu-id="dc809-165">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>

<span data-ttu-id="dc809-166">これらのコマンドレットの詳細については [、「Security Compliance &amp; Center コマンドレット」を参照してください](/powershell/exchange/exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="dc809-166">For more information on these cmdlets, see [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell).</span></span>

1. [<span data-ttu-id="dc809-167">リモート PowerShell を使用 &amp; してセキュリティ コンプライアンス センターに接続する</span><span class="sxs-lookup"><span data-stu-id="dc809-167">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="dc809-168">を使用してポリシーを作成します  `New-DlpCompliancePolicy` 。</span><span class="sxs-lookup"><span data-stu-id="dc809-168">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>

<span data-ttu-id="dc809-169">この PowerShell は、すべての場所に適用される DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc809-169">This PowerShell creates a DLP policy that applies to all locations.</span></span>

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. <span data-ttu-id="dc809-170">上記の 2 つのルールを作成するには、Low 値に対して 1 つのルールを使用し、別のルールは高値と中程度の値 `New-DlpComplianceRule` を **指定** します。  </span><span class="sxs-lookup"><span data-stu-id="dc809-170">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span>

   <span data-ttu-id="dc809-171">これら 2 つのルールを作成する PowerShell の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dc809-171">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="dc809-172">プロパティ名と値のペアは二重引用符で囲み、プロパティ名はスペースを使用しないコンマで区切られた複数の値を指定できます。  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="dc809-172">The property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   <span data-ttu-id="dc809-173">Windows Server FCI には、この例で使用される個人を特定できる情報を含む、多くの組み込みプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc809-173">Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="dc809-174">プロパティごとに使用できる値は、組織ごとに異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc809-174">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="dc809-175">ここで **使用する高** 値 **、中** 程度値、 **および低** 値は、一例です。</span><span class="sxs-lookup"><span data-stu-id="dc809-175">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="dc809-176">組織では、Windows Server ベースのファイル サーバー上のファイル サーバー リソース マネージャーで、可能な値を持つ Windows Server FCI 分類プロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="dc809-176">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="dc809-177">詳細については、「分類プロパティを [作成する」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759215(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="dc809-177">For more information, see [Create a classification property](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd759215(v=ws.11)).</span></span>

<span data-ttu-id="dc809-178">完了したら、両方とも Document プロパティを使用する 2 つの新しいルールにこれらの値 **の条件が含まれている必要** があります。</span><span class="sxs-lookup"><span data-stu-id="dc809-178">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="dc809-179">この条件は UI には表示されませんが、他の条件、アクション、および設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc809-179">This condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span>

<span data-ttu-id="dc809-180">1 つのルールは、[**個人情報**] プロパティが [**高**] または [**中**] の場合にコンテンツへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="dc809-180">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="dc809-181">2 番目のルールは、[**個人情報**] プロパティが [**低**] の場合にコンテンツについて通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="dc809-181">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>

![2 つのルールが作成されたことを示す[新しい DLP ポリシー] ダイアログ ボックス](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="dc809-183">DLP ポリシーを作成した後に</span><span class="sxs-lookup"><span data-stu-id="dc809-183">After you create the DLP policy</span></span>

<span data-ttu-id="dc809-184">前のセクションの手順を実行すると、そのプロパティを持つコンテンツをすばやく検出する DLP ポリシーが作成されますが、そのコンテンツが新しくアップロードされた場合 (コンテンツのインデックスが作成される) 場合、またはコンテンツが古いが編集済みである場合 (コンテンツの再インデックスが作成される場合) だけです。</span><span class="sxs-lookup"><span data-stu-id="dc809-184">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>

<span data-ttu-id="dc809-p117">対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc809-p117">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>

> [!CAUTION]
> <span data-ttu-id="dc809-189">サイトを再インデックス付けすると、検索システムで多大な負荷が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="dc809-189">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="dc809-190">シナリオで絶対に必要な場合を限り、サイトのインデックスを再設定しない。</span><span class="sxs-lookup"><span data-stu-id="dc809-190">Don't re-index your site unless your scenario absolutely requires it.</span></span>

<span data-ttu-id="dc809-191">詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](/sharepoint/crawl-site-content)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc809-191">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](/sharepoint/crawl-site-content).</span></span>

### <a name="reindex-a-site-optional"></a><span data-ttu-id="dc809-192">サイトのインデックスを再作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="dc809-192">Reindex a site (optional)</span></span>

1. <span data-ttu-id="dc809-193">サイトで、[設定] ( **右上** の歯車アイコン) [サイトの設定] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc809-193">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>

2. <span data-ttu-id="dc809-194">[検索 **] で**、[ **検索とオフラインの可用性の** \> **再インデックス サイト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dc809-194">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>

## <a name="more-information"></a><span data-ttu-id="dc809-195">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dc809-195">More information</span></span>

- [<span data-ttu-id="dc809-196">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="dc809-196">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="dc809-197">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="dc809-197">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)

- [<span data-ttu-id="dc809-198">通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="dc809-198">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

- [<span data-ttu-id="dc809-199">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="dc809-199">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)

- [<span data-ttu-id="dc809-200">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="dc809-200">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)