---
title: スタンドアロン EOP を使用して、中国のオンプレミスのメールボックスを保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 21Vianet Office 365を使用する中国の管理者は、スタンドアロン Exchange Online Protection (EOP) を使用してオンプレミスのメールボックスを保護する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4258d64721fc2042297bb15eaeecafa90dcf4bc1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206675"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a><span data-ttu-id="3fc17-103">スタンドアロン EOP を使用して、中国のオンプレミスのメールボックスを保護する</span><span class="sxs-lookup"><span data-stu-id="3fc17-103">Protect on-premises mailboxes in China with standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="3fc17-104">この記事は、中国Office 365 21Vianet が運営するサービスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3fc17-104">This article applies only to Office 365 operated by 21Vianet in China.</span></span>

<span data-ttu-id="3fc17-105">オンプレミスでメールボックスの一部またはすべてをホストする予定の場合でも、メールボックスをサーバー (EOP) でExchange Online Protectionできます。</span><span class="sxs-lookup"><span data-stu-id="3fc17-105">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP).</span></span> <span data-ttu-id="3fc17-106">コネクタを構成するには、アカウントがグローバル管理者または組織管理者 (Exchange管理役割グループ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fc17-106">To configure connectors, your account must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span> <span data-ttu-id="3fc17-107">アクセス許可と[21Vianet](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet)Office 365アクセス許可Exchangeする方法については、「21Vianet で管理役割を割り当Office 365する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fc17-107">For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet).</span></span> <span data-ttu-id="3fc17-108">すべてのメールボックスがオンプレミスExchange場合は、次の手順に従って EOP サービスをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="3fc17-108">If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span>

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="3fc17-109">手順 1: 管理者センター Microsoft 365を使用してドメインを追加および確認する</span><span class="sxs-lookup"><span data-stu-id="3fc17-109">Step 1: Use the Microsoft 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="3fc17-110">管理センター Microsoft 365[セットアップ] に移動して、ドメインをサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="3fc17-110">In the Microsoft 365 admin center, navigate to Setup to add your domain to the service.</span></span>

2. <span data-ttu-id="3fc17-111">ドメインの所有権を確認するには、ポータルの手順に従って該当する DNS レコードを DNS ホスティング プロバイダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="3fc17-111">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>

