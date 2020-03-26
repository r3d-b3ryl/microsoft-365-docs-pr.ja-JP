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
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955535"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="66eb8-104">Office 365 での自動調査の後の修復アクション</span><span class="sxs-lookup"><span data-stu-id="66eb8-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="66eb8-105">修復アクション</span><span class="sxs-lookup"><span data-stu-id="66eb8-105">Remediation actions</span></span>

<span data-ttu-id="66eb8-106">Office 365 の[自動調査および応答機能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)(AIR) [Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) プラン2には、特定の修復アクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="66eb8-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="66eb8-107">自動化された調査を実行している場合や、完了した場合は、通常、セキュリティ運用チームによる承認を必要とする1つ以上の修復アクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="66eb8-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="66eb8-108">次の表に、Office 365 ATP で現在利用可能な修復アクションの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="66eb8-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="66eb8-109">アクション</span><span class="sxs-lookup"><span data-stu-id="66eb8-109">Action</span></span> | <span data-ttu-id="66eb8-110">説明</span><span class="sxs-lookup"><span data-stu-id="66eb8-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="66eb8-111">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="66eb8-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="66eb8-112">悪意のある Url を含む電子メールメッセージやドキュメントを保護します。</span><span class="sxs-lookup"><span data-stu-id="66eb8-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="66eb8-113">これにより、ユーザーが既存の Office ファイルまたは古い電子メールメッセージ内のリンクをクリックしたときに、悪意のあるリンクや関連する web ページが[安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)でブロックされるようになります。</span><span class="sxs-lookup"><span data-stu-id="66eb8-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="66eb8-114">電子メールの削除 (ソフト)</span><span class="sxs-lookup"><span data-stu-id="66eb8-114">Soft delete email</span></span>  |<span data-ttu-id="66eb8-115">ユーザーのメールボックスから特定の電子メールメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="66eb8-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="66eb8-116">削除済みメッセージは、ユーザーの回復可能なアイテムフォルダーに移動され、削除済みアイテムの保存期間が経過するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="66eb8-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="66eb8-117">削除済みメールクラスターの回復</span><span class="sxs-lookup"><span data-stu-id="66eb8-117">Soft delete email clusters</span></span>  |<span data-ttu-id="66eb8-118">すべてのユーザーのメールボックスからのクエリに一致する悪意のある電子メールメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="66eb8-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="66eb8-119">削除済みメッセージは、ユーザーの [回復可能なアイテム] フォルダーに移動され、削除済みアイテムの保存期間が経過するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="66eb8-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="66eb8-120">外部メール転送の無効化</span><span class="sxs-lookup"><span data-stu-id="66eb8-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="66eb8-121">特定のエンドユーザーのメールボックスから転送ルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="66eb8-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="66eb8-122">Office 365 ATP では、修復アクションは自動的には実行されません。</span><span class="sxs-lookup"><span data-stu-id="66eb8-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="66eb8-123">修復処理は、組織のセキュリティチームによる承認時にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="66eb8-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="66eb8-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="66eb8-124">Next steps</span></span>

- [<span data-ttu-id="66eb8-125">Office 365 の自動調査の後に、保留中または完了した修復アクションを表示する</span><span class="sxs-lookup"><span data-stu-id="66eb8-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="66eb8-126">Office 365 の自動調査の詳細と結果</span><span class="sxs-lookup"><span data-stu-id="66eb8-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="66eb8-127">関連記事</span><span class="sxs-lookup"><span data-stu-id="66eb8-127">Related articles</span></span>

- [<span data-ttu-id="66eb8-128">Microsoft Defender Advanced Threat Protection の自動調査</span><span class="sxs-lookup"><span data-stu-id="66eb8-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="66eb8-129">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="66eb8-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)