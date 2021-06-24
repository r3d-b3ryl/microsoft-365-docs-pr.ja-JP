---
title: 報告されたメッセージの管理者によるレビュー
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 報告されたメッセージを確認し、ユーザーにフィードバックを与える方法について学習します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a9fa6c890f0fa6098a2bb712f79ab82fc1edb68b
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108561"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="41ad1-103">報告されたメッセージの管理者によるレビュー</span><span class="sxs-lookup"><span data-stu-id="41ad1-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="41ad1-104">この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="41ad1-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="41ad1-105">このドキュメントは、評価と探索の目的でのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="41ad1-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="41ad1-106">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="41ad1-106">**Applies to**</span></span>
- [<span data-ttu-id="41ad1-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="41ad1-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="41ad1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41ad1-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="41ad1-109">Microsoft 365メールボックスExchange Online Microsoft Defender for Office 365 の組織では、管理者は報告されたメッセージを確認した後、テンプレートメッセージをエンド ユーザーに送り返す機能を備えました。</span><span class="sxs-lookup"><span data-stu-id="41ad1-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="41ad1-110">これは、組織に合わせてカスタマイズし、管理者の評決にも基づいてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="41ad1-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="41ad1-111">この機能は、ユーザーにフィードバックを提供するように設計されますが、システム内のメッセージの評決は変更しません。</span><span class="sxs-lookup"><span data-stu-id="41ad1-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="41ad1-112">Microsoft がフィルターを更新して改善するには、管理者申請を使用して分析用のメッセージを送信 [する必要があります](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="41ad1-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="41ad1-113">メッセージが誤検知または偽陰性として報告された場合にのみ、ユーザーにレビュー結果をマークして [通知できます](report-false-positives-and-false-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="41ad1-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="41ad1-114">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="41ad1-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="41ad1-115"><https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="41ad1-115">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="41ad1-116">[申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="41ad1-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="41ad1-117">ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="41ad1-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="41ad1-118">[組織の管理] または [セキュリティ管理者][をMicrosoft 365 Defenderします](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="41ad1-118">Organization Management or Security Administrator in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="41ad1-119">[組織の管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="41ad1-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="41ad1-120">また、PowerShell へのアクセスExchange Online必要があります。</span><span class="sxs-lookup"><span data-stu-id="41ad1-120">You'll also need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="41ad1-121">使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、「ドメインに電子メール アドレスを指定する」というエラーが *表示されます*。</span><span class="sxs-lookup"><span data-stu-id="41ad1-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="41ad1-122">PowerShell へのアクセスを有効または無効にする方法のExchange Online、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="41ad1-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="41ad1-123">Exchange Online PowerShell へのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="41ad1-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="41ad1-124">クライアント アクセス ルール (Exchange Online</span><span class="sxs-lookup"><span data-stu-id="41ad1-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="41ad1-125">ユーザーに通知するために使用するメッセージを構成する</span><span class="sxs-lookup"><span data-stu-id="41ad1-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="41ad1-126">このポータルMicrosoft 365 Defender、[メール] グループ & **[** ルール&ポリシー] ページの [その他] セクション [ユーザーが報告したメッセージ設定] に \>  \>  \>  \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="41ad1-126">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="41ad1-127">[ユーザー申請] ページで、送信者の表示名を指定する場合は、[管理者レビュー結果の電子メール通知] セクションの [送信者として使用する **Office 365** 電子メール アドレスを指定する] チェック ボックスをオンにし、使用する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="41ad1-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="41ad1-128">これは、返信が送信されるメール アドレスとOutlookに表示される電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="41ad1-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="41ad1-129">テンプレートをカスタマイズする場合は、[メール通知のカスタマイズ **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="41ad1-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="41ad1-130">このフライアウトでは、次の情報のみをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="41ad1-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="41ad1-131">フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="41ad1-131">Phishing</span></span>
    - <span data-ttu-id="41ad1-132">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="41ad1-132">Junk</span></span>
    - <span data-ttu-id="41ad1-133">脅威は検出されませんでした</span><span class="sxs-lookup"><span data-stu-id="41ad1-133">No threats found</span></span>
    - <span data-ttu-id="41ad1-134">意識トレーニング</span><span class="sxs-lookup"><span data-stu-id="41ad1-134">Awareness training</span></span>
    - <span data-ttu-id="41ad1-135">フッター</span><span class="sxs-lookup"><span data-stu-id="41ad1-135">Footer</span></span>

4. <span data-ttu-id="41ad1-136">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41ad1-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="41ad1-137">これらの値をクリアするには、[ユーザー申請] **ページ** で [破棄] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41ad1-137">To clear these values, click **Discard** on the User submissions page.</span></span>
