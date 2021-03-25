---
title: インジケーターの管理
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュ、IP アドレス、URL、またはドメインのインジケーターを管理します。
keywords: インポート、インジケーター、リスト、ioc、csv、manage、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185947"
---
# <a name="manage-indicators"></a><span data-ttu-id="9a7f3-104">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="9a7f3-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9a7f3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-105">**Applies to:**</span></span>
- [<span data-ttu-id="9a7f3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9a7f3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9a7f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a7f3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="9a7f3-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="9a7f3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9a7f3-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="9a7f3-110">ナビゲーション ウィンドウで、[設定インジケーター]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="9a7f3-111">管理するエンティティの種類のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="9a7f3-112">インジケーターの詳細を更新し、[保存]**を** クリックするか、一覧からエンティティを削除する場合は [削除] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="9a7f3-113">IoC のリストのインポート</span><span class="sxs-lookup"><span data-stu-id="9a7f3-113">Import a list of IoCs</span></span>

<span data-ttu-id="9a7f3-114">また、インジケーターの属性、実行するアクション、その他の詳細を定義する CSV ファイルをアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="9a7f3-115">サポートされている列属性を知るサンプル CSV をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="9a7f3-116">ナビゲーション ウィンドウで、[設定インジケーター]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="9a7f3-117">インジケーターをインポートするエンティティの種類のタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="9a7f3-118">[インポート **] [ファイル**  >  **の選択] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="9a7f3-119">**[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-119">Select **Import**.</span></span> <span data-ttu-id="9a7f3-120">インポートするファイルすべてについて、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="9a7f3-121">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-121">Select **Done**.</span></span>

<span data-ttu-id="9a7f3-122">次の表に、サポートされているパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="9a7f3-123">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a7f3-123">Parameter</span></span> | <span data-ttu-id="9a7f3-124">種類</span><span class="sxs-lookup"><span data-stu-id="9a7f3-124">Type</span></span>    |   <span data-ttu-id="9a7f3-125">説明</span><span class="sxs-lookup"><span data-stu-id="9a7f3-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="9a7f3-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="9a7f3-126">indicatorType</span></span> | <span data-ttu-id="9a7f3-127">列挙</span><span class="sxs-lookup"><span data-stu-id="9a7f3-127">Enum</span></span> | <span data-ttu-id="9a7f3-128">インジケーターの種類。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-128">Type of the indicator.</span></span> <span data-ttu-id="9a7f3-129">指定できる値は、"FileSha1"、"FileSha256"、"IpAddress"、"DomainName" および "Url" です。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="9a7f3-130">**必須**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-130">**Required**</span></span>
<span data-ttu-id="9a7f3-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="9a7f3-131">indicatorValue</span></span> | <span data-ttu-id="9a7f3-132">文字列</span><span class="sxs-lookup"><span data-stu-id="9a7f3-132">String</span></span> | <span data-ttu-id="9a7f3-133">Indicator エンティティ [の](ti-indicator.md) ID。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="9a7f3-134">**必須**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-134">**Required**</span></span>
<span data-ttu-id="9a7f3-135">action</span><span class="sxs-lookup"><span data-stu-id="9a7f3-135">action</span></span> | <span data-ttu-id="9a7f3-136">列挙</span><span class="sxs-lookup"><span data-stu-id="9a7f3-136">Enum</span></span> | <span data-ttu-id="9a7f3-137">インジケーターが組織内で検出される場合に実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="9a7f3-138">指定できる値は、"Alert"、"AlertAndBlock"、"Allowed" です。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="9a7f3-139">**必須**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-139">**Required**</span></span>
<span data-ttu-id="9a7f3-140">title</span><span class="sxs-lookup"><span data-stu-id="9a7f3-140">title</span></span> | <span data-ttu-id="9a7f3-141">String</span><span class="sxs-lookup"><span data-stu-id="9a7f3-141">String</span></span> | <span data-ttu-id="9a7f3-142">インジケーターアラートのタイトル。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-142">Indicator alert title.</span></span> <span data-ttu-id="9a7f3-143">**必須**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-143">**Required**</span></span>
<span data-ttu-id="9a7f3-144">説明</span><span class="sxs-lookup"><span data-stu-id="9a7f3-144">description</span></span> | <span data-ttu-id="9a7f3-145">String</span><span class="sxs-lookup"><span data-stu-id="9a7f3-145">String</span></span> |  <span data-ttu-id="9a7f3-146">インジケーターの説明。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-146">Description of the indicator.</span></span> <span data-ttu-id="9a7f3-147">**必須**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-147">**Required**</span></span>
<span data-ttu-id="9a7f3-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="9a7f3-148">expirationTime</span></span> | <span data-ttu-id="9a7f3-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="9a7f3-149">DateTimeOffset</span></span> | <span data-ttu-id="9a7f3-150">次の形式の YYYYY-MM-DDTHH:MM:SS.0Z のインジケーターの有効期限。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="9a7f3-151">**Optional**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-151">**Optional**</span></span>
<span data-ttu-id="9a7f3-152">severity</span><span class="sxs-lookup"><span data-stu-id="9a7f3-152">severity</span></span> | <span data-ttu-id="9a7f3-153">列挙</span><span class="sxs-lookup"><span data-stu-id="9a7f3-153">Enum</span></span> | <span data-ttu-id="9a7f3-154">インジケーターの重大度。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-154">The severity of the indicator.</span></span> <span data-ttu-id="9a7f3-155">指定できる値は、"Informational"、"Low"、"Medium"、"High" です。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="9a7f3-156">**Optional**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-156">**Optional**</span></span>
<span data-ttu-id="9a7f3-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="9a7f3-157">recommendedActions</span></span> | <span data-ttu-id="9a7f3-158">文字列</span><span class="sxs-lookup"><span data-stu-id="9a7f3-158">String</span></span> | <span data-ttu-id="9a7f3-159">TI インジケーターアラート推奨アクション。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="9a7f3-160">**Optional**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-160">**Optional**</span></span>
<span data-ttu-id="9a7f3-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="9a7f3-161">rbacGroupNames</span></span> | <span data-ttu-id="9a7f3-162">文字列</span><span class="sxs-lookup"><span data-stu-id="9a7f3-162">String</span></span> | <span data-ttu-id="9a7f3-163">インジケーターが適用される RBAC グループ名のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="9a7f3-164">**Optional**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-164">**Optional**</span></span>
<span data-ttu-id="9a7f3-165">category</span><span class="sxs-lookup"><span data-stu-id="9a7f3-165">category</span></span> | <span data-ttu-id="9a7f3-166">文字列</span><span class="sxs-lookup"><span data-stu-id="9a7f3-166">String</span></span> | <span data-ttu-id="9a7f3-167">アラートのカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-167">Category of the alert.</span></span> <span data-ttu-id="9a7f3-168">例として、実行アクセスと資格情報アクセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="9a7f3-169">**Optional**</span><span class="sxs-lookup"><span data-stu-id="9a7f3-169">**Optional**</span></span>
<span data-ttu-id="9a7f3-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="9a7f3-170">mitretechniques</span></span>| <span data-ttu-id="9a7f3-171">文字列</span><span class="sxs-lookup"><span data-stu-id="9a7f3-171">String</span></span> | <span data-ttu-id="9a7f3-172">MITRE の手法 code/id (コンマ区切り)。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="9a7f3-173">詳細については [、「Enterprise tactics」を参照してください](https://attack.mitre.org/tactics/enterprise/)。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="9a7f3-174">**省略可能** MITRE 手法を使用する場合は、カテゴリに値を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="9a7f3-175">詳細については [、「Microsoft Defender for Endpoint alert categories are aligned with MITRE ATT&CK! 」を参照してください](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)。</span><span class="sxs-lookup"><span data-stu-id="9a7f3-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="9a7f3-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a7f3-176">See also</span></span>
- [<span data-ttu-id="9a7f3-177">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="9a7f3-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="9a7f3-178">ファイルのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="9a7f3-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="9a7f3-179">IPs と URL/ドメインのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="9a7f3-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="9a7f3-180">証明書に基づいてインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="9a7f3-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
