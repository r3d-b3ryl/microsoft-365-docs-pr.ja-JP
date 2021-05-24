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
description: 管理者は、メール フローとルーティングを構成するためのオプションについて、メール フロー (EOP) でExchange Online Protectionできます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ad80c4176c1b8b1c47b6b9ecafd34b4ca301f3f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623419"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="0ad38-103">EOP のメール フロー</span><span class="sxs-lookup"><span data-stu-id="0ad38-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ad38-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0ad38-104">**Applies to**</span></span>
- [<span data-ttu-id="0ad38-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0ad38-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0ad38-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0ad38-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0ad38-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ad38-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0ad38-108">Microsoft 365 Exchange Online メールボックスまたはスタンドアロン Exchange Online Protection (EOP) 組織が Exchange Online メールボックスを持つ組織では、組織に送信されたメッセージはすべて、ワーカーが EOP を表示する前に EOP を通過します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="0ad38-109">処理のために EOP を通過するメッセージをワーカー受信トレイにルーティングする方法に関するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0ad38-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="0ad38-110">メッセージとメッセージ アクセス オプションの操作</span><span class="sxs-lookup"><span data-stu-id="0ad38-110">Working with messages and message access options</span></span>

<span data-ttu-id="0ad38-111">EOP は、メッセージのルーティング方法に柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="0ad38-112">以下のトピックで、メール フロー プロセスの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="0ad38-113">[無効な受信者に送信されるメッセージを拒否](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) するには、ディレクトリ ベースのエッジ ブロックを使用するサービス ネットワーク境界で無効な受信者のメッセージを拒否できるディレクトリ ベースのエッジ ブロック機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="0ad38-114">「[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-114">[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="0ad38-115">組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。</span><span class="sxs-lookup"><span data-stu-id="0ad38-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="0ad38-116">サブドメインの詳細については、「メール のサブドメインのメール フローを有効にする」[を参照Exchange Online。](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="0ad38-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="0ad38-117">[コネクタを使用してメール フロー](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) を構成すると、コネクタが導入され、それらを使用してメール ルーティングをカスタマイズする方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="0ad38-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="0ad38-118">シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ad38-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="0ad38-119">[拡張コネクタのフィルター処理では、](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) メールが EOP の前にサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="0ad38-120">EOP がオンプレミスの Exchange メールボックスを保護するハイブリッド環境では、迷惑メール ルールがメッセージを迷惑メール フォルダーに移動できるよう、EOP スパム フィルターの評決を変換するために、オンプレミス Exchange でメール フロー ルール (トランスポート ルールとも呼ばれる) を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ad38-120">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="0ad38-121">詳細については、「ハイブリッド環境の迷惑メール フォルダーにスパムを配信する [EOP の構成」を参照してください](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="0ad38-121">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span> <span data-ttu-id="0ad38-122">各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ad38-122">If you don't  want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="0ad38-123">詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ad38-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="0ad38-124">メール フローを確認する</span><span class="sxs-lookup"><span data-stu-id="0ad38-124">Verify mail flow</span></span>

<span data-ttu-id="0ad38-p106">コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](/exchange/standalone-eop/set-up-your-eop-service)」の「このタスクの検証方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ad38-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service).</span></span>

<span data-ttu-id="0ad38-127">[メール フローをテストするには](/exchange/mail-flow-best-practices/test-mail-flow)、Microsoft 365コネクタを検証して、メール フローが正しく設定されていることをテストする手順を示します。</span><span class="sxs-lookup"><span data-stu-id="0ad38-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
