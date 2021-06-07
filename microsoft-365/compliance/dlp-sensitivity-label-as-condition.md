---
title: DLP ポリシーで秘密度ラベルを条件として使用する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 秘密度ラベルを DLP ポリシーの条件として使用できるサービスやアイテムの種類について説明します。
ms.openlocfilehash: 94d5e9f53471f6113dcc755995a3f94e95a58e53
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779845"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="ce113-103">DLP ポリシーで秘密度ラベルを条件として使用する</span><span class="sxs-lookup"><span data-stu-id="ce113-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="ce113-104">次の場所の DLP ポリシーでは、[秘密度ラベル](sensitivity-labels.md)を条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="ce113-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="ce113-105">Exchange Online メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="ce113-105">Exchange Online email messages</span></span>
- <span data-ttu-id="ce113-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ce113-106">SharePoint Online</span></span>
- <span data-ttu-id="ce113-107">OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="ce113-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="ce113-108">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="ce113-108">Windows 10 devices</span></span>

<span data-ttu-id="ce113-109">秘密度ラベルは、**コンテンツに含まれている** 一覧にオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce113-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ce113-110">![条件としての秘密度ラベル](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="ce113-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce113-111">DLP ポリシーを適用する場所として **Teams チャットとチャネル メッセージ** を選択している場合、条件としての **秘密度ラベル** は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ce113-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="ce113-112">サポートされているアイテム、シナリオ、ポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="ce113-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="ce113-113">秘密度ラベルは、これらのアイテム上やシナリオ内での条件として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ce113-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="ce113-114">サポートされているアイテム</span><span class="sxs-lookup"><span data-stu-id="ce113-114">Supported items</span></span>

