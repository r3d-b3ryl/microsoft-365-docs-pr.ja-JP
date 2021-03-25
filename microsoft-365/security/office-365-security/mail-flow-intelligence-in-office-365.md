---
title: メール フロー インテリジェンス
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理者は、コネクタ (メール フロー インテリジェンスとも呼ばれる) を使用してメッセージ配信に関連付けられているエラー コードについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb52e5865415440b3b2924a3ebcc96a7f8e17e5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206285"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="ee5b3-103">EOP でのメール フロー インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="ee5b3-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ee5b3-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="ee5b3-104">**Applies to**</span></span>
- [<span data-ttu-id="ee5b3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ee5b3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ee5b3-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="ee5b3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ee5b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee5b3-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ee5b3-108">Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織に Exchange Online メールボックスがない Microsoft 365 組織では、通常、コネクタを使用して EOP からオンプレミスの電子メール環境に電子メール メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="ee5b3-109">コネクタを使用して、Microsoft 365 からパートナー組織にメッセージをルーティングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-109">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="ee5b3-110">Microsoft 365 がコネクタを介してこれらのメッセージを配信できない場合は、Microsoft 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-110">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="ee5b3-111">Microsoft 365 は、メッセージごとに配信を 24 時間再試行します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-111">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="ee5b3-112">24 時間が経過すると、キューに入っているメッセージは期限切れになります。メッセージは配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) の元の送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-112">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="ee5b3-113">Microsoft 365 は、コネクタを使用してメッセージを配信できない場合にエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-113">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="ee5b3-114">最も一般的なエラーとその解決策については、この記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-114">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="ee5b3-115">まとめて、コネクタ経由で送信される配信不能メッセージのキューエラーと通知エラーは、メール フロー _インテリジェンスと呼ばれる。_</span><span class="sxs-lookup"><span data-stu-id="ee5b3-115">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="ee5b3-116">エラー コード:450 4.4.312 DNS クエリに失敗しました</span><span class="sxs-lookup"><span data-stu-id="ee5b3-116">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="ee5b3-117">通常、このエラーは、Microsoft 365 がコネクタで指定されているスマート ホストに接続しようとしましたが、スマート ホストの IP アドレスを検索するための DNS クエリが失敗したという意味です。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-117">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="ee5b3-118">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="ee5b3-118">The possible causes for this error are:</span></span>

- <span data-ttu-id="ee5b3-119">ご使用のドメインの DNS ホスティング サービス (ご使用のドメインの権威ネーム サーバーを管理しているパーティ) に問題があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-119">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="ee5b3-120">ご使用のドメインの有効期限が最近切れたため、MX レコードを取得できません。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-120">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="ee5b3-121">ドメインの MX レコードが最近変更され、DNS サーバーはドメインの DNS 情報を以前にキャッシュしています。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-121">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="ee5b3-122">エラー コード 450 4.4.312 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="ee5b3-122">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="ee5b3-123">DNS ホスティング サービスを使用して、ドメインの問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-123">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="ee5b3-124">パートナー組織 (サードパーティのクラウド サービス プロバイダーなど) からのエラーが発生した場合は、パートナーに問い合わせ、問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-124">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="ee5b3-125">エラー コード:450 4.4.315 接続がタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="ee5b3-125">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="ee5b3-126">通常、これは、Microsoft 365 が宛先メール サーバーに接続できないという意味です。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-126">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="ee5b3-127">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-127">The error details will explain the problem.</span></span> <span data-ttu-id="ee5b3-128">例:</span><span class="sxs-lookup"><span data-stu-id="ee5b3-128">For example:</span></span>

- <span data-ttu-id="ee5b3-129">オンプレミスの電子メール サーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-129">Your on-premises email server is down.</span></span>

