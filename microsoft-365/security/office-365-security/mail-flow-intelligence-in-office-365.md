---
title: メールフローのインテリジェンス
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
description: 管理者は、コネクタ (メールフローインテリジェンスとも呼ばれます) を使用したメッセージ配信に関連付けられているエラーコードについて理解できます。
ms.openlocfilehash: e8427f3e0341ccb381121b6cdc83d20727713d4c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307919"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="1aa1e-103">EOP でのメール フロー インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="1aa1e-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="1aa1e-104">Exchange online メールボックスを使用しない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、通常、コネクタを使用して、EOP から社内の電子メール環境に電子メールメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="1aa1e-105">また、コネクタを使用して、Microsoft 365 からパートナー組織にメッセージをルーティングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="1aa1e-106">Microsoft 365 は、これらのメッセージをコネクタ経由で配信できない場合、Microsoft 365 でキューに登録されています。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="1aa1e-107">Microsoft 365 は、24時間、各メッセージの配信を再試行し続けます。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="1aa1e-108">24時間後、キューに入れられたメッセージは期限切れになり、配信不能レポート (NDR またはバウンスメッセージとも呼ばれる) で元の送信者にメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="1aa1e-109">Microsoft 365 は、コネクタを使用してメッセージを配信できない場合にエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="1aa1e-110">最も一般的なエラーとその解決策について、このトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="1aa1e-111">コネクタ経由で送信された配信不能メッセージのキューイングおよび通知エラーは、 _メールフローインテリジェンス_と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="1aa1e-112">エラー コード:450 4.4.312 DNS クエリに失敗しました</span><span class="sxs-lookup"><span data-stu-id="1aa1e-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="1aa1e-113">通常、このエラーは、Microsoft 365 がコネクタで指定されたスマートホストに接続しようとしたが、スマートホストの IP アドレスを見つけるための DNS クエリが失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="1aa1e-114">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="1aa1e-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="1aa1e-115">ご使用のドメインの DNS ホスティング サービス (ご使用のドメインの権威ネーム サーバーを管理しているパーティ) に問題があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="1aa1e-116">ご使用のドメインの有効期限が最近切れたため、MX レコードを取得できません。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="1aa1e-117">ドメインの MX レコードが最近変更され、DNS サーバーが以前にドメインの DNS 情報をキャッシュしています。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="1aa1e-118">エラーコード 450 4.4.312 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="1aa1e-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="1aa1e-119">DNS ホスティングサービスと協力して、ドメインに関する問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="1aa1e-120">エラーがパートナー組織 (たとえば、サードパーティのクラウドサービスプロバイダー) によるものである場合は、パートナーに連絡して問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="1aa1e-121">エラー コード:450 4.4.315 接続がタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="1aa1e-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="1aa1e-122">通常、これは、Microsoft 365 が宛先の電子メールサーバーに接続できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="1aa1e-123">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-123">The error details will explain the problem.</span></span> <span data-ttu-id="1aa1e-124">例:</span><span class="sxs-lookup"><span data-stu-id="1aa1e-124">For example:</span></span>

