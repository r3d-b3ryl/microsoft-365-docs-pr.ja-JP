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
description: Microsoft 365 管理者はランスムウェア攻撃から回復する方法を学習できます。
ms.openlocfilehash: 2f8e5f5deb18cadfaea7acc1cffe73abbc43010b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827835"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a><span data-ttu-id="39136-103">Microsoft 365 でランスムウェア攻撃から回復する</span><span class="sxs-lookup"><span data-stu-id="39136-103">Recover from a ransomware attack in Microsoft 365</span></span>

<span data-ttu-id="39136-104">組織を保護するためにあらかじめすべての予防を受けたとしても、ランサムウェア攻撃の [きめはきまっても問題](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) はありません。</span><span class="sxs-lookup"><span data-stu-id="39136-104">Even if you take every precaution to protect your organization, you can still fall victim to a [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) attack.</span></span> <span data-ttu-id="39136-105">ランスパムウェアは大きなビジネスで、攻撃はさらに機会的であると確認されています。</span><span class="sxs-lookup"><span data-stu-id="39136-105">Ransomware is big business, and the attacks are verify sophisticated.</span></span>

<span data-ttu-id="39136-106">このトピックの手順を実行すると、ランムウェアによって暗号化されたデータを回復するおかつ最善の方法と、組織に感染の感染の範囲を停止することができます。</span><span class="sxs-lookup"><span data-stu-id="39136-106">The steps in this topic will give you the best chance to recover data that was encrypted by the ransomware, and will help stop the spread of the infection in your organization.</span></span> <span data-ttu-id="39136-107">開始する前に、次の項目を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39136-107">Before you get started, consider the following items:</span></span>

- <span data-ttu-id="39136-108">ランサムを支払ってもファイルへのアクセスが返されるわけでは、そのことを確認するものはありません。</span><span class="sxs-lookup"><span data-stu-id="39136-108">There's no guarantee that paying the ransom will return access to your files.</span></span> <span data-ttu-id="39136-109">一般に、代金を支払うなら、よりランムウェアのターゲットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="39136-109">In fact, paying the ransom can make you a target for more ransomware.</span></span> <span data-ttu-id="39136-110">既に済みの場合は、攻撃者の解決策を使用することなくファイルを正常に回復すでに済ませた場合、銀行を呼び出して取引が取引をブロックできるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39136-110">If you've already paid, but you were able to successfully recover your files without having to use the attacker's resolution, you should call your bank to see if they can block the transaction.</span></span> <span data-ttu-id="39136-111">また、このトピックで後述するように、ランダムウェア攻撃を法執行機関、スカム レポート Web サイト、Microsoft に報告していくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39136-111">We also recommend that you report the ransomware attack to law enforcement, scam reporting websites and Microsoft as described later in this topic.</span></span>

- <span data-ttu-id="39136-112">攻撃とその問題に対して迅速に対応するのが非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="39136-112">It's very important that you respond quickly to the attack and its consequences.</span></span> <span data-ttu-id="39136-113">待つ時間が長い時間は長いので、影響を受けるデータを回復できます。</span><span class="sxs-lookup"><span data-stu-id="39136-113">The longer you wait, the less likely it is that you can recover the affected data.</span></span>

## <a name="step-1-verify-your-backups"></a><span data-ttu-id="39136-114">手順 1: バックアップの確認</span><span class="sxs-lookup"><span data-stu-id="39136-114">Step 1: Verify your backups</span></span>

<span data-ttu-id="39136-115">バックアップをオフラインにしている場合は、おそらくランスタント**after**ペイロード (マルウェア) を環境から削除した後で、暗号化されたデータを復元できます。</span><span class="sxs-lookup"><span data-stu-id="39136-115">If you have offline backups, you can probably restore the encrypted data **after** you've removed the ransomware payload (malware) from your environment.</span></span>

<span data-ttu-id="39136-116">バックアップがない場合、またはバックアップがランムウェアにも影響を受け出した場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="39136-116">If you don't have backups, or if your backups were also affected by the ransomware, you can skip this step.</span></span>

## <a name="step-2-disable-activesync-and-onedrive-sync"></a><span data-ttu-id="39136-117">手順 2: ActiveSync と OneDrive の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="39136-117">Step 2: Disable ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="39136-118">ここで重要なのは、ランダムウェアによるデータ暗号化の詳細を停止する主要なポイントです。</span><span class="sxs-lookup"><span data-stu-id="39136-118">The key point here is to stop the spread of data encryption by the ransomware.</span></span>

