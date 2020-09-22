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
ms.service: O365-seccomp
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
description: 21Vianet が運営する Office 365 を使用した中国の管理者は、スタンドアロンの Exchange Online Protection (EOP) を使用してオンプレミスのメールボックスを保護する方法について説明します。
ms.openlocfilehash: eb17b25db93aa50c6c390b5f79cdbd707762a0f9
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202485"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a><span data-ttu-id="553c5-103">スタンドアロン EOP を使用して、中国のオンプレミスのメールボックスを保護する</span><span class="sxs-lookup"><span data-stu-id="553c5-103">Protect on-premises mailboxes in China with standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="553c5-104">この記事は、中国で21Vianet が運営する Office 365 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="553c5-104">This article applies only to Office 365 operated by 21Vianet in China.</span></span>

<span data-ttu-id="553c5-105">一部またはすべてのメールボックスを社内でホストすることを計画している場合でも、Exchange Online Protection (EOP) を使用してメールボックスを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="553c5-105">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP).</span></span> <span data-ttu-id="553c5-106">コネクタを構成するには、アカウントがグローバル管理者であるか、または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="553c5-106">To configure connectors, your account must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span> <span data-ttu-id="553c5-107">Office 365 のアクセス許可と Exchange のアクセス許可との関係の詳細については、「 [365 office 2013 で運用されている管理者ロールの割り当て](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="553c5-107">For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet).</span></span> <span data-ttu-id="553c5-108">すべての Exchange メールボックスがオンプレミスである場合は、次の手順に従って EOP サービスを設定します。</span><span class="sxs-lookup"><span data-stu-id="553c5-108">If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span>

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="553c5-109">手順 1: Microsoft 365 管理センターを使用してドメインを追加して確認する</span><span class="sxs-lookup"><span data-stu-id="553c5-109">Step 1: Use the Microsoft 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="553c5-110">Microsoft 365 管理センターで、[セットアップ] に移動して、ドメインをサービスに追加します。</span><span class="sxs-lookup"><span data-stu-id="553c5-110">In the Microsoft 365 admin center, navigate to Setup to add your domain to the service.</span></span>

2. <span data-ttu-id="553c5-111">ポータルの手順に従って、ドメインの所有権を確認するために、該当する dns レコードを DNS ホストプロバイダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="553c5-111">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>