- <span data-ttu-id="ee5b3-130">コネクタのスマート ホスト設定にエラーが発生し、Microsoft 365 が間違った IP アドレスに接続しようとしている。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-130">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="ee5b3-131">エラー コード 450 4.4.315 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="ee5b3-131">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="ee5b3-132">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-132">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="ee5b3-133">たとえば、メール フローが正しく機能し、コネクタの設定を変更していない場合は、サーバーがダウンしているか、ネットワーク インフラストラクチャに変更が加わったか (たとえば、インターネット サービス プロバイダーを変更したので、IP アドレスが異なっているなど)、オンプレミスのメール環境を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-133">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="ee5b3-134">パートナー組織 (サードパーティのクラウド サービス プロバイダーなど) からのエラーが発生した場合は、パートナーに問い合わせ、問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-134">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="ee5b3-135">エラー コード:450 4.4.316 接続が拒否されました</span><span class="sxs-lookup"><span data-stu-id="ee5b3-135">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="ee5b3-136">通常、このエラーは、Microsoft 365 が接続先の電子メール サーバーに接続しようとするときに接続エラーが発生したという意味です。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-136">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="ee5b3-137">このエラーの原因として、ファイアウォールが Microsoft 365 IP アドレスからの接続をブロックしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-137">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="ee5b3-138">または、オンプレミスの電子メール システムを Microsoft 365 に完全に移行し、オンプレミスの電子メール環境をシャットダウンした場合、このエラーは設計によって発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-138">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="ee5b3-139">エラー コード 450 4.4.316 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="ee5b3-139">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="ee5b3-140">オンプレミス環境にメールボックスがある場合は、ファイアウォール設定を変更して、TCP ポート 25 の Microsoft 365 IP アドレスからオンプレミスの電子メール サーバーへの接続を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-140">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="ee5b3-141">Microsoft 365 IP アドレスの一覧については [、「Microsoft 365 URL と IP アドレス範囲」を参照してください](../../enterprise/urls-and-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-141">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="ee5b3-142">オンプレミス環境にメッセージを配信する必要がない場合は、警告で[今すぐ修正] をクリックして、Microsoft 365 が無効な受信者を含むメッセージを直ちに拒否できます。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-142">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="ee5b3-143">これにより、無効な受信者に対する組織のクォータを超えるリスクが軽減され、通常のメッセージ配信に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-143">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="ee5b3-144">または、次の手順を使用して手動で問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-144">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="ee5b3-145">Exchange 管理 [センター (EAC)](/Exchange/exchange-admin-center)で、Microsoft 365 からオンプレミスの電子メール環境にメールを配信するコネクタを無効または削除します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-145">In the [Exchange admin center (EAC)](/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="ee5b3-146">EAC で、[メール フロー コネクタ **]** \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-146">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="ee5b3-147">[From] 値が **365** Officeのコネクタを選択し、[To **value** Your organization's **email server]** を選択し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="ee5b3-148">[削除] アイコンをクリックして **コネクタを** ![ 削除する](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="ee5b3-148">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="ee5b3-149">[編集] アイコンをクリック **し、[有効** にする] を ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) オフにしてコネクタ **を無効にします**。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-149">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="ee5b3-150">社内メール環境に関連付けられている Microsoft 365 の受け入れドメインを内部 **リレー** から権限のあるドメイン **に変更します**。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-150">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="ee5b3-151">手順については [、「Exchange Online で受け入れドメインを管理する」を参照してください](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-151">For instructions, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="ee5b3-152">**注**: 通常、これらの変更は有効に 30 分から 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-152">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="ee5b3-153">1 時間後に、エラーが表示されなくなったか確認します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-153">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="ee5b3-154">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-154">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="ee5b3-155">エラー コード:450 4.4.317 リモート サーバーに接続できません</span><span class="sxs-lookup"><span data-stu-id="ee5b3-155">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="ee5b3-156">通常、このエラーは、Microsoft 365 が宛先メール サーバーに接続されているが、サーバーが即時エラーで応答した、または接続要件を満たさなかったという意味です。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-156">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="ee5b3-157">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-157">The error details will explain the problem.</span></span> <span data-ttu-id="ee5b3-158">例:</span><span class="sxs-lookup"><span data-stu-id="ee5b3-158">For example:</span></span>

- <span data-ttu-id="ee5b3-159">送信先の電子メール サーバーは、サーバーが Microsoft 365 との通信を維持できないという "サービスが利用できない" エラーで応答しました。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-159">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="ee5b3-160">コネクタは TLS を必要とするように構成されますが、宛先メール サーバーは TLS をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-160">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="ee5b3-161">エラー コード 450 4.4.317 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="ee5b3-161">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="ee5b3-162">オンプレミスの電子メール サーバー上の TLS 設定と証明書、およびコネクタの TLS 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-162">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="ee5b3-163">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-163">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="ee5b3-164">エラー コード:450 4.4.318 接続が突然切断されました</span><span class="sxs-lookup"><span data-stu-id="ee5b3-164">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="ee5b3-165">通常、このエラーは、Microsoft 365 がオンプレミスの電子メール環境との通信が困難で、接続が削除されたという意味です。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-165">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="ee5b3-166">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="ee5b3-166">The possible causes for this error are:</span></span>

- <span data-ttu-id="ee5b3-167">ファイアウォールが SMTP パケットの検証規則を使用していますが、それらの規則が正しく動作していません。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-167">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="ee5b3-168">オンプレミスの電子メール サーバーが正しく動作していません (サービスのハング、クラッシュ、システム リソースの低下など)、サーバーがタイム アウトして Microsoft 365 への接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-168">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="ee5b3-169">オンプレミス環境と Microsoft 365 の間にはネットワークの問題があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-169">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="ee5b3-170">エラー コード 450 4.4.318 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="ee5b3-170">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="ee5b3-171">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-171">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="ee5b3-172">オンプレミス環境と Microsoft 365 の間のネットワークの問題が原因で問題が発生した場合は、ネットワーク チームに問い合わせ、問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-172">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="ee5b3-173">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-173">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="ee5b3-174">エラー コード:450 4.7.320 証明書の検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="ee5b3-174">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="ee5b3-175">通常、このエラーは、宛先メール サーバーの証明書の検証中に Microsoft 365 でエラーが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-175">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="ee5b3-176">エラーの詳細に、このエラーについての説明があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-176">The error details will explain the error.</span></span> <span data-ttu-id="ee5b3-177">例:</span><span class="sxs-lookup"><span data-stu-id="ee5b3-177">For example:</span></span>

- <span data-ttu-id="ee5b3-178">証明書が期限切れです</span><span class="sxs-lookup"><span data-stu-id="ee5b3-178">Certificate expired</span></span>

- <span data-ttu-id="ee5b3-179">証明書のサブジェクトが一致しません</span><span class="sxs-lookup"><span data-stu-id="ee5b3-179">Certificate subject mismatch</span></span>

- <span data-ttu-id="ee5b3-180">証明書が無効です</span><span class="sxs-lookup"><span data-stu-id="ee5b3-180">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="ee5b3-181">エラー コード 450 4.7.320 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="ee5b3-181">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="ee5b3-182">Microsoft 365 でキューに入っているメッセージを配信できるよう、コネクタの証明書または設定を修正します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-182">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="ee5b3-183">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="ee5b3-184">その他のエラー コード</span><span class="sxs-lookup"><span data-stu-id="ee5b3-184">Other error codes</span></span>

<span data-ttu-id="ee5b3-185">Microsoft 365 では、オンプレミスまたはパートナーの電子メール サーバーへのメッセージの配信が困難です。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-185">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="ee5b3-186">エラーに含まれる **宛先サーバー** の情報を確認して、ご使用の環境の問題を調べるか、構成エラーがあった場合はコネクタを変更します。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-186">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="ee5b3-187">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5b3-187">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>