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
description: 管理者は、Exchange Online Protection (EOP) でメール フローとルーティングを構成するオプションについて学習できます。
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827727"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="69439-103">EOP のメール フロー</span><span class="sxs-lookup"><span data-stu-id="69439-103">Mail flow in EOP</span></span>

<span data-ttu-id="69439-104">Exchange Online メールボックスを使用している Microsoft 365 組織、または Exchange Online メールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、組織に送信されたすべてのメッセージは EOP を通って作業者に表示されます。</span><span class="sxs-lookup"><span data-stu-id="69439-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="69439-105">社内の受信ボックスにルーティングされる前に処理するために EOP を通じて通るメッセージのルーティング方法に関するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="69439-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="69439-106">メッセージとメッセージ アクセス オプションの操作</span><span class="sxs-lookup"><span data-stu-id="69439-106">Working with messages and message access options</span></span>

<span data-ttu-id="69439-107">EOP はメッセージのルーティング方法を柔軟に行います。</span><span class="sxs-lookup"><span data-stu-id="69439-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="69439-108">以下のトピックで、メール フロー プロセスの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="69439-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="69439-109">[ディレクトリ ベースのエッジ ブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) サービス ネットワーク境界で無効な受信者宛てのメッセージを拒否できるディレクトリ ベースのエッジ ブロック機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="69439-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="69439-110">「[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="69439-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="69439-111">組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。</span><span class="sxs-lookup"><span data-stu-id="69439-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="69439-112">サブドメインの詳細については [、「Exchange Online でサブドメインのメール フローを有効にする」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。</span><span class="sxs-lookup"><span data-stu-id="69439-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="69439-113">[コネクタを使用するメール フローを構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) するには、コネクタを導入し、それを使ってメール ルーティングをカスタマイズする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="69439-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="69439-114">シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="69439-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="69439-115">[コネクタのフィルター処理の強化は、EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) の前にメールがサービスまたはデバイスにルーティングされる場合にコネクタを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="69439-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="69439-116">スタンドアロン EOP 組織では、迷惑メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされるのを、一組構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69439-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="69439-117">詳細については、ハイブリッド環境 [の [迷惑メール] フォルダーにスパムを配信するようにスタンドアロン EOP を構成する方法を詳しく説明しています](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="69439-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="69439-118">メッセージをそれぞれのユーザーの迷惑メール フォルダーに移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="69439-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="69439-119">詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69439-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="69439-120">メール フローを確認する</span><span class="sxs-lookup"><span data-stu-id="69439-120">Verify mail flow</span></span>

<span data-ttu-id="69439-p106">コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="69439-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="69439-123">[Microsoft 365 コネクタを検証してメール フローをテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) すると、メール フローが正しくセットアップされているかどうかのテスト手順が提供されます。</span><span class="sxs-lookup"><span data-stu-id="69439-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
