---
title: データ分類の使用を開始する
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
search.appverid:
- MOE150
- MET150
description: データ分類ダッシュボードを使用すると、組織内で検出、分類された機密データの量を確認できます。
ms.openlocfilehash: eda58ea2d34713a5c2cef40bbc2aa21b9964ddab
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327873"
---
# <a name="know-your-data---data-classification-overview"></a><span data-ttu-id="05263-103">データを把握する - データ分類の概要</span><span class="sxs-lookup"><span data-stu-id="05263-103">Know your data - data classification overview</span></span>

<span data-ttu-id="05263-104">Microsoft 365 の管理者またはコンプライアンス管理者は、組織内のコンテンツを評価してタグ付けすることにより、コンテンツの保存場所を制御し、保存場所に関わらずコンテンツを保護でき、また、組織のニーズに合わせてコンテンツを保持および削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="05263-104">As a Microsoft 365 administrator or compliance administrator, you can evaluate and then tag content in your organization in order to control where it goes, protect it no matter where it is and to ensure that it is preserved and deleted according your your organizations needs.</span></span> <span data-ttu-id="05263-105">これらは、[秘密ラベル](sensitivity-labels.md)、[保持ラベル](labels.md)、および機密情報の種類の分類を適用することにより行います。</span><span class="sxs-lookup"><span data-stu-id="05263-105">You do this through the application of [sensitivity labels](sensitivity-labels.md), [retention labels](labels.md), and sensitive information type classification.</span></span> <span data-ttu-id="05263-106">検出、評価、タグ付けを行うにはさまざまな方法がありますが、最終的には、これらのラベルの一方または両方を使用してタグ付けおよび分類された大量のドキュメントとメールが生み出される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05263-106">There are various ways to do the discovery, evaluation and tagging, but the end result is that you may have very large number of documents and emails that are tagged and classified with one or both of these labels.</span></span> <span data-ttu-id="05263-107">保持ラベルと機密ラベルを適用した後は、テナント全体でラベルがどのように使用されているか、これらのアイテムを使用してどのような操作が行われているかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05263-107">After you apply your retention labels and sensitivity labels, you'll want to see how the labels are being used across your tenant and what is being done with those items.</span></span> <span data-ttu-id="05263-108">こうした内容は、データ分類のページで確認できます。具体的には次の内容を確認できます。</span><span class="sxs-lookup"><span data-stu-id="05263-108">The data classification page provides visibility into that body of content, specifically:</span></span>

- <span data-ttu-id="05263-109">機密情報の種類として分類されたアイテムの数およびこれらの分類の種類</span><span class="sxs-lookup"><span data-stu-id="05263-109">the number items that have been classified as a sensitive information type and what those classifications are</span></span>
- <span data-ttu-id="05263-110">Microsoft 365 および Azure Information Protection の両方で最も多く適用されている機密ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-110">the top applied sensitivity labels in both Microsoft 365 and Azure Information Protection</span></span>
- <span data-ttu-id="05263-111">最も多く適用されている保持ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-111">the top applied retention labels</span></span>
- <span data-ttu-id="05263-112">機密コンテンツに対してユーザーが行っているアクティビティの概要</span><span class="sxs-lookup"><span data-stu-id="05263-112">a summary of activities that users are taking on your sensitive content</span></span>
- <span data-ttu-id="05263-113">機密データおよび保持されたデータの保存場所</span><span class="sxs-lookup"><span data-stu-id="05263-113">the locations of your sensitive and retained data</span></span>

<span data-ttu-id="05263-114">これらの機能は、データ分類のページでも管理することができます。</span><span class="sxs-lookup"><span data-stu-id="05263-114">You also manage these features on the data classification page:</span></span>
- [<span data-ttu-id="05263-115">トレーニング可能な分類子</span><span class="sxs-lookup"><span data-stu-id="05263-115">trainable classifiers</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="05263-116">機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="05263-116">sensitive information types</span></span>](what-the-sensitive-information-types-look-for.md)

<span data-ttu-id="05263-117">データ分類は、**Microsoft 365 コンプライアンス センター**または **Microsoft 365 セキュリティ センター**  >  [**分類**]  >  [**データ分類**] で確認することができます。</span><span class="sxs-lookup"><span data-stu-id="05263-117">You can find data classification in the **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Classification** > **Data Classification**.</span></span>

<span data-ttu-id="05263-118">データ分類機能についてのビデオ ツアーを開始します。</span><span class="sxs-lookup"><span data-stu-id="05263-118">Take a video tour of our data classification features.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

