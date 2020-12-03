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
ms.openlocfilehash: a3dd82dae76336dc3d1293430e10ba505585e707
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562978"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a><span data-ttu-id="2a20f-103">FCI または他のプロパティを使用したドキュメントを保護する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2a20f-103">Create a DLP policy to protect documents with FCI or other properties</span></span>

<span data-ttu-id="2a20f-104">Microsoft 365 データ損失防止 (DLP) ポリシーでは、分類プロパティまたはアイテムのプロパティを使用して機密アイテムを識別できます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-104">Microsoft 365 data loss prevention (DLP) policies can use classification properties or item properties to identify sensitive items.</span></span> <span data-ttu-id="2a20f-105">たとえば、次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-105">For example you can use:</span></span>

- <span data-ttu-id="2a20f-106">Windows Server ファイル分類インフラストラクチャ (FCI) プロパティ</span><span class="sxs-lookup"><span data-stu-id="2a20f-106">Windows Server File Classification infrastructure (FCI) properties</span></span>
- <span data-ttu-id="2a20f-107">SharePoint ドキュメントのプロパティ</span><span class="sxs-lookup"><span data-stu-id="2a20f-107">SharePoint document properties</span></span>
- <span data-ttu-id="2a20f-108">サードパーティ製のシステムドキュメントプロパティ</span><span class="sxs-lookup"><span data-stu-id="2a20f-108">third-party system document properties</span></span>