<span data-ttu-id="39136-119">電子メールが対象であると不確かな場合には、メールボックスへのユーザー アクセスを一時的に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39136-119">If you suspect that email is a target, you should temporarily disable user access to mailboxes.</span></span> <span data-ttu-id="39136-120">Exchange ActiveSyncはモバイル デバイスによって、デバイスと Exchange Online メールボックス間でデータを同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="39136-120">Exchange ActiveSync is used by mobile devices to synchronize data between the device and the Exchange Online mailbox.</span></span>

<span data-ttu-id="39136-121">メールボックスの ActiveSync を無効にするには [、「Exchange Online でユーザーの Exchange ActiveSync を無効にする方法」を参照してください](https://support.microsoft.com/help/2795303)。</span><span class="sxs-lookup"><span data-stu-id="39136-121">To disable ActiveSync for a mailbox, see [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).</span></span>

<span data-ttu-id="39136-122">メールボックスへの他の種類のアクセスを無効にするには、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39136-122">To disable other types of access to a mailbox, see:</span></span>

- <span data-ttu-id="39136-123">[メールボックスの MAPI を有効または無効にします](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)。</span><span class="sxs-lookup"><span data-stu-id="39136-123">[Enable or disable MAPI for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).</span></span>

- [<span data-ttu-id="39136-124">ユーザーの POP3 または IMAP4 アクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="39136-124">Enable or Disable POP3 or IMAP4 access for a user</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

<span data-ttu-id="39136-125">OneDrive 同期を一時停止すると、潜在的に感染しているデバイスによるクラウド データの更新を行いないようにします。</span><span class="sxs-lookup"><span data-stu-id="39136-125">Pausing OneDrive sync will help protect your cloud data from being updated by potentially infected devices.</span></span> <span data-ttu-id="39136-126">詳細については [、OneDrive で同期を一時停止および再開する方法を参照してください](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)。</span><span class="sxs-lookup"><span data-stu-id="39136-126">For more information, see [How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).</span></span>

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a><span data-ttu-id="39136-127">手順 3: 影響を受けるデバイスからマルウェアを削除する</span><span class="sxs-lookup"><span data-stu-id="39136-127">Step 3: Remove the malware from the affected devices</span></span>

<span data-ttu-id="39136-128">検出されたすべてのコンピューターやデバイスで最新の更新プログラムを使ってフル ウイルス対策スキャンを実行し、ランサムウェアに関連付けられているペイロードを検出および削除します。</span><span class="sxs-lookup"><span data-stu-id="39136-128">Run a full antivirus scan with the latest updates on all suspected computers and devices to detect and remove the payload that's associated with the ransomware.</span></span> <span data-ttu-id="39136-129">データの同期中のデバイスやマップされたネットワーク ドライブのターゲット (これらのコンピューターやデバイスもスキャンする必要があるコンピューターやデバイスも使用する必要がある) を使いません。</span><span class="sxs-lookup"><span data-stu-id="39136-129">Don't forget devices that are synchronizing data, or the target of mapped network drives (those computers and devices need to be scanned, too).</span></span>

<span data-ttu-id="39136-130">以前のクライアント [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) 使用することもできます。(以前のクライアントの場合) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)。</span><span class="sxs-lookup"><span data-stu-id="39136-130">You can use [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) or (for older clients) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).</span></span>

