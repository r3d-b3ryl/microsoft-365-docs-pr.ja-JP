---
title: Web コンテンツ のフィルター処理
description: Microsoft Defender ATP の Web コンテンツ フィルターを使用して、コンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および調整します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、監視、レポート、カード、ドメイン リスト、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dd1b21b306d40ab03fa518f48c8a0bc985191f69
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063723"
---
# <a name="web-content-filtering"></a><span data-ttu-id="86014-104">Web コンテンツ のフィルター処理</span><span class="sxs-lookup"><span data-stu-id="86014-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86014-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="86014-105">**Applies to:**</span></span>
- [<span data-ttu-id="86014-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="86014-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="86014-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86014-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="86014-108">**Web コンテンツ フィルターは現在パブリック プレビュー中です**</span><span class="sxs-lookup"><span data-stu-id="86014-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="86014-109">このプレビュー バージョンはサービス レベル契約なしで提供され、実稼働ワークロードには推奨されません。</span><span class="sxs-lookup"><span data-stu-id="86014-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="86014-110">一部の機能はサポートされていないか、制限された機能を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86014-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="86014-111">詳細については [、「Microsoft Defender for Endpoint プレビュー機能」を参照してください](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="86014-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="86014-112">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="86014-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="86014-113">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="86014-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="86014-114">Web コンテンツ フィルターは [、Microsoft Defender](web-protection-overview.md) for Endpoint の Web 保護機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="86014-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="86014-115">これにより、組織はコンテンツ カテゴリに基づいて Web サイトへのアクセスを追跡および規制できます。</span><span class="sxs-lookup"><span data-stu-id="86014-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="86014-116">これらの Web サイトの多くは悪意のあるものではないが、コンプライアンス規制、帯域幅の使用、その他の懸念により問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86014-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="86014-117">デバイス グループ全体のポリシーを構成して、特定のカテゴリをブロックします。</span><span class="sxs-lookup"><span data-stu-id="86014-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="86014-118">カテゴリをブロックすると、指定したデバイス グループ内のユーザーは、そのカテゴリに関連付けられた URL にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="86014-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="86014-119">ブロックされていないカテゴリの場合、URL は自動的に監査されます。</span><span class="sxs-lookup"><span data-stu-id="86014-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="86014-120">ユーザーは中断することなく URL にアクセスできます。また、アクセス統計を収集して、よりカスタム ポリシーの決定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="86014-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="86014-121">表示しているページ上の要素がブロックされたリソースを呼び出している場合、ユーザーにブロック通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="86014-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="86014-122">Web コンテンツ フィルターは主要な Web ブラウザーで利用できます。ブロックは Windows Defender SmartScreen (Microsoft Edge) とネットワーク保護 (Chrome、Firefox、Brave、Opera) によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="86014-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="86014-123">ブラウザーのサポートの詳細については、「前提条件」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="86014-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="86014-124">利点の概要:</span><span class="sxs-lookup"><span data-stu-id="86014-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="86014-125">ユーザーが、オンプレミスまたは離れた場所を閲覧している場合でも、ブロックされたカテゴリの Web サイトにアクセスするのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="86014-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="86014-126">Microsoft Defender for Endpoint の役割ベースのアクセス制御設定で定義されているデバイス グループを使用して、ユーザーのグループにポリシー [を簡単に展開する](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="86014-126">Conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="86014-127">同じ中央の場所で Web レポートにアクセスし、実際のブロックと Web 使用状況を可視化</span><span class="sxs-lookup"><span data-stu-id="86014-127">Access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="86014-128">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="86014-128">User experience</span></span>

<span data-ttu-id="86014-129">サードパーティがサポートするブラウザーのブロック エクスペリエンスは、ネットワーク保護によって提供されます。これは、ブロックされた接続をユーザーに通知するシステム レベルのトーストを提供します。</span><span class="sxs-lookup"><span data-stu-id="86014-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> 

<span data-ttu-id="86014-130">ブラウザー内での使い方が簡単な場合は、Microsoft Edge の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="86014-130">For a more user-friendly in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86014-131">前提条件</span><span class="sxs-lookup"><span data-stu-id="86014-131">Prerequisites</span></span>

<span data-ttu-id="86014-132">この機能を試す前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="86014-132">Before trying out this feature, make sure you have the following requirements:</span></span>

- <span data-ttu-id="86014-133">Windows 10 Enterprise E5 ライセンスまたは Microsoft 365 E3 + Microsoft 365 E5 セキュリティ アドオン。</span><span class="sxs-lookup"><span data-stu-id="86014-133">Windows 10 Enterprise E5 license OR Microsoft 365 E3 + Microsoft 365 E5 Security add-on.</span></span>
- <span data-ttu-id="86014-134">Microsoft Defender セキュリティ センター ポータルへのアクセス</span><span class="sxs-lookup"><span data-stu-id="86014-134">Access to Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="86014-135">最新の MoCAMP 更新プログラムを使用して Windows 10 Anniversary Update (バージョン 1607) 以降を実行しているデバイス。</span><span class="sxs-lookup"><span data-stu-id="86014-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>

<span data-ttu-id="86014-136">SmartScreen Windows Defenderが有効ではない場合、ネットワーク保護はブロックを引き継ぐ。</span><span class="sxs-lookup"><span data-stu-id="86014-136">If Windows Defender SmartScreen isn't turned on, Network Protection will take over the blocking.</span></span> <span data-ttu-id="86014-137">デバイスで [ネットワーク保護を有効にする](enable-network-protection.md) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="86014-137">It requires [enabling Network Protection](enable-network-protection.md) on the device.</span></span> <span data-ttu-id="86014-138">Chrome、Firefox、Brave、Opera は現在、この機能が有効になっているサードパーティのブラウザーです。</span><span class="sxs-lookup"><span data-stu-id="86014-138">Chrome, Firefox, Brave, and Opera are currently 3rd party browsers in which this feature is enabled.</span></span>

## <a name="data-handling"></a><span data-ttu-id="86014-139">データ処理</span><span class="sxs-lookup"><span data-stu-id="86014-139">Data handling</span></span>

<span data-ttu-id="86014-140">Microsoft Defender for Endpoint データ処理設定の一部として使用する選択した地域 [に従います](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy)。</span><span class="sxs-lookup"><span data-stu-id="86014-140">We will follow whichever region you have elected to use as part of your [Microsoft Defender for Endpoint data handling settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/data-storage-privacy).</span></span> <span data-ttu-id="86014-141">データは、その地域のデータ センターから離れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="86014-141">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="86014-142">さらに、お客様のデータは、データ プロバイダーを含む第三者と共有されることはありません。</span><span class="sxs-lookup"><span data-stu-id="86014-142">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="86014-143">Web コンテンツ フィルターを有効にする</span><span class="sxs-lookup"><span data-stu-id="86014-143">Turn on web content filtering</span></span>

<span data-ttu-id="86014-144">左側のナビゲーション メニューで、[設定] を選択し、[全般 **>機能>選択します**。</span><span class="sxs-lookup"><span data-stu-id="86014-144">From the left-hand navigation menu, select **Settings > General > Advanced Features**.</span></span> <span data-ttu-id="86014-145">Web コンテンツ フィルターのエントリが表示されるまで **下にスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="86014-145">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="86014-146">トグルを [オン] と **[保存\*\*\*\*] の基本設定に切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="86014-146">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="86014-147">Web コンテンツ フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="86014-147">Configure web content filtering policies</span></span>

<span data-ttu-id="86014-148">Web コンテンツ フィルター ポリシーは、どのサイト カテゴリがどのデバイス グループでブロックされるのか指定します。</span><span class="sxs-lookup"><span data-stu-id="86014-148">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="86014-149">ポリシーを管理するには、[Web コンテンツ フィルターの **設定>ルール>に移動します**。</span><span class="sxs-lookup"><span data-stu-id="86014-149">To manage the policies, go to **Settings > Rules > Web content filtering**.</span></span>

<span data-ttu-id="86014-150">フィルターを使用して、特定のブロックされたカテゴリを含むポリシー、または特定のデバイス グループに適用されるポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="86014-150">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="86014-151">ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="86014-151">Create a policy</span></span>

<span data-ttu-id="86014-152">新しいポリシーを追加するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="86014-152">To add a new policy:</span></span>

1. <span data-ttu-id="86014-153">[設定 **] の** [Web コンテンツ フィルター] **ページで [ポリシーの** 追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86014-153">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>
2. <span data-ttu-id="86014-154">名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="86014-154">Specify a name.</span></span>
3. <span data-ttu-id="86014-155">ブロックするカテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="86014-155">Select the categories to block.</span></span> <span data-ttu-id="86014-156">展開アイコンを使用して、各親カテゴリを完全に展開し、特定の Web コンテンツ カテゴリを選択します。</span><span class="sxs-lookup"><span data-stu-id="86014-156">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>
4. <span data-ttu-id="86014-157">ポリシー スコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="86014-157">Specify the policy scope.</span></span> <span data-ttu-id="86014-158">ポリシーを適用する場所を指定するデバイス グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="86014-158">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="86014-159">選択したデバイス グループ内のデバイスだけが、選択したカテゴリの Web サイトにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="86014-159">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>
5. <span data-ttu-id="86014-160">概要を確認し、ポリシーを保存します。</span><span class="sxs-lookup"><span data-stu-id="86014-160">Review the summary and save the policy.</span></span> <span data-ttu-id="86014-161">ポリシーの更新には、選択したデバイスに適用するために最大 2 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="86014-161">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

<span data-ttu-id="86014-162">ヒント: デバイス グループでカテゴリを選択せずにポリシーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="86014-162">Tip: You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="86014-163">このアクションは、ブロック ポリシーを作成する前にユーザーの動作を理解するのに役立つ監査専用ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="86014-163">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>

>[!NOTE]
><span data-ttu-id="86014-164">ポリシーを削除したり、デバイス グループを同時に変更したりすると、ポリシーの展開が遅れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86014-164">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>

>[!IMPORTANT]
><span data-ttu-id="86014-165">"未分類" カテゴリをブロックすると、予期しない結果が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86014-165">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="86014-166">特定の Web サイトを許可する</span><span class="sxs-lookup"><span data-stu-id="86014-166">Allow specific websites</span></span>

<span data-ttu-id="86014-167">Web コンテンツ フィルターでブロックされたカテゴリを上書きして、カスタム インジケーター ポリシーを作成して 1 つのサイトを許可できます。</span><span class="sxs-lookup"><span data-stu-id="86014-167">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="86014-168">カスタム インジケーター ポリシーは、Web コンテンツ フィルター ポリシーが問題のデバイス グループに適用されると、そのポリシーに取って代えられます。</span><span class="sxs-lookup"><span data-stu-id="86014-168">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="86014-169">[設定インジケーター URL/ドメインの追加アイテム] に移動して、Microsoft Defender セキュリティ センターでカスタム インジケーター  >    >  **を**  >  **作成する**</span><span class="sxs-lookup"><span data-stu-id="86014-169">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**</span></span>
2. <span data-ttu-id="86014-170">サイトのドメインを入力する</span><span class="sxs-lookup"><span data-stu-id="86014-170">Enter the domain of the site</span></span>
3. <span data-ttu-id="86014-171">ポリシー アクションを [許可] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="86014-171">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="86014-172">不正確なレポート</span><span class="sxs-lookup"><span data-stu-id="86014-172">Reporting inaccuracies</span></span>

<span data-ttu-id="86014-173">誤って分類されたドメインが発生した場合は、[Web コンテンツ フィルター レポート] ページから不正確な情報を直接報告できます。</span><span class="sxs-lookup"><span data-stu-id="86014-173">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="86014-174">この機能は、新しい Microsoft 365 セキュリティ センター (security.microsoft.com) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="86014-174">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="86014-175">不正確な情報を報告するには、[Web コンテンツ フィルターの詳細>ドメイン> **レポート] >移動します**。</span><span class="sxs-lookup"><span data-stu-id="86014-175">To report an inaccuracy, navigate to **Reports > Web protection > Web Content Filtering Details > Domains**.</span></span> <span data-ttu-id="86014-176">Web コンテンツ フィルター レポートの [ドメイン] タブに、各ドメインの横に省略記号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="86014-176">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="86014-177">この省略記号にカーソルを合わせると、[ **不正確なレポート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="86014-177">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="86014-178">パネルが開き、優先度を選択し、再分類の推奨カテゴリなどの詳細を追加できます。</span><span class="sxs-lookup"><span data-stu-id="86014-178">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="86014-179">フォームが完成したら、[送信] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="86014-179">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="86014-180">チームは 1 営業日以内に要求を確認します。</span><span class="sxs-lookup"><span data-stu-id="86014-180">Our team will review the request within one business day.</span></span> <span data-ttu-id="86014-181">ブロック解除を直ちに行う場合は、カスタム許可 [インジケーターを作成します](indicator-ip-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="86014-181">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="86014-182">Web コンテンツ フィルター カードと詳細</span><span class="sxs-lookup"><span data-stu-id="86014-182">Web content filtering cards and details</span></span>

<span data-ttu-id="86014-183">[ **レポートと web >]** を選択して、Web コンテンツ フィルターと Web 脅威保護に関する情報を含むカードを表示します。</span><span class="sxs-lookup"><span data-stu-id="86014-183">Select **Reports > Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="86014-184">次のカードは、Web コンテンツ フィルターに関する概要情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="86014-184">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="86014-185">カテゴリ別の Web アクティビティ</span><span class="sxs-lookup"><span data-stu-id="86014-185">Web activity by category</span></span>

<span data-ttu-id="86014-186">このカードには、アクセス試行回数の増加または減少が最も大きい親 Web コンテンツ カテゴリが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="86014-186">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="86014-187">過去 30 日間、3 か月、または 6 か月の組織の Web アクティビティ パターンの大幅な変化を理解します。</span><span class="sxs-lookup"><span data-stu-id="86014-187">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="86014-188">詳細を表示するには、カテゴリ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="86014-188">Select a category name to view more information.</span></span>

<span data-ttu-id="86014-189">この機能を使用した最初の 30 日間で、組織にはこの情報を表示するのに十分なデータが含めなかった可能性があります。</span><span class="sxs-lookup"><span data-stu-id="86014-189">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![カテゴリ カード別の Web アクティビティのイメージ](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="86014-191">Web コンテンツ フィルターの概要カード</span><span class="sxs-lookup"><span data-stu-id="86014-191">Web content filtering  summary card</span></span>

<span data-ttu-id="86014-192">このカードは、異なる親 Web コンテンツ カテゴリに対するブロックされたアクセス試行の分布を表示します。</span><span class="sxs-lookup"><span data-stu-id="86014-192">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="86014-193">色付きバーのいずれかを選択して、特定の親 Web カテゴリに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="86014-193">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Web コンテンツ フィルターの概要カードのイメージ](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="86014-195">Web アクティビティの概要カード</span><span class="sxs-lookup"><span data-stu-id="86014-195">Web activity summary card</span></span>

<span data-ttu-id="86014-196">このカードには、すべての URL の Web コンテンツに対する要求の総数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="86014-196">This card displays the total number of requests for web content in all URLs.</span></span>

![Web アクティビティの概要カードの画像](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="86014-198">カードの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="86014-198">View card details</span></span>

<span data-ttu-id="86014-199">カード内のグラフ **からテーブル** 行または色付きバーを選択すると、各カードのレポートの詳細にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="86014-199">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="86014-200">各カードのレポートの詳細ページには、Web コンテンツ カテゴリ、Web サイト ドメイン、デバイス グループに関する広範な統計データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="86014-200">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Web 保護レポートの詳細の画像](images/web-protection-report-details.png)

- <span data-ttu-id="86014-202">**Web カテゴリ**: 組織内でアクセス試行を行った Web コンテンツ カテゴリを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="86014-202">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="86014-203">特定のカテゴリを選択してサマリー フライアウトを開きます。</span><span class="sxs-lookup"><span data-stu-id="86014-203">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="86014-204">**ドメイン**: 組織でアクセスまたはブロックされた Web ドメインを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="86014-204">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="86014-205">特定のドメインを選択して、そのドメインに関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="86014-205">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="86014-206">**デバイス グループ**: 組織で Web アクティビティを生成したデバイス グループの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="86014-206">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="86014-207">ページの左上にある時間範囲フィルターを使用して、期間を選択します。</span><span class="sxs-lookup"><span data-stu-id="86014-207">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="86014-208">情報をフィルター処理したり、列をカスタマイズしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="86014-208">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="86014-209">行を選択して、選択したアイテムに関するさらに詳しい情報を含むフライアウト ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="86014-209">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="86014-210">エラーと問題</span><span class="sxs-lookup"><span data-stu-id="86014-210">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="86014-211">このプレビューの制限事項と既知の問題</span><span class="sxs-lookup"><span data-stu-id="86014-211">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="86014-212">デバイスの OS 構成が Server (cmd > Systeminfo > OS 構成) の場合にのみ、Microsoft Edge がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="86014-212">Only Microsoft Edge is supported if your device's OS configuration is Server (cmd > Systeminfo > OS Configuration).</span></span> <span data-ttu-id="86014-213">ネットワーク保護は、サポートされているサードパーティのブラウザー間のトラフィックをセキュリティ保護するサーバー デバイスの検査モードでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="86014-213">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="86014-214">割り当てられていないデバイスでは、レポート内に正しくないデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="86014-214">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="86014-215">[デバイス グループのレポート>] ピボットに、空白の [デバイス グループ] フィールドを含む行が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="86014-215">In the Report details > Device groups pivot, you may see a row with a blank Device Group field.</span></span> <span data-ttu-id="86014-216">このグループには、割り当てられていないデバイスが指定したグループに入る前に含まれる。</span><span class="sxs-lookup"><span data-stu-id="86014-216">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="86014-217">この行のレポートには、デバイスの正確な数やアクセス数が含まれているとは思えない。</span><span class="sxs-lookup"><span data-stu-id="86014-217">The report for this row may not contain an accurate count of devices or access counts.</span></span>

## <a name="related-topics"></a><span data-ttu-id="86014-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="86014-218">Related topics</span></span>

- [<span data-ttu-id="86014-219">Web 保護の概要</span><span class="sxs-lookup"><span data-stu-id="86014-219">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="86014-220">Web 脅威保護</span><span class="sxs-lookup"><span data-stu-id="86014-220">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="86014-221">Web セキュリティの監視</span><span class="sxs-lookup"><span data-stu-id="86014-221">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="86014-222">Web の脅威に対応する</span><span class="sxs-lookup"><span data-stu-id="86014-222">Respond to web threats</span></span>](web-protection-response.md)