![Office 365 と外部の分類システムを示す図](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

<span data-ttu-id="2a20f-110">たとえば、組織で Windows Server FCI を使用して、社会保障番号などの個人データを持つアイテムを識別してから、ドキュメントを分類するには、ドキュメント内で見つかった個人データの種類と出現回数に基づいて個人 **情報** プロパティを **高** **、中**、 **低**、 **公開**、または **非 PII** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-110">For example, your organization might use Windows Server FCI to identify items with personal data such as social security numbers, and then classify the document by setting the **Personally Identifiable Information** property to **High**, **Moderate**, **Low**, **Public**, or **Not PII** based on the type and number of occurrences of personal data found in the document.</span></span>

<span data-ttu-id="2a20f-111">Microsoft 365 では、このプロパティが設定されているドキュメントを特定の値 ( **高** 、 **中** など) に識別する DLP ポリシーを作成し、それらのファイルへのアクセスをブロックするなどの処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-111">In Microsoft 365, you can create a DLP policy that identifies documents that have that property set to specific values, such as **High** and **Medium**, and then takes an action such as blocking access to those files.</span></span> <span data-ttu-id="2a20f-112">プロパティが [**低**] に設定されている場合には (電子メールの通知送信などの) 異なるアクションを実行する別のルールを同じポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-112">The same policy can have another rule that takes a different action if the property is set to **Low**, such as sending an email notification.</span></span> <span data-ttu-id="2a20f-113">このようにして、DLP は Windows Server FCI と統合され、Windows Server ベースのファイルサーバーから Microsoft 365 にアップロードまたは共有される Office ドキュメントを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-113">In this way, DLP integrates with Windows Server FCI and can help protect Office documents uploaded or shared to Microsoft 365 from Windows Server-based file servers.</span></span>

<span data-ttu-id="2a20f-114">DLP ポリシーは、特定のプロパティの名前と値のペアを検索するだけです。</span><span class="sxs-lookup"><span data-stu-id="2a20f-114">A DLP policy simply looks for a specific property name/value pair.</span></span> <span data-ttu-id="2a20f-115">プロパティに対応する SharePoint 検索用の管理プロパティがある限り、任意のドキュメントプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-115">Any document property can be used, as long as the property has a corresponding managed property for SharePoint search.</span></span> <span data-ttu-id="2a20f-116">たとえば、SharePoint サイトコレクションでは、 **Customer** という必須のフィールドを持つ、**旅行レポート** という名前のコンテンツタイプが使用されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-116">For example, a SharePoint site collection might use a content type named **Trip Report** with a required field named **Customer**.</span></span> <span data-ttu-id="2a20f-117">ユーザーが旅行報告書を作成するときには常に、顧客名を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-117">Whenever a person creates a trip report, they must enter the customer name.</span></span> <span data-ttu-id="2a20f-118">このプロパティの名前と値のペアを DLP ポリシーで使用することもできます。たとえば、 **顧客** フィールドに **Contoso** という情報が含まれている場合に、ゲストのドキュメントへのアクセスをブロックするルールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-118">This property name/value pair can also be used in a DLP policy—for example, if you want a rule that blocks access to the document for guests when the **Customer** field contains **Contoso**.</span></span>

<span data-ttu-id="2a20f-119">特定の Microsoft 365 ラベルを持つコンテンツに DLP ポリシーを適用する場合は、ここに記載されている手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="2a20f-119">If you want to apply your DLP policy to content with specific Microsoft 365 labels, you should not follow the steps here.</span></span> <span data-ttu-id="2a20f-120">代わりに、 [DLP ポリシーの条件として保持ラベルを使用](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-120">Instead, learn how to [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

## <a name="before-you-create-the-dlp-policy"></a><span data-ttu-id="2a20f-121">DLP ポリシーを作成する前に</span><span class="sxs-lookup"><span data-stu-id="2a20f-121">Before you create the DLP policy</span></span>

<span data-ttu-id="2a20f-122">DLP ポリシーで Windows Server FCI プロパティまたは他のプロパティを使用するには、その前に、SharePoint 管理センターで管理プロパティを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-122">Before you can use a Windows Server FCI property or other property in a DLP policy, you need to create a managed property in the SharePoint admin center.</span></span> <span data-ttu-id="2a20f-123">理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2a20f-123">Here's why.</span></span>

<span data-ttu-id="2a20f-p106">例</span><span class="sxs-lookup"><span data-stu-id="2a20f-p106">In SharePoint Online and OneDrive for Business, the search index is built up by crawling the content on your sites. The crawler picks up content and metadata from the documents in the form of crawled properties. The search schema helps the crawler decide what content and metadata to pick up. Examples of metadata are the author and the title of a document. However, to get the content and metadata from the documents into the search index, the crawled properties must be mapped to managed properties. Only managed properties are kept in the index. For example, a crawled property related to author is mapped to a managed property related to author.</span></span>

<span data-ttu-id="2a20f-131">DLP は検索クローラーを使用してサイト上の機密情報を識別および分類し、その機密情報を検索インデックスのセキュリティで保護された部分に保存するため、これは重要です。</span><span class="sxs-lookup"><span data-stu-id="2a20f-131">This is important because DLP uses the search crawler to identify and classify sensitive information on your sites, and then store that sensitive information in a secure portion of the search index.</span></span> <span data-ttu-id="2a20f-132">Office 365 にドキュメントをアップロードすると、SharePoint は、ドキュメントプロパティに基づいて、クロールされたプロパティを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-132">When you upload a document to Office 365, SharePoint automatically creates crawled properties based on the document properties.</span></span> <span data-ttu-id="2a20f-133">ただし、DLP ポリシーで FCI またはその他のプロパティを使用するには、クロールされたプロパティを管理プロパティにマッピングして、そのプロパティを持つコンテンツがインデックスに保持されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-133">But to use an FCI or other property in a DLP policy, that crawled property needs to be mapped to a managed property so that content with that property is kept in the index.</span></span>

<span data-ttu-id="2a20f-134">検索および管理プロパティの詳細については、「 [SharePoint Online で検索スキーマを管理する](https://go.microsoft.com/fwlink/p/?LinkID=627454)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a20f-134">For more information on search and managed properties, see [Manage the search schema in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454).</span></span>

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a><span data-ttu-id="2a20f-135">手順 1: 必要なプロパティが含まれるドキュメントを Office 365 にアップロードする</span><span class="sxs-lookup"><span data-stu-id="2a20f-135">Step 1: Upload a document with the needed property to Office 365</span></span>

<span data-ttu-id="2a20f-136">最初に、DLP ポリシーで参照するプロパティが含まれるドキュメントをアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-136">You first need to upload a document with the property that you want to reference in your DLP policy.</span></span> <span data-ttu-id="2a20f-137">Microsoft 365 はプロパティを検出し、クロールされたプロパティを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-137">Microsoft 365 will detect the property and automatically create a crawled property from it.</span></span> <span data-ttu-id="2a20f-138">次の手順では、管理プロパティを作成し、管理プロパティをこのクロールされたプロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="2a20f-138">In the next step, you'll create a managed property, and then map the managed property to this crawled property.</span></span>

### <a name="step-2-create-a-managed-property"></a><span data-ttu-id="2a20f-139">手順 2: 管理プロパティを作成する</span><span class="sxs-lookup"><span data-stu-id="2a20f-139">Step 2: Create a managed property</span></span>

1. <span data-ttu-id="2a20f-140">Microsoft 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2a20f-140">Sign in to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="2a20f-141">左側のナビゲーションで、[**管理センター** SharePoint] を選択し \> **SharePoint** ます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-141">In the left navigation, choose **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="2a20f-142">SharePoint 管理センターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-142">You're now in the SharePoint admin center.</span></span>

3. <span data-ttu-id="2a20f-143">左側のナビゲーションで、[検索管理] ページの [**検索] を選択し** \> **search administration** \> ます。**検索スキーマを管理** します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-143">In the left navigation, choose **search** \> on the **search administration** page \> **Manage Search Schema**.</span></span>

   ![SharePoint 管理センターの検索管理ページ](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. <span data-ttu-id="2a20f-145">[ **管理プロパティ** ] ページで、 \> **新しい管理プロパティを追加** します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-145">On the **Managed Properties** page \> **New Managed Property**.</span></span>

   ![[新しい管理プロパティ] ボタンが強調表示されている[プロパティ管理] ページ](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. <span data-ttu-id="2a20f-p110">プロパティの名前と説明を入力します。この名前が、DLP ポリシーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-p110">Enter a name and description for the property. This name is what will appear in your DLP policies.</span></span>

6. <span data-ttu-id="2a20f-149">[**型**] で [**テキスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-149">For **Type**, choose **Text**.</span></span>

7. <span data-ttu-id="2a20f-150">[**主な特徴**] では [**クエリ可能**] と [**取得可能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-150">Under **Main characteristics**, select **Queryable** and **Retrievable**.</span></span>

8. <span data-ttu-id="2a20f-151">[クロールされた **プロパティへのマッピング**] で \> **マッピングを追加** します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-151">Under **Mappings to crawled properties** \> **Add a mapping**.</span></span>

9. <span data-ttu-id="2a20f-152">[クロールされた **プロパティの選択**] ダイアログボックスで、 \> DLP ポリシーで使用する Windows Server fci プロパティまたはその他のプロパティに対応するクロールされたプロパティを検索して選択し \> **OK** ます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-152">In the **crawled property selection** dialog box \> find and select the crawled property that corresponds to the Windows Server FCI property or other property that you will use in your DLP policy \> **OK**.</span></span>

   ![[クロールされたプロパティの選択] ダイアログ ボックス](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. <span data-ttu-id="2a20f-154">ページの下部にある \> **[OK] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-154">At the bottom of the page \> **OK**.</span></span>

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a><span data-ttu-id="2a20f-155">FCI プロパティまたは他のプロパティを使用する DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2a20f-155">Create a DLP policy that uses an FCI property or other property</span></span>

<span data-ttu-id="2a20f-156">この例では、組織が Windows Server ベースのファイルサーバー上で FCI を使用しています。具体的には、[**高** **]、[中**]、[**低**]、[**パブリック**]、および [PII] で **はなく**、可能な値を持つ、"**個人識別情報**" という名前の fci 分類プロパティを使用しています。</span><span class="sxs-lookup"><span data-stu-id="2a20f-156">In this example, an organization is using FCI on its Windows Server-based file servers; specifically, they're using the FCI classification property named **Personally Identifiable Information** with possible values of **High**, **Moderate**, **Low**, **Public**, and **Not PII**.</span></span> <span data-ttu-id="2a20f-157">これで、Office 365 の DLP ポリシーで既存の FCI 分類を使用することになりました。</span><span class="sxs-lookup"><span data-stu-id="2a20f-157">Now they want to use their existing FCI classification in their DLP policies in Office 365.</span></span>

<span data-ttu-id="2a20f-158">まず、前述の手順に従って SharePoint Online で管理プロパティを作成します。管理プロパティを、FCI に基づいて自動作成された、クロールされたプロパティにマッピングします。</span><span class="sxs-lookup"><span data-stu-id="2a20f-158">First, they follow the steps above to create a managed property in SharePoint Online, which maps to the crawled property created automatically from the FCI property.</span></span>

<span data-ttu-id="2a20f-159">次に、2つのルールを使用する DLP ポリシーを作成します。両方のプロパティには、条件 **ドキュメントプロパティに次のいずれかの値が含まれ** ています。</span><span class="sxs-lookup"><span data-stu-id="2a20f-159">Next, they create a DLP policy with two rules that both use the condition **Document properties contain any of these values**:</span></span>

- <span data-ttu-id="2a20f-160">**Fci PII コンテンツ-高、** 中最初のルールは、FCI 分類プロパティの個人を特定できる **情報** が **高** または **モデレート** で、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-160">**FCI PII content - High, Moderate** The first rule restricts access to the document if the FCI classification property **Personally Identifiable Information** equals **High** or **Moderate** and the document is shared with people outside the organization.</span></span>

- <span data-ttu-id="2a20f-161">**Fci PII コンテンツ-低** 2番目のルールは、FCI 分類プロパティの個人を特定できる **情報** が **少なく** 、ドキュメントが組織外のユーザーと共有されている場合に、ドキュメント所有者に通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-161">**FCI PII content - Low** The second rule sends a notification to the document owner if the FCI classification property **Personally Identifiable Information** equals **Low** and the document is shared with people outside the organization.</span></span>

### <a name="create-the-dlp-policy-by-using-powershell"></a><span data-ttu-id="2a20f-162">PowerShell を使用して DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="2a20f-162">Create the DLP policy by using PowerShell</span></span>

<span data-ttu-id="2a20f-163">条件 **ドキュメントのプロパティにこれらの値のいずれかが含ま** れている場合、セキュリティコンプライアンスセンターの UI では一時的に使用できません &amp; が、PowerShell を使用してこの条件を引き続き使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-163">The condition **Document properties contain any of these values** is temporarily not available in the UI of the Security &amp; Compliance Center, but you can still use this condition by using PowerShell.</span></span> <span data-ttu-id="2a20f-164">コマンドレットを使用して  `New\Set\Get-DlpCompliancePolicy` DLP ポリシーを操作し、パラメーターを指定したコマンドレットを使用して、  `New\Set\Get-DlpComplianceRule`  `ContentPropertyContainsWords` 条件 **ドキュメントプロパティにこれらの値のいずれかを含める** ことができます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-164">You can use the  `New\Set\Get-DlpCompliancePolicy` cmdlets to work with a DLP policy, and use the  `New\Set\Get-DlpComplianceRule` cmdlets with the  `ContentPropertyContainsWords` parameter to add the condition **Document properties contain any of these values**.</span></span>

<span data-ttu-id="2a20f-165">これらのコマンドレットの詳細については、「 [セキュリティ &amp; コンプライアンスセンターのコマンドレット](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a20f-165">For more information on these cmdlets, see [Security &amp; Compliance Center cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).</span></span>

1. [<span data-ttu-id="2a20f-166">&amp;リモート PowerShell を使用してセキュリティコンプライアンスセンターに接続する</span><span class="sxs-lookup"><span data-stu-id="2a20f-166">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. <span data-ttu-id="2a20f-167">を使用してポリシーを作成し  `New-DlpCompliancePolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-167">Create the policy by using  `New-DlpCompliancePolicy`.</span></span>

<span data-ttu-id="2a20f-168">この PowerShell は、すべての場所に適用する DLP ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-168">This PowerShell creates a DLP policy that applies to all locations.</span></span>

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. <span data-ttu-id="2a20f-169">上記の2つのルールを使用して  `New-DlpComplianceRule` 、1つのルールを **低** 値に、もう1つは **高** および中 **程度** のルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-169">Create the two rules described above by using  `New-DlpComplianceRule`, where one rule is for the **Low** value, and another rule is for the **High** and **Moderate** values.</span></span>

   <span data-ttu-id="2a20f-170">これら2つのルールを作成する PowerShell の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-170">Here is a PowerShell example that creates these two rules.</span></span> <span data-ttu-id="2a20f-171">プロパティ名と値のペアは二重引用符で囲まれ、プロパティ名はコンマで区切った複数の値をコンマで区切って指定できます。たとえば、次のようにスペースを含めません。  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span><span class="sxs-lookup"><span data-stu-id="2a20f-171">The property name/value pairs are enclosed in quotation marks, and a property name may specify multiple values separated by commas with no spaces, like  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`</span></span>

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   <span data-ttu-id="2a20f-172">Windows Server FCI には、この例で使用されている **個人を特定できる情報** を含む、多くの組み込みのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2a20f-172">Windows Server FCI includes many built-in properties, including **Personally Identifiable Information** used in this example.</span></span> <span data-ttu-id="2a20f-173">各プロパティに指定できる値は、すべての組織によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-173">The possible values for each property can be different for every organization.</span></span> <span data-ttu-id="2a20f-174">ここで使用されているの **は、次** に示すように、**高**、中、**低** の値だけです。</span><span class="sxs-lookup"><span data-stu-id="2a20f-174">The **High**, **Moderate**, and **Low** values used here are only an example.</span></span> <span data-ttu-id="2a20f-175">組織では、windows server FCI 分類プロパティを、Windows Server ベースのファイルサーバー上のファイルサーバーリソースマネージャーで指定可能な値で表示できます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-175">For your organization, you can view the Windows Server FCI classification properties with their possible values in the file Server Resource Manager on the Windows Server-based file server.</span></span> <span data-ttu-id="2a20f-176">詳細については、「 [分類プロパティを作成する](https://go.microsoft.com/fwlink/p/?LinkID=627456)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a20f-176">For more information, see [Create a classification property](https://go.microsoft.com/fwlink/p/?LinkID=627456).</span></span>

<span data-ttu-id="2a20f-177">完了したら、ドキュメントプロパティを使用する2つの新しいルールに **これらの値の条件が含まれ** ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-177">When you finish, your policy should have two new rules that both use the **Document properties contain any of these values** condition.</span></span> <span data-ttu-id="2a20f-178">この条件は UI には表示されませんが、その他の条件、アクション、設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-178">This condition won't appear in the UI, though the other conditions, actions, and settings will appear.</span></span>

<span data-ttu-id="2a20f-179">1 つのルールは、[**個人情報**] プロパティが [**高**] または [**中**] の場合にコンテンツへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2a20f-179">One rule blocks access to content where the **Personally Identifiable Information** property equals **High** or **Moderate**.</span></span> <span data-ttu-id="2a20f-180">2 番目のルールは、[**個人情報**] プロパティが [**低**] の場合にコンテンツについて通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="2a20f-180">A second rule sends a notification about content where the **Personally Identifiable Information** property equals **Low**.</span></span>

![2 つのルールが作成されたことを示す[新しい DLP ポリシー] ダイアログ ボックス](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a><span data-ttu-id="2a20f-182">DLP ポリシーを作成した後に</span><span class="sxs-lookup"><span data-stu-id="2a20f-182">After you create the DLP policy</span></span>

<span data-ttu-id="2a20f-183">前のセクションの手順を実行すると、そのプロパティを使用してコンテンツを迅速に検出する DLP ポリシーが作成されます。ただし、そのコンテンツが新しくアップロードされた場合 (コンテンツのインデックスが作成されます)、またはそのコンテンツが古く、編集された (コンテンツの再インデックスが作成される) 場合のみです。</span><span class="sxs-lookup"><span data-stu-id="2a20f-183">Doing the steps in the previous sections will create a DLP policy that will quickly detect content with that property, but only if that content is newly uploaded (so that the content's indexed), or if that content is old but just edited (so that the content's re-indexed).</span></span>

<span data-ttu-id="2a20f-p117">対象プロパティが含まれるコンテンツを検出するには、ライブラリ、サイト、サイト コレクションの再インデックス付けを手動で要求し、対象プロパティが含まれるコンテンツすべてを DLP ポリシーが認識するようにできます。SharePoint Online では、定義されているクロール スケジュールに基づいてコンテンツは自動的にクロールされます。クローラーは、最後にクロールされて以降に変更が加えられたコンテンツを取得して、インデックスを更新します。スケジュールされたクロールが次に実行される前にコンテンツを保護する DLP ポリシーが必要となる場合には、以下の手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-p117">To detect content with that property everywhere, you may want to manually request that your library, site, or site collection be re-indexed, so that the DLP policy is aware of all the content with that property. In SharePoint Online, content is automatically crawled based on a defined crawl schedule. The crawler picks up content that has changed since the last crawl and updates the index. If you need your DLP policy to protect content before the next scheduled crawl, you can take these steps.</span></span>

> [!CAUTION]
> <span data-ttu-id="2a20f-188">サイトを再インデックス付けすると、検索システムで多大な負荷が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2a20f-188">Re-indexing a site can cause a massive load on the search system.</span></span> <span data-ttu-id="2a20f-189">シナリオで絶対に必要でない限り、サイトを再インデックス化しないでください。</span><span class="sxs-lookup"><span data-stu-id="2a20f-189">Don't re-index your site unless your scenario absolutely requires it.</span></span>

<span data-ttu-id="2a20f-190">詳細については、「[サイト、ライブラリ、またはリストのクロールおよび再インデックスの手動要求](https://go.microsoft.com/fwlink/p/?LinkID=627457)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a20f-190">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://go.microsoft.com/fwlink/p/?LinkID=627457).</span></span>

### <a name="reindex-a-site-optional"></a><span data-ttu-id="2a20f-191">サイトのインデックスを再作成する (オプション)</span><span class="sxs-lookup"><span data-stu-id="2a20f-191">Reindex a site (optional)</span></span>

1. <span data-ttu-id="2a20f-192">サイトで、[**設定**] (右上にある歯車アイコン) [サイトの設定] を選択し \> **Site Settings** ます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-192">On the site, choose **Settings** (gear icon in upper right) \> **Site Settings**.</span></span>

2. <span data-ttu-id="2a20f-193">[**検索**] で、[**検索とオフライン可用性** インデックス作成サイト] を選択し \> **Reindex site** ます。</span><span class="sxs-lookup"><span data-stu-id="2a20f-193">Under **Search**, choose **Search and offline availability** \> **Reindex site**.</span></span>

## <a name="more-information"></a><span data-ttu-id="2a20f-194">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2a20f-194">More information</span></span>

- [<span data-ttu-id="2a20f-195">データ損失防止ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="2a20f-195">Overview of data loss prevention policies</span></span>](data-loss-prevention-policies.md)

- [<span data-ttu-id="2a20f-196">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="2a20f-196">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)

- [<span data-ttu-id="2a20f-197">通知を送信して、DLP ポリシーのポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="2a20f-197">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)

- [<span data-ttu-id="2a20f-198">DLP ポリシー テンプレートに含まれるもの</span><span class="sxs-lookup"><span data-stu-id="2a20f-198">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)

- [<span data-ttu-id="2a20f-199">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="2a20f-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
