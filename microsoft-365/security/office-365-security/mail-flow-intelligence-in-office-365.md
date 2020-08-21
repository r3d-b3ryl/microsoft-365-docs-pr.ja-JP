---
title: メール フロー インテリジェンス
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理者は、コネクタ (メール フロー インテリジェンスとも呼ばれる) を使用してメッセージ配信に関連付けられたエラー コードについて学習できます。
ms.openlocfilehash: b345b52f572efca2aca1fde6ba720d733e521cc4
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827715"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="6a4c0-103">EOP でのメール フロー インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="6a4c0-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="6a4c0-104">Exchange Online にメールボックスを含む Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、通常、コネクタを使用して EOP から社内の電子メール環境に電子メール メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="6a4c0-105">また、Microsoft 365 からパートナーの組織にメッセージをルーティングするためにコネクタを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="6a4c0-106">コネクタを介して Microsoft 365 がこれらのメッセージを配信しない場合、そのメッセージは Microsoft 365 でキューに入れされます。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="6a4c0-107">Microsoft 365 は、24 時間につき各メッセージの配信を再試行し続けします。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="6a4c0-108">24 時間後、キュー内のメッセージは期限切れになってから、配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) 内で元の送信者にそのメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="6a4c0-109">コネクタを使用してメッセージを配信しない場合、Microsoft 365 はエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="6a4c0-110">最も一般的なエラーとその解決策について、このトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="6a4c0-111">コネクタ経由で送信された配信不可能なメッセージのキューイングおよび通知エラーは、メール フロー インテリジェン _スと呼ばれます_。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="6a4c0-112">エラー コード:450 4.4.312 DNS クエリに失敗しました</span><span class="sxs-lookup"><span data-stu-id="6a4c0-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="6a4c0-113">通常、このエラーは、Microsoft 365 がコネクタで指定されたスマート ホストに接続しようとしたが、スマート ホストの IP アドレスを見つけるための DNS クエリが失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="6a4c0-114">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="6a4c0-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="6a4c0-115">ご使用のドメインの DNS ホスティング サービス (ご使用のドメインの権威ネーム サーバーを管理しているパーティ) に問題があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="6a4c0-116">ご使用のドメインの有効期限が最近切れたため、MX レコードを取得できません。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="6a4c0-117">ドメインの MX レコードが最近変更されましたが、DNS サーバーは以前にキャッシュに入れていたドメインの DNS 情報を依然として参照しています。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="6a4c0-118">エラー コード 450 4.4.312 の修正方法</span><span class="sxs-lookup"><span data-stu-id="6a4c0-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="6a4c0-119">DNS ホスティング サービスにお使いのドメインの問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="6a4c0-120">エラーがパートナー組織 (たとえば、サード パーティ製のクラウド サービス プロバイダー) に送信されたものである場合は、パートナーに連絡して問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="6a4c0-121">エラー コード:450 4.4.315 接続がタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="6a4c0-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="6a4c0-122">通常、これは Microsoft 365 が宛先のメール サーバーに接続できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="6a4c0-123">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-123">The error details will explain the problem.</span></span> <span data-ttu-id="6a4c0-124">例:</span><span class="sxs-lookup"><span data-stu-id="6a4c0-124">For example:</span></span>

