---
title: ランサムウェア攻撃からの回復
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Office 365 管理者は、ランサムウェア攻撃から回復する方法について説明します。
ms.openlocfilehash: 04cfd2f2417b0c2e084a88f9ee156521339b18c4
ms.sourcegitcommit: e47694dedf7e213167d3d979a44c07c668bba543
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41932375"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a><span data-ttu-id="579b4-103">Office 365 でランサムウェア攻撃から回復する</span><span class="sxs-lookup"><span data-stu-id="579b4-103">Recover from a ransomware attack in Office 365</span></span>

<span data-ttu-id="579b4-104">Office 365 組織を保護するためにすべての予防措置を講じたとしても、[ランサムウェア](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)攻撃に被害を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-104">Even if you take every precaution to protect your Office 365 organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="579b4-105">ランサムウェアは大規模なものであり、攻撃は高度なものとなっています。</span><span class="sxs-lookup"><span data-stu-id="579b4-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="579b4-106">このトピックの手順に従って、ランサムウェアによって暗号化されたデータを復元する機会が最善になり、Office 365 組織における感染の拡大を止めることができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your Office 365 organization.</span></span> <span data-ttu-id="579b4-107">開始する前に、次の項目を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="579b4-108">Ransom からファイルへのアクセスが返される保証はありません。</span><span class="sxs-lookup"><span data-stu-id="579b4-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="579b4-109">実際には、ransom を支払うことで、ランサムウェアをさらに確保することができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="579b4-110">既に有料になっていても、攻撃者の解決策を使用せずにファイルを正常に復元できた場合は、銀行に電話して、トランザクションをブロックできるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="579b4-111">また、このトピックの後半で説明するように、ランサムウェア攻撃を司法機関、詐欺報告用 web サイト、および Microsoft に報告することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="579b4-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="579b4-112">攻撃とその影響に迅速に対応することが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="579b4-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="579b4-113">待機時間が長くなるほど、影響を受けるデータを回復できる可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="579b4-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="579b4-114">手順 1: バックアップを確認する</span><span class="sxs-lookup"><span data-stu-id="579b4-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="579b4-115">オフラインバックアップを使用している場合は、使用している環境からランサムウェアペイロード (マルウェア) を削除**した後**で、暗号化されたデータを復元する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="579b4-116">バックアップがない場合、またはバックアップがランサムウェアの影響を受けている場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="579b4-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="579b4-117">手順 2: ActiveSync と OneDrive の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="579b4-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="579b4-118">ここで重要な点は、ランサムウェアによるデータ暗号化の拡散を停止することです。</span><span class="sxs-lookup"><span data-stu-id="579b4-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="579b4-119">メールが対象になると考えられる場合は、メールボックスへのユーザーアクセスを一時的に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="579b4-120">Exchange ActiveSync は、モバイルデバイスがデバイスと Exchange Online メールボックスの間でデータを同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="579b4-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="579b4-121">メールボックスの ActiveSync を無効にするには、「 [How to Disable Exchange activesync In Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="579b4-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Office 365](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).</span></span>

