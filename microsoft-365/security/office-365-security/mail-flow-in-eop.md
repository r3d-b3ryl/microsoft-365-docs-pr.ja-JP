---
title: EOP のメール フロー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) でメール フローとルーティングを構成するためのオプションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd07c4448d9b30c90c97c7bc89c787b2fdc08cdd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167241"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="3ad4f-103">EOP のメール フロー</span><span class="sxs-lookup"><span data-stu-id="3ad4f-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3ad4f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="3ad4f-104">**Applies to**</span></span>
- [<span data-ttu-id="3ad4f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3ad4f-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="3ad4f-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="3ad4f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3ad4f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ad4f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3ad4f-108">Exchange Online メールボックスを持つ Microsoft 365 組織、または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織では、組織に送信されたメッセージはすべて、従業員に表示される前に EOP を通過します。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="3ad4f-109">処理のために EOP を通過するメッセージをワーカーの受信トレイにルーティングする方法については、オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="3ad4f-110">メッセージとメッセージ アクセス オプションの操作</span><span class="sxs-lookup"><span data-stu-id="3ad4f-110">Working with messages and message access options</span></span>

<span data-ttu-id="3ad4f-111">EOP は、メッセージのルーティング方法に柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="3ad4f-112">以下のトピックで、メール フロー プロセスの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="3ad4f-113">[ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) サービス ネットワーク境界で無効な受信者に対するメッセージを拒否できる、ディレクトリ ベースのエッジ ブロック機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="3ad4f-114">「[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="3ad4f-115">組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="3ad4f-116">サブドメインの詳細については、「Exchange Online でサブドメインのメール フローを [有効にする」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="3ad4f-117">[コネクタを使用してメール フローを構成すると](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 、コネクタが導入され、コネクタを使用してメール ルーティングをカスタマイズする方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-117">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="3ad4f-118">シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="3ad4f-119">[コネクタの拡張フィルタリングでは、](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) メールが EOP の前にサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-119">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="3ad4f-120">スタンドアロン EOP 組織では、いくつかの構成手順を実行して、迷惑メールが各ユーザーの迷惑メール フォルダーに正しくルーティングされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="3ad4f-121">詳細については、「ハイブリッド環境で迷惑メール フォルダーにスパムを配信するためにスタンドアロン [EOP を構成する」を参照してください](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="3ad4f-122">メッセージを各ユーザーの迷惑メール フォルダーに移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="3ad4f-123">詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="3ad4f-124">メール フローを確認する</span><span class="sxs-lookup"><span data-stu-id="3ad4f-124">Verify mail flow</span></span>

<span data-ttu-id="3ad4f-p106">コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="3ad4f-127">[Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) コネクタを検証してメール フローをテストすると、メール フローが正しく設定されていることをテストするための手順が提供されます。</span><span class="sxs-lookup"><span data-stu-id="3ad4f-127">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