- <span data-ttu-id="6a4c0-125">オンプレミスのメール サーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="6a4c0-126">コネクタのスマート ホストの設定にエラーがあるため、Microsoft 365 が誤った IP アドレスに接続しようとしています。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="6a4c0-127">エラー コード 450 4.4.315 の修正方法</span><span class="sxs-lookup"><span data-stu-id="6a4c0-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="6a4c0-128">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="6a4c0-129">たとえば、メール フローがこれまで正しく動作してきたがコネクタの設定を変更していない場合は、オンプレミスのメール環境をチェックして、サーバーがダウンしていないか、またはネットワーク インフラストラクチャへの変更 (たとえば、インターネット サービス プロバイダーを変更したため、IP アドレスが以前とは異なる) が確認される場合を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="6a4c0-130">エラーがパートナー組織 (たとえば、サード パーティ製のクラウド サービス プロバイダー) に送信されたものである場合は、パートナーに連絡して問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="6a4c0-131">エラー コード:450 4.4.316 接続が拒否されました</span><span class="sxs-lookup"><span data-stu-id="6a4c0-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="6a4c0-132">通常、このエラーは、Microsoft 365 が宛先のメール サーバーに接続を試みて接続エラーが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="6a4c0-133">このエラーの原因として考えられるのは、ファイアウォールが Microsoft 365 の IP アドレスからの接続をブロックしている場合です。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="6a4c0-134">または、このエラーは、完全にオンプレミスのメール システムを Microsoft 365 に移行し、オンプレミスのメール環境をシャット ダウンした場合の設計上、一般的なエラーである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="6a4c0-135">エラー コード 450 4.4.316 の修正方法</span><span class="sxs-lookup"><span data-stu-id="6a4c0-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="6a4c0-136">オンプレミスの環境にメールボックスがある場合は、TCP ポート 25 で Microsoft 365 の IP アドレスからオンプレミスの電子メール サーバーへの接続を許可するようにファイアウォールの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="6a4c0-137">Microsoft 365 IP アドレスの一覧については [、「Microsoft 365 URL および IP アドレス範囲」をご覧ください](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="6a4c0-138">オンプレミスの環境にメッセージを配信する必要がなくなった場合は、アラート **内の** [今すぐ修正] をクリックし、無効な受信者が含まれますら Microsoft 365 がすぐにメッセージを拒否できます。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="6a4c0-139">これにより、無効な受信者に対する組織のクォータを超過するリスクが軽減されます。これにより、通常のメッセージ配信に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="6a4c0-140">または、次の手順に従って問題を手動で解決することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="6a4c0-141">Exchange 管理 [センター (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)で、Microsoft 365 からオンプレミスの電子メール環境に電子メールを送信するコネクタを無効にするか削除します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="6a4c0-142">EAC で、メール フロー **コネクタに** \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="6a4c0-143">[送信元]**の**値**が Office 365、** かつ組織のメール サーバーのメール サーバーの **[送信\*\*\*\*先]** 値のコネクタを選択し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="6a4c0-144">[削除] アイコンをクリックして **コネクタを** ![ 削除する](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="6a4c0-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="6a4c0-145">[編集] アイコンをクリック **して [Turn** ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) it] をクリックして、コネクタ **を無効にする**。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="6a4c0-146">オンプレミスのメール環境に関連付けられている Microsoft 365 の承認済みドメインを **、"内部の中継" から "権限を持\*\*\*\*つ" に変更します**。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="6a4c0-147">手順については [、Exchange Online で承認済みドメインの管理に関するページを参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="6a4c0-148">**注**: 通常、これらの変更が有効になるには、30 分から 1 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="6a4c0-149">1 時間後に、エラーが表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="6a4c0-150">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="6a4c0-151">エラー コード:450 4.4.317 リモート サーバーに接続できません</span><span class="sxs-lookup"><span data-stu-id="6a4c0-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="6a4c0-152">通常、このエラーは、Microsoft 365 が宛先のメール サーバーに接続したが、サーバーが即時エラーを返したか、接続要件を満たしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="6a4c0-153">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-153">The error details will explain the problem.</span></span> <span data-ttu-id="6a4c0-154">例:</span><span class="sxs-lookup"><span data-stu-id="6a4c0-154">For example:</span></span>

- <span data-ttu-id="6a4c0-155">送信先のメール サーバーから"サービスは利用できません" というエラーが返されました。これは、サーバーが Microsoft 365 との通信を維持できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="6a4c0-156">コネクタは TLS を要求するように設定されていますが、送信先のメール サーバーが TLS をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="6a4c0-157">エラー コード 450 4.4.317 の修正方法</span><span class="sxs-lookup"><span data-stu-id="6a4c0-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="6a4c0-158">オンプレミスのメール サーバーで TLS の設定と証明書と、コネクタの TLS の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="6a4c0-159">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="6a4c0-160">エラー コード:450 4.4.318 接続が突然切断されました</span><span class="sxs-lookup"><span data-stu-id="6a4c0-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="6a4c0-161">通常、このエラーは、Microsoft 365 とオンプレミスのメール環境との情報のやり取りに問題が発生したため、接続が切れていたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="6a4c0-162">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="6a4c0-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="6a4c0-163">ファイアウォールが SMTP パケットの検証規則を使用していますが、それらの規則が正しく動作していません。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="6a4c0-164">オンプレミスのメール サーバーが正しく動作していない (たとえば、サービスのハング、クラッシュ、システム リソースの不使用) ため、サーバーは Microsoft 365 への接続がタイムアウトし、終了します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="6a4c0-165">オンプレミス環境と Microsoft 365 の間にネットワークの問題があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="6a4c0-166">エラー コード 450 4.4.318 の修正方法</span><span class="sxs-lookup"><span data-stu-id="6a4c0-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="6a4c0-167">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="6a4c0-168">オンプレミス環境と Microsoft 365 の間のネットワーク問題が原因で発生した問題の場合は、ネットワーク チームに連絡して、問題のトラブルシューティングを行ってください。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="6a4c0-169">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="6a4c0-170">エラー コード:450 4.7.320 証明書の検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="6a4c0-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="6a4c0-171">通常、このエラーは、Microsoft 365 が宛先のメール サーバーの証明書を検証しているときにエラーが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="6a4c0-172">エラーの詳細に、このエラーについての説明があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-172">The error details will explain the error.</span></span> <span data-ttu-id="6a4c0-173">例:</span><span class="sxs-lookup"><span data-stu-id="6a4c0-173">For example:</span></span>

- <span data-ttu-id="6a4c0-174">証明書が期限切れです</span><span class="sxs-lookup"><span data-stu-id="6a4c0-174">Certificate expired</span></span>

- <span data-ttu-id="6a4c0-175">証明書のサブジェクトが一致しません</span><span class="sxs-lookup"><span data-stu-id="6a4c0-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="6a4c0-176">証明書が無効です</span><span class="sxs-lookup"><span data-stu-id="6a4c0-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="6a4c0-177">エラー コード 450 4.7.320 の修正方法</span><span class="sxs-lookup"><span data-stu-id="6a4c0-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="6a4c0-178">証明書またはコネクタの設定を修正し、Microsoft 365 でキューに入れていないメッセージが配信されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="6a4c0-179">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="6a4c0-180">その他のエラー コード</span><span class="sxs-lookup"><span data-stu-id="6a4c0-180">Other error codes</span></span>

<span data-ttu-id="6a4c0-181">Microsoft 365 がオンプレミスまたはパートナーのメール サーバーにメッセージを配信するのに問題があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="6a4c0-182">エラーに含まれる **宛先サーバー**の情報を確認して、ご使用の環境の問題を調べるか、構成エラーがあった場合はコネクタを変更します。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="6a4c0-183">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4c0-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
