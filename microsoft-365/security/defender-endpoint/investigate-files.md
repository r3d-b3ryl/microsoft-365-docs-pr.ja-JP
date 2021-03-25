---
title: Microsoft Defender for Endpoint ファイルの調査
description: 調査オプションを使用して、アラート、動作、またはイベントに関連付けられたファイルの詳細を取得します。
keywords: 調査、調査、ファイル、悪意のあるアクティビティ、攻撃の動機、深い分析、深い分析レポート
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b509ab6d0c3e5183b99173e950198bad0ccd8ee0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186067"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="4506c-104">Microsoft Defender for Endpoint アラートに関連付けられたファイルを調査する</span><span class="sxs-lookup"><span data-stu-id="4506c-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4506c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4506c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4506c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4506c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4506c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4506c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="4506c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="4506c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4506c-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="4506c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="4506c-110">特定のアラート、動作、またはイベントに関連付けられたファイルの詳細を調査して、ファイルに悪意のあるアクティビティが発生したかどうかを判断し、攻撃の動機を特定し、侵害の潜在的な範囲を理解します。</span><span class="sxs-lookup"><span data-stu-id="4506c-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="4506c-111">特定のファイルの詳細なプロファイル ページにアクセスするには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="4506c-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="4506c-112">たとえば、検索機能を使用したり、アラート プロセス ツリー 、**インシデント** グラフ、アーティファクト タイムラインからのリンクをクリックしたり、デバイス タイムラインに一覧表示されているイベント **を選択できます**。 </span><span class="sxs-lookup"><span data-stu-id="4506c-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="4506c-113">詳細なプロファイル ページに移動したら、新しい [ファイル] ページを切り替えて、新しいページ レイアウトと古いページ レイアウト **を切り替えることができます**。</span><span class="sxs-lookup"><span data-stu-id="4506c-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="4506c-114">この記事の残りの部分では、新しいページ レイアウトについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4506c-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="4506c-115">ファイル ビューでは、次のセクションから情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4506c-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="4506c-116">ファイルの詳細, マルウェアの検出, ファイルの普及率</span><span class="sxs-lookup"><span data-stu-id="4506c-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="4506c-117">深い分析</span><span class="sxs-lookup"><span data-stu-id="4506c-117">Deep analysis</span></span>
- <span data-ttu-id="4506c-118">アラート</span><span class="sxs-lookup"><span data-stu-id="4506c-118">Alerts</span></span>
- <span data-ttu-id="4506c-119">組織内で観察される</span><span class="sxs-lookup"><span data-stu-id="4506c-119">Observed in organization</span></span>
- <span data-ttu-id="4506c-120">深い分析</span><span class="sxs-lookup"><span data-stu-id="4506c-120">Deep analysis</span></span>
- <span data-ttu-id="4506c-121">ファイル名</span><span class="sxs-lookup"><span data-stu-id="4506c-121">File names</span></span>

<span data-ttu-id="4506c-122">このページからファイルに対してアクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="4506c-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="4506c-123">ファイル操作</span><span class="sxs-lookup"><span data-stu-id="4506c-123">File actions</span></span>

<span data-ttu-id="4506c-124">プロファイル ページの上部、ファイル情報カードの上。</span><span class="sxs-lookup"><span data-stu-id="4506c-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="4506c-125">ここで実行できるアクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4506c-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="4506c-126">停止と検疫</span><span class="sxs-lookup"><span data-stu-id="4506c-126">Stop and quarantine</span></span>
- <span data-ttu-id="4506c-127">インジケーターの追加および編集</span><span class="sxs-lookup"><span data-stu-id="4506c-127">Add/edit indicator</span></span>
- <span data-ttu-id="4506c-128">ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="4506c-128">Download file</span></span>
- <span data-ttu-id="4506c-129">脅威の専門家に相談する</span><span class="sxs-lookup"><span data-stu-id="4506c-129">Consult a threat expert</span></span>
- <span data-ttu-id="4506c-130">アクション センター</span><span class="sxs-lookup"><span data-stu-id="4506c-130">Action center</span></span>

