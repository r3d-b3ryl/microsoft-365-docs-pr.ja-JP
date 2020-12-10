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
- m365initiative-m365-defender
description: Microsoft 365 管理者は、ランサムウェア攻撃から回復する方法について学ぶことができます。
ms.openlocfilehash: ad3f044e338abeb56046538bdda8df7b8510be0e
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615902"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="e0ef6-103">Microsoft 365 のランサムウェア攻撃からの回復</span><span class="sxs-lookup"><span data-stu-id="e0ef6-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e0ef6-104">組織を保護するためにすべての予防措置を講じたとしても、 [ランサムウェア](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 攻撃に被害を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="e0ef6-105">ランサムウェアは大規模で、攻撃は非常に巧妙になっています。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-105">Ransomware is big business, and the attacks are very sophisticated.</span></span>

<span data-ttu-id="e0ef6-106">この記事の手順では、データを復元し、感染の内部蔓延を停止するための最適な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-106">The steps in this article will give you the best chance to recover data and stop the internal spread of infection.</span></span> <span data-ttu-id="e0ef6-107">開始する前に、次の項目を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="e0ef6-108">Ransom からファイルへのアクセスが返される保証はありません。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="e0ef6-109">実際には、ransom を支払うことで、ランサムウェアをさらに確保することができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-109">In fact, paying the ransom can make you a target for more ransomware.</span></span>

  <span data-ttu-id="e0ef6-110">既に支払いを行っているが、攻撃者の解決策を使用せずに回復した場合は、銀行に連絡して、取引をブロックできるかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-110">If you already paid, but you recovered without using the attacker's solution, contact your bank to see if they can block the transaction.</span></span>

  <span data-ttu-id="e0ef6-111">また、この記事の後半で説明するように、ランサムウェア攻撃を司法機関、詐欺報告用 web サイト、Microsoft に報告することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites, and Microsoft as described later in this article.</span></span>

- <span data-ttu-id="e0ef6-112">攻撃とその影響に迅速に対応することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-112">It's important for you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="e0ef6-113">待機時間が長くなるほど、影響を受けるデータを回復できる可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="e0ef6-114">手順 1: バックアップを確認する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="e0ef6-115">オフラインバックアップを使用している場合は、使用している環境からランサムウェアペイロード (マルウェア) を削除 **した後** で、暗号化されたデータを復元する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="e0ef6-116">バックアップがない場合、またはバックアップがランサムウェアの影響を受けている場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="e0ef6-117">手順 2: Exchange ActiveSync および OneDrive sync を無効にする</span><span class="sxs-lookup"><span data-stu-id="e0ef6-117">Step 2: Disable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="e0ef6-118">ここで重要な点は、ランサムウェアによるデータ暗号化の拡散を停止することです。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="e0ef6-119">ランサムウェアの暗号化の対象として電子メールの疑いがある場合は、メールボックスへのユーザーアクセスを一時的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-119">If you suspect email as a target of the ransomware encryption, temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="e0ef6-120">Exchange ActiveSync は、デバイスと Exchange Online メールボックスの間でデータを同期します。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-120">Exchange ActiveSync synchronizes data between devices and Exchange Online mailboxes.</span></span>

