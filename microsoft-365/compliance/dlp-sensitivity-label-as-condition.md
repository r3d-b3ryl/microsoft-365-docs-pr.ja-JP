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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235724"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="2c74f-103">秘密度ラベルを DLP ポリシーの条件として使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2c74f-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="2c74f-104">次の場所の DLP ポリシーでは、[秘密度ラベル](sensitivity-labels.md)を条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="2c74f-105">Exchange Online メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="2c74f-105">Exchange Online email messages</span></span>
- <span data-ttu-id="2c74f-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2c74f-106">SharePoint Online</span></span>
- <span data-ttu-id="2c74f-107">OneDrive for Business サイト</span><span class="sxs-lookup"><span data-stu-id="2c74f-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="2c74f-108">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="2c74f-108">Windows 10 devices</span></span>

<span data-ttu-id="2c74f-109">秘密度ラベルは、**コンテンツに含まれている**一覧にオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![条件としての秘密度ラベル](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="2c74f-111">サポートされているアイテム、シナリオ、ポリシー ヒント</span><span class="sxs-lookup"><span data-stu-id="2c74f-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="2c74f-112">秘密度ラベルは、これらのアイテム上やシナリオ内での条件として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="2c74f-113">サポートされているアイテム</span><span class="sxs-lookup"><span data-stu-id="2c74f-113">Supported items</span></span>

|<span data-ttu-id="2c74f-114">サービス</span><span class="sxs-lookup"><span data-stu-id="2c74f-114">service</span></span>  |<span data-ttu-id="2c74f-115">アイテムの種類</span><span class="sxs-lookup"><span data-stu-id="2c74f-115">item type</span></span>  |<span data-ttu-id="2c74f-116">ポリシー ヒントに利用可能</span><span class="sxs-lookup"><span data-stu-id="2c74f-116">available to policy tip</span></span>  |<span data-ttu-id="2c74f-117">強制可能</span><span class="sxs-lookup"><span data-stu-id="2c74f-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="2c74f-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="2c74f-118">Exchange</span></span>    |<span data-ttu-id="2c74f-119">メール メッセージ</span><span class="sxs-lookup"><span data-stu-id="2c74f-119">email message</span></span>         |<span data-ttu-id="2c74f-120">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-120">yes</span></span>         |<span data-ttu-id="2c74f-121">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-121">yes</span></span>         |
|<span data-ttu-id="2c74f-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="2c74f-122">Exchange</span></span>    |<span data-ttu-id="2c74f-123">メールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="2c74f-123">email attachment</span></span>         |<span data-ttu-id="2c74f-124">いいえ \*</span><span class="sxs-lookup"><span data-stu-id="2c74f-124">no \*</span></span>         |<span data-ttu-id="2c74f-125">いいえ \*</span><span class="sxs-lookup"><span data-stu-id="2c74f-125">no \*</span></span>         |
|<span data-ttu-id="2c74f-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2c74f-126">SharePoint Online</span></span>     |<span data-ttu-id="2c74f-127">SharePoint Online 内のアイテム</span><span class="sxs-lookup"><span data-stu-id="2c74f-127">items in SharePoint Online</span></span>         |<span data-ttu-id="2c74f-128">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-128">yes</span></span>         |<span data-ttu-id="2c74f-129">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-129">yes</span></span>         |
|<span data-ttu-id="2c74f-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="2c74f-130">OneDrive for Business</span></span>     |<span data-ttu-id="2c74f-131">アイテム</span><span class="sxs-lookup"><span data-stu-id="2c74f-131">items</span></span>         |<span data-ttu-id="2c74f-132">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-132">yes</span></span>         |<span data-ttu-id="2c74f-133">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-133">yes</span></span>         |
|<span data-ttu-id="2c74f-134">Teams</span><span class="sxs-lookup"><span data-stu-id="2c74f-134">Teams</span></span>     |<span data-ttu-id="2c74f-135">Teams とチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="2c74f-135">Teams and channel messages</span></span>         |<span data-ttu-id="2c74f-136">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c74f-136">not applicable</span></span>         |<span data-ttu-id="2c74f-137">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c74f-137">not applicable</span></span>         |
|<span data-ttu-id="2c74f-138">Teams</span><span class="sxs-lookup"><span data-stu-id="2c74f-138">Teams</span></span>     |<span data-ttu-id="2c74f-139">添付ファイル</span><span class="sxs-lookup"><span data-stu-id="2c74f-139">attachements</span></span>         |<span data-ttu-id="2c74f-140">はい \*\*</span><span class="sxs-lookup"><span data-stu-id="2c74f-140">yes \*\*</span></span>         |<span data-ttu-id="2c74f-141">はい \*\*</span><span class="sxs-lookup"><span data-stu-id="2c74f-141">yes \*\*</span></span>         |
|<span data-ttu-id="2c74f-142">Windows 10 デバイス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2c74f-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="2c74f-143">アイテム</span><span class="sxs-lookup"><span data-stu-id="2c74f-143">items</span></span>         |<span data-ttu-id="2c74f-144">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-144">yes</span></span>         |<span data-ttu-id="2c74f-145">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-145">yes</span></span>         |
|<span data-ttu-id="2c74f-146">MCAS (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2c74f-146">MCAS (preview)</span></span> |<span data-ttu-id="2c74f-147">アイテム</span><span class="sxs-lookup"><span data-stu-id="2c74f-147">items</span></span>         |<span data-ttu-id="2c74f-148">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-148">yes</span></span>         |<span data-ttu-id="2c74f-149">はい</span><span class="sxs-lookup"><span data-stu-id="2c74f-149">yes</span></span>         |

<span data-ttu-id="2c74f-150">\* メールの秘密度ラベルの DLP 検出がサポートされました。</span><span class="sxs-lookup"><span data-stu-id="2c74f-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="2c74f-151">秘密度ラベル付きのメールの添付ファイルの DLP 検出はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2c74f-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="2c74f-152">\*\* 1:1 チャットまたはチャネルを介して Teams で送信された添付ファイルは、One drive for business や SharePoint に自動的にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="2c74f-153">そのため、SharePoint Online や One Drive for Business が DLP ポリシー内の場所として含まれている場合、Teams で送信されたラベル付きの添付ファイルは自動的にこの条件の範囲に含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="2c74f-154">場所としての Teams は、DLP ポリシーで選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2c74f-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="2c74f-155">サポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="2c74f-155">Supported scenarios</span></span>

- <span data-ttu-id="2c74f-156">DLP 管理者が 1 つ以上の秘密度ラベルを条件として含めることを選択すると、DLP 管理者はテナント内のすべての秘密度ラベルの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="2c74f-157">秘密度ラベルの条件としての使用は、上記のサポートのマトリックスで示されているように、すべてのワークロードでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2c74f-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="2c74f-158">DLP ポリシーのヒントは、秘密度ラベルを条件として含む DLP ポリシーのワークロード (Outlook Win32 を除く) 全体で表示され続けます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="2c74f-159">秘密度ラベルを条件として持つ DLP ポリシーが一致した場合、秘密度ラベルはインシデント レポート メールの一部としても表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="2c74f-160">秘密度ラベルの詳細情報は、秘密度ラベルを条件として含む DLP ポリシーの一致の DLP ルール一致監査ログにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c74f-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="2c74f-161">ポリシー ヒントのサポート</span><span class="sxs-lookup"><span data-stu-id="2c74f-161">Support policy tips</span></span>


|<span data-ttu-id="2c74f-162">ワークロード</span><span class="sxs-lookup"><span data-stu-id="2c74f-162">workload</span></span>  |<span data-ttu-id="2c74f-163">ポリシーヒントのサポートあり/サポートなし</span><span class="sxs-lookup"><span data-stu-id="2c74f-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="2c74f-164">OWA</span><span class="sxs-lookup"><span data-stu-id="2c74f-164">OWA</span></span> |    <span data-ttu-id="2c74f-165">サポート対象</span><span class="sxs-lookup"><span data-stu-id="2c74f-165">supported</span></span>     |
|<span data-ttu-id="2c74f-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="2c74f-166">Outlook Win 32</span></span>    |  <span data-ttu-id="2c74f-167">サポートなし</span><span class="sxs-lookup"><span data-stu-id="2c74f-167">not supported</span></span>       |
|<span data-ttu-id="2c74f-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="2c74f-168">SharePoint</span></span>   |   <span data-ttu-id="2c74f-169">サポート対象</span><span class="sxs-lookup"><span data-stu-id="2c74f-169">supported</span></span>      |
|<span data-ttu-id="2c74f-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="2c74f-170">OneDrive for Business</span></span>    |    <span data-ttu-id="2c74f-171">サポート対象</span><span class="sxs-lookup"><span data-stu-id="2c74f-171">supported</span></span>     |
|<span data-ttu-id="2c74f-172">エンドポイント デバイス</span><span class="sxs-lookup"><span data-stu-id="2c74f-172">endpoint devices</span></span>   |  <span data-ttu-id="2c74f-173">サポートなし</span><span class="sxs-lookup"><span data-stu-id="2c74f-173">not supported</span></span>       |
