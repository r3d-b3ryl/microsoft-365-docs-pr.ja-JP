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
ms.openlocfilehash: b33e6704a3311740c1e386f77f1c751382ee6958
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651094"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="feaad-103">DLP ポリシーで秘密度ラベルを条件として使用する</span><span class="sxs-lookup"><span data-stu-id="feaad-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="feaad-104">次の場所の DLP ポリシーでは、[秘密度ラベル](sensitivity-labels.md)を条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="feaad-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="feaad-105">Exchange Online メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="feaad-105">Exchange Online email messages</span></span>
- <span data-ttu-id="feaad-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="feaad-106">SharePoint Online</span></span>
- <span data-ttu-id="feaad-107">OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="feaad-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="feaad-108">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="feaad-108">Windows 10 devices</span></span>

<span data-ttu-id="feaad-109">秘密度ラベルは、**コンテンツに含まれている** 一覧にオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="feaad-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="feaad-110">![条件としての秘密度ラベル](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="feaad-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feaad-111">DLP ポリシーを適用する場所として **Teams チャットとチャネル メッセージ** を選択している場合、条件としての **秘密度ラベル** は使用できません。</span><span class="sxs-lookup"><span data-stu-id="feaad-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="feaad-112">サポートされているアイテム、シナリオ、ポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="feaad-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="feaad-113">秘密度ラベルは、これらのアイテム上やシナリオ内での条件として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="feaad-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="feaad-114">サポートされているアイテム</span><span class="sxs-lookup"><span data-stu-id="feaad-114">Supported items</span></span>

