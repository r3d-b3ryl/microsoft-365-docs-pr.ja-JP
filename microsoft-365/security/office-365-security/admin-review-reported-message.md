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
ms.openlocfilehash: 7386f5b283e2bfabb76eee91d33dfda0e42ec7b1
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769127"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="0cb2e-103">報告されたメッセージの管理者によるレビュー</span><span class="sxs-lookup"><span data-stu-id="0cb2e-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="0cb2e-104">この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0cb2e-105">このドキュメントは、評価と探索の目的でのみ提供されています。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="0cb2e-106">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0cb2e-106">**Applies to**</span></span>
- [<span data-ttu-id="0cb2e-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0cb2e-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0cb2e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0cb2e-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0cb2e-109">Microsoft 365メールボックスExchange Online Microsoft Defender for Office 365 の組織では、管理者は報告されたメッセージを確認した後、テンプレートメッセージをエンド ユーザーに送り返す機能を備えました。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="0cb2e-110">これは、組織に合わせてカスタマイズし、管理者の評決にも基づいてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-110">This can be customized for your organization and based on your admin’s verdict as well.</span></span>

<span data-ttu-id="0cb2e-111">この機能は、ユーザーにフィードバックを提供するように設計されますが、システム内のメッセージの評決は変更しません。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="0cb2e-112">Microsoft がフィルターを更新して改善するには、管理者申請を使用して分析用のメッセージを送信 [する必要があります](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="0cb2e-113">メッセージが誤検知または偽陰性として報告された場合にのみ、ユーザーにレビュー結果をマークして [通知できます](report-false-positives-and-false-negatives.md)。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0cb2e-114">事前に必要な知識</span><span class="sxs-lookup"><span data-stu-id="0cb2e-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0cb2e-115">ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-115">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="0cb2e-116">セキュリティ センターの組織の管理[またはMicrosoft 365管理者](permissions-microsoft-365-security-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-116">Organization Management or Security Administrator in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="0cb2e-117">[組織の管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-117">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span></span>

- <span data-ttu-id="0cb2e-118">PowerShell にアクセスする必要Exchange Onlineがあります。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-118">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="0cb2e-119">使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、「ドメインに電子メール アドレスを指定する」というエラーが *表示されます*。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-119">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="0cb2e-120">PowerShell へのアクセスを有効または無効にする方法のExchange Online、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-120">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="0cb2e-121">Exchange Online PowerShell へのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="0cb2e-121">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="0cb2e-122">クライアント アクセス ルール (Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0cb2e-122">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="0cb2e-123">ユーザーに通知するために使用するメッセージを構成する</span><span class="sxs-lookup"><span data-stu-id="0cb2e-123">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="0cb2e-124">[セキュリティ センター [Microsoft 365に移動](../defender/overview-security-center.md)し、[ポリシー  ] &脅威ポリシー ユーザーがメッセージ設定 \>  \> **を報告しました**。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-124">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Policies & rules** \> **Threat policies** \> **User reported message settings**.</span></span>

2. <span data-ttu-id="0cb2e-125">送信者の表示名を指定する場合は、[管理者レビュー結果の電子メール通知] セクションの [送信者として使用する **Office 365** 電子メール アドレスを指定する] チェック ボックスをオンにし、使用する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-125">If you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="0cb2e-126">これは、返信が送信されるメール アドレスとOutlookに表示される電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-126">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="0cb2e-127">テンプレートをカスタマイズする場合は、[メール通知のカスタマイズ **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-127">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="0cb2e-128">このフライアウトでは、次の情報のみをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-128">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="0cb2e-129">フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="0cb2e-129">Phishing</span></span>
    - <span data-ttu-id="0cb2e-130">迷惑メール</span><span class="sxs-lookup"><span data-stu-id="0cb2e-130">Junk</span></span>
    - <span data-ttu-id="0cb2e-131">脅威は検出されませんでした</span><span class="sxs-lookup"><span data-stu-id="0cb2e-131">No threats found</span></span>
    - <span data-ttu-id="0cb2e-132">意識トレーニング</span><span class="sxs-lookup"><span data-stu-id="0cb2e-132">Awareness training</span></span>
    - <span data-ttu-id="0cb2e-133">フッター</span><span class="sxs-lookup"><span data-stu-id="0cb2e-133">Footer</span></span>

4. <span data-ttu-id="0cb2e-134">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="0cb2e-135">これらの値をクリアするには、[ユーザー申請] **ページ** で [破棄] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cb2e-135">To clear these values, click **Discard** on the User submissions page.</span></span>