<span data-ttu-id="05263-119">データ分類は、ポリシーを作成する前に、機密コンテンツとラベル付きコンテンツをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="05263-119">Data classification will scan your sensitive content and labeled content before you create any policies.</span></span> <span data-ttu-id="05263-120">これは **ゼロ変更管理** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="05263-120">This is called **zero change management**.</span></span> <span data-ttu-id="05263-121">これにより、すべての保持ラベルおよび機密ラベルが環境に与える影響を確認でき、保護ポリシーおよびガバナンス ポリシーのニーズの評価を開始できます。</span><span class="sxs-lookup"><span data-stu-id="05263-121">This lets you see the impact that all the retention and sensitivity labels are having in your environment and empower you to start assessing your protection and governance policy needs.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05263-122">前提条件</span><span class="sxs-lookup"><span data-stu-id="05263-122">Prerequisites</span></span>

<span data-ttu-id="05263-123">データ分類にアクセスし、データ分類を使用するすべてのアカウントには、以下のサブスクリプションのいずれかからライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="05263-123">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="05263-124">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="05263-124">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="05263-125">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="05263-125">Office 365 (E5)</span></span>
- <span data-ttu-id="05263-126">高度なコンプライアンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="05263-126">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="05263-127">高度な脅威インテリジェンス (E5) アドオン</span><span class="sxs-lookup"><span data-stu-id="05263-127">Advanced Threat Intelligence (E5) add-on</span></span>

### <a name="permissions"></a><span data-ttu-id="05263-128">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="05263-128">Permissions</span></span>

 <span data-ttu-id="05263-129">データ分類のページにアクセスするには、アカウントはこれらの役割または役割グループに割り当てられたメンバーシップであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="05263-129">In order to get access to the data classification page, an account must be assigned membership in any one of these roles or role groups.</span></span>

<span data-ttu-id="05263-130">**Microsoft 365 の役割グループ**</span><span class="sxs-lookup"><span data-stu-id="05263-130">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="05263-131">全体管理者</span><span class="sxs-lookup"><span data-stu-id="05263-131">Global administrator</span></span>
- <span data-ttu-id="05263-132">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="05263-132">Compliance administrator</span></span>
- <span data-ttu-id="05263-133">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="05263-133">Security administrator</span></span>
- <span data-ttu-id="05263-134">コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="05263-134">Compliance data administrator</span></span>

## <a name="sensitive-information-types-used-most-in-your-content"></a><span data-ttu-id="05263-135">コンテンツで最も多く使用されている機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="05263-135">Sensitive information types used most in your content</span></span>

<span data-ttu-id="05263-136">Microsoft 365 では、社会保障番号を含むアイテムやクレジットカード番号を含むアイテムなど、機密情報の種類の定義が多数提供されています。</span><span class="sxs-lookup"><span data-stu-id="05263-136">Microsoft 365 comes with many definitions of sensitive information types, such as an item containing a social security number or a credit card number.</span></span> <span data-ttu-id="05263-137">機密情報の種類の詳細については、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-137">For more information on sensitive information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="05263-138">機密情報の種類カードには、組織全体で検出されたラベル付けされている機密情報の種類のうち上位のものが示されます。</span><span class="sxs-lookup"><span data-stu-id="05263-138">The sensitive information type card shows the top sensitive information types that have been found and labeled across your organization.</span></span>

![上位の機密情報の種類](../media/data-classification-sens-info-types-card.png)

<span data-ttu-id="05263-140">特定の分類カテゴリに含まれるアイテムの数を確認するには、そのカテゴリのバーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="05263-140">To find out how many items are in any given classification category, hover over the bar for the category.</span></span>

![上位の機密情報の種類をポイントした際の詳細情報](../media/data-classification-sens-info-types-hover.png)