> [!TIP]
> <span data-ttu-id="3fc17-112">ドメインとユーザーを[21Vianet](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet)が運用する Office 365 に追加し[、DNS](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet)レコードを管理するときに Office 365 の DNS レコードを作成すると、サービスにドメインを追加し、DNS を構成するときに参照する際に役立つリソースになります。</span><span class="sxs-lookup"><span data-stu-id="3fc17-112">[Add your domain and users to Office 365 operated by 21Vianet](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet) and [Create DNS records for Office 365 when you manage your DNS records](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span>

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="3fc17-113">手順 2: 受信者を追加し、ドメインの種類を構成する</span><span class="sxs-lookup"><span data-stu-id="3fc17-113">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="3fc17-114">EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3fc17-114">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service.</span></span> <span data-ttu-id="3fc17-115">「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="3fc17-115">There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="3fc17-116">さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fc17-116">Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative.</span></span> <span data-ttu-id="3fc17-117">DBEB の詳細については [、「Use Directory Based Edge Blocking to reject messages to invalid recipients 」を参照してください](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="3fc17-117">For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="3fc17-118">手順 3:EAC を使用してメール フローをセットアップする</span><span class="sxs-lookup"><span data-stu-id="3fc17-118">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="3fc17-119">Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3fc17-119">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers.</span></span> <span data-ttu-id="3fc17-120">詳細な手順については、「コネクタを使用してメール フローを構成する」[を参照Office 365。](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)</span><span class="sxs-lookup"><span data-stu-id="3fc17-120">For detailed instructions, see [Configure mail flow using connectors in Office 365](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

 <span data-ttu-id="3fc17-121">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="3fc17-121">How do you know this task worked?</span></span>

 <span data-ttu-id="3fc17-122">「[メール フローをテストする」を参照してください。Office 365を参照してください](/exchange/mail-flow-best-practices/test-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="3fc17-122">See [Test mail flow by validating your Office 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="3fc17-123">手順 4: 受信ポート 25 SMTP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="3fc17-123">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="3fc17-124">コネクタを構成した後、DNS レコードの更新が伝達されるよう 72 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="3fc17-124">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates.</span></span> <span data-ttu-id="3fc17-125">この後、ファイアウォールまたはメール サーバー上の受信ポート 25 SMTP トラフィックを、EOP データセンターからのメールのみを受け入れる (特に[、URL](../../enterprise/managing-office-365-endpoints.md)および Office 365 の IP アドレス範囲に記載されている IP アドレスから) 制限します。</span><span class="sxs-lookup"><span data-stu-id="3fc17-125">Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365](../../enterprise/managing-office-365-endpoints.md).</span></span> <span data-ttu-id="3fc17-126">これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。</span><span class="sxs-lookup"><span data-stu-id="3fc17-126">This protects your on-premises environment by limiting the scope of inbound messages you can receive.</span></span> <span data-ttu-id="3fc17-127">また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。</span><span class="sxs-lookup"><span data-stu-id="3fc17-127">Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>

> [!TIP]
> <span data-ttu-id="3fc17-p105">SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。</span><span class="sxs-lookup"><span data-stu-id="3fc17-p105">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span>

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="3fc17-130">手順 5: スパムが各ユーザーの迷惑メール フォルダーにルーティングされるのを確認する</span><span class="sxs-lookup"><span data-stu-id="3fc17-130">Step 5: Ensure that spam is routed to each user's Junk Email folder</span></span>

<span data-ttu-id="3fc17-131">スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fc17-131">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps.</span></span> <span data-ttu-id="3fc17-132">手順については、「スタンドアロン EOP を構成してハイブリッド環境の迷惑メール フォルダーにスパムを配信 [する」で説明します](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="3fc17-132">The steps are provided in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="3fc17-133">各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3fc17-133">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="3fc17-134">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fc17-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="3fc17-135">手順 6: 管理センター Microsoft 365使用して MX レコードを EOP にポイントする</span><span class="sxs-lookup"><span data-stu-id="3fc17-135">Step 6: Use the Microsoft 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="3fc17-136">Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP 経由で流れるようにします。</span><span class="sxs-lookup"><span data-stu-id="3fc17-136">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP.</span></span> <span data-ttu-id="3fc17-137">詳細については、DNS レコードを管理する際に、Office 365 DNS レコード[の作成を参照できます](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="3fc17-137">For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet).</span></span>

<span data-ttu-id="3fc17-138">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="3fc17-138">How do you know this task worked?</span></span>

 <span data-ttu-id="3fc17-139">「[メール フローをテストする」を参照してください。Office 365を参照してください](/exchange/mail-flow-best-practices/test-mail-flow)。</span><span class="sxs-lookup"><span data-stu-id="3fc17-139">See [Test mail flow by validating your Office 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

<span data-ttu-id="3fc17-p108">ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。</span><span class="sxs-lookup"><span data-stu-id="3fc17-p108">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>

- <span data-ttu-id="3fc17-142">リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。</span><span class="sxs-lookup"><span data-stu-id="3fc17-142">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>

- <span data-ttu-id="3fc17-p109">Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。</span><span class="sxs-lookup"><span data-stu-id="3fc17-p109">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>

- <span data-ttu-id="3fc17-145">送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3fc17-145">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="3fc17-146">あまり一般的でなく:オンプレミスおよびクラウド内のメールボックスを使用したハイブリッド セットアップ</span><span class="sxs-lookup"><span data-stu-id="3fc17-146">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="3fc17-147">オンプレミスのExchange、クラウド内に 1 つ以上のメールボックスがある場合Exchange Onlineハイブリッド セットアップ *があります*。</span><span class="sxs-lookup"><span data-stu-id="3fc17-147">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a *hybrid* setup.</span></span> <span data-ttu-id="3fc17-148">ハイブリッドセットアップでは、空き時間情報の予定表の共有やメール ルーティングなどの機能が、オンプレミス環境とクラウド環境で一緒に機能します。</span><span class="sxs-lookup"><span data-stu-id="3fc17-148">In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments.</span></span> <span data-ttu-id="3fc17-149">メールボックスを別のユーザーに移行する際に、ハイブリッドセットアップExchange Online。</span><span class="sxs-lookup"><span data-stu-id="3fc17-149">You might have a hybrid setup in place while you transition mailboxes to Exchange Online.</span></span> <span data-ttu-id="3fc17-150">ハイブリッド環境は、EOP スタンドアロン保護とは異なる方法でセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="3fc17-150">A hybrid environment is set up differently than EOP standalone protection.</span></span>

<span data-ttu-id="3fc17-151">ハイブリッド シナリオを選択して、ほとんどの従業員にクラウドベースの電子メールを利用できます。</span><span class="sxs-lookup"><span data-stu-id="3fc17-151">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees.</span></span> <span data-ttu-id="3fc17-152">これを行う一方で、一部のメールボックスをオンプレミスでホストできます。たとえば、法務部門の場合などです。</span><span class="sxs-lookup"><span data-stu-id="3fc17-152">You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span>

<span data-ttu-id="3fc17-153">ハイブリッドセットアップは複雑な場合がありますが、多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="3fc17-153">A hybrid setup can be complex, but it has many benefits.</span></span> <span data-ttu-id="3fc17-154">ハイブリッド シナリオとハイブリッド シナリオのセットアップの詳細については、「Exchangeハイブリッド[Exchange Server」を参照してください](/Exchange/exchange-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="3fc17-154">To learn more about setting up hybrid scenarios with Exchange, see [Exchange Server hybrid deployments](/Exchange/exchange-hybrid).</span></span>