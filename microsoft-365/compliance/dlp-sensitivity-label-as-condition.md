---
title: 秘密度ラベルを DLP ポリシーの条件として使用する (プレビュー)
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
ms.openlocfilehash: 561a6cbd7b8aeb9082862319c5cc6419fd79c896
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321112"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="d595e-103">秘密度ラベルを DLP ポリシーの条件として使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d595e-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="d595e-104">次の場所の DLP ポリシーでは、[秘密度ラベル](sensitivity-labels.md)を条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="d595e-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="d595e-105">Exchange Online メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="d595e-105">Exchange Online email messages</span></span>
- <span data-ttu-id="d595e-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d595e-106">SharePoint Online</span></span>
- <span data-ttu-id="d595e-107">OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="d595e-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="d595e-108">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="d595e-108">Windows 10 devices</span></span>

<span data-ttu-id="d595e-109">秘密度ラベルは、**コンテンツに含まれている**一覧にオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="d595e-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![条件としての秘密度ラベル](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="d595e-111">サポートされているアイテム、シナリオ、ポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="d595e-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="d595e-112">秘密度ラベルは、これらのアイテム上やシナリオ内での条件として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d595e-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="d595e-113">サポートされているアイテム</span><span class="sxs-lookup"><span data-stu-id="d595e-113">Supported items</span></span>

