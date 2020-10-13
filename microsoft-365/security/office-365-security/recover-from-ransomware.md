---
title: ランサムウェア攻撃から回復する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft 365 管理者は、ランサムウェア攻撃から回復する方法について学ぶことができます。
ms.openlocfilehash: c9a8e1035e00509f5c57b8699966544b60b7f9c1
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430611"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="45d80-103">Microsoft 365 のランサムウェア攻撃からの回復</span><span class="sxs-lookup"><span data-stu-id="45d80-103">Recover from a ransomware attack in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="45d80-104">組織を保護するためにすべての予防措置を講じたとしても、 [ランサムウェア](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 攻撃に被害を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="45d80-105">ランサムウェアは大規模なものであり、攻撃は高度なものとなっています。</span><span class="sxs-lookup"><span data-stu-id="45d80-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="45d80-106">このトピックの手順に従って、ランサムウェアによって暗号化されたデータを復元する機会が最善になり、組織内での感染拡大を止めることができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your organization.</span></span> <span data-ttu-id="45d80-107">開始する前に、次の項目を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45d80-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="45d80-108">Ransom からファイルへのアクセスが返される保証はありません。</span><span class="sxs-lookup"><span data-stu-id="45d80-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="45d80-109">実際には、ransom を支払うことで、ランサムウェアをさらに確保することができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="45d80-110">既に有料になっていても、攻撃者の解決策を使用せずにファイルを正常に復元できた場合は、銀行に電話して、トランザクションをブロックできるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45d80-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="45d80-111">また、このトピックの後半で説明するように、ランサムウェア攻撃を司法機関、詐欺報告用 web サイト、および Microsoft に報告することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="45d80-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="45d80-112">攻撃とその影響に迅速に対応することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="45d80-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="45d80-113">待機時間が長くなるほど、影響を受けるデータを回復できる可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="45d80-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="45d80-114">手順 1: バックアップを確認する</span><span class="sxs-lookup"><span data-stu-id="45d80-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="45d80-115">オフラインバックアップを使用している場合は、使用している環境からランサムウェアペイロード (マルウェア) を削除 **した後** で、暗号化されたデータを復元する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45d80-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="45d80-116">バックアップがない場合、またはバックアップがランサムウェアの影響を受けている場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="45d80-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="45d80-117">手順 2: ActiveSync と OneDrive の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="45d80-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="45d80-118">ここで重要な点は、ランサムウェアによるデータ暗号化の拡散を停止することです。</span><span class="sxs-lookup"><span data-stu-id="45d80-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="45d80-119">メールが対象になると考えられる場合は、メールボックスへのユーザーアクセスを一時的に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="45d80-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="45d80-120">Exchange ActiveSync は、モバイルデバイスがデバイスと Exchange Online メールボックスの間でデータを同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="45d80-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="45d80-121">メールボックスの ActiveSync を無効にする方法については、「 [Exchange Online でユーザーの Exchange activesync を無効にする方法](https://support.microsoft.com/help/2795303)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d80-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="45d80-122">メールボックスへの他の種類のアクセスを無効にするには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d80-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="45d80-123">[メールボックスの MAPI を有効または無効](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)にします。</span><span class="sxs-lookup"><span data-stu-id="45d80-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="45d80-124">ユーザーの POP3 または IMAP4 アクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="45d80-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="45d80-125">OneDrive 同期を一時停止すると、潜在的に感染しているデバイスによるクラウドデータの更新を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="45d80-126">詳細については、「 [OneDrive で同期を一時停止および再開する方法](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d80-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="45d80-127">手順 3: 影響を受けたデバイスからマルウェアを削除する</span><span class="sxs-lookup"><span data-stu-id="45d80-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="45d80-128">すべての疑いのあるコンピューターおよびデバイスで最新の更新プログラムを使用して完全なウイルス対策スキャンを実行し、ランサムウェアに関連付けられているペイロードを検出して削除します。</span><span class="sxs-lookup"><span data-stu-id="45d80-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="45d80-129">データを同期しているデバイス、またはマップされたネットワークドライブのターゲット (それらのコンピューターとデバイスもスキャンする必要がある) を忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="45d80-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="45d80-130">[Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)は、 [Windows Defender](https://www.microsoft.com/windows/comprehensive-security)または (古いクライアントの場合) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="45d80-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="45d80-131">また、ランサムウェアまたはマルウェアを削除するための代替手段として、悪意のある [ソフトウェアの削除ツール (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905)もあります。</span><span class="sxs-lookup"><span data-stu-id="45d80-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="45d80-132">これらのオプションが機能しない場合は、[マルウェアの検出と削除に関する問題のトラブルシューティング](https://support.microsoft.com/help/4466982)を[Windows Defender オフライン](https://support.microsoft.com/help/17466)で試みることができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="45d80-133">手順 4: クリーニングされたコンピューターまたはデバイス上のファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="45d80-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="45d80-134">前の手順を完了して、使用している環境からランサムウェアのペイロードを削除します (これにより、ランサムウェアによるファイルの暗号化や削除ができなくなります)。 windows 7 では、windows 8.1 10 の [ファイル履歴](https://support.microsoft.com/help/17128) を使用して、ローカルのファイルとフォルダーの回復を試みることができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="45d80-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="45d80-135">**Notes**:</span></span>

- <span data-ttu-id="45d80-136">また、一部のランサムウェアはバックアップバージョンを暗号化または削除するので、ファイル履歴またはシステム保護を使用してファイルを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="45d80-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="45d80-137">その場合は、次のセクションで説明するように、ランサムウェアまたは OneDrive の影響を受けない外部ドライブまたはデバイスでバックアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45d80-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="45d80-138">フォルダーが OneDrive に同期されていて、最新バージョンの Windows を使用していない場合は、ファイル履歴を使用するといくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="45d80-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="45d80-139">手順 5: OneDrive for Business のファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="45d80-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="45d80-140">OneDrive for business のファイルの復元を使用すると、OneDrive 全体を過去30日以内に過去の時点に復元することができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="45d80-141">詳細については、「 [OneDrive を復元する](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d80-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="45d80-142">手順 6: 削除済みメールを復元する</span><span class="sxs-lookup"><span data-stu-id="45d80-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="45d80-143">ランサムウェアによってすべての電子メールが削除された場合は、削除済みアイテムを回復できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="45d80-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="45d80-144">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d80-144">For more information, see:</span></span>

- [<span data-ttu-id="45d80-145">ユーザーのメールボックス内の削除済みメッセージを復元する</span><span class="sxs-lookup"><span data-stu-id="45d80-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="45d80-146">Windows 版 Outlook で削除済みのアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="45d80-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="45d80-147">手順 7: Exchange ActiveSync と OneDrive の同期を再度有効にする</span><span class="sxs-lookup"><span data-stu-id="45d80-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="45d80-148">コンピューターとデバイスを消去してデータを回復したら、 [手順 2](#step-2-disable-activesync-and-onedrive-sync)で以前に無効にした ActiveSync と OneDrive の同期を再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="45d80-149">手順 8 (オプション): 特定のファイル拡張子に対して OneDrive 同期をブロックする</span><span class="sxs-lookup"><span data-stu-id="45d80-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="45d80-150">回復した後で、OneDrive for Business クライアントがこのランサムウェアの影響を受けたファイルの種類を同期できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="45d80-151">詳細については、「 [get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d80-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="45d80-152">攻撃を報告する</span><span class="sxs-lookup"><span data-stu-id="45d80-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="45d80-153">連絡先の法的執行</span><span class="sxs-lookup"><span data-stu-id="45d80-153">Contact law enforcement</span></span>

<span data-ttu-id="45d80-154">地域または連邦法執行機関に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45d80-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="45d80-155">たとえば、米国内にいる場合は、 [FBI ローカルフィールド office](https://www.fbi.gov/contact-us/field)、 [IC3](http://www.ic3.gov/complaint/default.aspx) 、または [Secret サービス](http://www.secretservice.gov/)に問い合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="45d80-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="45d80-156">国内の詐欺報告 web サイトにレポートを提出する</span><span class="sxs-lookup"><span data-stu-id="45d80-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="45d80-157">詐欺の報告 web サイトは、詐欺を防止および回避する方法についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="45d80-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="45d80-158">また、詐欺の被害を受けた場合に報告するメカニズムも提供します。</span><span class="sxs-lookup"><span data-stu-id="45d80-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="45d80-159">オーストラリア: [Scamwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="45d80-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="45d80-160">カナダ: [カナダの詐欺防止センター](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="45d80-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="45d80-161">フランス: [agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="45d80-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="45d80-162">ドイツ: [Bundesamt Für Sicherheit in Der Informationst k](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="45d80-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="45d80-163">アイルランド: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="45d80-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="45d80-164">ニュージーランド: [消費者詐欺詐欺](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="45d80-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="45d80-165">英国: [アクションの不正行為](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="45d80-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="45d80-166">米国: [ガードオンライン](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="45d80-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="45d80-167">お住まいの国が表示されない場合は、地域または連邦法執行機関にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="45d80-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="45d80-168">Microsoft に電子メールメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="45d80-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="45d80-169">複数の方法のいずれかを使用して、ランサムウェアを含むフィッシングメッセージを報告できます。</span><span class="sxs-lookup"><span data-stu-id="45d80-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="45d80-170">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45d80-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="45d80-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="45d80-171">See also</span></span>

- [<span data-ttu-id="45d80-172">サム</span><span class="sxs-lookup"><span data-stu-id="45d80-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="45d80-173">サムウェア対策応答—支払いを行うかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="45d80-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="45d80-174">Norsk Hydro は、透過可能なランサム攻撃に応答します。</span><span class="sxs-lookup"><span data-stu-id="45d80-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="45d80-175">OneDrive でのファイルのランサムウェア検出と復元</span><span class="sxs-lookup"><span data-stu-id="45d80-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="45d80-176">Microsoft セキュリティインテリジェンスレポート</span><span class="sxs-lookup"><span data-stu-id="45d80-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="45d80-177">Office ファイルのマクロを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="45d80-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="45d80-178">EOP および Office 365 の ATP セキュリティに関する推奨設定</span><span class="sxs-lookup"><span data-stu-id="45d80-178">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="45d80-179">アップグレードに値する場合: Windows 10 の次世代セキュリティは、2017でランサムウェアに対する回復性を証明します。</span><span class="sxs-lookup"><span data-stu-id="45d80-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="45d80-180">Mas なし、Samas このランサムウェアの modus の動作</span><span class="sxs-lookup"><span data-stu-id="45d80-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="45d80-181">Locky マルウェア、幸運による回避</span><span class="sxs-lookup"><span data-stu-id="45d80-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="45d80-182">MSRT 2016 年7月: Cerber ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="45d80-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="45d80-183">Cer(英語) のような、Cerber ランサムウェアの3つのヘッド</span><span class="sxs-lookup"><span data-stu-id="45d80-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="45d80-184">() Da Vinci コードによって影響を受ける Troldesh ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="45d80-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
