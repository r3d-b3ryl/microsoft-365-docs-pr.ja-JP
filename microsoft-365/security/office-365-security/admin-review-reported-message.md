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
ms.openlocfilehash: 9e6969b6dee38135ee2d1d41bbcdb2561943d1fe
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878714"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="f70dc-103">報告されたメッセージの管理者によるレビュー</span><span class="sxs-lookup"><span data-stu-id="f70dc-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="f70dc-104">この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="f70dc-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="f70dc-105">このドキュメントは、評価と探索の目的でのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="f70dc-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="f70dc-106">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="f70dc-106">**Applies to**</span></span>
- [<span data-ttu-id="f70dc-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="f70dc-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f70dc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f70dc-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f70dc-109">Microsoft 365メールボックスExchange Online Microsoft Defender for Office 365 の組織では、管理者は報告されたメッセージを確認した後、テンプレートメッセージをエンド ユーザーに送り返す機能を備えました。</span><span class="sxs-lookup"><span data-stu-id="f70dc-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="f70dc-110">これは、組織に合わせてカスタマイズし、管理者の評決にも基づいてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f70dc-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="f70dc-111">この機能は、ユーザーにフィードバックを提供するように設計されますが、システム内のメッセージの評決は変更しません。</span><span class="sxs-lookup"><span data-stu-id="f70dc-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="f70dc-112">Microsoft がフィルターを更新して改善するには、管理者申請を使用して分析用のメッセージを送信 [する必要があります](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f70dc-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="f70dc-113">メッセージが誤検知または偽陰性として報告された場合にのみ、ユーザーにレビュー結果をマークして [通知できます](report-false-positives-and-false-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="f70dc-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f70dc-114">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f70dc-114">What do you need to know before you begin?</span></span>


- <span data-ttu-id="f70dc-115">[セキュリティ センター] Microsoft 365開きます <https://security.microsoft.com/> 。</span><span class="sxs-lookup"><span data-stu-id="f70dc-115">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="f70dc-116">[申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="f70dc-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="f70dc-117">ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f70dc-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="f70dc-118">セキュリティ センターの組織の管理[またはMicrosoft 365管理者](permissions-microsoft-365-security-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="f70dc-118">Organization Management or Security Administrator in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="f70dc-119">[組織の管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="f70dc-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>


- <span data-ttu-id="f70dc-120">PowerShell にアクセスする必要Exchange Onlineがあります。</span><span class="sxs-lookup"><span data-stu-id="f70dc-120">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="f70dc-121">使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、「ドメインに電子メール アドレスを指定する」というエラーが *表示されます*。</span><span class="sxs-lookup"><span data-stu-id="f70dc-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="f70dc-122">PowerShell へのアクセスを有効または無効にする方法のExchange Online、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f70dc-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="f70dc-123">Exchange Online PowerShell へのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="f70dc-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="f70dc-124">クライアント アクセス ルール (Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f70dc-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="f70dc-125">ユーザーに通知するために使用するメッセージを構成する</span><span class="sxs-lookup"><span data-stu-id="f70dc-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="f70dc-126">[Defender ポータルMicrosoft 365で、[メール] グループ& ポリシー &[その他] セクション [ユーザーが報告したメッセージの設定] に \>  \>  \>  \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f70dc-126">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="f70dc-127">[ユーザー申請] ページで、送信者の表示名を指定する場合は、[管理者レビュー結果の電子メール通知] セクションの [送信者として使用する **Office 365** 電子メール アドレスを指定する] チェック ボックスをオンにし、使用する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f70dc-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="f70dc-128">これは、返信が送信されるメール アドレスとOutlookに表示される電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="f70dc-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="f70dc-129">テンプレートをカスタマイズする場合は、[メール通知のカスタマイズ **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f70dc-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="f70dc-130">このフライアウトでは、次の情報のみをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f70dc-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="f70dc-131">フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="f70dc-131">Phishing</span></span>
    - <span data-ttu-id="f70dc-132">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="f70dc-132">Junk</span></span>
    - <span data-ttu-id="f70dc-133">脅威は検出されませんでした</span><span class="sxs-lookup"><span data-stu-id="f70dc-133">No threats found</span></span>
    - <span data-ttu-id="f70dc-134">意識トレーニング</span><span class="sxs-lookup"><span data-stu-id="f70dc-134">Awareness training</span></span>
    - <span data-ttu-id="f70dc-135">フッター</span><span class="sxs-lookup"><span data-stu-id="f70dc-135">Footer</span></span>

4. <span data-ttu-id="f70dc-136">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f70dc-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="f70dc-137">これらの値をクリアするには、[ユーザー申請] **ページ** で [破棄] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f70dc-137">To clear these values, click **Discard** on the User submissions page.</span></span>
