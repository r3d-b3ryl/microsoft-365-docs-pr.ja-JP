---
title: ランサムウェア攻撃から回復する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365管理者は、ランサムウェア攻撃から回復する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 608fac50fc65f20a612b80ed151252eb2a0c2e01
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415555"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="273f9-103">ユーザーのランサムウェア攻撃から回復Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="273f9-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="273f9-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="273f9-104">**Applies to**</span></span>
- [<span data-ttu-id="273f9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="273f9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="273f9-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="273f9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="273f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="273f9-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="273f9-108">組織を保護するためにあらゆる予防措置を講じた場合でも、ランサムウェア攻撃の被害に陥 [る可能性](/windows/security/threat-protection/intelligence/ransomware-malware) があります。</span><span class="sxs-lookup"><span data-stu-id="273f9-108">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="273f9-109">ランサムウェアは大きなビジネスであり、攻撃は非常に高度です。</span><span class="sxs-lookup"><span data-stu-id="273f9-109">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="273f9-110">この記事の手順では、データを回復し、感染の内部拡散を停止する最良の機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="273f9-110">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="273f9-111">開始する前に、次の項目を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="273f9-111">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="273f9-112">身代金の支払いによってファイルへのアクセスが返されるという保証はありません。</span><span class="sxs-lookup"><span data-stu-id="273f9-112">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="273f9-113">実際、身代金を支払って、より多くのランサムウェアのターゲットとなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="273f9-113">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="273f9-114">支払い済みで、攻撃者のソリューションを使用せずに回復した場合は、銀行に問い合わせ、トランザクションをブロックできるのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="273f9-114">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="273f9-115">また、この記事で後述するように、ランサムウェア攻撃を法執行機関、詐欺報告 Web サイト、および Microsoft に報告することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="273f9-115">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="273f9-116">攻撃とその結果に迅速に対応することが重要です。</span><span class="sxs-lookup"><span data-stu-id="273f9-116">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="273f9-117">待つ時間が長くなると、影響を受けるデータを回復できる可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="273f9-117">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="273f9-118">手順 1: バックアップを確認する</span><span class="sxs-lookup"><span data-stu-id="273f9-118">Step 1: Verify your backups</span></span>

<span data-ttu-id="273f9-119">オフライン バックアップがある場合は、環境からランサムウェア ペイロード (マルウェア) を削除した後で、暗号化されたデータを復元できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="273f9-119">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="273f9-120">バックアップが作成されていない場合、またはバックアップがランサムウェアの影響を受けた場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="273f9-120">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="273f9-121">手順 2: サーバーとExchange ActiveSyncを無効OneDrive 同期</span><span class="sxs-lookup"><span data-stu-id="273f9-121">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="273f9-122">ここで重要なポイントは、ランサムウェアによるデータ暗号化の拡散を停止することです。</span><span class="sxs-lookup"><span data-stu-id="273f9-122">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="273f9-123">ランサムウェア暗号化のターゲットとしてメールが疑われる場合は、メールボックスへのユーザー アクセスを一時的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="273f9-123">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="273f9-124">Exchange ActiveSyncデバイスとメールボックス間でデータExchange Online同期します。</span><span class="sxs-lookup"><span data-stu-id="273f9-124">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="273f9-125">メールボックスのExchange ActiveSyncを無効にするには、「ユーザーのメールボックスを無効にするExchange ActiveSync[する方法」をExchange Online。](https://support.microsoft.com/help/2795303)</span><span class="sxs-lookup"><span data-stu-id="273f9-125">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="273f9-126">メールボックスへの他の種類のアクセスを無効にするには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="273f9-126">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="273f9-127">[メールボックスの MAPI を有効または無効にします](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。</span><span class="sxs-lookup"><span data-stu-id="273f9-127">[Enable or disable MAPI for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="273f9-128">ユーザーの POP3 または IMAP4 アクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="273f9-128">Enable or Disable POP3 or IMAP4 access for a user</span></span>](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="273f9-129">一時停止OneDrive 同期は、感染する可能性のあるデバイスによってクラウド データが更新されるのを保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="273f9-129">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="273f9-130">詳細については、「How to Pause and Resume sync in [OneDrive」 を参照してください](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。</span><span class="sxs-lookup"><span data-stu-id="273f9-130">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="273f9-131">手順 3: 影響を受けるデバイスからマルウェアを削除する</span><span class="sxs-lookup"><span data-stu-id="273f9-131">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="273f9-132">疑わしいすべてのコンピューターとデバイスで現在の完全なウイルス対策スキャンを実行して、ランサムウェアに関連付けられているペイロードを検出して削除します。</span><span class="sxs-lookup"><span data-stu-id="273f9-132">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="273f9-133">データを同期しているデバイス、またはマップされたネットワーク ドライブのターゲットをスキャンすることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="273f9-133">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="273f9-134">古いクライアント[Windows Defender](https://www.microsoft.com/windows/comprehensive-security)または (古い[クライアントの場合](https://www.microsoft.com/download/details.aspx?id=5201)) を使用Microsoft Security Essentials。</span><span class="sxs-lookup"><span data-stu-id="273f9-134">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="273f9-135">ランサムウェアやマルウェアの削除にも役立つ代替手段は、 [悪意のあるソフトウェア削除ツール (MSRT) です](https://www.microsoft.com/download/details.aspx?id=9905)。</span><span class="sxs-lookup"><span data-stu-id="273f9-135">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="273f9-136">これらのオプションが機能しない場合は、[オフライン][](https://support.microsoft.com/help/17466)または [Windows Defenderマルウェアの検出と削除に関する問題のトラブルシューティング] を[試してみてください](https://support.microsoft.com/help/4466982)。</span><span class="sxs-lookup"><span data-stu-id="273f9-136">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="273f9-137">手順 4: クリーンアップされたコンピューターまたはデバイス上のファイルを回復する</span><span class="sxs-lookup"><span data-stu-id="273f9-137">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="273f9-138">環境からランサムウェア ペイロードを削除する前の手順を完了したら (ランサムウェアがファイルを暗号化または削除することを防ぐ)、Windows 7 の[](https://support.microsoft.com/help/17128)Windows 10 および Windows 8.1 または System Protection のファイル履歴を使用して、ローカル ファイルとフォルダーの回復を試みることもできます。</span><span class="sxs-lookup"><span data-stu-id="273f9-138">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="273f9-139">**注意**:</span><span class="sxs-lookup"><span data-stu-id="273f9-139">**Notes**:</span></span>

- <span data-ttu-id="273f9-140">また、一部のランサムウェアはバックアップ バージョンを暗号化または削除します。そのため、ファイルの履歴やシステム保護を使用してファイルを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="273f9-140">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="273f9-141">その場合は、次のセクションで説明するように、ランサムウェアやマルウェアの影響を受けOneDriveデバイスでバックアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="273f9-141">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="273f9-142">フォルダーが OneDrive に同期され、最新バージョンの Windows を使用していない場合は、ファイル履歴を使用していくつかの制限が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="273f9-142">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="273f9-143">手順 5: ファイルを復元する方法OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="273f9-143">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="273f9-144">[ファイルの復元] OneDrive for Businessを使用すると、過去 30 日以内OneDrive以前の時点に復元できます。</span><span class="sxs-lookup"><span data-stu-id="273f9-144">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="273f9-145">詳細については、「[OneDrive を復元する](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="273f9-145">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="273f9-146">手順 6: 削除されたメールを復元する</span><span class="sxs-lookup"><span data-stu-id="273f9-146">Step 6: Recover deleted email</span></span>

<span data-ttu-id="273f9-147">まれに、ランサムウェアがすべてのメールを削除した場合、削除されたアイテムを復元できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="273f9-147">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="273f9-148">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="273f9-148">For more information, see:</span></span>

- [<span data-ttu-id="273f9-149">ユーザーのメールボックス内の削除済みメッセージを復元する</span><span class="sxs-lookup"><span data-stu-id="273f9-149">Recover deleted messages in a user's mailbox</span></span>](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="273f9-150">Windows 版 Outlook で削除済みのアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="273f9-150">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="273f9-151">手順 7: 再び有効にし、Exchange ActiveSyncをOneDrive 同期</span><span class="sxs-lookup"><span data-stu-id="273f9-151">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="273f9-152">コンピューターとデバイスをクリーンアップしてデータを回復した後、手順 2 で以前に無効にした Exchange ActiveSync と OneDrive 同期 を再[び有効にすることができます](#step-2-disable-exchange-activesync-and-onedrive-sync)。</span><span class="sxs-lookup"><span data-stu-id="273f9-152">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="273f9-153">手順 8 (オプション): 特定のOneDrive 同期ファイルのブロック</span><span class="sxs-lookup"><span data-stu-id="273f9-153">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="273f9-154">回復後、このランサムウェアの影響を受けたOneDrive for Businessクライアントが同期されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="273f9-154">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="273f9-155">詳細については [、「Set-SPOTenantSyncClientRestriction」を参照してください。](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="273f9-155">For more information, see [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="273f9-156">攻撃を報告する</span><span class="sxs-lookup"><span data-stu-id="273f9-156">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="273f9-157">法執行機関に問い合わせ</span><span class="sxs-lookup"><span data-stu-id="273f9-157">Contact law enforcement</span></span>

<span data-ttu-id="273f9-158">現地または連邦の法執行機関に問い合わせるべきです。</span><span class="sxs-lookup"><span data-stu-id="273f9-158">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="273f9-159">たとえば、米国にいる場合は [、FBI](https://www.fbi.gov/contact-us/field)ローカル フィールド オフィス [、IC3、](http://www.ic3.gov/complaint/default.aspx) シークレット サービスに [問い合わせできます](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="273f9-159">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="273f9-160">国の詐欺報告 Web サイトにレポートを送信する</span><span class="sxs-lookup"><span data-stu-id="273f9-160">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="273f9-161">詐欺報告 Web サイトは、詐欺を防止し回避する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="273f9-161">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="273f9-162">また、詐欺の被害に見合った場合に報告するメカニズムも提供されます。</span><span class="sxs-lookup"><span data-stu-id="273f9-162">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="273f9-163">オーストラリア: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="273f9-163">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="273f9-164">カナダ: [カナダ詐欺対策センター](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="273f9-164">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="273f9-165">フランス: [アジェンス・ナショナル・デ・ラ・セクリテ・デ・システムズの情報](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="273f9-165">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="273f9-166">ドイツ: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="273f9-166">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="273f9-167">アイルランド: [ガルダ Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="273f9-167">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="273f9-168">ニュージーランド: [消費者問題詐欺](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="273f9-168">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="273f9-169">スイス [ナナレス Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span><span class="sxs-lookup"><span data-stu-id="273f9-169">Switzerland [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)</span></span>

- <span data-ttu-id="273f9-170">英国: [アクション詐欺](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="273f9-170">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="273f9-171">米国: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="273f9-171">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="273f9-172">国が一覧に表示されていない場合は、地域または連邦の法執行機関に問い合います。</span><span class="sxs-lookup"><span data-stu-id="273f9-172">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="273f9-173">Microsoft に電子メール メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="273f9-173">Submit email messages to Microsoft</span></span>

<span data-ttu-id="273f9-174">ランサムウェアを含むフィッシング メッセージを報告するには、いくつかの方法のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="273f9-174">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="273f9-175">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="273f9-175">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="additional-ransomware-resources"></a><span data-ttu-id="273f9-176">その他のランサムウェア リソース</span><span class="sxs-lookup"><span data-stu-id="273f9-176">Additional ransomware resources</span></span>

<span data-ttu-id="273f9-177">主要な業界情報:</span><span class="sxs-lookup"><span data-stu-id="273f9-177">Key industry information:</span></span>

- [<span data-ttu-id="273f9-178">人が操作するランサムウェアの概要</span><span class="sxs-lookup"><span data-stu-id="273f9-178">Human-operated ransomware overview</span></span>](/security/compass/human-operated-ransomware)

- [<span data-ttu-id="273f9-179">ランサムウェアや強要から迅速に保護する</span><span class="sxs-lookup"><span data-stu-id="273f9-179">Rapidly protect against ransomware and extortion</span></span>](/security/compass/protect-against-ransomware)

- <span data-ttu-id="273f9-180">[最新のMicrosoft セキュリティ インテリジェンスレポート](https://www.microsoft.com/securityinsights/)(P. 22-24)</span><span class="sxs-lookup"><span data-stu-id="273f9-180">[The latest Microsoft Security Intelligence Report](https://www.microsoft.com/securityinsights/) (see pages 22-24)</span></span>

- <span data-ttu-id="273f9-181">**ランサムウェア: Microsoft 365 Defender** ポータルの Threat **analytics** ノードにある、継続的な脅威レポート (以下のライセンス要件を [参照](/microsoft-365/security/defender/prerequisites#licensing-requirements))</span><span class="sxs-lookup"><span data-stu-id="273f9-181">**Ransomware: A pervasive and ongoing threat** report in the **Threat analytics node** of the Microsoft 365 Defender portal (see these [licensing requirements](/microsoft-365/security/defender/prerequisites#licensing-requirements))</span></span>

<span data-ttu-id="273f9-182">Microsoft 365保護:</span><span class="sxs-lookup"><span data-stu-id="273f9-182">Microsoft 365 protection:</span></span>

- [<span data-ttu-id="273f9-183">マルウェアと ランサムウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="273f9-183">Malware and ransomware protection</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [<span data-ttu-id="273f9-184">ランサムウェアの検出と、ファイルの復元OneDrive</span><span class="sxs-lookup"><span data-stu-id="273f9-184">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)
- [<span data-ttu-id="273f9-185">ファイル内のマクロを有効またはOfficeする</span><span class="sxs-lookup"><span data-stu-id="273f9-185">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)
- [<span data-ttu-id="273f9-186">EOP と Microsoft Defender のセキュリティに関するOffice 365設定</span><span class="sxs-lookup"><span data-stu-id="273f9-186">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365.md)

<span data-ttu-id="273f9-187">Microsoft Security チームのブログ投稿:</span><span class="sxs-lookup"><span data-stu-id="273f9-187">Microsoft Security team blog posts:</span></span>

- [<span data-ttu-id="273f9-188">サイバーセキュリティリスクを理解することで回復力を高める:パート 4:現在の脅威をナビゲートする (2021 年 5 月)</span><span class="sxs-lookup"><span data-stu-id="273f9-188">Becoming resilient by understanding cybersecurity risks: Part 4—navigating current threats (May 2021)</span></span>](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  <span data-ttu-id="273f9-189">「ランサムウェア **」セクションを参照** してください。</span><span class="sxs-lookup"><span data-stu-id="273f9-189">See the **Ransomware** section.</span></span>

- [<span data-ttu-id="273f9-190">人が操作するランサムウェア攻撃: 予防可能な災害 (2020 年 3 月)</span><span class="sxs-lookup"><span data-stu-id="273f9-190">Human-operated ransomware attacks: A preventable disaster (March 2020)</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)
- [<span data-ttu-id="273f9-191">ランサムウェアの応答 - 支払いを行う場合と支払わない場合(2019 年 12 月)</span><span class="sxs-lookup"><span data-stu-id="273f9-191">Ransomware response—to pay or not to pay? (December 2019)</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [<span data-ttu-id="273f9-192">Norsk Hydro が透明性を持つランサムウェア攻撃に対応 (2019 年 12 月)</span><span class="sxs-lookup"><span data-stu-id="273f9-192">Norsk Hydro responds to ransomware attack with transparency (December 2019)</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
- [<span data-ttu-id="273f9-193">価値あるアップグレード: 2017 年Windows 10に対する回復力を証明する次世代セキュリティ (2018 年 1 月)</span><span class="sxs-lookup"><span data-stu-id="273f9-193">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017 (January 2018)</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

