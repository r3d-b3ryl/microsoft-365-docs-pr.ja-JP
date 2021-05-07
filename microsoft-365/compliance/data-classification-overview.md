---
title: データ分類について
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: データ分類ダッシュボードを使用すると、組織内で検出、分類された機密データの量を確認できます。
ms.openlocfilehash: 2867e545221061f5f99bf7ff669f9655b3777ba8
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899387"
---
# <a name="learn-about-data-classification"></a><span data-ttu-id="4a70f-103">データ分類について</span><span class="sxs-lookup"><span data-stu-id="4a70f-103">Learn about data classification</span></span>

<span data-ttu-id="4a70f-104">Microsoft 365 の管理者またはコンプライアンス管理者は、組織内のコンテンツを評価してタグ付けすることにより、コンテンツの保存場所を制御し、保存場所に関わらずコンテンツを保護でき、また、組織のニーズに合わせてコンテンツを保持および削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a70f-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according to your organizations needs.</span></span> <span data-ttu-id="4a70f-105">これらは、[秘密ラベル](sensitivity-labels.md)、[保持ラベル](retention.md#retention-labels)、および機密情報の種類の分類を適用することにより行います。</span><span class="sxs-lookup"><span data-stu-id="4a70f-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](retention.md#retention-labels), and sensitive information type classification.</span></span> <span data-ttu-id="4a70f-106">検出、評価、タグ付けを行うにはさまざまな方法がありますが、最終的には、これらのラベルの一方または両方を使用してタグ付けおよび分類された大量のドキュメントとメールが生み出される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a70f-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large number of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="4a70f-107">保持ラベルと機密ラベルを適用した後は、テナント全体でラベルがどのように使用されているか、これらのアイテムを使用してどのような操作が行われているかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a70f-107">After you apply your retention labels and sensitivity labels, you'll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="4a70f-108">こうした内容は、データ分類のページで確認できます。具体的には次の内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="4a70f-109">機密情報の種類として分類されたアイテムの数およびこれらの分類の種類</span><span class="sxs-lookup"><span data-stu-id="4a70f-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="4a70f-110">Microsoft 365 および Azure Information Protection の両方で最も多く適用されている機密ラベル</span><span class="sxs-lookup"><span data-stu-id="4a70f-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="4a70f-111">最も多く適用されている保持ラベル</span><span class="sxs-lookup"><span data-stu-id="4a70f-111">the top applied retention labels</span></span>
- <span data-ttu-id="4a70f-112">機密コンテンツに対してユーザーが行っているアクティビティの概要</span><span class="sxs-lookup"><span data-stu-id="4a70f-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="4a70f-113">機密データおよび保持されたデータの保存場所</span><span class="sxs-lookup"><span data-stu-id="4a70f-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="4a70f-114">これらの機能は、データ分類のページでも管理することができます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-114">You also manage these features on the data classification page:</span></span>

- [<span data-ttu-id="4a70f-115">トレーニング可能な分類子</span><span class="sxs-lookup"><span data-stu-id="4a70f-115">trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="4a70f-116">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="4a70f-116">sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="4a70f-117">完全に一致するデータ</span><span class="sxs-lookup"><span data-stu-id="4a70f-117">exact data matches</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="4a70f-118">コンテンツ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="4a70f-118">content explorer</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="4a70f-119">アクティビティ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="4a70f-119">activity explorer</span></span>](data-classification-activity-explorer.md)

<span data-ttu-id="4a70f-120">データ分類は、**Microsoft 365 コンプライアンス センター** または **Microsoft 365 セキュリティ センター**  >  [**分類**]  >  [**データ分類**] で確認することができます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-120">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

<span data-ttu-id="4a70f-121">データ分類機能についてのビデオ ツアーを開始します。</span><span class="sxs-lookup"><span data-stu-id="4a70f-121">Take a video tour of our data classification features.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

<span data-ttu-id="4a70f-122">データ分類は、ポリシーを作成する前に、機密コンテンツとラベル付きコンテンツをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="4a70f-122">Data classification will scan your sensitive content and labeled content before you create any policies.</span></span> <span data-ttu-id="4a70f-123">これは **ゼロ変更管理** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-123">This is called **zero change management**.</span></span> <span data-ttu-id="4a70f-124">これにより、すべての保持ラベルおよび機密ラベルが環境に与える影響を確認でき、保護ポリシーおよびガバナンス ポリシーのニーズの評価を開始できます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-124">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4a70f-125">前提条件</span><span class="sxs-lookup"><span data-stu-id="4a70f-125">Prerequisites</span></span>

<span data-ttu-id="4a70f-126">さまざまなサブスクリプションがエンドポイント DLP をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4a70f-126">A number of different subscriptions support Endpoint DLP.</span></span> <span data-ttu-id="4a70f-127">エンドポイント DLP のライセンス オプションについては、「[情報保護ライセンスのガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-127">To see licensing options for Endpoint DLP see [Information Protection licensing for guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span> 

### <a name="permissions"></a><span data-ttu-id="4a70f-128">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="4a70f-128">Permissions</span></span>

 <span data-ttu-id="4a70f-129">データ分類のページにアクセスするには、アカウントはこれらの役割または役割グループに割り当てられたメンバーシップであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="4a70f-129">In order to get access to the data classification page, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="4a70f-130">**Microsoft 365 の役割グループ**</span><span class="sxs-lookup"><span data-stu-id="4a70f-130">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="4a70f-131">全体管理者</span><span class="sxs-lookup"><span data-stu-id="4a70f-131">Global administrator</span></span>
- <span data-ttu-id="4a70f-132">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="4a70f-132">Compliance administrator</span></span>
- <span data-ttu-id="4a70f-133">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="4a70f-133">Security administrator</span></span>
- <span data-ttu-id="4a70f-134">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="4a70f-134">Compliance data administrator</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="4a70f-135">コンテンツで最も多く使用されている機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="4a70f-135">Sensitive information types used most in your content</span></span>

<span data-ttu-id="4a70f-136">Microsoft 365 では、社会保障番号を含むアイテムやクレジットカード番号を含むアイテムなど、機密情報の種類の定義が多数提供されています。</span><span class="sxs-lookup"><span data-stu-id="4a70f-136">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="4a70f-137">機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-137">For more information on sensitive information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="4a70f-138">機密情報の種類カードには、組織全体で検出されたラベル付けされている機密情報の種類のうち上位のものが示されます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-138">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![上位の機密情報の種類](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="4a70f-140">特定の分類カテゴリに含まれるアイテムの数を確認するには、そのカテゴリのバーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="4a70f-140">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![上位の機密情報の種類をポイントした際の詳細情報](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="4a70f-142">"No data found with sensitive information" (機密情報が含まれるデータが見つかりませんでした) というメッセージがカードに表示される場合、</span><span class="sxs-lookup"><span data-stu-id="4a70f-142">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="4a70f-143">機密情報の種類として分類されているアイテムが組織に存在しないか、クロールされたアイテムが存在しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4a70f-143">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="4a70f-144">ラベルの使用を開始するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-144">To get started with labels, see:</span></span>
>- [<span data-ttu-id="4a70f-145">秘密度ラベルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="4a70f-145">Get started with sensitivity labels</span></span>](get-started-with-sensitivity-labels.md)
>- [<span data-ttu-id="4a70f-146">保持ポリシーおよび保持ラベルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="4a70f-146">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)
>- [<span data-ttu-id="4a70f-147">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="4a70f-147">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="4a70f-148">コンテンツに適用されている上位の機密ラベル</span><span class="sxs-lookup"><span data-stu-id="4a70f-148">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="4a70f-149">Microsoft 365 または Azure Information Protection (AIP) のいずれかでアイテムに機密ラベルを適用すると、次の 2 つのことが起こります。</span><span class="sxs-lookup"><span data-stu-id="4a70f-149">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="4a70f-150">組織にとってのアイテムの価値を示すタグがドキュメントに埋め込まれ、そのタグはドキュメントとともにどこにでも移動します。</span><span class="sxs-lookup"><span data-stu-id="4a70f-150">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="4a70f-151">タグが含まれることで、必須のウォーターマークや暗号化など、さまざまな保護機能が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-151">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="4a70f-152">エンド ポイントの保護を有効にすると、アイテムを組織の制御から離れさせないようにもできます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-152">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="4a70f-153">機密ラベルの詳細については、「[Learn about sensitivity labels (機密ラベルの詳細)](sensitivity-labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-153">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="4a70f-154">SharePoint および OneDrive にあるファイルに対応するデータがデータ分類ページに表示されるようにするには、機密度ラベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a70f-154">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="4a70f-155">詳細については、「[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-155">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="4a70f-156">機密ラベル カードには、機密レベルごとのアイテム (メールやドキュメント) の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-156">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![機密ラベルの分類別のコンテンツの内訳用プレースホルダーのスクリーンショット](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="4a70f-p108">機密ラベルをまだ作成または発行していない場合、または、いずれのコンテンツにも機密ラベルが適用されていない場合、"No sensitivity labels detected" (機密ラベルが検出されませんでした) というメッセージがこのカードに表示されます。機密ラベルの使用を開始するには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-p108">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected". To get started with sensitivity labels, see:</span></span>
>- <span data-ttu-id="4a70f-160">[機密ラベルの使用を開始する](get-started-with-sensitivity-labels.md) または、AIP については [Azure Information Protection ポリシーを構成する](/azure/information-protection/configure-policy)</span><span class="sxs-lookup"><span data-stu-id="4a70f-160">[Get started with sensitivity labels](get-started-with-sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="4a70f-161">コンテンツに適用されている上位の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="4a70f-161">Top retention labels applied to content</span></span>

<span data-ttu-id="4a70f-162">保持ラベルは、組織内のコンテンツの保持と廃棄を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-162">Retention labels are used to manage the retention and disposition of content in your organization.</span></span> <span data-ttu-id="4a70f-163">適用された保持ラベルは、アイテムが削除されるまでどのように保持するか、削除前に確認を必要とするかどうか、保持期間の有効期限、記録としてマークするかどうかを制御するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-163">When applied, they can be used to control how an item will be kept before deletion, whether it should be reviewed prior to deletion, when its retention period expires, and whether it should be marked as a record.</span></span> <span data-ttu-id="4a70f-164">詳細については、「[アイテム保持ポリシーと保持ラベルの詳細](retention.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-164">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="4a70f-165">最も多く適用されている保持ラベルのカードには、特定の保持ラベルが付けられているアイテムの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-165">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![最も多く適用されている保持ラベル用プレースホルダーのスクリーンショット](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="4a70f-167">「No retention labels detected」 (保持ラベルが検出されませんでした) というメッセージがカードに表示される場合、保持ラベルが作成または発行されていないか、いずれのコンテンツにも保持ラベルが適用されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="4a70f-167">If this card displays the message, "No retention labels detected", it means you haven't created or published any retention labels or no content has had a retention label applied.</span></span> <span data-ttu-id="4a70f-168">保持ラベルの使用を開始するには、</span><span class="sxs-lookup"><span data-stu-id="4a70f-168">To get started with retention labels, see:</span></span>
>- [<span data-ttu-id="4a70f-169">アイテム保持ポリシーおよび保持ラベルの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="4a70f-169">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)

## <a name="top-activities-detected"></a><span data-ttu-id="4a70f-170">検出された上位アクティビティ</span><span class="sxs-lookup"><span data-stu-id="4a70f-170">Top activities detected</span></span>

<span data-ttu-id="4a70f-171">このカードでは、機密ラベルが付けられたアイテムに対してユーザーが行う最も一般的な操作の概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-171">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="4a70f-172">[アクティビティ エクスプローラー](data-classification-activity-explorer.md)を使用すると、ラベル付きコンテンツおよび Windows 10 のエンドポイントにあるコンテンツでの、Microsoft 365 により追跡されるいくつかのアクティビティの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-172">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on the different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="4a70f-p112">"No activity detected" (アクティビティが検出されませんでした) というメッセージがこのカードに表示される場合、ファイルに対して行われたアクティビティがなかったか、ユーザーまたは管理者による監査が有効化されていないことを意味します。監査ログをオンにするには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-p112">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on. To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="4a70f-175">セキュリティ/コンプライアンス センターで監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="4a70f-175">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="4a70f-176">場所別の機密ラベルおよび保持ラベル付きデータ</span><span class="sxs-lookup"><span data-stu-id="4a70f-176">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="4a70f-177">データ分類の報告の目的は、どのラベルが付いているアイテムがどこにいくつあるかを確認できるようにすることにあります。</span><span class="sxs-lookup"><span data-stu-id="4a70f-177">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="4a70f-178">これらのカードでは、Exchange、SharePoint、OneDrive などにあるラベル付きのアイテムの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a70f-178">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="4a70f-p114">"No locations detected" (場所が検出されませんでした) というメッセージがこのカードに表示される場合、機密ラベルが作成または発行されていないか、いずれのコンテンツにも保持ラベルが適用されていないことを意味します。機密ラベルの使用を開始するには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a70f-p114">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied. To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="4a70f-181">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="4a70f-181">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="4a70f-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a70f-182">See also</span></span>

- [<span data-ttu-id="4a70f-183">ラベル アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="4a70f-183">View label activity</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="4a70f-184">ラベル付きコンテンツの表示</span><span class="sxs-lookup"><span data-stu-id="4a70f-184">View labeled content</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="4a70f-185">秘密度ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="4a70f-185">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="4a70f-186">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="4a70f-186">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="4a70f-187">機密情報の種類に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="4a70f-187">Learn about sensitive information types</span></span>](sensitive-information-type-learn-about.md)
- [<span data-ttu-id="4a70f-188">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="4a70f-188">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="4a70f-189">トレーニング可能な分類子の詳細 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4a70f-189">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)