- <span data-ttu-id="1aa1e-125">オンプレミスの電子メールサーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="1aa1e-126">コネクタのスマートホスト設定にエラーがあるため、Microsoft 365 は間違った IP アドレスに接続しようとしています。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="1aa1e-127">エラーコード 450 4.4.315 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="1aa1e-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="1aa1e-128">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="1aa1e-129">たとえば、メールフローが正しく動作していて、コネクタの設定を変更していない場合は、オンプレミスの電子メール環境をチェックして、サーバーがダウンしているかどうか、またはネットワークインフラストラクチャに何らかの変更があったかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="1aa1e-130">エラーがパートナー組織 (たとえば、サードパーティのクラウドサービスプロバイダー) によるものである場合は、パートナーに連絡して問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="1aa1e-131">エラー コード:450 4.4.316 接続が拒否されました</span><span class="sxs-lookup"><span data-stu-id="1aa1e-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="1aa1e-132">通常、このエラーは、Microsoft 365 で、宛先の電子メールサーバーに接続しようとしたときに接続エラーが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="1aa1e-133">このエラーの原因として、ファイアウォールが Microsoft 365 の IP アドレスからの接続をブロックしていることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="1aa1e-134">または、オンプレミスの電子メールシステムを Microsoft 365 に完全に移行し、オンプレミスの電子メール環境をシャットダウンした場合に、このエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="1aa1e-135">エラーコード 450 4.4.316 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="1aa1e-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="1aa1e-136">オンプレミスの環境にメールボックスがある場合は、TCP ポート25の Microsoft 365 IP アドレスからオンプレミスの電子メールサーバーへの接続を許可するように、ファイアウォールの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="1aa1e-137">Microsoft 365 の IP アドレスの一覧については、「 [microsoft 365 の url と ip アドレスの範囲](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="1aa1e-138">オンプレミス環境にメッセージを配信する必要がない場合は、[通知で **今すぐ修正** する] をクリックして、Microsoft 365 が無効な受信者を含むメッセージを直ちに拒否できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="1aa1e-139">これにより、通常のメッセージ配信に影響を与える可能性がある、無効な受信者に対する組織のクォータを超えるリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="1aa1e-140">または、次の手順を使用して、手動で問題を解決することもできます。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="1aa1e-141">[Exchange 管理センター (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)で、Microsoft 365 からオンプレミスの電子メール環境に電子メールを配信するコネクタを無効にするか、削除します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="1aa1e-142">EAC で、[**メールフロー**コネクタ] に移動し \> **Connectors**ます。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="1aa1e-143">[ **差出人** ] の値が **Office 365** で、[ **宛先** ] が **組織の電子メールサーバー** の値であるコネクタを選択し、次の手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="1aa1e-144">\*\*[削除] [削除\*\* ![ ] アイコンをクリックしてコネクタを削除する](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="1aa1e-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="1aa1e-145">[編集] 編集アイコン**Edit**をクリックしてコネクタを無効にし、 ![ ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **[有効にする**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="1aa1e-146">オンプレミスの電子メール環境に関連付けられている Microsoft 365 の承認済みドメインを、 **内部の中継** から **権限**のあるドメインに変更します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="1aa1e-147">手順については、「 [Exchange Online で承認済みドメインを管理](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="1aa1e-148">**注**: 通常、これらの変更は30分から1時間かかり、有効になります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="1aa1e-149">1時間後に、エラーが表示されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="1aa1e-150">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="1aa1e-151">エラー コード:450 4.4.317 リモート サーバーに接続できません</span><span class="sxs-lookup"><span data-stu-id="1aa1e-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="1aa1e-152">通常、このエラーは、Microsoft 365 が宛先の電子メールサーバーに接続したが、サーバーが即時エラーで応答したか、接続要件を満たしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="1aa1e-153">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-153">The error details will explain the problem.</span></span> <span data-ttu-id="1aa1e-154">例:</span><span class="sxs-lookup"><span data-stu-id="1aa1e-154">For example:</span></span>

- <span data-ttu-id="1aa1e-155">宛先の電子メールサーバーが、"サービスは利用できません" というエラーで応答しました。これは、サーバーが Microsoft 365 との通信を維持できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="1aa1e-156">コネクタは TLS を要求するように構成されていますが、送信先の電子メールサーバーが TLS をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="1aa1e-157">エラーコード 450 4.4.317 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="1aa1e-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="1aa1e-158">オンプレミスの電子メールサーバー上の TLS 設定と証明書、およびコネクタの TLS 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="1aa1e-159">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="1aa1e-160">エラー コード:450 4.4.318 接続が突然切断されました</span><span class="sxs-lookup"><span data-stu-id="1aa1e-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="1aa1e-161">通常、このエラーは、Microsoft 365 がオンプレミスの電子メール環境との通信に問題が発生し、接続が切断されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="1aa1e-162">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="1aa1e-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="1aa1e-163">ファイアウォールが SMTP パケットの検証規則を使用していますが、それらの規則が正しく動作していません。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="1aa1e-164">オンプレミスの電子メールサーバーが正しく動作していない (たとえば、サービスのハング、クラッシュ、システムリソースの不足) ため、サーバーがタイムアウトし、Microsoft 365 への接続を終了しています。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="1aa1e-165">オンプレミス環境と Microsoft 365 の間にネットワークの問題があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="1aa1e-166">エラーコード 450 4.4.318 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="1aa1e-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="1aa1e-167">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="1aa1e-168">オンプレミス環境と Microsoft 365 の間のネットワークの問題によって問題が発生している場合は、ネットワークチームに連絡して問題のトラブルシューティングを依頼してください。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="1aa1e-169">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="1aa1e-170">エラー コード:450 4.7.320 証明書の検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1aa1e-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="1aa1e-171">通常、このエラーは、Microsoft 365 で、宛先の電子メールサーバーの証明書を検証しようとしたときにエラーが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="1aa1e-172">エラーの詳細に、このエラーについての説明があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-172">The error details will explain the error.</span></span> <span data-ttu-id="1aa1e-173">例:</span><span class="sxs-lookup"><span data-stu-id="1aa1e-173">For example:</span></span>

- <span data-ttu-id="1aa1e-174">証明書が期限切れです</span><span class="sxs-lookup"><span data-stu-id="1aa1e-174">Certificate expired</span></span>

- <span data-ttu-id="1aa1e-175">証明書のサブジェクトが一致しません</span><span class="sxs-lookup"><span data-stu-id="1aa1e-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="1aa1e-176">証明書が無効です</span><span class="sxs-lookup"><span data-stu-id="1aa1e-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="1aa1e-177">エラーコード 450 4.7.320 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="1aa1e-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="1aa1e-178">Microsoft 365 でキューに入れられたメッセージが配信されるように、コネクタの証明書または設定を修正します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="1aa1e-179">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="1aa1e-180">その他のエラー コード</span><span class="sxs-lookup"><span data-stu-id="1aa1e-180">Other error codes</span></span>

<span data-ttu-id="1aa1e-181">Microsoft 365 は、社内またはパートナーの電子メールサーバーにメッセージを配信する際に問題が発生しています。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="1aa1e-182">エラーに含まれる **宛先サーバー**の情報を確認して、ご使用の環境の問題を調べるか、構成エラーがあった場合はコネクタを変更します。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="1aa1e-183">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1aa1e-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
