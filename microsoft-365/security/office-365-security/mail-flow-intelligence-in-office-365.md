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
description: 管理者は、コネクタ (メール フロー インテリジェンスとも呼ばれる) を使用して、メッセージ配信に関連付けられているエラー コードについて学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7d4277d1ce3baeabcb5b1795b5d57583fbc8245
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029258"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="419f9-103">EOP でのメール フロー インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="419f9-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="419f9-104">Exchange Online または Exchange Online メールボックスのないスタンドアロンの Exchange Online Protection (EOP) 組織にメールボックスがある Microsoft 365 組織では、通常、コネクタを使用して EOP からオンプレミスの電子メール環境に電子メール メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="419f9-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="419f9-105">コネクタを使用して、Microsoft 365 からパートナー組織にメッセージをルーティングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="419f9-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="419f9-106">Microsoft 365 がコネクタ経由でこれらのメッセージを配信できない場合、Microsoft 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="419f9-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="419f9-107">Microsoft 365 は、メッセージごとに引き続き配信を 24 時間再試行します。</span><span class="sxs-lookup"><span data-stu-id="419f9-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="419f9-108">24 時間後、キューに入っているメッセージの有効期限が切れ、配信前レポート (NDR またはバウンス メッセージとも呼ばれる) で元の送信者にメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="419f9-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="419f9-109">コネクタを使用してメッセージを配信できない場合、Microsoft 365 はエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="419f9-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="419f9-110">この記事では、最も一般的なエラーとその解決策について説明します。</span><span class="sxs-lookup"><span data-stu-id="419f9-110">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="419f9-111">コネクタ経由で送信される配信不能メッセージのキュー エラーと通知エラーは、総称してメール フロー _インテリジェンスと呼ばれる機能です_。</span><span class="sxs-lookup"><span data-stu-id="419f9-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="419f9-112">エラー コード:450 4.4.312 DNS クエリに失敗しました</span><span class="sxs-lookup"><span data-stu-id="419f9-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="419f9-113">通常、このエラーは、Microsoft 365 がコネクタで指定されているスマート ホストに接続しようとしたが、スマート ホストの IP アドレスを検索するための DNS クエリが失敗した場合を意味します。</span><span class="sxs-lookup"><span data-stu-id="419f9-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="419f9-114">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="419f9-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="419f9-115">ご使用のドメインの DNS ホスティング サービス (ご使用のドメインの権威ネーム サーバーを管理しているパーティ) に問題があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="419f9-116">ご使用のドメインの有効期限が最近切れたため、MX レコードを取得できません。</span><span class="sxs-lookup"><span data-stu-id="419f9-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="419f9-117">ドメインの MX レコードが最近変更され、DNS サーバーは以前にドメインの DNS 情報をキャッシュしています。</span><span class="sxs-lookup"><span data-stu-id="419f9-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="419f9-118">エラー コード 450 4.4.312 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="419f9-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="419f9-119">DNS ホスティング サービスを使用して、ドメインの問題を特定して解決します。</span><span class="sxs-lookup"><span data-stu-id="419f9-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="419f9-120">パートナー組織 (たとえば、サードパーティのクラウド サービス プロバイダー) からエラーが発生した場合は、パートナーに連絡して問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="419f9-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="419f9-121">エラー コード:450 4.4.315 接続がタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="419f9-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="419f9-122">通常、これは Microsoft 365 が宛先の電子メール サーバーに接続できないという意味です。</span><span class="sxs-lookup"><span data-stu-id="419f9-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="419f9-123">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-123">The error details will explain the problem.</span></span> <span data-ttu-id="419f9-124">例:</span><span class="sxs-lookup"><span data-stu-id="419f9-124">For example:</span></span>