> [!TIP]
> <span data-ttu-id="553c5-112">「 [21vianet が運用する office 365 にドメインとユーザーを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet)する」と「 [365 office の Dns レコードを作成](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet)する」を参照してください。 dns レコードを管理するときは、ドメインをサービスに追加して dns を構成する際に参照するのに役立つリソースです。</span><span class="sxs-lookup"><span data-stu-id="553c5-112">[Add your domain and users to Office 365 operated by 21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet) and [Create DNS records for Office 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span>

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="553c5-113">手順 2: 受信者を追加してドメインの種類を構成する</span><span class="sxs-lookup"><span data-stu-id="553c5-113">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="553c5-114">EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。</span><span class="sxs-lookup"><span data-stu-id="553c5-114">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service.</span></span> <span data-ttu-id="553c5-115">「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="553c5-115">There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="553c5-116">さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="553c5-116">Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative.</span></span> <span data-ttu-id="553c5-117">DBEB の詳細については、「 [ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="553c5-117">For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="553c5-118">手順 3:EAC を使用してメール フローをセットアップする</span><span class="sxs-lookup"><span data-stu-id="553c5-118">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="553c5-119">Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。</span><span class="sxs-lookup"><span data-stu-id="553c5-119">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers.</span></span> <span data-ttu-id="553c5-120">詳細な手順については、「 [Configure mail flow using connector Using Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="553c5-120">For detailed instructions, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

 <span data-ttu-id="553c5-121">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="553c5-121">How do you know this task worked?</span></span>

 <span data-ttu-id="553c5-122">「 [Office 365 のコネクタを検証する」の「テストメールフロー」を](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)参照してください。</span><span class="sxs-lookup"><span data-stu-id="553c5-122">See [Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="553c5-123">手順 4: 受信ポート 25 SMTP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="553c5-123">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="553c5-124">コネクタを構成した後、DNS レコードの更新が伝達されるよう 72 時間待ちます。</span><span class="sxs-lookup"><span data-stu-id="553c5-124">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates.</span></span> <span data-ttu-id="553c5-125">次に、ファイアウォールまたはメールサーバーで受信ポート-25 の SMTP トラフィックを制限して、EOP データセンターからのメールのみを受け入れるようにします。具体的には、 [Office 365 の url および ip アドレス範囲](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)に記載されている ip アドレスからのみを受信します。</span><span class="sxs-lookup"><span data-stu-id="553c5-125">Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints).</span></span> <span data-ttu-id="553c5-126">これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。</span><span class="sxs-lookup"><span data-stu-id="553c5-126">This protects your on-premises environment by limiting the scope of inbound messages you can receive.</span></span> <span data-ttu-id="553c5-127">また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。</span><span class="sxs-lookup"><span data-stu-id="553c5-127">Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>

> [!TIP]
> <span data-ttu-id="553c5-p105">SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。</span><span class="sxs-lookup"><span data-stu-id="553c5-p105">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span>

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="553c5-130">手順 5: スパムが各ユーザーの迷惑メールフォルダーにルーティングされるようにする</span><span class="sxs-lookup"><span data-stu-id="553c5-130">Step 5: Ensure that spam is routed to each user's Junk Email folder</span></span>

<span data-ttu-id="553c5-131">スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="553c5-131">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps.</span></span> <span data-ttu-id="553c5-132">この手順は、 [ハイブリッド環境の迷惑メールフォルダーにスパムを配信するように、[スタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)] で提供されています。</span><span class="sxs-lookup"><span data-stu-id="553c5-132">The steps are provided in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="553c5-133">メッセージを各ユーザーの迷惑メールフォルダーに移動しない場合は、スパム対策ポリシー (コンテンツフィルターポリシーとも呼ばれる) を編集して別のアクションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="553c5-133">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="553c5-134">詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="553c5-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="553c5-135">手順 6: Microsoft 365 管理センターを使用して MX レコードを EOP にポイントする</span><span class="sxs-lookup"><span data-stu-id="553c5-135">Step 6: Use the Microsoft 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="553c5-136">Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP 経由で流れるようにします。</span><span class="sxs-lookup"><span data-stu-id="553c5-136">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP.</span></span> <span data-ttu-id="553c5-137">詳細については、「DNS レコードを [管理するときに、Office 365 の dns レコードを作成](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="553c5-137">For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="553c5-138">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="553c5-138">How do you know this task worked?</span></span>

 <span data-ttu-id="553c5-139">「 [Office 365 のコネクタを検証する」の「テストメールフロー」を](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)参照してください。</span><span class="sxs-lookup"><span data-stu-id="553c5-139">See [Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

<span data-ttu-id="553c5-p108">ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。</span><span class="sxs-lookup"><span data-stu-id="553c5-p108">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>

- <span data-ttu-id="553c5-142">リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。</span><span class="sxs-lookup"><span data-stu-id="553c5-142">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>

- <span data-ttu-id="553c5-p109">Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。</span><span class="sxs-lookup"><span data-stu-id="553c5-p109">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>

- <span data-ttu-id="553c5-145">送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="553c5-145">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="553c5-146">あまり一般的ではない: オンプレミスのメールボックスとクラウド内のハイブリッドセットアップ</span><span class="sxs-lookup"><span data-stu-id="553c5-146">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="553c5-147">Exchange Online で Exchange メールボックスがオンプレミスにあり、クラウド内に1つ以上のメールボックスがある場合は、 *ハイブリッド* セットアップがあります。</span><span class="sxs-lookup"><span data-stu-id="553c5-147">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a *hybrid* setup.</span></span> <span data-ttu-id="553c5-148">ハイブリッドセットアップでは、オンプレミス環境とクラウド環境で、空き時間情報予定表共有やメールルーティングなどの機能が一緒に機能します。</span><span class="sxs-lookup"><span data-stu-id="553c5-148">In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments.</span></span> <span data-ttu-id="553c5-149">メールボックスを Exchange Online に移行する際に、ハイブリッドセットアップが行われている場合があります。</span><span class="sxs-lookup"><span data-stu-id="553c5-149">You might have a hybrid setup in place while you transition mailboxes to Exchange Online.</span></span> <span data-ttu-id="553c5-150">ハイブリッド環境は、EOP スタンドアロンの保護とは異なる方法で設定されます。</span><span class="sxs-lookup"><span data-stu-id="553c5-150">A hybrid environment is set up differently than EOP standalone protection.</span></span>

<span data-ttu-id="553c5-151">多くの従業員に対してクラウドベースの電子メールを活用するために、ハイブリッドシナリオを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="553c5-151">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees.</span></span> <span data-ttu-id="553c5-152">この操作は、オンプレミスのメールボックスの一部をホストするときに実行することもできます。たとえば、法務部門の場合です。</span><span class="sxs-lookup"><span data-stu-id="553c5-152">You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span>

<span data-ttu-id="553c5-153">ハイブリッドセットアップは複雑になることがありますが、多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="553c5-153">A hybrid setup can be complex, but it has many benefits.</span></span> <span data-ttu-id="553c5-154">Exchange を使用したハイブリッドシナリオのセットアップの詳細については、「 [Exchange Server のハイブリッド展開](https://docs.microsoft.com/Exchange/exchange-hybrid)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="553c5-154">To learn more about setting up hybrid scenarios with Exchange, see [Exchange Server hybrid deployments](https://docs.microsoft.com/Exchange/exchange-hybrid).</span></span>
