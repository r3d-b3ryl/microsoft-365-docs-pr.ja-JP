---
title: Web コンテンツ フィルタリング
description: Microsoft Defender for Endpoint の Web コンテンツ フィルターを使用して、コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、監視、レポート、カード、ドメイン リスト、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c7b39b600af2fed130a0b78a590740a8bc063f50
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861697"
---
# <a name="web-content-filtering"></a><span data-ttu-id="3ee7c-104">Web コンテンツ フィルタリング</span><span class="sxs-lookup"><span data-stu-id="3ee7c-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3ee7c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3ee7c-105">**Applies to:**</span></span>
- [<span data-ttu-id="3ee7c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3ee7c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3ee7c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ee7c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="3ee7c-108">**Web コンテンツ フィルターは現在パブリック プレビュー中です**</span><span class="sxs-lookup"><span data-stu-id="3ee7c-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="3ee7c-109">このプレビュー バージョンはサービス レベル契約なしで提供され、実稼働ワークロードには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="3ee7c-110">一部の機能はサポートされていないか、制限された機能を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="3ee7c-111">詳細については [、「Microsoft Defender for Endpoint プレビュー機能」を参照してください](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

> [!TIP]
> <span data-ttu-id="3ee7c-112">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="3ee7c-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3ee7c-113">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="3ee7c-114">Web コンテンツ フィルターは [、Microsoft Defender](web-protection-overview.md) for Endpoint の Web 保護機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3ee7c-115">これにより、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="3ee7c-116">これらの Web サイトの多くは悪意のあるものではないが、コンプライアンス規制、帯域幅の使用、その他の懸念により問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="3ee7c-117">デバイス グループ全体のポリシーを構成して、特定のカテゴリをブロックします。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="3ee7c-118">カテゴリをブロックすると、指定したデバイス グループ内のユーザーは、そのカテゴリに関連付けられた URL にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="3ee7c-119">ブロックされていないカテゴリの場合、URL は自動的に監査されます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="3ee7c-120">ユーザーは中断することなく URL にアクセスできます。また、アクセス統計を収集して、よりカスタム ポリシーの決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="3ee7c-121">表示しているページ上の要素がブロックされたリソースを呼び出している場合、ユーザーにブロック通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="3ee7c-122">Web コンテンツ フィルターは主要な Web ブラウザーで利用できます。ブロックは Windows Defender SmartScreen (Microsoft Edge) とネットワーク保護 (Chrome、Firefox、Brave、Opera) によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="3ee7c-123">ブラウザーのサポートの詳細については、「前提条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="3ee7c-124">利点の概要:</span><span class="sxs-lookup"><span data-stu-id="3ee7c-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="3ee7c-125">ユーザーが、オンプレミスまたは離れた場所を閲覧している場合でも、ブロックされたカテゴリの Web サイトにアクセスするのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="3ee7c-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="3ee7c-126">セキュリティ チームは、Microsoft Defender for Endpoint の役割ベースのアクセス制御設定で定義されているデバイス グループを使用して、ユーザーのグループにポリシーを簡単に [展開できます。](/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="3ee7c-126">Your security team can conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="3ee7c-127">セキュリティ チームは、同じ中央の場所にある Web レポートにアクセスし、実際のブロックと Web 使用状況を可視化できます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-127">Your security team can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="3ee7c-128">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="3ee7c-128">User experience</span></span>

<span data-ttu-id="3ee7c-129">サードパーティがサポートするブラウザーのブロック エクスペリエンスは、ネットワーク保護によって提供されます。これは、ブロックされた接続をユーザーに通知するシステム レベルのトーストを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> <span data-ttu-id="3ee7c-130">ユーザーフレンドリーでブラウザー内でのエクスペリエンスを向上するには、ユーザーエクスペリエンスの使用Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-130">For a more user-friendly, in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ee7c-131">前提条件</span><span class="sxs-lookup"><span data-stu-id="3ee7c-131">Prerequisites</span></span>

<span data-ttu-id="3ee7c-132">この機能を試す前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-132">Before trying out this feature, make sure you meet the following requirements:</span></span>

- <span data-ttu-id="3ee7c-133">Windows 10 EnterpriseE5、Microsoft 365 E5、Microsoft 365 E5 Security、Microsoft 365 E3 + Microsoft 365 E5 Securityまたは Microsoft Defender for Endpoint スタンドアロン ライセンス。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security add-on or the Microsoft Defender for Endpoint standalone license.</span></span> 
- <span data-ttu-id="3ee7c-134">ポータルへのMicrosoft Defender セキュリティ センターアクセス ( https://securitycenter.windows.com) .</span><span class="sxs-lookup"><span data-stu-id="3ee7c-134">Access to Microsoft Defender Security Center portal (https://securitycenter.windows.com).</span></span>
- <span data-ttu-id="3ee7c-135">Anniversary update (Windows 10 1607) 以降で最新の MoCAMP 更新プログラムを使用して実行されているデバイス。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>
- <span data-ttu-id="3ee7c-136">Windows DefenderSmartScreen とネットワーク保護が有効です。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-136">Windows Defender SmartScreen and Network protection enabled.</span></span>


## <a name="data-handling"></a><span data-ttu-id="3ee7c-137">データの処理</span><span class="sxs-lookup"><span data-stu-id="3ee7c-137">Data handling</span></span>

<span data-ttu-id="3ee7c-138">データは、Microsoft Defender for Endpoint データ処理設定の一部として選択された領域 [に格納されます](data-storage-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-138">Data is stored in the region that was selected as part of your [Microsoft Defender for Endpoint data handling settings](data-storage-privacy.md).</span></span> <span data-ttu-id="3ee7c-139">データは、その地域のデータ センターから離れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-139">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="3ee7c-140">さらに、お客様のデータは、データ プロバイダーを含む第三者と共有されることはありません。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-140">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="3ee7c-141">Web コンテンツ フィルターを有効にする</span><span class="sxs-lookup"><span data-stu-id="3ee7c-141">Turn on web content filtering</span></span>

<span data-ttu-id="3ee7c-142">左側のナビゲーション メニューで、[全般高度な機能]**設定**  >  **を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-142">From the left-hand navigation menu, select **Settings** > **General** > **Advanced Features**.</span></span> <span data-ttu-id="3ee7c-143">Web コンテンツ フィルターのエントリが表示されるまで **下にスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-143">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="3ee7c-144">トグルを [オン] と **[保存\*\*\*\*] の基本設定に切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-144">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="3ee7c-145">Web コンテンツ フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="3ee7c-145">Configure web content filtering policies</span></span>

<span data-ttu-id="3ee7c-146">Web コンテンツ フィルター ポリシーは、どのサイト カテゴリがどのデバイス グループでブロックされるのか指定します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-146">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="3ee7c-147">ポリシーを管理するには、[ルール] **Web 設定**  >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-147">To manage the policies, go to **Settings** > **Rules** > **Web content filtering**.</span></span>

<span data-ttu-id="3ee7c-148">フィルターを使用して、特定のブロックされたカテゴリを含むポリシー、または特定のデバイス グループに適用されるポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-148">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="3ee7c-149">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="3ee7c-149">Create a policy</span></span>

<span data-ttu-id="3ee7c-150">新しいポリシーを追加するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-150">To add a new policy:</span></span>

1. <span data-ttu-id="3ee7c-151">[Web **コンテンツ フィルター]** ページの **[ポリシーの追加] を選択\*\*\*\*設定。**</span><span class="sxs-lookup"><span data-stu-id="3ee7c-151">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>

2. <span data-ttu-id="3ee7c-152">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-152">Specify a name.</span></span>

3. <span data-ttu-id="3ee7c-153">ブロックするカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-153">Select the categories to block.</span></span> <span data-ttu-id="3ee7c-154">展開アイコンを使用して、各親カテゴリを完全に展開し、特定の Web コンテンツ カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-154">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>

4. <span data-ttu-id="3ee7c-155">ポリシー スコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-155">Specify the policy scope.</span></span> <span data-ttu-id="3ee7c-156">ポリシーを適用する場所を指定するデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-156">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="3ee7c-157">選択したデバイス グループ内のデバイスだけが、選択したカテゴリの Web サイトにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-157">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>

5. <span data-ttu-id="3ee7c-158">概要を確認し、ポリシーを保存します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-158">Review the summary and save the policy.</span></span> <span data-ttu-id="3ee7c-159">ポリシーの更新には、選択したデバイスに適用するために最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-159">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

> [!NOTE]
> - <span data-ttu-id="3ee7c-160">デバイス グループでカテゴリを選択せずにポリシーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-160">You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="3ee7c-161">このアクションは、ブロック ポリシーを作成する前にユーザーの動作を理解するのに役立つ監査専用ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-161">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>
> - <span data-ttu-id="3ee7c-162">ポリシーを削除したり、デバイス グループを同時に変更したりすると、ポリシーの展開が遅れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-162">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>
> - <span data-ttu-id="3ee7c-163">"未分類" カテゴリをブロックすると、予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-163">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="3ee7c-164">特定の Web サイトを許可する</span><span class="sxs-lookup"><span data-stu-id="3ee7c-164">Allow specific websites</span></span>

<span data-ttu-id="3ee7c-165">Web コンテンツ フィルターでブロックされたカテゴリを上書きして、カスタム インジケーター ポリシーを作成して 1 つのサイトを許可できます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-165">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="3ee7c-166">カスタム インジケーター ポリシーは、Web コンテンツ フィルター ポリシーが問題のデバイス グループに適用されると、そのポリシーに取って代えられます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-166">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="3ee7c-167">[インジケーターの URL/ドメインの追加] Microsoft Defender セキュリティ センターにアクセスして、設定インジケーター  >    >  **を**  >  **作成します**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-167">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**.</span></span>

2. <span data-ttu-id="3ee7c-168">サイトのドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-168">Enter the domain of the site.</span></span>

3. <span data-ttu-id="3ee7c-169">ポリシー アクションを [許可] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-169">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="3ee7c-170">不正確なレポート</span><span class="sxs-lookup"><span data-stu-id="3ee7c-170">Reporting inaccuracies</span></span>

<span data-ttu-id="3ee7c-171">誤って分類されたドメインが発生した場合は、[Web コンテンツ フィルター レポート] ページから不正確な情報を直接報告できます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-171">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="3ee7c-172">この機能は、新しいセキュリティ センター (Microsoft 365) でのみ security.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-172">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="3ee7c-173">不正確な情報を報告するには、[レポート Web保護 Web コンテンツ フィルターの詳細ドメイン]  >    >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-173">To report an inaccuracy, navigate to **Reports** > **Web protection** > **Web Content Filtering Details** > **Domains**.</span></span> <span data-ttu-id="3ee7c-174">Web コンテンツ フィルター レポートの [ドメイン] タブに、各ドメインの横に省略記号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-174">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="3ee7c-175">この省略記号にカーソルを合わせると、[ **不正確なレポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-175">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="3ee7c-176">パネルが開き、優先度を選択し、再分類の推奨カテゴリなどの詳細を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-176">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="3ee7c-177">フォームが完成したら、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-177">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="3ee7c-178">チームは 1 営業日以内に要求を確認します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-178">Our team will review the request within one business day.</span></span> <span data-ttu-id="3ee7c-179">ブロック解除を直ちに行う場合は、カスタム許可 [インジケーターを作成します](indicator-ip-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-179">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="3ee7c-180">Web コンテンツ フィルター カードと詳細</span><span class="sxs-lookup"><span data-stu-id="3ee7c-180">Web content filtering cards and details</span></span>

<span data-ttu-id="3ee7c-181">[**レポート**  >  **Web 保護] を** 選択して、Web コンテンツ フィルターと Web 脅威保護に関する情報を含むカードを表示します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-181">Select **Reports** > **Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="3ee7c-182">次のカードは、Web コンテンツ フィルターに関する概要情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-182">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="3ee7c-183">カテゴリ別の Web アクティビティ</span><span class="sxs-lookup"><span data-stu-id="3ee7c-183">Web activity by category</span></span>

<span data-ttu-id="3ee7c-184">このカードには、アクセス試行回数の増加または減少が最も大きい親 Web コンテンツ カテゴリが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-184">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="3ee7c-185">過去 30 日間、3 か月、または 6 か月の組織の Web アクティビティ パターンの大幅な変化を理解します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-185">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="3ee7c-186">詳細を表示するには、カテゴリ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-186">Select a category name to view more information.</span></span>

<span data-ttu-id="3ee7c-187">この機能を使用した最初の 30 日間で、組織にはこの情報を表示するのに十分なデータが含めなかった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-187">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![カテゴリ カード別の Web アクティビティのイメージ](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="3ee7c-189">Web コンテンツ フィルターの概要カード</span><span class="sxs-lookup"><span data-stu-id="3ee7c-189">Web content filtering  summary card</span></span>

<span data-ttu-id="3ee7c-190">このカードは、異なる親 Web コンテンツ カテゴリに対するブロックされたアクセス試行の分布を表示します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-190">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="3ee7c-191">色付きバーのいずれかを選択して、特定の親 Web カテゴリに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-191">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Web コンテンツ フィルターの概要カードのイメージ](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="3ee7c-193">Web アクティビティの概要カード</span><span class="sxs-lookup"><span data-stu-id="3ee7c-193">Web activity summary card</span></span>

<span data-ttu-id="3ee7c-194">このカードには、すべての URL の Web コンテンツに対する要求の総数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-194">This card displays the total number of requests for web content in all URLs.</span></span>

![Web アクティビティの概要カードの画像](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="3ee7c-196">カードの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="3ee7c-196">View card details</span></span>

<span data-ttu-id="3ee7c-197">カード内のグラフ **からテーブル** 行または色付きバーを選択すると、各カードのレポートの詳細にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-197">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="3ee7c-198">各カードのレポートの詳細ページには、Web コンテンツ カテゴリ、Web サイト ドメイン、デバイス グループに関する広範な統計データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-198">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Web 保護レポートの詳細の画像](images/web-protection-report-details.png)

- <span data-ttu-id="3ee7c-200">**Web カテゴリ**: 組織内でアクセス試行を行った Web コンテンツ カテゴリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-200">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="3ee7c-201">特定のカテゴリを選択してサマリー フライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-201">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="3ee7c-202">**ドメイン**: 組織でアクセスまたはブロックされた Web ドメインを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-202">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="3ee7c-203">特定のドメインを選択して、そのドメインに関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-203">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="3ee7c-204">**デバイス グループ**: 組織で Web アクティビティを生成したデバイス グループの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-204">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="3ee7c-205">ページの左上にある時間範囲フィルターを使用して、期間を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-205">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="3ee7c-206">情報をフィルター処理したり、列をカスタマイズしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-206">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="3ee7c-207">行を選択して、選択したアイテムに関するさらに詳しい情報を含むフライアウト ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-207">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="3ee7c-208">エラーと問題</span><span class="sxs-lookup"><span data-stu-id="3ee7c-208">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="3ee7c-209">このプレビューの制限事項と既知の問題</span><span class="sxs-lookup"><span data-stu-id="3ee7c-209">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="3ee7c-210">デバイスMicrosoft Edgeの OS 構成が Server **(cmd**  >  **Systeminfo**  >  **OS Configuration)** の場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-210">Only Microsoft Edge is supported if your device's OS configuration is Server (**cmd** > **Systeminfo** > **OS Configuration**).</span></span> <span data-ttu-id="3ee7c-211">ネットワーク保護は、サポートされているサードパーティのブラウザー間のトラフィックをセキュリティ保護するサーバー デバイスの検査モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-211">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="3ee7c-212">割り当てられていないデバイスでは、レポート内に正しくないデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-212">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="3ee7c-213">[レポートの **詳細]**[デバイス グループ] ピボットに、空白の [デバイス グループ] フィールド  >  を含む行が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-213">In the **Report details** > **Device groups** pivot, you might see a row with a blank Device Group field.</span></span> <span data-ttu-id="3ee7c-214">このグループには、割り当てられていないデバイスが指定したグループに入る前に含まれる。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-214">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="3ee7c-215">この行のレポートには、デバイスの正確な数やアクセス数が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-215">The report for this row might not contain an accurate count of devices or access counts.</span></span>

- <span data-ttu-id="3ee7c-216">Web コンテンツ フィルター レポートは、現在、上位 5,000 レコードの表示に制限されています。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-216">Web Content Filtering reports are currently limited to showing the top 5000 records.</span></span> <span data-ttu-id="3ee7c-217">たとえば、ドメイン レポートには、該当する場合、特定のフィルター クエリの上位 5000 ドメインの最大数だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ee7c-217">For example, the Domains report will only show a maximum of the top 5000 domains for a given filter query, if applicable.</span></span> 



- [<span data-ttu-id="3ee7c-218">Web 保護の概要</span><span class="sxs-lookup"><span data-stu-id="3ee7c-218">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="3ee7c-219">Web の脅威に対する保護</span><span class="sxs-lookup"><span data-stu-id="3ee7c-219">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="3ee7c-220">Web セキュリティの監視</span><span class="sxs-lookup"><span data-stu-id="3ee7c-220">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="3ee7c-221">Web の脅威への対応</span><span class="sxs-lookup"><span data-stu-id="3ee7c-221">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="3ee7c-222">ネットワーク保護の要件</span><span class="sxs-lookup"><span data-stu-id="3ee7c-222">Requirements for Network Protection</span></span>](web-content-filtering.md)