> [!NOTE]
> <span data-ttu-id="05263-142">"No data found with sensitive information" (機密情報が含まれるデータが見つかりませんでした) というメッセージがカードに表示される場合、</span><span class="sxs-lookup"><span data-stu-id="05263-142">If the card displays the message "No data found with sensitive information".</span></span> <span data-ttu-id="05263-143">機密情報の種類として分類されているアイテムが組織に存在しないか、クロールされたアイテムが存在しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="05263-143">It means that there are no items in your organization that have been classified as being a sensitive information type or no items that have been crawled.</span></span> <span data-ttu-id="05263-144">ラベルの使用を開始するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-144">To get started with labels, see:</span></span>
>- [<span data-ttu-id="05263-145">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-145">Sensitivity labels</span></span>](sensitivity-labels.md)
>- [<span data-ttu-id="05263-146">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-146">Retention labels</span></span>](labels.md)
>- [<span data-ttu-id="05263-147">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="05263-147">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

## <a name="top-sensitivity-labels-applied-to-content"></a><span data-ttu-id="05263-148">コンテンツに適用されている上位の機密ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-148">Top sensitivity labels applied to content</span></span>

<span data-ttu-id="05263-149">Microsoft 365 または Azure Information Protection (AIP) のいずれかでアイテムに機密ラベルを適用すると、次の 2 つのことが起こります。</span><span class="sxs-lookup"><span data-stu-id="05263-149">When you apply a sensitivity label to an item either through Microsoft 365 or Azure Information Protection (AIP), two things happen:</span></span>

- <span data-ttu-id="05263-150">組織にとってのアイテムの価値を示すタグがドキュメントに埋め込まれ、そのタグはドキュメントとともにどこにでも移動します。</span><span class="sxs-lookup"><span data-stu-id="05263-150">a tag that indicates the value of the item to your org is embedded in the document and will follow it everywhere it goes</span></span>
- <span data-ttu-id="05263-151">タグが含まれることで、必須のウォーターマークや暗号化など、さまざまな保護機能が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="05263-151">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="05263-152">エンド ポイントの保護を有効にすると、アイテムを組織の制御から離れさせないようにもできます。</span><span class="sxs-lookup"><span data-stu-id="05263-152">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="05263-153">機密ラベルの詳細については、「[Learn about sensitivity labels (機密ラベルの詳細)](sensitivity-labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-153">For more information on sensitivity labels, see: [Learn about sensitivity labels](sensitivity-labels.md)</span></span>

<span data-ttu-id="05263-154">SharePoint および OneDrive にあるファイルに対応するデータがデータ分類ページに表示されるようにするには、機密度ラベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="05263-154">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="05263-155">詳細については、「[SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-155">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

<span data-ttu-id="05263-156">機密ラベル カードには、機密レベルごとのアイテム (メールやドキュメント) の数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05263-156">The sensitivity label card shows the number of items (email or document) by sensitivity level.</span></span>

![機密ラベルの分類別のコンテンツの内訳用プレースホルダーのスクリーンショット](../media/data-classification-top-sensitivity-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="05263-158">機密ラベルをまだ作成または発行していない場合、または、いずれのコンテンツにも機密ラベルが適用されていない場合、"No sensitivity labels detected" (機密ラベルが検出されませんでした) というメッセージがこのカードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="05263-158">If you haven't created or published any sensitivity labels or no content has had a sensitivity label applied, this card will display the message "No sensitivity labels detected".</span></span> <span data-ttu-id="05263-159">ラベルの使用を開始するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-159">To get started with labels, see:</span></span>
>- <span data-ttu-id="05263-160">「[機密ラベル](sensitivity-labels.md)」または、AIPについては「[Azure Information Protection ポリシーを構成する](https://docs.microsoft.com/azure/information-protection/configure-policy)」</span><span class="sxs-lookup"><span data-stu-id="05263-160">[sensitivity labels](sensitivity-labels.md) or for AIP [Configure the Azure information protection policy](https://docs.microsoft.com/azure/information-protection/configure-policy)</span></span>

## <a name="top-retention-labels-applied-to-content"></a><span data-ttu-id="05263-161">コンテンツに適用されている上位の保持ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-161">Top retention labels applied to content</span></span>

<span data-ttu-id="05263-162">保持ラベルは、組織内のコンテンツの廃棄を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="05263-162">Retention labels are used to manage the disposition of content in your organization.</span></span> <span data-ttu-id="05263-163">適用された保持ラベルは、ドキュメントが削除されるまでの期間、削除前に確認を必要とするかどうか、保持期間の有効期限、または削除できないよう記録としてマークするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="05263-163">When applied, they can be used to control how long a document will be kept before deletion, whether it should be reviewed prior to deletion, when it's retention period expires, or whether it should be marked as a record which can never be deleted.</span></span> <span data-ttu-id="05263-164">詳細については、「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-164">For more information see, [Overview of retention labels](labels.md).</span></span>

<span data-ttu-id="05263-165">最も多く適用されている保持ラベルのカードには、特定の保持ラベルが付けられているアイテムの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05263-165">The top applied retention labels card shows you how many items have a given retention label.</span></span>

![最も多く適用されている保持ラベル用プレースホルダーのスクリーンショット](../media/data-classification-top-retention-labels-applied.png)

> [!NOTE]
> <span data-ttu-id="05263-167">"No retention labels detected" (保持ラベルが検出されませんでした) というメッセージがカードに表示される場合、保持ラベルが作成または発行されていないか、いずれのコンテンツにも保持ラベルが適用されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="05263-167">If this card displays the message, "No retention labels detected, it means you haven't created or published any retention  labels or no content has had a retention label applied.</span></span> <span data-ttu-id="05263-168">保持ラベルの使用を開始するには、</span><span class="sxs-lookup"><span data-stu-id="05263-168">To get started with retention labels, see:</span></span>
>- <span data-ttu-id="05263-169">「[保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-169">[Overview of retention labels](labels.md)</span></span>

## <a name="top-activities-detected"></a><span data-ttu-id="05263-170">検出された上位アクティビティ</span><span class="sxs-lookup"><span data-stu-id="05263-170">Top activities detected</span></span>

<span data-ttu-id="05263-171">このカードでは、機密ラベルが付けられたアイテムに対してユーザーが行う最も一般的な操作の概要が示されます。</span><span class="sxs-lookup"><span data-stu-id="05263-171">This card provides a quick summary of the most common actions that users are taking on the sensitivity labeled items.</span></span> <span data-ttu-id="05263-172">[アクティビティ エクスプローラー](data-classification-activity-explorer.md)を使用すると、ラベル付きコンテンツおよび Windows 10 のエンドポイントにあるコンテンツでの、Microsoft 365 により追跡される 8 つの異なるアクティビティの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="05263-172">You can use the [Activity explorer](data-classification-activity-explorer.md) to drill deep down on eight different activities that Microsoft 365 tracks on labeled content and content that is located on Windows 10 endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="05263-173">"No activity detected" (アクティビティが検出されませんでした) というメッセージがこのカードに表示される場合、ファイルに対して行われたアクティビティがなかったか、ユーザーまたは管理者による監査が有効化されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="05263-173">If this card displays the message, "No activity detected" it means that there's been no activity on the files or that user and admin auditing isn't turned on.</span></span> <span data-ttu-id="05263-174">監査ログをオンにするには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-174">To turn the audit logs on , see:</span></span>
>- [<span data-ttu-id="05263-175">セキュリティ/コンプライアンス センターで監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="05263-175">Search the audit log in security & compliance center</span></span>](search-the-audit-log-in-security-and-compliance.md)

## <a name="sensitivity-and-retention-labeled-data-by-location"></a><span data-ttu-id="05263-176">場所別の機密ラベルおよび保持ラベル付きデータ</span><span class="sxs-lookup"><span data-stu-id="05263-176">Sensitivity and retention labeled data by location</span></span>

<span data-ttu-id="05263-177">データ分類の報告の目的は、どのラベルが付いているアイテムがどこにいくつあるかを確認できるようにすることにあります。</span><span class="sxs-lookup"><span data-stu-id="05263-177">The point of the data classification reporting is to provide visibility into the number of items that have which label as well as their location.</span></span> <span data-ttu-id="05263-178">これらのカードでは、Exchange、SharePoint、OneDrive などにあるラベル付きのアイテムの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05263-178">These cards let you know how many labeled items the are in Exchange, SharePoint, and OneDrive etc.</span></span>

> [!NOTE]
> <span data-ttu-id="05263-179">"No locations detected" (場所が検出されませんでした) というメッセージがこのカードに表示される場合、機密ラベルが作成または発行されていないか、いずれのコンテンツにも保持ラベルが適用されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="05263-179">If this card displays the message, "No locations detected, it means you haven't created or published any sensitivity labels or no content has had a retention label applied.</span></span> <span data-ttu-id="05263-180">機密ラベルの使用を開始するには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05263-180">To get started with sensitivity labels, see:</span></span>
>- [<span data-ttu-id="05263-181">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-181">Sensitivity labels</span></span>](sensitivity-labels.md)

## <a name="see-also"></a><span data-ttu-id="05263-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="05263-182">See also</span></span>

- [<span data-ttu-id="05263-183">ラベル アクティビティを表示する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="05263-183">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="05263-184">ラベル付きコンテンツの表示 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="05263-184">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="05263-185">機密ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-185">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="05263-186">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="05263-186">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="05263-187">機密情報の種類のエンティティ定義</span><span class="sxs-lookup"><span data-stu-id="05263-187">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="05263-188">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="05263-188">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="05263-189">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="05263-189">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