<span data-ttu-id="e0ef6-121">メールボックスの Exchange ActiveSync を無効にする方法については、「exchange [Online でユーザーの Exchange activesync を無効にする方法](https://support.microsoft.com/help/2795303)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-121">To disable Exchange ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="e0ef6-122">メールボックスへの他の種類のアクセスを無効にするには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="e0ef6-123">[メールボックスの MAPI を有効または無効](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)にします。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="e0ef6-124">ユーザーの POP3 または IMAP4 アクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e0ef6-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="e0ef6-125">OneDrive 同期を一時停止すると、潜在的に感染しているデバイスによるクラウドデータの更新を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="e0ef6-126">詳細については、「 [OneDrive で同期を一時停止および再開する方法](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="e0ef6-127">手順 3: 影響を受けたデバイスからマルウェアを削除する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="e0ef6-128">すべての疑いのあるコンピューターおよびデバイスで、完全に最新のウイルス対策スキャンを実行して、ランサムウェアに関連付けられているペイロードを検出して削除します。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-128">Run a full, current antivirus scan on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span>

<span data-ttu-id="e0ef6-129">データを同期しているデバイス、またはマップされたネットワークドライブのターゲットをスキャンすることを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-129">Don't forget to scan devices that are synchronizing data, or the targets of mapped network drives.</span></span>

<span data-ttu-id="e0ef6-130">[Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)は、 [Windows Defender](https://www.microsoft.com/windows/comprehensive-security)または (古いクライアントの場合) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="e0ef6-131">また、ランサムウェアまたはマルウェアを削除するための代替手段として、悪意のある [ソフトウェアの削除ツール (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905)もあります。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="e0ef6-132">これらのオプションが機能しない場合は、[マルウェアの検出と削除に関する問題のトラブルシューティング](https://support.microsoft.com/help/4466982)を[Windows Defender オフライン](https://support.microsoft.com/help/17466)で試みることができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="e0ef6-133">手順 4: クリーニングされたコンピューターまたはデバイス上のファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="e0ef6-134">前の手順を完了して、使用している環境からランサムウェアのペイロードを削除します (これにより、ランサムウェアによるファイルの暗号化や削除ができなくなります)。 windows 7 では、windows 8.1 10 の [ファイル履歴](https://support.microsoft.com/help/17128) を使用して、ローカルのファイルとフォルダーの回復を試みることができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="e0ef6-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="e0ef6-135">**Notes**:</span></span>

- <span data-ttu-id="e0ef6-136">また、一部のランサムウェアはバックアップバージョンを暗号化または削除するので、ファイル履歴またはシステム保護を使用してファイルを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="e0ef6-137">その場合は、次のセクションで説明するように、ランサムウェアまたは OneDrive の影響を受けない外部ドライブまたはデバイスでバックアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="e0ef6-138">フォルダーが OneDrive に同期されていて、最新バージョンの Windows を使用していない場合は、ファイル履歴を使用するといくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="e0ef6-139">手順 5: OneDrive for Business のファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="e0ef6-140">OneDrive for business のファイルの復元を使用すると、OneDrive 全体を過去30日以内に過去の時点に復元することができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="e0ef6-141">詳細については、「 [OneDrive を復元する](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="e0ef6-142">手順 6: 削除済みメールを復元する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="e0ef6-143">ランサムウェアによってすべての電子メールが削除された場合は、削除済みアイテムを回復できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="e0ef6-144">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-144">For more information, see:</span></span>

- [<span data-ttu-id="e0ef6-145">ユーザーのメールボックス内の削除済みメッセージを復元する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="e0ef6-146">Windows 版 Outlook で削除済みのアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="e0ef6-147">手順 7: Exchange ActiveSync と OneDrive の同期を再度有効にする</span><span class="sxs-lookup"><span data-stu-id="e0ef6-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="e0ef6-148">コンピューターとデバイスを消去してデータを回復した後、 [手順 2](#step-2-disable-exchange-activesync-and-onedrive-sync)で以前無効にした Exchange ActiveSync と OneDrive 同期を再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-148">After you've cleaned your computers and devices and recovered your data, you can re-enable Exchange ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-exchange-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="e0ef6-149">手順 8 (オプション): 特定のファイル拡張子に対して OneDrive 同期をブロックする</span><span class="sxs-lookup"><span data-stu-id="e0ef6-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="e0ef6-150">回復した後で、OneDrive for Business クライアントがこのランサムウェアの影響を受けたファイルの種類を同期できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="e0ef6-151">詳細については、「 [get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="e0ef6-152">攻撃を報告する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="e0ef6-153">連絡先の法的執行</span><span class="sxs-lookup"><span data-stu-id="e0ef6-153">Contact law enforcement</span></span>

<span data-ttu-id="e0ef6-154">地域または連邦法執行機関に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="e0ef6-155">たとえば、米国内にいる場合は、 [FBI ローカルフィールド office](https://www.fbi.gov/contact-us/field)、 [IC3](http://www.ic3.gov/complaint/default.aspx) 、または [Secret サービス](http://www.secretservice.gov/)に問い合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="e0ef6-156">国内の詐欺報告 web サイトにレポートを提出する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="e0ef6-157">詐欺の報告 web サイトは、詐欺を防止および回避する方法についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="e0ef6-158">また、詐欺の被害を受けた場合に報告するメカニズムも提供します。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="e0ef6-159">オーストラリア: [Scamwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="e0ef6-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="e0ef6-160">カナダ: [カナダの詐欺防止センター](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="e0ef6-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="e0ef6-161">フランス: [agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="e0ef6-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="e0ef6-162">ドイツ: [Bundesamt Für Sicherheit in Der Informationst k](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="e0ef6-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="e0ef6-163">アイルランド: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="e0ef6-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="e0ef6-164">ニュージーランド: [消費者詐欺詐欺](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="e0ef6-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="e0ef6-165">英国: [アクションの不正行為](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="e0ef6-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="e0ef6-166">米国: [ガードオンライン](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="e0ef6-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="e0ef6-167">お住まいの国が表示されない場合は、地域または連邦法執行機関にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="e0ef6-168">Microsoft に電子メールメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="e0ef6-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="e0ef6-169">ランサムウェアを含むフィッシングメッセージは、いくつかの方法のいずれかを使用して報告できます。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-169">You can report phishing messages that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="e0ef6-170">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0ef6-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0ef6-171">See also</span></span>

- [<span data-ttu-id="e0ef6-172">サム</span><span class="sxs-lookup"><span data-stu-id="e0ef6-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="e0ef6-173">サムウェア対策応答—支払いを行うかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="e0ef6-174">Norsk Hydro は、透過可能なランサム攻撃に応答します。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="e0ef6-175">OneDrive でのファイルのランサムウェア検出と復元</span><span class="sxs-lookup"><span data-stu-id="e0ef6-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="e0ef6-176">Microsoft セキュリティインテリジェンスレポート</span><span class="sxs-lookup"><span data-stu-id="e0ef6-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="e0ef6-177">Office ファイルのマクロを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e0ef6-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="e0ef6-178">EOP および Microsoft Defender for Office 365 のセキュリティに関する推奨設定</span><span class="sxs-lookup"><span data-stu-id="e0ef6-178">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)

- [<span data-ttu-id="e0ef6-179">アップグレードに値する場合: Windows 10 の次世代セキュリティは、2017でランサムウェアに対する回復性を証明します。</span><span class="sxs-lookup"><span data-stu-id="e0ef6-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="e0ef6-180">Mas なし、Samas このランサムウェアの modus の動作</span><span class="sxs-lookup"><span data-stu-id="e0ef6-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="e0ef6-181">Locky マルウェア、幸運による回避</span><span class="sxs-lookup"><span data-stu-id="e0ef6-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="e0ef6-182">MSRT 2016 年7月: Cerber ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="e0ef6-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="e0ef6-183">Cer(英語) のような、Cerber ランサムウェアの3つのヘッド</span><span class="sxs-lookup"><span data-stu-id="e0ef6-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="e0ef6-184">() Da Vinci コードによって影響を受ける Troldesh ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="e0ef6-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