<span data-ttu-id="579b4-122">メールボックスへの他の種類のアクセスを無効にするには、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="579b4-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="579b4-123">[メールボックスの MAPI を有効または無効](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)にします。</span><span class="sxs-lookup"><span data-stu-id="579b4-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="579b4-124">ユーザーの POP3 または IMAP4 アクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="579b4-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="579b4-125">OneDrive 同期を一時停止すると、潜在的に感染しているデバイスによるクラウドデータの更新を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="579b4-126">詳細については、「 [OneDrive で同期を一時停止および再開する方法](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="579b4-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="579b4-127">手順 3: 影響を受けたデバイスからマルウェアを削除する</span><span class="sxs-lookup"><span data-stu-id="579b4-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="579b4-128">すべての疑いのあるコンピューターおよびデバイスで最新の更新プログラムを使用して完全なウイルス対策スキャンを実行し、ランサムウェアに関連付けられているペイロードを検出して削除します。</span><span class="sxs-lookup"><span data-stu-id="579b4-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="579b4-129">データを同期しているデバイス、またはマップされたネットワークドライブのターゲット (それらのコンピューターとデバイスもスキャンする必要がある) を忘れないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="579b4-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="579b4-130">[Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)は、 [Windows Defender](https://www.microsoft.com/windows/comprehensive-security)または (古いクライアントの場合) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="579b4-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="579b4-131">また、ランサムウェアまたはマルウェアを削除するための代替手段として、悪意のある[ソフトウェアの削除ツール (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905)もあります。</span><span class="sxs-lookup"><span data-stu-id="579b4-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="579b4-132">これらのオプションが機能しない場合は、[マルウェアの検出と削除に関する問題のトラブルシューティング](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)を[Windows Defender オフライン](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc)で試みることができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="579b4-133">手順 4: クリーニングされたコンピューターまたはデバイス上のファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="579b4-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="579b4-134">前の手順を完了して、使用している環境からランサムウェアのペイロードを削除します (これにより、ランサムウェアによるファイルの暗号化や削除ができなくなります)。 windows 7 では、windows 8.1 10 の[ファイル履歴](https://support.microsoft.com/help/17128/windows-8-file-history)を使用して、ローカルのファイルとフォルダーの回復を試みることができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128/windows-8-file-history) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="579b4-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="579b4-135">**Notes**:</span></span>

- <span data-ttu-id="579b4-136">また、一部のランサムウェアはバックアップバージョンを暗号化または削除するので、ファイル履歴またはシステム保護を使用してファイルを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="579b4-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="579b4-137">その場合は、次のセクションで説明するように、ランサムウェアまたは OneDrive の影響を受けない外部ドライブまたはデバイスでバックアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="579b4-138">フォルダーが OneDrive に同期されていて、最新バージョンの Windows を使用していない場合は、ファイル履歴を使用するといくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="579b4-139">手順 5: OneDrive for Business のファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="579b4-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="579b4-140">OneDrive for Business では、保存したファイルを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-140">OneDrive for Business will allow you to recover any files you have stored in it.</span></span> <span data-ttu-id="579b4-141">次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-141">You have two options:</span></span>

- <span data-ttu-id="579b4-142">[OneDrive web サイト](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893)を使用します。</span><span class="sxs-lookup"><span data-stu-id="579b4-142">Use the [OneDrive website](https://support.office.com/article/159cad6d-d76e-4981-88ef-de6e96c93893).</span></span>

- <span data-ttu-id="579b4-143">多数のファイルが影響を受けた場合は、"サイトコレクションの復元" のサポート要求を作成できます。</span><span class="sxs-lookup"><span data-stu-id="579b4-143">If a large number of files were affected, you can create a support request for a "Site Collection Restore".</span></span> <span data-ttu-id="579b4-144">この要求では、過去14日以内にファイルを復元できます。</span><span class="sxs-lookup"><span data-stu-id="579b4-144">This request can restore files from up to 14 days in the past.</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="579b4-145">手順 6: 削除済みメールを復元する</span><span class="sxs-lookup"><span data-stu-id="579b4-145">Step 6: Recover deleted email</span></span>

<span data-ttu-id="579b4-146">ランサムウェアによってすべての電子メールが削除された場合は、削除済みアイテムを回復できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-146">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="579b4-147">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="579b4-147">For more information, see:</span></span>

- [<span data-ttu-id="579b4-148">ユーザーのメールボックス内の削除済みメッセージを復元する</span><span class="sxs-lookup"><span data-stu-id="579b4-148">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="579b4-149">Windows 版 Outlook で削除済みのアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="579b4-149">Recover deleted items in Outlook for Windows</span></span>](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="579b4-150">手順 7: Exchange ActiveSync と OneDrive の同期を再度有効にする</span><span class="sxs-lookup"><span data-stu-id="579b4-150">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="579b4-151">コンピューターとデバイスを消去してデータを回復したら、[手順 2](#step-2-disable-activesync-and-onedrive-sync)で以前に無効にした ActiveSync と OneDrive の同期を再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-151">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="579b4-152">手順 8 (オプション): 特定のファイル拡張子に対して OneDrive 同期をブロックする</span><span class="sxs-lookup"><span data-stu-id="579b4-152">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="579b4-153">回復した後で、OneDrive for Business クライアントがこのランサムウェアの影響を受けたファイルの種類を同期できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-153">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="579b4-154">詳細については、「 [get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="579b4-154">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="579b4-155">攻撃を報告する</span><span class="sxs-lookup"><span data-stu-id="579b4-155">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="579b4-156">連絡先の法的執行</span><span class="sxs-lookup"><span data-stu-id="579b4-156">Contact law enforcement</span></span>

<span data-ttu-id="579b4-157">地域または連邦法執行機関に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="579b4-157">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="579b4-158">たとえば、米国内にいる場合は、 [FBI ローカルフィールド office](https://www.fbi.gov/contact-us/field)、 [IC3](http://www.ic3.gov/complaint/default.aspx) 、または[Secret サービス](http://www.secretservice.gov/)に問い合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="579b4-158">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="579b4-159">国内の詐欺報告 web サイトにレポートを提出する</span><span class="sxs-lookup"><span data-stu-id="579b4-159">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="579b4-160">詐欺の報告 web サイトは、詐欺を防止および回避する方法についての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="579b4-160">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="579b4-161">また、詐欺の被害を受けた場合に報告するメカニズムも提供します。</span><span class="sxs-lookup"><span data-stu-id="579b4-161">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="579b4-162">オーストラリア: [Scamwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="579b4-162">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="579b4-163">カナダ:[カナダの詐欺防止センター](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="579b4-163">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="579b4-164">フランス: [agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="579b4-164">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="579b4-165">ドイツ: [Bundesamt Für Sicherheit in Der Informationst k](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="579b4-165">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="579b4-166">アイルランド: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="579b4-166">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="579b4-167">ニュージーランド:[消費者詐欺詐欺](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="579b4-167">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="579b4-168">英国:[アクションの不正行為](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="579b4-168">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="579b4-169">米国:[ガードオンライン](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="579b4-169">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="579b4-170">お住まいの国が表示されない場合は、地域または連邦法執行機関にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="579b4-170">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="579b4-171">Microsoft に電子メールメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="579b4-171">Submit email messages to Microsoft</span></span>

<span data-ttu-id="579b4-172">ランサムウェアを含むフィッシングメッセージを報告するには、 [「スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="579b4-172">You can report phishing message that contain ransomware by following the instructions in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](https://docs.microsoft.com/microsoft-365/security/office-365-security/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis).</span></span>

## <a name="see-also"></a><span data-ttu-id="579b4-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="579b4-173">See also</span></span>

- [<span data-ttu-id="579b4-174">サム</span><span class="sxs-lookup"><span data-stu-id="579b4-174">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="579b4-175">サムウェア対策応答—支払いを行うかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="579b4-175">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="579b4-176">Norsk Hydro は、透過可能なランサム攻撃に応答します。</span><span class="sxs-lookup"><span data-stu-id="579b4-176">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="579b4-177">OneDrive でのファイルのランサムウェア検出と復元</span><span class="sxs-lookup"><span data-stu-id="579b4-177">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="579b4-178">Microsoft セキュリティインテリジェンスレポート</span><span class="sxs-lookup"><span data-stu-id="579b4-178">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="579b4-179">Office ファイルのマクロを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="579b4-179">Enable or disable macros in Office files</span></span>](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="579b4-180">EOP および Office 365 の ATP セキュリティに関する推奨設定</span><span class="sxs-lookup"><span data-stu-id="579b4-180">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="579b4-181">アップグレードに値する場合: Windows 10 の次世代セキュリティは、2017でランサムウェアに対する回復性を証明します。</span><span class="sxs-lookup"><span data-stu-id="579b4-181">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="579b4-182">Mas なし、Samas このランサムウェアの modus の動作</span><span class="sxs-lookup"><span data-stu-id="579b4-182">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="579b4-183">Locky マルウェア、幸運による回避</span><span class="sxs-lookup"><span data-stu-id="579b4-183">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="579b4-184">MSRT 2016 年7月: Cerber ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="579b4-184">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="579b4-185">Cer(英語) のような、Cerber ランサムウェアの3つのヘッド</span><span class="sxs-lookup"><span data-stu-id="579b4-185">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="579b4-186">() Da Vinci コードによって影響を受ける Troldesh ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="579b4-186">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
