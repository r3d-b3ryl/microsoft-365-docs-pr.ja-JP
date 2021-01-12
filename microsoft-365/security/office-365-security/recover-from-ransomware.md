---
title: ランサムウェア攻撃から回復する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.article: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 管理者は、ランサムウェア攻撃から回復する方法を学習できます。
ms.openlocfilehash: 753171578dc7b76aefadf4b8587e84320d98b912
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794450"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="a9b9c-103">Microsoft 365 でランサムウェア攻撃から回復する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a9b9c-104">組織を保護するためにあらゆる予防措置を講じた場合でも、ランサムウェア攻撃の被害を [受け取る可能性](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) があります。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="a9b9c-105">ランサムウェアは大企業であり、攻撃は非常に高度です。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-105">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="a9b9c-106">この記事の手順では、データを回復し、感染の内部拡散を止める最善の機会を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-106">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="a9b9c-107">開始する前に、次の項目を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="a9b9c-108">身代金を支払ってファイルへのアクセスを返す保証はありません。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="a9b9c-109">実際、身代金を支払うなら、より多くのランサムウェアのターゲットになれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-109">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="a9b9c-110">既に支払い済みで、攻撃者のソリューションを使用せずに回復した場合は、銀行に問い合わせ、取引をブロックすることができるか確認してください。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-110">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="a9b9c-111">また、この記事で後述するように、ランサムウェア攻撃を法執行機関、詐欺報告 Web サイト、および Microsoft に報告することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="a9b9c-112">攻撃とその結果に迅速に対応することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-112">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="a9b9c-113">待つ時間が長くなると、影響を受けるデータを回復できる可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="a9b9c-114">手順 1: バックアップを確認する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="a9b9c-115">オフライン バックアップがある場合は、環境からランサムウェア ペイロード (マルウェア) を削除した後、暗号化されたデータを復元できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="a9b9c-116">バックアップを作成しない場合、またはバックアップがランサムウェアの影響を受けた場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="a9b9c-117">手順 2: OneDrive Exchange ActiveSync同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="a9b9c-117">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="a9b9c-118">ここでの重要なポイントは、ランサムウェアによるデータ暗号化の拡散を停止することです。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="a9b9c-119">ランサムウェア暗号化のターゲットとしてメールが疑われる場合は、メールボックスへのユーザー アクセスを一時的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-119">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="a9b9c-120">Exchange ActiveSyncと Exchange Online メールボックス間でデータを同期します。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-120">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="a9b9c-121">メールボックスのExchange ActiveSyncを無効にするには、Exchange Online でユーザーのメールボックスのExchange ActiveSyncを [無効にする方法を参照してください](https://support.microsoft.com/help/2795303)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-121">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="a9b9c-122">メールボックスへの他の種類のアクセスを無効にするには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="a9b9c-123">[メールボックスの MAPI を有効または無効にします](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="a9b9c-124">ユーザーの POP3 または IMAP4 アクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="a9b9c-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="a9b9c-125">OneDrive 同期を一時停止すると、感染している可能性のあるデバイスによってクラウド データが更新されるのを保護できます。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="a9b9c-126">詳細については [、「OneDrive で同期を一時停止および再開する方法」を参照してください](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="a9b9c-127">手順 3: 影響を受けるデバイスからマルウェアを削除する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="a9b9c-128">疑わしいすべてのコンピューターとデバイスで最新の完全なウイルス対策スキャンを実行し、ランサムウェアに関連付けられているペイロードを検出して削除します。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-128">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="a9b9c-129">データを同期しているデバイスや、マップされたネットワーク ドライブのターゲットをスキャンすることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-129">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="a9b9c-130">以前 [のクライアントWindows Defender](https://www.microsoft.com/windows/comprehensive-security) (古い [クライアントの場合](https://www.microsoft.com/download/details.aspx?id=5201)) を使用Microsoft Security Essentials。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="a9b9c-131">ランサムウェアやマルウェアの削除にも役立つ代替手段として、悪意のあるソフトウェアの削除 [ツール (MSRT) があります](https://www.microsoft.com/download/details.aspx?id=9905)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="a9b9c-132">これらのオプションが機能しない場合は、[オフライン] または [マルウェアの [Windows Defender](https://support.microsoft.com/help/17466) と削除に関する問題のトラブルシューティング] を [試してください](https://support.microsoft.com/help/4466982)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="a9b9c-133">手順 4: クリーンアップされたコンピューターまたはデバイス上のファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="a9b9c-134">ランサムウェア ペイロードを環境から削除する前の手順を完了したら (ランサムウェアによるファイルの暗号化や削除を防ぐ)、Windows 10 および[](https://support.microsoft.com/help/17128)Windows 8.1 のファイル履歴、または Windows 7 の System Protection を使用して、ローカルのファイルとフォルダーの回復を試みることもできます。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="a9b9c-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="a9b9c-135">**Notes**:</span></span>

- <span data-ttu-id="a9b9c-136">一部のランサムウェアはバックアップ バージョンも暗号化または削除します。そのため、ファイル履歴やシステム保護を使用してファイルを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="a9b9c-137">その場合は、次のセクションで説明するように、ランサムウェアまたは OneDrive の影響を受けない外部ドライブまたはデバイスでバックアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="a9b9c-138">フォルダーが OneDrive と同期され、最新バージョンの Windows を使用していない場合は、ファイル履歴の使用にいくつかの制限が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="a9b9c-139">手順 5: OneDrive for Business でファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="a9b9c-140">OneDrive for Business でのファイルの復元では、過去 30 日以内に OneDrive 全体を以前の時点に復元できます。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="a9b9c-141">詳細については [、「OneDrive を復元する」を参照してください](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="a9b9c-142">手順 6: 削除されたメールを復元する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="a9b9c-143">ランサムウェアによってすべてのメールが削除されるというまれなケースでは、おそらく削除済みアイテムを回復できます。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="a9b9c-144">詳しくは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-144">For more information, see:</span></span>

- [<span data-ttu-id="a9b9c-145">ユーザーのメールボックス内の削除済みメッセージを復元する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="a9b9c-146">Windows 版 Outlook で削除済みのアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="a9b9c-147">手順 7: 同期と OneDrive Exchange ActiveSyncを再び有効にする</span><span class="sxs-lookup"><span data-stu-id="a9b9c-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="a9b9c-148">コンピューターとデバイスをクリーンアップしてデータを回復した後、手順 2 で無効にした Exchange ActiveSync と OneDrive の同期を再 [び有効にすることができます](#step-2-disable-exchange-activesync-and-onedrive-sync)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-148">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="a9b9c-149">手順 8 (オプション): 特定のファイル拡張子に対する OneDrive 同期をブロックする</span><span class="sxs-lookup"><span data-stu-id="a9b9c-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="a9b9c-150">回復した後、OneDrive for Business クライアントがこのランサムウェアの影響を受けたファイルの種類を同期されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="a9b9c-151">詳細については[、「Set-SPOTenantSyncClientRestriction」を参照してください](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="a9b9c-152">攻撃を報告する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="a9b9c-153">法執行機関に問い合わせ</span><span class="sxs-lookup"><span data-stu-id="a9b9c-153">Contact law enforcement</span></span>

<span data-ttu-id="a9b9c-154">現地または連邦法執行機関に問い合わせが必要です。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="a9b9c-155">たとえば、米国にいる場合は [、FBI](https://www.fbi.gov/contact-us/field)ローカル フィールド オフィス [、IC3、](http://www.ic3.gov/complaint/default.aspx) またはシークレット サービスに [問い合わせできます](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="a9b9c-156">お客様の国の詐欺報告 Web サイトにレポートを送信する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="a9b9c-157">詐欺報告 Web サイトは、詐欺を防止および回避する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="a9b9c-158">また、詐欺の被害を受けした場合に報告するメカニズムも提供します。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="a9b9c-159">オーストラリア: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="a9b9c-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="a9b9c-160">カナダ: [カナダ詐欺対策センター](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="a9b9c-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="a9b9c-161">フランス: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="a9b9c-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="a9b9c-162">ドイツ: [Bundesamt fの Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="a9b9c-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="a9b9c-163">アイルランド: [アン・シオホザ](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="a9b9c-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="a9b9c-164">ニュージーランド: [消費者消費者詐欺](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="a9b9c-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="a9b9c-165">英国: [アクション詐欺](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="a9b9c-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="a9b9c-166">米国: [On Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="a9b9c-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="a9b9c-167">お客様の国が一覧に表示されていない場合は、現地の法執行機関または連邦法執行機関にお問い合ください。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="a9b9c-168">Microsoft に電子メール メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="a9b9c-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="a9b9c-169">ランサムウェアを含むフィッシング メッセージは、いくつかの方法のいずれかを使用して報告できます。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-169">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="a9b9c-170">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a9b9c-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9b9c-171">See also</span></span>

- [<span data-ttu-id="a9b9c-172">ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="a9b9c-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="a9b9c-173">ランサムウェアの応答 — 支払いを行うのか、それとも支払わないか。</span><span class="sxs-lookup"><span data-stu-id="a9b9c-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="a9b9c-174">Norsk Respond は、透明性を持つランサムウェア攻撃に対応します</span><span class="sxs-lookup"><span data-stu-id="a9b9c-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="a9b9c-175">OneDrive でのランサムウェア検出とファイルの回復</span><span class="sxs-lookup"><span data-stu-id="a9b9c-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="a9b9c-176">Microsoft セキュリティ インテリジェンス レポート</span><span class="sxs-lookup"><span data-stu-id="a9b9c-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="a9b9c-177">ファイル内のマクロを有効またはOfficeする</span><span class="sxs-lookup"><span data-stu-id="a9b9c-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="a9b9c-178">EOP と Microsoft Defender の 365 セキュリティOffice推奨設定</span><span class="sxs-lookup"><span data-stu-id="a9b9c-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="a9b9c-179">価値あるアップグレード: Windows 10 の次世代セキュリティは、2017 年のランサムウェアの発生に対する回復力を証明します</span><span class="sxs-lookup"><span data-stu-id="a9b9c-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="a9b9c-180">No mas, Samas: What's in this ransomware's modus operandi?</span><span class="sxs-lookup"><span data-stu-id="a9b9c-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="a9b9c-181">ロックされたマルウェアを避けるためのマルウェア</span><span class="sxs-lookup"><span data-stu-id="a9b9c-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="a9b9c-182">MSRT 2016 年 7 月: Cerber ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="a9b9c-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="a9b9c-183">Cerberus に似た Cerber ランサムウェアの 3 人のヘッド</span><span class="sxs-lookup"><span data-stu-id="a9b9c-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="a9b9c-184">(the) Da The 数人のコードの影響を受ける、ストルデシ ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="a9b9c-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