<span data-ttu-id="4506c-131">これらのアクションの詳細については、「ファイルに [対して応答アクションを実行する」を参照してください](respond-file-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="4506c-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="4506c-132">ファイルの詳細、マルウェア検出、ファイルの普及率</span><span class="sxs-lookup"><span data-stu-id="4506c-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="4506c-133">ファイルの詳細、インシデント、マルウェア検出、およびファイル普及率カードには、ファイルに関するさまざまな属性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4506c-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="4506c-134">ファイルの MD5、ウイルスの合計検出率、使用可能な場合は Microsoft Defender AV 検出、ファイルの普及率などの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4506c-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="4506c-135">ファイルの有病率カードは、組織内および世界中のデバイスでファイルが見られた場所を示します。</span><span class="sxs-lookup"><span data-stu-id="4506c-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="4506c-136">異なるユーザーは、ファイル普及カードの組織セクションのデバイスに異なる値を表示する場合があります。</span><span class="sxs-lookup"><span data-stu-id="4506c-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="4506c-137">これは、ユーザーが持つ RBAC スコープに基づいて情報がカードに表示されるためです。</span><span class="sxs-lookup"><span data-stu-id="4506c-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="4506c-138">つまり、ユーザーが特定のデバイス セットで表示を許可されている場合、それらのデバイスに対するファイル組織の普及率だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4506c-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![ファイル情報のイメージ](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="4506c-140">アラート</span><span class="sxs-lookup"><span data-stu-id="4506c-140">Alerts</span></span>

<span data-ttu-id="4506c-141">[ **アラート]** タブには、ファイルに関連付けられているアラートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4506c-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="4506c-142">このリストには、影響を受けるデバイスが属するデバイス グループがある場合を除き、アラート キューと同じ情報の多くが含まれる。</span><span class="sxs-lookup"><span data-stu-id="4506c-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="4506c-143">列ヘッダーの上にあるツールバーから [列のカスタマイズ] を選択すると、表示される情報の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4506c-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![ファイル セクションに関連するアラートのイメージ](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="4506c-145">組織内で観察される</span><span class="sxs-lookup"><span data-stu-id="4506c-145">Observed in organization</span></span>

<span data-ttu-id="4506c-146">[ **組織で観察]** タブを使用すると、日付範囲を指定して、ファイルで観察されたデバイスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4506c-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="4506c-147">このタブには、最大 100 台のデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4506c-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="4506c-148">ファイルを _含む_ すべてのデバイスを表示するには、タブの列ヘッダーの上にあるアクションメニューから [エクスポート] を選択して、タブを CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="4506c-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![ファイルを含む最新の観測デバイスのイメージ](images/atp-observed-machines.png)

<span data-ttu-id="4506c-150">スライダーまたは範囲セレクターを使用して、ファイルに関連するイベントを確認する期間をすばやく指定します。</span><span class="sxs-lookup"><span data-stu-id="4506c-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="4506c-151">タイム ウィンドウは、1 日に限り小さく指定できます。</span><span class="sxs-lookup"><span data-stu-id="4506c-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="4506c-152">これにより、その時点でその IP アドレスと通信したファイルだけが表示され、不要なスクロールと検索が大幅に削減されます。</span><span class="sxs-lookup"><span data-stu-id="4506c-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="4506c-153">深い分析</span><span class="sxs-lookup"><span data-stu-id="4506c-153">Deep analysis</span></span>

<span data-ttu-id="4506c-154">[**深い分析**] タブ [](respond-file-alerts.md#deep-analysis)を使用すると、ファイルを詳細に分析するためにファイルを提出し、ファイルの動作の詳細と、ファイルが組織に与える影響を明らかにできます。</span><span class="sxs-lookup"><span data-stu-id="4506c-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="4506c-155">ファイルを送信すると、結果が得られたら、このタブに詳細分析レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4506c-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="4506c-156">深い分析で何も見つからなかった場合、レポートは空で、結果領域は空白のままです。</span><span class="sxs-lookup"><span data-stu-id="4506c-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![[詳細分析] タブの画像](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="4506c-158">ファイル名</span><span class="sxs-lookup"><span data-stu-id="4506c-158">File names</span></span>

<span data-ttu-id="4506c-159">[ **ファイル名] タブ** には、組織でファイルが使用されているすべての名前が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4506c-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![[ファイル名] タブのイメージ](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="4506c-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="4506c-161">Related topics</span></span>

- [<span data-ttu-id="4506c-162">Microsoft Defender for Endpoint キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="4506c-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="4506c-163">エンドポイント通知の Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="4506c-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="4506c-164">Microsoft Defender for Endpoint アラートの調査</span><span class="sxs-lookup"><span data-stu-id="4506c-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="4506c-165">Microsoft Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="4506c-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="4506c-166">Microsoft Defender for Endpoint アラートに関連付けられている IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="4506c-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="4506c-167">Microsoft Defender for Endpoint アラートに関連付けられているドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="4506c-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="4506c-168">Microsoft Defender for Endpoint のユーザー アカウントを調査する</span><span class="sxs-lookup"><span data-stu-id="4506c-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="4506c-169">ファイルに対して応答アクションを実行する</span><span class="sxs-lookup"><span data-stu-id="4506c-169">Take response actions on a file</span></span>](respond-file-alerts.md)
