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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) でメールフローとルーティングを構成するためのオプションについて説明します。
ms.openlocfilehash: e1c821e3de8dd7dd18c192522bd18fd32a395dca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200705"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="34adc-103">EOP のメール フロー</span><span class="sxs-lookup"><span data-stu-id="34adc-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="34adc-104">Exchange Online メールボックスを使用する Microsoft 365 組織、または Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、組織に送信されるすべてのメッセージが EOP を経由してワーカーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="34adc-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="34adc-105">EOP を経由して処理するメッセージを、ワーカーの受信トレイにルーティングする前にルーティングする方法についてのオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="34adc-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="34adc-106">メッセージとメッセージ アクセス オプションの操作</span><span class="sxs-lookup"><span data-stu-id="34adc-106">Working with messages and message access options</span></span>

<span data-ttu-id="34adc-107">EOP は、メッセージのルーティング方法に柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="34adc-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="34adc-108">以下のトピックで、メール フロー プロセスの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="34adc-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="34adc-109">[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) サービスネットワーク境界で無効な受信者宛てのメッセージを拒否できるようにする、ディレクトリベースのエッジブロック機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="34adc-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="34adc-110">「[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34adc-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="34adc-111">組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。</span><span class="sxs-lookup"><span data-stu-id="34adc-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="34adc-112">サブドメインの詳細については [、「Exchange Online でサブドメインのメールフローを有効にする」](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34adc-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="34adc-113">[コネクタを使用してメールフローを構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) するコネクタを導入し、それらを使用してメールルーティングをカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="34adc-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="34adc-114">シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="34adc-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="34adc-115">[コネクタの拡張フィルター処理](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) EOP の前に、メールがサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="34adc-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="34adc-116">スタンドアロンの EOP 組織では、いくつかの構成手順を実行して、迷惑メールがそれぞれのユーザーの迷惑メールフォルダーに正しくルーティングされるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="34adc-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="34adc-117">これらの詳細につい [ては、「Configure STANDALONE EOP to The 迷惑メールフォルダーにハイブリッド環境でスパムを配信する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="34adc-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="34adc-118">メッセージを各ユーザーの [迷惑メール] フォルダーに移動しない場合は、スパム対策ポリシー (コンテンツフィルターポリシーとも呼ばれる) を編集して別のアクションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="34adc-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="34adc-119">詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34adc-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="34adc-120">メール フローを確認する</span><span class="sxs-lookup"><span data-stu-id="34adc-120">Verify mail flow</span></span>

<span data-ttu-id="34adc-p106">コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="34adc-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="34adc-123">[Microsoft 365 コネクタを検証してメールフローをテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) するメールフローが正しく設定されていることをテストする手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="34adc-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