|<span data-ttu-id="feaad-115">サービス</span><span class="sxs-lookup"><span data-stu-id="feaad-115">Service</span></span>  |<span data-ttu-id="feaad-116">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="feaad-116">Item type</span></span>  |<span data-ttu-id="feaad-117">ポリシー ヒントに利用可能</span><span class="sxs-lookup"><span data-stu-id="feaad-117">Available to policy tip</span></span>  |<span data-ttu-id="feaad-118">強制可能</span><span class="sxs-lookup"><span data-stu-id="feaad-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="feaad-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="feaad-119">Exchange</span></span>    |<span data-ttu-id="feaad-120">メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="feaad-120">email message</span></span>         |<span data-ttu-id="feaad-121">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-121">yes</span></span>         |<span data-ttu-id="feaad-122">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-122">yes</span></span>         |
|<span data-ttu-id="feaad-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="feaad-123">Exchange</span></span>    |<span data-ttu-id="feaad-124">メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="feaad-124">email attachment</span></span>         |<span data-ttu-id="feaad-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="feaad-125">no</span></span>         |<span data-ttu-id="feaad-126">はい \*</span><span class="sxs-lookup"><span data-stu-id="feaad-126">yes \*</span></span>         |
|<span data-ttu-id="feaad-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="feaad-127">SharePoint Online</span></span>     |<span data-ttu-id="feaad-128">SharePoint Online 内のアイテム</span><span class="sxs-lookup"><span data-stu-id="feaad-128">items in SharePoint Online</span></span>         |<span data-ttu-id="feaad-129">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-129">yes</span></span>         |<span data-ttu-id="feaad-130">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-130">yes</span></span>         |
|<span data-ttu-id="feaad-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="feaad-131">OneDrive for Business</span></span>     |<span data-ttu-id="feaad-132">アイテム</span><span class="sxs-lookup"><span data-stu-id="feaad-132">items</span></span>         |<span data-ttu-id="feaad-133">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-133">yes</span></span>         |<span data-ttu-id="feaad-134">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-134">yes</span></span>         |
|<span data-ttu-id="feaad-135">Teams</span><span class="sxs-lookup"><span data-stu-id="feaad-135">Teams</span></span>     |<span data-ttu-id="feaad-136">Teams とチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="feaad-136">Teams and channel messages</span></span>         |<span data-ttu-id="feaad-137">該当なし</span><span class="sxs-lookup"><span data-stu-id="feaad-137">not applicable</span></span>         |<span data-ttu-id="feaad-138">該当なし</span><span class="sxs-lookup"><span data-stu-id="feaad-138">not applicable</span></span>         |
|<span data-ttu-id="feaad-139">Teams</span><span class="sxs-lookup"><span data-stu-id="feaad-139">Teams</span></span>     |<span data-ttu-id="feaad-140">attachments</span><span class="sxs-lookup"><span data-stu-id="feaad-140">attachments</span></span>         |<span data-ttu-id="feaad-141">はい \*\*</span><span class="sxs-lookup"><span data-stu-id="feaad-141">yes \*\*</span></span>         |<span data-ttu-id="feaad-142">はい \*\*</span><span class="sxs-lookup"><span data-stu-id="feaad-142">yes \*\*</span></span>         |
|<span data-ttu-id="feaad-143">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="feaad-143">Windows 10 devices</span></span>     |<span data-ttu-id="feaad-144">アイテム</span><span class="sxs-lookup"><span data-stu-id="feaad-144">items</span></span>         |<span data-ttu-id="feaad-145">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-145">yes</span></span>         |<span data-ttu-id="feaad-146">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-146">yes</span></span>         |
|<span data-ttu-id="feaad-147">MCAS (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="feaad-147">MCAS (preview)</span></span> |<span data-ttu-id="feaad-148">アイテム</span><span class="sxs-lookup"><span data-stu-id="feaad-148">items</span></span>         |<span data-ttu-id="feaad-149">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-149">yes</span></span>         |<span data-ttu-id="feaad-150">はい</span><span class="sxs-lookup"><span data-stu-id="feaad-150">yes</span></span>         |

<span data-ttu-id="feaad-151">\* 秘密度ラベル付き電子メール添付ファイルの DLP 検知機能は、Microsoft Office ファイルタイプのみサポートします。</span><span class="sxs-lookup"><span data-stu-id="feaad-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="feaad-152">\*\* 1:1 チャットまたはチャネルを介して Teams で送信された添付ファイルは、OneDrive for Business や SharePoint に自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="feaad-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="feaad-153">そのため、SharePoint Online や OneDrive for Business が DLP ポリシー内の場所として含まれている場合、Teams で送信されたラベル付きの添付ファイルは自動的にこの条件の範囲に含まれます。</span><span class="sxs-lookup"><span data-stu-id="feaad-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="feaad-154">場所としての Teams は、DLP ポリシーで選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="feaad-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="feaad-155">サポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="feaad-155">Supported scenarios</span></span>

- <span data-ttu-id="feaad-156">DLP 管理者が 1 つ以上の秘密度ラベルを条件として含めることを選択すると、DLP 管理者はテナント内のすべての秘密度ラベルの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="feaad-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="feaad-157">秘密度ラベルの条件としての使用は、上記のサポートのマトリックスで示されているように、すべてのワークロードでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="feaad-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="feaad-158">DLP ポリシーのヒントは、秘密度ラベルを条件として含む DLP ポリシーのワークロード (Outlook Win32 を除く) 全体で表示され続けます。</span><span class="sxs-lookup"><span data-stu-id="feaad-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="feaad-159">秘密度ラベルを条件として持つ DLP ポリシーが一致した場合、秘密度ラベルはインシデント レポート メールの一部としても表示されます。</span><span class="sxs-lookup"><span data-stu-id="feaad-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="feaad-160">秘密度ラベルの詳細情報は、秘密度ラベルを条件として含む DLP ポリシーの一致の DLP ルール一致監査ログにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="feaad-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="feaad-161">ポリシー ヒントのサポート</span><span class="sxs-lookup"><span data-stu-id="feaad-161">Support policy tips</span></span>


|<span data-ttu-id="feaad-162">ワークロード</span><span class="sxs-lookup"><span data-stu-id="feaad-162">Workload</span></span>  |<span data-ttu-id="feaad-163">ポリシー ヒントのサポートあり/サポートなし</span><span class="sxs-lookup"><span data-stu-id="feaad-163">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="feaad-164">OWA</span><span class="sxs-lookup"><span data-stu-id="feaad-164">OWA</span></span> |    <span data-ttu-id="feaad-165">サポート対象</span><span class="sxs-lookup"><span data-stu-id="feaad-165">supported</span></span>     |
|<span data-ttu-id="feaad-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="feaad-166">Outlook Win 32</span></span>    |  <span data-ttu-id="feaad-167">サポートなし</span><span class="sxs-lookup"><span data-stu-id="feaad-167">not supported</span></span>       |
|<span data-ttu-id="feaad-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="feaad-168">SharePoint</span></span>   |   <span data-ttu-id="feaad-169">サポート対象</span><span class="sxs-lookup"><span data-stu-id="feaad-169">supported</span></span>      |
|<span data-ttu-id="feaad-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="feaad-170">OneDrive for Business</span></span>    |    <span data-ttu-id="feaad-171">サポート対象</span><span class="sxs-lookup"><span data-stu-id="feaad-171">supported</span></span>     |
|<span data-ttu-id="feaad-172">エンドポイント デバイス</span><span class="sxs-lookup"><span data-stu-id="feaad-172">endpoint devices</span></span>   |  <span data-ttu-id="feaad-173">サポートなし</span><span class="sxs-lookup"><span data-stu-id="feaad-173">not supported</span></span>       |