- <span data-ttu-id="419f9-125">オンプレミスの電子メール サーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="419f9-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="419f9-126">コネクタのスマート ホスト設定にエラーが発生し、Microsoft 365 が間違った IP アドレスに接続しようとしている。</span><span class="sxs-lookup"><span data-stu-id="419f9-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="419f9-127">エラー コード 450 4.4.315 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="419f9-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="419f9-128">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="419f9-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="419f9-129">たとえば、メール フローが正しく機能し、コネクタの設定を変更していない場合は、オンプレミスの電子メール環境を確認して、サーバーがダウンしているか、ネットワーク インフラストラクチャに変更が加えらたか (たとえば、インターネット サービス プロバイダーを変更したので、IP アドレスが異なっているなど) 確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="419f9-130">パートナー組織 (たとえば、サードパーティのクラウド サービス プロバイダー) からエラーが発生した場合は、パートナーに連絡して問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="419f9-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="419f9-131">エラー コード:450 4.4.316 接続が拒否されました</span><span class="sxs-lookup"><span data-stu-id="419f9-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="419f9-132">通常、このエラーは、Microsoft 365 が宛先の電子メール サーバーに接続しようとするときに接続エラーが発生したという意味です。</span><span class="sxs-lookup"><span data-stu-id="419f9-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="419f9-133">このエラーの原因として考えられるのは、ファイアウォールが Microsoft 365 IP アドレスからの接続をブロックしているという点です。</span><span class="sxs-lookup"><span data-stu-id="419f9-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="419f9-134">または、オンプレミスのメール システムを Microsoft 365 に完全に移行し、オンプレミスの電子メール環境をシャットダウンした場合は、このエラーが設計されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="419f9-135">エラー コード 450 4.4.316 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="419f9-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="419f9-136">オンプレミス環境にメールボックスがある場合は、TCP ポート 25 の Microsoft 365 IP アドレスからオンプレミスの電子メール サーバーへの接続を許可するためにファイアウォール設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="419f9-137">Microsoft 365 の IP アドレスの一覧については [、Microsoft 365 の URL](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)と IP アドレスの範囲を参照してください。</span><span class="sxs-lookup"><span data-stu-id="419f9-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="419f9-138">それ以上オンプレミス環境にメッセージを配信しない場合は、アラートで[今すぐ修正] をクリックして、Microsoft 365 が無効な受信者を含むメッセージを直ちに拒否できます。</span><span class="sxs-lookup"><span data-stu-id="419f9-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="419f9-139">これにより、無効な受信者に対する組織のクォータを超えるリスクが軽減され、通常のメッセージ配信に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="419f9-140">または、次の手順を使用して手動で問題を解決することもできます。</span><span class="sxs-lookup"><span data-stu-id="419f9-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="419f9-141">Exchange 管理 [センター (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)で、Microsoft 365 からオンプレミスの電子メール環境に電子メールを配信するコネクタを無効または削除します。</span><span class="sxs-lookup"><span data-stu-id="419f9-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="419f9-142">EAC で、メール フロー **コネクタに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="419f9-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="419f9-143">From 値がOffice **365** で[To **value** **Your organization's email server]** のコネクタを選択し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="419f9-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="419f9-144">[削除] アイコンをクリックして **コネクタを** ![ 削除する](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="419f9-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="419f9-145">[編集] アイコンをクリックし、[ **有効** にする] をオフにしてコネクタ ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **を無効にします**。</span><span class="sxs-lookup"><span data-stu-id="419f9-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="419f9-146">オンプレミスの電子メール環境に関連付けられている Microsoft 365 の受け入れドメインを内部 **の中継** から権限のあるドメインに **変更します**。</span><span class="sxs-lookup"><span data-stu-id="419f9-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="419f9-147">手順については [、「Exchange Online で承認されたドメインを管理する」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="419f9-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="419f9-148">**注**: 通常、これらの変更は有効に 30 分から 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="419f9-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="419f9-149">1 時間後に、エラーが表示されなくなったのを確認します。</span><span class="sxs-lookup"><span data-stu-id="419f9-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="419f9-150">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="419f9-151">エラー コード:450 4.4.317 リモート サーバーに接続できません</span><span class="sxs-lookup"><span data-stu-id="419f9-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="419f9-152">通常、このエラーは、Microsoft 365 が宛先の電子メール サーバーに接続したが、サーバーが即時エラーで応答した、または接続要件を満たさなかった場合を意味します。</span><span class="sxs-lookup"><span data-stu-id="419f9-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="419f9-153">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-153">The error details will explain the problem.</span></span> <span data-ttu-id="419f9-154">例:</span><span class="sxs-lookup"><span data-stu-id="419f9-154">For example:</span></span>

- <span data-ttu-id="419f9-155">送信先の電子メール サーバーが"サービスを利用できません" というエラーで応答しました。これは、サーバーが Microsoft 365 との通信を維持できない状態を示しています。</span><span class="sxs-lookup"><span data-stu-id="419f9-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="419f9-156">コネクタは TLS を要求するように構成されますが、送信先の電子メール サーバーは TLS をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="419f9-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="419f9-157">エラー コード 450 4.4.317 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="419f9-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="419f9-158">オンプレミスの電子メール サーバー上の TLS 設定と証明書、およびコネクタの TLS 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="419f9-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="419f9-159">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="419f9-160">エラー コード:450 4.4.318 接続が突然切断されました</span><span class="sxs-lookup"><span data-stu-id="419f9-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="419f9-161">通常、このエラーは、Microsoft 365 がオンプレミスの電子メール環境との通信に問題が発生し、接続が破棄されたという意味です。</span><span class="sxs-lookup"><span data-stu-id="419f9-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="419f9-162">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="419f9-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="419f9-163">ファイアウォールが SMTP パケットの検証規則を使用していますが、それらの規則が正しく動作していません。</span><span class="sxs-lookup"><span data-stu-id="419f9-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="419f9-164">オンプレミスの電子メール サーバーが正しく動作していません (サービスのハング、クラッシュ、システム リソースの低下など)。このため、サーバーがタイム アウトして Microsoft 365 への接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="419f9-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="419f9-165">オンプレミス環境と Microsoft 365 の間にはネットワークの問題があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="419f9-166">エラー コード 450 4.4.318 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="419f9-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="419f9-167">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="419f9-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="419f9-168">オンプレミス環境と Microsoft 365 の間のネットワークの問題が原因で問題が発生した場合は、ネットワーク チームに問い合わせ、問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="419f9-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="419f9-169">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="419f9-170">エラー コード:450 4.7.320 証明書の検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="419f9-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="419f9-171">通常、このエラーは、Microsoft 365 が宛先の電子メール サーバーの証明書を検証しようとしてエラーを検出したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="419f9-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="419f9-172">エラーの詳細に、このエラーについての説明があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-172">The error details will explain the error.</span></span> <span data-ttu-id="419f9-173">例:</span><span class="sxs-lookup"><span data-stu-id="419f9-173">For example:</span></span>

- <span data-ttu-id="419f9-174">証明書が期限切れです</span><span class="sxs-lookup"><span data-stu-id="419f9-174">Certificate expired</span></span>

- <span data-ttu-id="419f9-175">証明書のサブジェクトが一致しません</span><span class="sxs-lookup"><span data-stu-id="419f9-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="419f9-176">証明書が無効です</span><span class="sxs-lookup"><span data-stu-id="419f9-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="419f9-177">エラー コード 450 4.7.320 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="419f9-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="419f9-178">Microsoft 365 でキューに入っているメッセージを配信できるよう、コネクタの証明書または設定を修正します。</span><span class="sxs-lookup"><span data-stu-id="419f9-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="419f9-179">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="419f9-180">その他のエラー コード</span><span class="sxs-lookup"><span data-stu-id="419f9-180">Other error codes</span></span>

<span data-ttu-id="419f9-181">Microsoft 365 では、オンプレミスまたはパートナーの電子メール サーバーにメッセージを配信できません。</span><span class="sxs-lookup"><span data-stu-id="419f9-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="419f9-182">エラーに含まれる **宛先サーバー** の情報を確認して、ご使用の環境の問題を調べるか、構成エラーがあった場合はコネクタを変更します。</span><span class="sxs-lookup"><span data-stu-id="419f9-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="419f9-183">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="419f9-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