<span data-ttu-id="39136-131">悪意のあるソフトウェアの削除ツール [(MSRT)](https://www.microsoft.com/download/details.aspx?id=9905)も同様の方法です。</span><span class="sxs-lookup"><span data-stu-id="39136-131">An alternative that will also help you remove ransomware or malware is the [Malicious Software Removal Tool (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).</span></span>

<span data-ttu-id="39136-132">これらのオプションが機能しない場合は、オフラインでの [Windows Defender、マルウェアの検出](https://support.microsoft.com/help/17466) と削除 [に関する問題を解決してください](https://support.microsoft.com/help/4466982)。</span><span class="sxs-lookup"><span data-stu-id="39136-132">If these options don't work, you can try [Windows Defender Offline](https://support.microsoft.com/help/17466) or [Troubleshoot problems with detecting and removing malware](https://support.microsoft.com/help/4466982).</span></span>

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a><span data-ttu-id="39136-133">手順 4: クリーンなコンピューターまたはデバイス上でファイルを回復する</span><span class="sxs-lookup"><span data-stu-id="39136-133">Step 4: Recover files on a cleaned computer or device</span></span>

<span data-ttu-id="39136-134">前の手順を完了してランダムウェア ペイロードを環境から削除すると (ランムウェアによるファイルの暗号化や削除を実行できません)、Windows 10 および Windows [File History](https://support.microsoft.com/help/17128) 7 の Windows 8.1 またはシステム保護を使用して、ローカル ファイルとフォルダーの回復を試行できます。</span><span class="sxs-lookup"><span data-stu-id="39136-134">After you've completed the previous step to remove the ransomware payload from your environment (which will prevent the ransomware from encrypting or removing your files), you can use [File History](https://support.microsoft.com/help/17128) in Windows 10 and Windows 8.1 or System Protection in Windows 7 to attempt to recover your local files and folders.</span></span>

<span data-ttu-id="39136-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="39136-135">**Notes**:</span></span>

- <span data-ttu-id="39136-136">一部のランムウェアはバックアップ バージョンを暗号化または削除するので、ファイル履歴またはシステム保護を使用してファイルを復元することはできません。</span><span class="sxs-lookup"><span data-stu-id="39136-136">Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files.</span></span> <span data-ttu-id="39136-137">その場合は、次のセクションで説明されているのように、外部ドライブや、ランムウェアや OneDrive の影響を受けずに影響を受けたデバイスでバックアップを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39136-137">If that happens, you need use backups on external drives or devices that were not affected by the ransomware or OneDrive as described in the next section.</span></span>

- <span data-ttu-id="39136-138">フォルダーが OneDrive と同期される際に、その Windows の最新バージョンを使っていない場合は、[ファイル履歴] を使用するいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="39136-138">If a folder is synchronized to OneDrive and you aren't using the latest version of Windows, there might be some limitations using File History.</span></span>

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a><span data-ttu-id="39136-139">手順 5: OneDrive for Business でファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="39136-139">Step 5: Recover your files in your OneDrive for Business</span></span>

<span data-ttu-id="39136-140">OneDrive for Business でのファイルの復元を使用すると、過去 30 日以内の以前の時刻に OneDrive 全体を復元することができます。</span><span class="sxs-lookup"><span data-stu-id="39136-140">Files Restore in OneDrive for Business allows you to restore your entire OneDrive to a previous point in time within the last 30 days.</span></span> <span data-ttu-id="39136-141">詳細については [、「OneDrive を復元する」を参照してください](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)。</span><span class="sxs-lookup"><span data-stu-id="39136-141">For more information, see [Restore your OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).</span></span>

## <a name="step-6-recover-deleted-email"></a><span data-ttu-id="39136-142">手順 6:削除されたメールを復元する</span><span class="sxs-lookup"><span data-stu-id="39136-142">Step 6: Recover deleted email</span></span>

<span data-ttu-id="39136-143">ランムウェアがすべてのメールを削除するというごく一般的なケースでは、削除済みアイテムを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="39136-143">In the rare case that the ransomware deleted all your email, you can probably recover the deleted items.</span></span> <span data-ttu-id="39136-144">詳しくは、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39136-144">For more information, see:</span></span>

- [<span data-ttu-id="39136-145">ユーザーのメールボックス内の削除済みメッセージを復元する</span><span class="sxs-lookup"><span data-stu-id="39136-145">Recover deleted messages in a user's mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [<span data-ttu-id="39136-146">Windows 版 Outlook で削除済みのアイテムを復元する</span><span class="sxs-lookup"><span data-stu-id="39136-146">Recover deleted items in Outlook for Windows</span></span>](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a><span data-ttu-id="39136-147">手順 7: クライアントと OneDrive Exchange ActiveSync再有効化する</span><span class="sxs-lookup"><span data-stu-id="39136-147">Step 7: Re-enable Exchange ActiveSync and OneDrive sync</span></span>

<span data-ttu-id="39136-148">コンピューターとデバイスをクリーンアップし、データを回復した後、手順 2 で無効にした ActiveSync と OneDrive 同期を再 [有効にすることができます](#step-2-disable-activesync-and-onedrive-sync)。</span><span class="sxs-lookup"><span data-stu-id="39136-148">After you've cleaned your computers and devices and recovered your data, you can re-enable ActiveSync and OneDrive sync that you previously disabled in [Step 2](#step-2-disable-activesync-and-onedrive-sync).</span></span>

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a><span data-ttu-id="39136-149">手順 8 (省略可能):特定のファイル拡張子に対して OneDrive の同期をブロックする</span><span class="sxs-lookup"><span data-stu-id="39136-149">Step 8 (Optional): Block OneDrive sync for specific file extensions</span></span>

<span data-ttu-id="39136-150">回復した後、OneDrive for Business クライアントがこのランスムウェアの影響を受けるファイルの種類を同期できなようになります。</span><span class="sxs-lookup"><span data-stu-id="39136-150">After you've recovered, you can prevent OneDrive for Business clients from synchronizing the file types that were affected by this ransomware.</span></span> <span data-ttu-id="39136-151">詳細については [、「Set-SPOTenantSyncClientRestriction」を参照してください。](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span><span class="sxs-lookup"><span data-stu-id="39136-151">For more information, see [Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)</span></span>

## <a name="report-the-attack"></a><span data-ttu-id="39136-152">攻撃を報告する</span><span class="sxs-lookup"><span data-stu-id="39136-152">Report the attack</span></span>

### <a name="contact-law-enforcement"></a><span data-ttu-id="39136-153">連絡先の法的執行</span><span class="sxs-lookup"><span data-stu-id="39136-153">Contact law enforcement</span></span>

<span data-ttu-id="39136-154">地名または連携的な法執行年に問い合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="39136-154">You should contact your local or federal law enforcement agencies.</span></span> <span data-ttu-id="39136-155">たとえば、米国にいっている場合は [、FBI](https://www.fbi.gov/contact-us/field)のローカル フィールド オフィス [、IC3](http://www.ic3.gov/complaint/default.aspx) または Secret Service に問い合 [わせてください](http://www.secretservice.gov/)。</span><span class="sxs-lookup"><span data-stu-id="39136-155">For example, if you are in the United States you can contact the [FBI local field office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) or [Secret Service](http://www.secretservice.gov/).</span></span>

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a><span data-ttu-id="39136-156">国の Scam レポート Web サイトにレポートを提出する</span><span class="sxs-lookup"><span data-stu-id="39136-156">Submit a report to your country's scam reporting website</span></span>

<span data-ttu-id="39136-157">Scam のレポート Web サイトでは、不カムの防止方法と回避方法に関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="39136-157">Scam reporting websites provide information about how to prevent and avoid scams.</span></span> <span data-ttu-id="39136-158">また、scam からレポートを送信するメカニズムも提供します。</span><span class="sxs-lookup"><span data-stu-id="39136-158">They also provide mechanisms to report if you were victim of scam.</span></span>

- <span data-ttu-id="39136-159">ストーストラリア: [SCAMwatch](http://www.scamwatch.gov.au/)</span><span class="sxs-lookup"><span data-stu-id="39136-159">Australia: [SCAMwatch](http://www.scamwatch.gov.au/)</span></span>

- <span data-ttu-id="39136-160">カナダ: [カナダのオブレーダのオブレーダル](http://www.antifraudcentre-centreantifraude.ca/)</span><span class="sxs-lookup"><span data-stu-id="39136-160">Canada: [Canadian Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)</span></span>

- <span data-ttu-id="39136-161">フランス: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span><span class="sxs-lookup"><span data-stu-id="39136-161">France: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)</span></span>

- <span data-ttu-id="39136-162">ドイツ: [Bundesamt fír Sicherheit インフォットワード (Itstechnik)](https://www.bsi.bund.de/DE/Home/home_node.html)</span><span class="sxs-lookup"><span data-stu-id="39136-162">Germany: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)</span></span>

- <span data-ttu-id="39136-163">アイルランド: [Garda Síochána](http://www.garda.ie/)</span><span class="sxs-lookup"><span data-stu-id="39136-163">Ireland: [An Garda Síochána](http://www.garda.ie/)</span></span>

- <span data-ttu-id="39136-164">ニュージーランド: [カスタマー アフレース スキャミム](http://www.consumeraffairs.govt.nz/scams)</span><span class="sxs-lookup"><span data-stu-id="39136-164">New Zealand: [Consumer Affairs Scams](http://www.consumeraffairs.govt.nz/scams)</span></span>

- <span data-ttu-id="39136-165">英国: [アクション不行](http://www.actionfraud.police.uk/)</span><span class="sxs-lookup"><span data-stu-id="39136-165">United Kingdom: [Action Fraud](http://www.actionfraud.police.uk/)</span></span>

- <span data-ttu-id="39136-166">米国: On [Guard Online](http://www.onguardonline.gov/)</span><span class="sxs-lookup"><span data-stu-id="39136-166">United States: [On Guard Online](http://www.onguardonline.gov/)</span></span>

<span data-ttu-id="39136-167">お国が一覧にない場合は、地当しているまたは法的執行年法の執行を確認します。</span><span class="sxs-lookup"><span data-stu-id="39136-167">If your country isn't listed, ask your local or federal law enforcement agencies.</span></span>

### <a name="submit-email-messages-to-microsoft"></a><span data-ttu-id="39136-168">Microsoft にメール メッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="39136-168">Submit email messages to Microsoft</span></span>

<span data-ttu-id="39136-169">ランスパンシャウェアを含むフィッシング メッセージを報告するには、いくつかの方法のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="39136-169">You can report phishing message that contain ransomware by using one of several methods.</span></span> <span data-ttu-id="39136-170">詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39136-170">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="39136-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="39136-171">See also</span></span>

- [<span data-ttu-id="39136-172">ランスムウェア</span><span class="sxs-lookup"><span data-stu-id="39136-172">Ransomware</span></span>](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [<span data-ttu-id="39136-173">ランムウェアの応答 (支払いまたは支払いを受けないか)</span><span class="sxs-lookup"><span data-stu-id="39136-173">Ransomware response—to pay or not to pay?</span></span>](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [<span data-ttu-id="39136-174">Norsk Hydro は、透明性を持つランスムウェア攻撃に対応する</span><span class="sxs-lookup"><span data-stu-id="39136-174">Norsk Hydro responds to ransomware attack with transparency</span></span>](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [<span data-ttu-id="39136-175">ランスムウェアの検出と OneDrive でのファイルの回復</span><span class="sxs-lookup"><span data-stu-id="39136-175">Ransomware detection and recovering your files in OneDrive</span></span>](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [<span data-ttu-id="39136-176">Microsoft Security Intelligence Report</span><span class="sxs-lookup"><span data-stu-id="39136-176">Microsoft Security Intelligence Report</span></span>](https://www.microsoft.com/securityinsights/)

- [<span data-ttu-id="39136-177">ファイルのマクロを有効または Office無効にする</span><span class="sxs-lookup"><span data-stu-id="39136-177">Enable or disable macros in Office files</span></span>](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [<span data-ttu-id="39136-178">EOP およびドメイン 365 ATP セキュリティに関Office推奨設定</span><span class="sxs-lookup"><span data-stu-id="39136-178">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [<span data-ttu-id="39136-179">ワード ワイズ アップグレード: Windows 10 の次世代のセキュリティは、2017 年のランサムウェアの発生に対する解決策が提供されます。</span><span class="sxs-lookup"><span data-stu-id="39136-179">A worthy upgrade: Next-gen security on Windows 10 proves resilient against ransomware outbreaks in 2017</span></span>](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [<span data-ttu-id="39136-180">不合格: このランサムウェアのモニュラはどういうですか?</span><span class="sxs-lookup"><span data-stu-id="39136-180">No mas, Samas: What's in this ransomware's modus operandi?</span></span>](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [<span data-ttu-id="39136-181">ロックしてマルウェアを回避する</span><span class="sxs-lookup"><span data-stu-id="39136-181">Locky malware, lucky to avoid it</span></span>](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [<span data-ttu-id="39136-182">MSRT 2016 年 7 月: カーベル ランサムウェア</span><span class="sxs-lookup"><span data-stu-id="39136-182">MSRT July 2016: Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [<span data-ttu-id="39136-183">Cerberus のような Cerber ランのランソムウェアの 3 本。</span><span class="sxs-lookup"><span data-stu-id="39136-183">The three heads of the Cerberus-like Cerber ransomware</span></span>](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [<span data-ttu-id="39136-184">トールドドランサムウェアは、Da Vinci コード (The) によって影響を与えます</span><span class="sxs-lookup"><span data-stu-id="39136-184">Troldesh ransomware influenced by (the) Da Vinci code</span></span>](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