|<span data-ttu-id="d595e-114">サービス</span><span class="sxs-lookup"><span data-stu-id="d595e-114">service</span></span>  |<span data-ttu-id="d595e-115">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="d595e-115">item type</span></span>  |<span data-ttu-id="d595e-116">ポリシー ヒントに利用可能</span><span class="sxs-lookup"><span data-stu-id="d595e-116">available to policy tip</span></span>  |<span data-ttu-id="d595e-117">強制可能</span><span class="sxs-lookup"><span data-stu-id="d595e-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="d595e-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="d595e-118">Exchange</span></span>    |<span data-ttu-id="d595e-119">メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="d595e-119">email message</span></span>         |<span data-ttu-id="d595e-120">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-120">yes</span></span>         |<span data-ttu-id="d595e-121">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-121">yes</span></span>         |
|<span data-ttu-id="d595e-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="d595e-122">Exchange</span></span>    |<span data-ttu-id="d595e-123">メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="d595e-123">email attachment</span></span>         |<span data-ttu-id="d595e-124">いいえ \*</span><span class="sxs-lookup"><span data-stu-id="d595e-124">no \*</span></span>         |<span data-ttu-id="d595e-125">いいえ \*</span><span class="sxs-lookup"><span data-stu-id="d595e-125">no \*</span></span>         |
|<span data-ttu-id="d595e-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d595e-126">SharePoint Online</span></span>     |<span data-ttu-id="d595e-127">SharePoint Online 内のアイテム</span><span class="sxs-lookup"><span data-stu-id="d595e-127">items in SharePoint Online</span></span>         |<span data-ttu-id="d595e-128">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-128">yes</span></span>         |<span data-ttu-id="d595e-129">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-129">yes</span></span>         |
|<span data-ttu-id="d595e-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d595e-130">OneDrive for Business</span></span>     |<span data-ttu-id="d595e-131">アイテム</span><span class="sxs-lookup"><span data-stu-id="d595e-131">items</span></span>         |<span data-ttu-id="d595e-132">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-132">yes</span></span>         |<span data-ttu-id="d595e-133">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-133">yes</span></span>         |
|<span data-ttu-id="d595e-134">Teams</span><span class="sxs-lookup"><span data-stu-id="d595e-134">Teams</span></span>     |<span data-ttu-id="d595e-135">Teams とチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="d595e-135">Teams and channel messages</span></span>         |<span data-ttu-id="d595e-136">該当なし</span><span class="sxs-lookup"><span data-stu-id="d595e-136">not applicable</span></span>         |<span data-ttu-id="d595e-137">該当なし</span><span class="sxs-lookup"><span data-stu-id="d595e-137">not applicable</span></span>         |
|<span data-ttu-id="d595e-138">Teams</span><span class="sxs-lookup"><span data-stu-id="d595e-138">Teams</span></span>     |<span data-ttu-id="d595e-139">attachments</span><span class="sxs-lookup"><span data-stu-id="d595e-139">attachments</span></span>         |<span data-ttu-id="d595e-140">はい \*\*</span><span class="sxs-lookup"><span data-stu-id="d595e-140">yes \*\*</span></span>         |<span data-ttu-id="d595e-141">はい \*\*</span><span class="sxs-lookup"><span data-stu-id="d595e-141">yes \*\*</span></span>         |
|<span data-ttu-id="d595e-142">Windows 10 デバイス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d595e-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="d595e-143">アイテム</span><span class="sxs-lookup"><span data-stu-id="d595e-143">items</span></span>         |<span data-ttu-id="d595e-144">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-144">yes</span></span>         |<span data-ttu-id="d595e-145">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-145">yes</span></span>         |
|<span data-ttu-id="d595e-146">MCAS (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d595e-146">MCAS (preview)</span></span> |<span data-ttu-id="d595e-147">アイテム</span><span class="sxs-lookup"><span data-stu-id="d595e-147">items</span></span>         |<span data-ttu-id="d595e-148">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-148">yes</span></span>         |<span data-ttu-id="d595e-149">はい</span><span class="sxs-lookup"><span data-stu-id="d595e-149">yes</span></span>         |

<span data-ttu-id="d595e-150">\* メールの秘密度ラベルの DLP 検出がサポートされました。</span><span class="sxs-lookup"><span data-stu-id="d595e-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="d595e-151">秘密度ラベル付きのメールの添付ファイルの DLP 検出はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d595e-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="d595e-152">\*\* 1:1 チャットまたはチャネルを介して Teams で送信された添付ファイルは、OneDrive for Business や SharePoint に自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="d595e-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="d595e-153">そのため、SharePoint Online や OneDrive for Business が DLP ポリシー内の場所として含まれている場合、Teams で送信されたラベル付きの添付ファイルは自動的にこの条件の範囲に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d595e-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="d595e-154">場所としての Teams は、DLP ポリシーで選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d595e-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="d595e-155">サポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="d595e-155">Supported scenarios</span></span>

- <span data-ttu-id="d595e-156">DLP 管理者が 1 つ以上の秘密度ラベルを条件として含めることを選択すると、DLP 管理者はテナント内のすべての秘密度ラベルの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d595e-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="d595e-157">秘密度ラベルの条件としての使用は、上記のサポートのマトリックスで示されているように、すべてのワークロードでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d595e-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="d595e-158">DLP ポリシーのヒントは、秘密度ラベルを条件として含む DLP ポリシーのワークロード (Outlook Win32 を除く) 全体で表示され続けます。</span><span class="sxs-lookup"><span data-stu-id="d595e-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="d595e-159">秘密度ラベルを条件として持つ DLP ポリシーが一致した場合、秘密度ラベルはインシデント レポート メールの一部としても表示されます。</span><span class="sxs-lookup"><span data-stu-id="d595e-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="d595e-160">秘密度ラベルの詳細情報は、秘密度ラベルを条件として含む DLP ポリシーの一致の DLP ルール一致監査ログにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="d595e-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="d595e-161">ポリシー ヒントのサポート</span><span class="sxs-lookup"><span data-stu-id="d595e-161">Support policy tips</span></span>


|<span data-ttu-id="d595e-162">ワークロード</span><span class="sxs-lookup"><span data-stu-id="d595e-162">workload</span></span>  |<span data-ttu-id="d595e-163">ポリシーヒントのサポートあり/サポートなし</span><span class="sxs-lookup"><span data-stu-id="d595e-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="d595e-164">OWA</span><span class="sxs-lookup"><span data-stu-id="d595e-164">OWA</span></span> |    <span data-ttu-id="d595e-165">サポート対象</span><span class="sxs-lookup"><span data-stu-id="d595e-165">supported</span></span>     |
|<span data-ttu-id="d595e-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="d595e-166">Outlook Win 32</span></span>    |  <span data-ttu-id="d595e-167">サポートなし</span><span class="sxs-lookup"><span data-stu-id="d595e-167">not supported</span></span>       |
|<span data-ttu-id="d595e-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d595e-168">SharePoint</span></span>   |   <span data-ttu-id="d595e-169">サポート対象</span><span class="sxs-lookup"><span data-stu-id="d595e-169">supported</span></span>      |
|<span data-ttu-id="d595e-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="d595e-170">OneDrive for Business</span></span>    |    <span data-ttu-id="d595e-171">サポート対象</span><span class="sxs-lookup"><span data-stu-id="d595e-171">supported</span></span>     |
|<span data-ttu-id="d595e-172">エンドポイント デバイス</span><span class="sxs-lookup"><span data-stu-id="d595e-172">endpoint devices</span></span>   |  <span data-ttu-id="d595e-173">サポートなし</span><span class="sxs-lookup"><span data-stu-id="d595e-173">not supported</span></span>       |