|<span data-ttu-id="ce113-115">サービス</span><span class="sxs-lookup"><span data-stu-id="ce113-115">Service</span></span>  |<span data-ttu-id="ce113-116">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="ce113-116">Item type</span></span>  |<span data-ttu-id="ce113-117">ポリシー ヒントに利用可能</span><span class="sxs-lookup"><span data-stu-id="ce113-117">Available to policy tip</span></span>  |<span data-ttu-id="ce113-118">強制可能</span><span class="sxs-lookup"><span data-stu-id="ce113-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="ce113-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="ce113-119">Exchange</span></span>    |<span data-ttu-id="ce113-120">メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="ce113-120">email message</span></span>         |<span data-ttu-id="ce113-121">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-121">yes</span></span>         |<span data-ttu-id="ce113-122">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-122">yes</span></span>         |
|<span data-ttu-id="ce113-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="ce113-123">Exchange</span></span>    |<span data-ttu-id="ce113-124">メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="ce113-124">email attachment</span></span>         |<span data-ttu-id="ce113-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="ce113-125">no</span></span>         |<span data-ttu-id="ce113-126">はい \*</span><span class="sxs-lookup"><span data-stu-id="ce113-126">yes \*</span></span>         |
|<span data-ttu-id="ce113-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ce113-127">SharePoint Online</span></span>     |<span data-ttu-id="ce113-128">SharePoint Online 内のアイテム</span><span class="sxs-lookup"><span data-stu-id="ce113-128">items in SharePoint Online</span></span>         |<span data-ttu-id="ce113-129">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-129">yes</span></span>         |<span data-ttu-id="ce113-130">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-130">yes</span></span>         |
|<span data-ttu-id="ce113-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="ce113-131">OneDrive for Business</span></span>     |<span data-ttu-id="ce113-132">アイテム</span><span class="sxs-lookup"><span data-stu-id="ce113-132">items</span></span>         |<span data-ttu-id="ce113-133">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-133">yes</span></span>         |<span data-ttu-id="ce113-134">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-134">yes</span></span>         |
|<span data-ttu-id="ce113-135">Teams</span><span class="sxs-lookup"><span data-stu-id="ce113-135">Teams</span></span>     |<span data-ttu-id="ce113-136">Teams とチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="ce113-136">Teams and channel messages</span></span>         |<span data-ttu-id="ce113-137">該当なし</span><span class="sxs-lookup"><span data-stu-id="ce113-137">not applicable</span></span>         |<span data-ttu-id="ce113-138">該当なし</span><span class="sxs-lookup"><span data-stu-id="ce113-138">not applicable</span></span>         |
|<span data-ttu-id="ce113-139">Teams</span><span class="sxs-lookup"><span data-stu-id="ce113-139">Teams</span></span>     |<span data-ttu-id="ce113-140">attachments</span><span class="sxs-lookup"><span data-stu-id="ce113-140">attachments</span></span>         |<span data-ttu-id="ce113-141">はい \*\*</span><span class="sxs-lookup"><span data-stu-id="ce113-141">yes \*\*</span></span>         |<span data-ttu-id="ce113-142">はい \*\*</span><span class="sxs-lookup"><span data-stu-id="ce113-142">yes \*\*</span></span>         |
|<span data-ttu-id="ce113-143">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="ce113-143">Windows 10 devices</span></span>     |<span data-ttu-id="ce113-144">アイテム</span><span class="sxs-lookup"><span data-stu-id="ce113-144">items</span></span>         |<span data-ttu-id="ce113-145">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-145">yes</span></span>         |<span data-ttu-id="ce113-146">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-146">yes</span></span>         |
|<span data-ttu-id="ce113-147">MCAS (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ce113-147">MCAS (preview)</span></span> |<span data-ttu-id="ce113-148">アイテム</span><span class="sxs-lookup"><span data-stu-id="ce113-148">items</span></span>         |<span data-ttu-id="ce113-149">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-149">yes</span></span>         |<span data-ttu-id="ce113-150">はい</span><span class="sxs-lookup"><span data-stu-id="ce113-150">yes</span></span>         |

<span data-ttu-id="ce113-151">\* 秘密度ラベル付き電子メール添付ファイルの DLP 検知機能は、Microsoft Office ファイルタイプのみサポートします。</span><span class="sxs-lookup"><span data-stu-id="ce113-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="ce113-152">\*\* 1:1 チャットまたはチャネルを介して Teams で送信された添付ファイルは、OneDrive for Business や SharePoint に自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="ce113-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="ce113-153">そのため、SharePoint Online や OneDrive for Business が DLP ポリシー内の場所として含まれている場合、Teams で送信されたラベル付きの添付ファイルは自動的にこの条件の範囲に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ce113-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="ce113-154">場所としての Teams は、DLP ポリシーで選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ce113-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

> [!NOTE]
> <span data-ttu-id="ce113-155">SharePoint および OneDrive for Business で秘密度ラベルを検出する DLP の機能は制限されています。</span><span class="sxs-lookup"><span data-stu-id="ce113-155">DLP's ability to detect sensitivity labels in SharePoint and OneDrive for business is limited.</span></span> <span data-ttu-id="ce113-156">詳細については、「[SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md#limitations)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce113-156">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="ce113-157">サポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="ce113-157">Supported scenarios</span></span>

- <span data-ttu-id="ce113-158">DLP 管理者が 1 つ以上の秘密度ラベルを条件として含めることを選択すると、DLP 管理者はテナント内のすべての秘密度ラベルの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ce113-158">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="ce113-159">秘密度ラベルの条件としての使用は、上記のサポートのマトリックスで示されているように、すべてのワークロードでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ce113-159">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="ce113-160">DLP ポリシーのヒントは、秘密度ラベルを条件として含む DLP ポリシーのワークロード (Outlook Win32 を除く) 全体で表示され続けます。</span><span class="sxs-lookup"><span data-stu-id="ce113-160">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="ce113-161">秘密度ラベルを条件として持つ DLP ポリシーが一致した場合、秘密度ラベルはインシデント レポート メールの一部としても表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce113-161">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="ce113-162">秘密度ラベルの詳細情報は、秘密度ラベルを条件として含む DLP ポリシーの一致の DLP ルール一致監査ログにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="ce113-162">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="ce113-163">ポリシー ヒントのサポート</span><span class="sxs-lookup"><span data-stu-id="ce113-163">Support policy tips</span></span>


|<span data-ttu-id="ce113-164">ワークロード</span><span class="sxs-lookup"><span data-stu-id="ce113-164">Workload</span></span>  |<span data-ttu-id="ce113-165">ポリシー ヒントのサポートあり/サポートなし</span><span class="sxs-lookup"><span data-stu-id="ce113-165">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="ce113-166">OWA</span><span class="sxs-lookup"><span data-stu-id="ce113-166">OWA</span></span> |    <span data-ttu-id="ce113-167">サポート対象</span><span class="sxs-lookup"><span data-stu-id="ce113-167">supported</span></span>     |
|<span data-ttu-id="ce113-168">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="ce113-168">Outlook Win 32</span></span>    |  <span data-ttu-id="ce113-169">サポートなし</span><span class="sxs-lookup"><span data-stu-id="ce113-169">not supported</span></span>       |
|<span data-ttu-id="ce113-170">SharePoint</span><span class="sxs-lookup"><span data-stu-id="ce113-170">SharePoint</span></span>   |   <span data-ttu-id="ce113-171">サポート対象</span><span class="sxs-lookup"><span data-stu-id="ce113-171">supported</span></span>      |
|<span data-ttu-id="ce113-172">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="ce113-172">OneDrive for Business</span></span>    |    <span data-ttu-id="ce113-173">サポート対象</span><span class="sxs-lookup"><span data-stu-id="ce113-173">supported</span></span>     |
|<span data-ttu-id="ce113-174">エンドポイント デバイス</span><span class="sxs-lookup"><span data-stu-id="ce113-174">endpoint devices</span></span>   |  <span data-ttu-id="ce113-175">サポートなし</span><span class="sxs-lookup"><span data-stu-id="ce113-175">not supported</span></span>       |
