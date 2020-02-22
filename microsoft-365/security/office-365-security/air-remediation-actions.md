---
title: Office 365 の修復アクション自動調査と応答
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の修復アクションについて説明します。
ms.openlocfilehash: e75ef1523247cbddcf6cb28d69a889db1de8e42f
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228533"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="d22af-104">Office 365 での自動調査の後の修復アクション</span><span class="sxs-lookup"><span data-stu-id="d22af-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions-overview"></a><span data-ttu-id="d22af-105">修復アクションの概要</span><span class="sxs-lookup"><span data-stu-id="d22af-105">Remediation actions overview</span></span>

<span data-ttu-id="d22af-106">Office 365 の[自動調査および応答機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)高度な脅威保護には、特定の修復アクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d22af-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="d22af-107">自動化された調査を実行している場合や、完了した場合は、通常、セキュリティ運用チームによる承認を必要とする1つ以上の修復アクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d22af-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> <span data-ttu-id="d22af-108">次の表に、Office 365 Advanced Threat Protection で現在利用可能な修復処置の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="d22af-108">The following table summarizes remediation actions currently available in Office 365 Advanced Threat Protection.</span></span> 

|<span data-ttu-id="d22af-109">アクション</span><span class="sxs-lookup"><span data-stu-id="d22af-109">Action</span></span> | <span data-ttu-id="d22af-110">説明</span><span class="sxs-lookup"><span data-stu-id="d22af-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="d22af-111">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="d22af-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="d22af-112">悪意のある Url を含む電子メールやドキュメントを保護します。</span><span class="sxs-lookup"><span data-stu-id="d22af-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="d22af-113">これにより、ユーザーが既存の Office ファイルまたは古い電子メールメッセージ内のリンクをクリックしたときに、悪意のあるリンクや関連する web ページが[安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)でブロックされるようになります。</span><span class="sxs-lookup"><span data-stu-id="d22af-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="d22af-114">電子メールの削除 (ソフト)</span><span class="sxs-lookup"><span data-stu-id="d22af-114">Soft delete email</span></span>  |<span data-ttu-id="d22af-115">ユーザーのメールボックスから特定の電子メールメッセージを削除する</span><span class="sxs-lookup"><span data-stu-id="d22af-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="d22af-116">削除済みメールクラスターの回復</span><span class="sxs-lookup"><span data-stu-id="d22af-116">Soft delete email clusters</span></span>  |<span data-ttu-id="d22af-117">すべてのユーザーのメールボックスからのクエリに一致する悪意のある電子メールメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="d22af-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="d22af-118">外部メール転送の無効化</span><span class="sxs-lookup"><span data-stu-id="d22af-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="d22af-119">特定のエンドユーザーのメールボックスから転送ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d22af-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="d22af-120">保留中のアクションを承認 (または拒否) します。</span><span class="sxs-lookup"><span data-stu-id="d22af-120">Approve (or reject) pending actions</span></span>

![AIR の調査処理 ページ](../../media/air-investigationactionspage.png)

<span data-ttu-id="d22af-122">[調査の詳細](air-view-investigation-results.md)を表示している間に、保留中の修復処理を承認または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="d22af-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="d22af-123">自動化された調査が完了するように、この手順をできるだけ早く実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d22af-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d22af-124">修復アクションを承認または拒否するには、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d22af-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="d22af-125">[AIR 機能を使用するには、必要なアクセス許可を](office-365-air.md#required-permissions-to-use-air-capabilities)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d22af-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="d22af-126">[**操作**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d22af-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="d22af-127">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="d22af-127">Select an item in the list.</span></span> <span data-ttu-id="d22af-128">(これにより、[承認] ボタンと [拒否] ボタンが有効になります)。</span><span class="sxs-lookup"><span data-stu-id="d22af-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="d22af-129">選択したアイテムの利用可能な情報を確認し、その操作を承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="d22af-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="d22af-130">**承認**は修復を開始することを許可します。</span><span class="sxs-lookup"><span data-stu-id="d22af-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="d22af-131">**却下**にはその他のアクションはありません</span><span class="sxs-lookup"><span data-stu-id="d22af-131">**Reject** takes no further action</span></span>

## <a name="related-articles"></a><span data-ttu-id="d22af-132">関連記事</span><span class="sxs-lookup"><span data-stu-id="d22af-132">Related articles</span></span>

[<span data-ttu-id="d22af-133">Microsoft の脅威保護の自動化された調査と対応について説明します。</span><span class="sxs-lookup"><span data-stu-id="d22af-133">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)