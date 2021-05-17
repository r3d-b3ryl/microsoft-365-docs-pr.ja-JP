---
title: 驚異の保護を強化する
f1.keywords:
- NOCSH
ms.author: sharik
author: Skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5abfef7b-5957-484a-b06b-a7c55e013e44
description: ユーザーの保護のレベルを上Microsoft 365
ms.openlocfilehash: a1f4714d5b7dcd8d6a22a07c118055e13b27e069
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398279"
---
# <a name="increase-threat-protection-for-microsoft-365-subscription"></a><span data-ttu-id="c917b-103">サブスクリプションの脅威保護をMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="c917b-103">Increase threat protection for Microsoft 365 subscription</span></span>

<span data-ttu-id="c917b-104">この記事は、フィッシング、マルウェア、その他の脅威Microsoft 365保護するために、サブスクリプションの保護を強化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c917b-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="c917b-105">これらの推奨事項は、政治キャンペーン、法律事務所、医療クリニックなど、セキュリティの必要性が高い組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="c917b-105">These recommendations are appropriate for organizations with an increased need for security, like political campaigns, law offices, and health care clinics.</span></span>

<span data-ttu-id="c917b-106">開始する前に、Microsoft Secure Score を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c917b-106">Before you begin, check your Microsoft Secure Score.</span></span> <span data-ttu-id="c917b-107">Microsoft Secure Score は、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="c917b-107">Microsoft Secure Score analyzes your organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="c917b-108">まず、現在のスコアをメモします。</span><span class="sxs-lookup"><span data-stu-id="c917b-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="c917b-109">この記事で推奨されるアクションを実行すると、スコアが上昇します。</span><span class="sxs-lookup"><span data-stu-id="c917b-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="c917b-110">目標は、最大スコアを達成するのではなく、ユーザーの生産性に悪影響を及ぼしない環境を保護する機会を認識する方法です。</span><span class="sxs-lookup"><span data-stu-id="c917b-110">The goal isn't to achieve the max score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="c917b-111">詳細については [、「Microsoft Secure Score」を参照してください](../security/defender/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="c917b-111">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="c917b-112">メール内のマルウェアに対する保護のレベルを上げる</span><span class="sxs-lookup"><span data-stu-id="c917b-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="c917b-113">ユーザー Office 365またはMicrosoft 365にはマルウェアに対する保護が含まれますが、マルウェアに一般的に使用されるファイルの種類を含む添付ファイルをブロックすることで、この保護を強化できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="c917b-114">電子メールでマルウェア保護を強化するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-114">To bump up malware protection in email:</span></span>

1. <span data-ttu-id="c917b-115">管理者アカウント <https://protection.office.com> の資格情報に移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c917b-115">Go to <https://protection.office.com> and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="c917b-116">セキュリティ コンプライアンス センター&左側のナビゲーション ウィンドウの [脅威の **管理**] で、[ **ポリシーマルウェア対策**] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-116">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="c917b-117">既定のポリシーをダブルクリックして、この会社全体のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="c917b-117">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="c917b-118">**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-118">Click **Settings**.</span></span>

5. <span data-ttu-id="c917b-119">[共通 **の添付ファイルの種類フィルター] で**、[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="c917b-120">ブロックされているファイルの種類は、このコントロールの直下のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c917b-120">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="c917b-121">次のファイル型を追加してください。</span><span class="sxs-lookup"><span data-stu-id="c917b-121">Make sure you add these filetypes:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="c917b-122">必要に応じて、後でファイルの種類を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-122">You can add or delete file types later, if needed.</span></span>

6. <span data-ttu-id="c917b-123">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-123">Click **Save.**</span></span>

<span data-ttu-id="c917b-124">詳細については [、「EOP でのマルウェア対策保護」を参照してください](../security/office-365-security/anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c917b-124">For more information, see [Anti-malware protection in EOP](../security/office-365-security/anti-malware-protection.md).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="c917b-125">ランサムウェアから保護する</span><span class="sxs-lookup"><span data-stu-id="c917b-125">Protect against ransomware</span></span>

<span data-ttu-id="c917b-126">ランサムウェアは、ファイルを暗号化するか、コンピューター画面をロックすることで、データへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="c917b-126">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="c917b-127">その後、データへのアクセスと引き換えに、通常はBitcoinのような暗号化の形で「身代金」を求め、被害者から金銭を強要しようとする。</span><span class="sxs-lookup"><span data-stu-id="c917b-127">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="c917b-128">ランサムウェアから保護するには、1 つ以上のメール フロー ルールを作成して、ランサムウェアに一般的に使用されるファイル拡張子 (メール[](#raise-the-level-of-protection-against-malware-in-mail)ステップでマルウェアに対する保護レベルの向上に追加されたファイル拡張子) をブロックしたり、電子メールでこれらの添付ファイルを受け取るユーザーに警告したりします。</span><span class="sxs-lookup"><span data-stu-id="c917b-128">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="c917b-129">前の手順でブロックしたファイルに加えて、マクロを含む Office ファイル添付ファイルを開く前にユーザーに警告するルールを作成する方法も良い方法です。</span><span class="sxs-lookup"><span data-stu-id="c917b-129">In addition to the files that you blocked in the previous step, it's also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="c917b-130">ランサムウェアはマクロ内に隠される可能性があります。そのため、ユーザーに知らない人からこれらのファイルを開かされないように警告します。</span><span class="sxs-lookup"><span data-stu-id="c917b-130">Ransomware can be hidden inside macros, so warn users to not open these files from people they don't know.</span></span>

<span data-ttu-id="c917b-131">メール トランスポート ルールを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-131">To create a mail transport rule:</span></span>

1. <span data-ttu-id="c917b-132">管理センターに移動し、[管理 <https://admin.microsoft.com> センター]**を選択Exchange。** \> </span><span class="sxs-lookup"><span data-stu-id="c917b-132">Go to the admin center at <https://admin.microsoft.com> and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="c917b-133">メール フロー **カテゴリで、[** ルール] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c917b-133">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="c917b-134">を **+** クリックし、[新しい **ルールの作成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c917b-134">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="c917b-135">ダイアログ **ボックスの下部** にある [その他のオプション] をクリックして、オプションの完全なセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="c917b-135">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="c917b-136">ルールの次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="c917b-136">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="c917b-137">残りの設定は、変更しない限り、既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="c917b-137">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="c917b-138">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-138">Click **Save**.</span></span>

|<span data-ttu-id="c917b-139">Setting</span><span class="sxs-lookup"><span data-stu-id="c917b-139">Setting</span></span>|<span data-ttu-id="c917b-140">ファイルの添付ファイルを開く前にユーザーにOfficeする</span><span class="sxs-lookup"><span data-stu-id="c917b-140">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="c917b-141">名前</span><span class="sxs-lookup"><span data-stu-id="c917b-141">Name</span></span>|<span data-ttu-id="c917b-142">ランサムウェア対策ルール: ユーザーに警告する</span><span class="sxs-lookup"><span data-stu-id="c917b-142">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="c917b-143">場合は、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="c917b-143">Apply this rule if .</span></span> <span data-ttu-id="c917b-144">.</span><span class="sxs-lookup"><span data-stu-id="c917b-144">.</span></span> <span data-ttu-id="c917b-145">.</span><span class="sxs-lookup"><span data-stu-id="c917b-145">.</span></span>|<span data-ttu-id="c917b-146">任意の添付ファイル 。</span><span class="sxs-lookup"><span data-stu-id="c917b-146">Any attachment .</span></span> <span data-ttu-id="c917b-147">.</span><span class="sxs-lookup"><span data-stu-id="c917b-147">.</span></span> <span data-ttu-id="c917b-148">.</span><span class="sxs-lookup"><span data-stu-id="c917b-148">.</span></span> <span data-ttu-id="c917b-149">ファイル拡張子が一致します。</span><span class="sxs-lookup"><span data-stu-id="c917b-149">file extension matches .</span></span> <span data-ttu-id="c917b-150">.</span><span class="sxs-lookup"><span data-stu-id="c917b-150">.</span></span> <span data-ttu-id="c917b-151">.</span><span class="sxs-lookup"><span data-stu-id="c917b-151">.</span></span>|
|<span data-ttu-id="c917b-152">単語または語句を指定する</span><span class="sxs-lookup"><span data-stu-id="c917b-152">Specify words or phrases</span></span>|<span data-ttu-id="c917b-153">次のファイルの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="c917b-153">Add these file types:</span></span> <br/> `dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm`|
|<span data-ttu-id="c917b-154">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c917b-154">Do the following .</span></span> <span data-ttu-id="c917b-155">.</span><span class="sxs-lookup"><span data-stu-id="c917b-155">.</span></span> <span data-ttu-id="c917b-156">.</span><span class="sxs-lookup"><span data-stu-id="c917b-156">.</span></span>|<span data-ttu-id="c917b-157">受信者にメッセージで通知します。</span><span class="sxs-lookup"><span data-stu-id="c917b-157">Notify the recipient with a message</span></span>|
|<span data-ttu-id="c917b-158">メッセージ テキストを提供する</span><span class="sxs-lookup"><span data-stu-id="c917b-158">Provide message text</span></span>|<span data-ttu-id="c917b-159">これらの種類のファイルは、悪意のあるコードを含むマクロが含まれている可能性があるから、知らない人から開かれません。</span><span class="sxs-lookup"><span data-stu-id="c917b-159">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="c917b-160">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c917b-160">For more information, see:</span></span>

- [<span data-ttu-id="c917b-161">ランサムウェア: リスクを軽減する方法</span><span class="sxs-lookup"><span data-stu-id="c917b-161">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="c917b-162">OneDrive を復元する</span><span class="sxs-lookup"><span data-stu-id="c917b-162">Restore your OneDrive</span></span>](https://support.microsoft.com//office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="c917b-163">電子メールの自動転送を停止する</span><span class="sxs-lookup"><span data-stu-id="c917b-163">Stop auto-forwarding for email</span></span>

<span data-ttu-id="c917b-164">ユーザーのメールボックスにアクセスするハッカーは、メールを自動的に転送するメールボックスを設定することで、メールを盗む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c917b-164">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="c917b-165">これは、ユーザーの認識がなくても発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c917b-165">This can happen even without the user's awareness.</span></span> <span data-ttu-id="c917b-166">メール フロー ルールを構成することで、この問題を回避できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-166">You can prevent this from happening by configuring a mail flow rule.</span></span>

<span data-ttu-id="c917b-167">メール トランスポート ルールを作成するには、この短い [ビデオを見](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-167">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="c917b-168">[管理センター Microsoft 365で、[管理センター]**をクリックExchange。** \> </span><span class="sxs-lookup"><span data-stu-id="c917b-168">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="c917b-169">メール フロー **カテゴリで、[** ルール] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c917b-169">In the **mail flow** category, click **rules**.</span></span>

3. <span data-ttu-id="c917b-170">を **+** クリックし、[新しい **ルールの作成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c917b-170">Click **+**, and then click **Create a new rule**.</span></span>

4. <span data-ttu-id="c917b-171">ダイアログ **ボックスの下部** にある [その他のオプション] をクリックして、オプションの完全なセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="c917b-171">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="c917b-172">次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="c917b-172">Apply the settings in the following table.</span></span> <span data-ttu-id="c917b-173">残りの設定は、変更しない限り、既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="c917b-173">Leave the rest of the settings at the default, unless you want to change them.</span></span>

6. <span data-ttu-id="c917b-174">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-174">Click **Save**.</span></span>

|<span data-ttu-id="c917b-175">Setting</span><span class="sxs-lookup"><span data-stu-id="c917b-175">Setting</span></span>|<span data-ttu-id="c917b-176">ファイルの添付ファイルを開く前にユーザーにOfficeする</span><span class="sxs-lookup"><span data-stu-id="c917b-176">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="c917b-177">名前</span><span class="sxs-lookup"><span data-stu-id="c917b-177">Name</span></span>|<span data-ttu-id="c917b-178">外部ドメインへの電子メールの自動転送を防止する</span><span class="sxs-lookup"><span data-stu-id="c917b-178">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="c917b-179">... の場合は、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="c917b-179">Apply this rule if ...</span></span>|<span data-ttu-id="c917b-180">送信者 。</span><span class="sxs-lookup"><span data-stu-id="c917b-180">The sender .</span></span> <span data-ttu-id="c917b-181">.</span><span class="sxs-lookup"><span data-stu-id="c917b-181">.</span></span> <span data-ttu-id="c917b-182">.</span><span class="sxs-lookup"><span data-stu-id="c917b-182">.</span></span> <span data-ttu-id="c917b-183">は外部/内部です。</span><span class="sxs-lookup"><span data-stu-id="c917b-183">is external/internal .</span></span> <span data-ttu-id="c917b-184">.</span><span class="sxs-lookup"><span data-stu-id="c917b-184">.</span></span> <span data-ttu-id="c917b-185">.</span><span class="sxs-lookup"><span data-stu-id="c917b-185">.</span></span> <span data-ttu-id="c917b-186">組織内</span><span class="sxs-lookup"><span data-stu-id="c917b-186">Inside the organization</span></span>|
|<span data-ttu-id="c917b-187">条件の追加</span><span class="sxs-lookup"><span data-stu-id="c917b-187">Add condition</span></span>|<span data-ttu-id="c917b-188">メッセージのプロパティ 。</span><span class="sxs-lookup"><span data-stu-id="c917b-188">The message properties .</span></span> <span data-ttu-id="c917b-189">.</span><span class="sxs-lookup"><span data-stu-id="c917b-189">.</span></span> <span data-ttu-id="c917b-190">.</span><span class="sxs-lookup"><span data-stu-id="c917b-190">.</span></span> <span data-ttu-id="c917b-191">メッセージの種類を含める。</span><span class="sxs-lookup"><span data-stu-id="c917b-191">include the message type .</span></span> <span data-ttu-id="c917b-192">.</span><span class="sxs-lookup"><span data-stu-id="c917b-192">.</span></span> <span data-ttu-id="c917b-193">.</span><span class="sxs-lookup"><span data-stu-id="c917b-193">.</span></span> <span data-ttu-id="c917b-194">自動転送</span><span class="sxs-lookup"><span data-stu-id="c917b-194">Auto-forward</span></span>|
|<span data-ttu-id="c917b-195">次の ..を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-195">Do the following ...</span></span>|<span data-ttu-id="c917b-196">メッセージをブロックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-196">Block the message .</span></span> <span data-ttu-id="c917b-197">.</span><span class="sxs-lookup"><span data-stu-id="c917b-197">.</span></span> <span data-ttu-id="c917b-198">.</span><span class="sxs-lookup"><span data-stu-id="c917b-198">.</span></span> <span data-ttu-id="c917b-199">メッセージを拒否し、説明を含める。</span><span class="sxs-lookup"><span data-stu-id="c917b-199">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="c917b-200">メッセージ テキストを提供する</span><span class="sxs-lookup"><span data-stu-id="c917b-200">Provide message text</span></span>|<span data-ttu-id="c917b-201">この組織外の電子メールの自動転送は、セキュリティ上の理由から防止されます。</span><span class="sxs-lookup"><span data-stu-id="c917b-201">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|

## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="c917b-202">フィッシング攻撃からメールを保護する</span><span class="sxs-lookup"><span data-stu-id="c917b-202">Protect your email from phishing attacks</span></span>

<span data-ttu-id="c917b-203">1 つ以上のカスタム ドメインを Office 365または Microsoft 365環境に構成した場合は、ターゲットフィッシング対策保護を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-203">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="c917b-204">Microsoft Defender for Office 365 の一部であるフィッシング対策保護は、悪意のある偽装ベースのフィッシング攻撃や他のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c917b-204">Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="c917b-205">カスタム ドメインを構成していない場合は、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c917b-205">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="c917b-206">最も重要なユーザーとカスタム ドメインを保護するためのポリシーを作成して、この保護を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c917b-206">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="c917b-207">Defender for Office 365でフィッシング対策ポリシーを作成するには、この短いトレーニング[](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)ビデオを見る、または次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-207">To create an anti-phishing policy in Defender for Office 365, watch [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="c917b-208"><https://protection.office.com> に移動します。</span><span class="sxs-lookup"><span data-stu-id="c917b-208">Go to <https://protection.office.com>.</span></span>

2. <span data-ttu-id="c917b-209">セキュリティ コンプライアンス センター&左側のナビゲーション ウィンドウの [脅威の **管理]** で、[ポリシー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-209">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="c917b-210">[ポリシー] **ページで** 、[フィッシング対策 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-210">On the **Policy** page, choose **Anti-phishing**.</span></span>

4. <span data-ttu-id="c917b-211">[フィッシング **対策] ページで、[+** 作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-211">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="c917b-212">ウィザードが起動し、フィッシング対策ポリシーを定義する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-212">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="c917b-213">推奨されるポリシーの名前、説明、設定を以下のグラフで指定します。</span><span class="sxs-lookup"><span data-stu-id="c917b-213">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="c917b-214">詳細については、「Microsoft Defender のフィッシング対策ポリシーについて」を参照[してください。Office 365してください](../security/office-365-security/set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c917b-214">For more information, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

6. <span data-ttu-id="c917b-215">設定を確認した後、必要に応じて [このポリシーを作成する] または **[\*\*\*\*保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-215">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="c917b-216">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="c917b-216">Setting or option</span></span>|<span data-ttu-id="c917b-217">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="c917b-217">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="c917b-218">名前</span><span class="sxs-lookup"><span data-stu-id="c917b-218">Name</span></span>|<span data-ttu-id="c917b-219">ドメインと最も貴重なスタッフ</span><span class="sxs-lookup"><span data-stu-id="c917b-219">Domain and most valuable staff</span></span>|
|<span data-ttu-id="c917b-220">説明</span><span class="sxs-lookup"><span data-stu-id="c917b-220">Description</span></span>|<span data-ttu-id="c917b-221">最も重要なスタッフとドメインが偽装されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="c917b-221">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="c917b-222">保護対象のユーザーの追加</span><span class="sxs-lookup"><span data-stu-id="c917b-222">Add users to protect</span></span>|<span data-ttu-id="c917b-223">[+**条件の追加] を選択します。受信者は .**</span><span class="sxs-lookup"><span data-stu-id="c917b-223">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="c917b-224">ユーザー名を入力するか、ビジネス所有者、パートナー、または候補者、マネージャー、その他の重要なスタッフ メンバーの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c917b-224">Type user names or enter the email address of the business owners, partners, or candidate, managers, and other important staff members.</span></span> <span data-ttu-id="c917b-225">偽装から保護する最大 20 の内部アドレスと外部アドレスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-225">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="c917b-226">保護対象のドメインの追加</span><span class="sxs-lookup"><span data-stu-id="c917b-226">Add domains to protect</span></span>|<span data-ttu-id="c917b-227">Select **+ Add a condition, the recipient domain is**.</span><span class="sxs-lookup"><span data-stu-id="c917b-227">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="c917b-228">サブスクリプションを定義している場合は、Microsoft 365に関連付けられているカスタム ドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="c917b-228">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="c917b-229">複数のドメインを入力できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-229">You can enter more than one domain.</span></span>|
|<span data-ttu-id="c917b-230">処理の選択</span><span class="sxs-lookup"><span data-stu-id="c917b-230">Choose actions</span></span>|<span data-ttu-id="c917b-231">偽装ユーザーによって電子メールが送信される場合: **[メッセージ** を別の電子メール アドレスにリダイレクトする] を選択し、セキュリティ管理者の電子メール アドレスを入力します。たとえば *、Alice <span> <span> @contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="c917b-231">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <br/> <span data-ttu-id="c917b-232">メールが偽装ドメインによって送信されている場合: **[メッセージを検疫]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-232">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="c917b-233">メールボックス インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="c917b-233">Mailbox intelligence</span></span>|<span data-ttu-id="c917b-234">既定では、新しいフィッシング対策ポリシーの作成時にはメールボックス インテリジェンスが選択されています。</span><span class="sxs-lookup"><span data-stu-id="c917b-234">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="c917b-235">最適な結果が得られるように、この設定は **[オン]** のままにしておいてください。</span><span class="sxs-lookup"><span data-stu-id="c917b-235">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="c917b-236">信頼できる送信者とドメインの追加</span><span class="sxs-lookup"><span data-stu-id="c917b-236">Add trusted senders and domains</span></span>|<span data-ttu-id="c917b-237">ここでは、独自のドメイン、または他の信頼できるドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-237">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="c917b-238">適用先</span><span class="sxs-lookup"><span data-stu-id="c917b-238">Applied to</span></span>|<span data-ttu-id="c917b-239">**[受信者のドメインが次の場合]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-239">Select **The recipient domain is**.</span></span> <span data-ttu-id="c917b-240">**[これらのいずれか]** では、**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-240">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="c917b-241">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-241">Select **+ Add**.</span></span> <span data-ttu-id="c917b-242">contoso など、ドメインの名前の横にあるチェック ボックスを *オンにします。 <span> <span>com* をクリックし、一覧で [追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-242">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="c917b-243">**[完了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-243">Select **Done**.</span></span>|

<span data-ttu-id="c917b-244">詳細については、「Defender [for Office 365」を参照してください](../security/office-365-security/set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c917b-244">For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

## <a name="protect-against-malicious-attachments-files-and-links-with-defender-for-office-365"></a><span data-ttu-id="c917b-245">Defender を使用して悪意のある添付ファイル、ファイル、およびリンクから保護Office 365</span><span class="sxs-lookup"><span data-stu-id="c917b-245">Protect against malicious attachments, files, and links with Defender for Office 365</span></span>

![を指す https://aka.ms/aboutM365preview バナー。](../media/m365admincenterchanging.png)

<span data-ttu-id="c917b-247">最初に、管理センターで新しい管理センターのプレビューを有効 <https://admin.microsoft.com> にしてください。</span><span class="sxs-lookup"><span data-stu-id="c917b-247">First, make sure, in the admin center at <https://admin.microsoft.com> that you have the new admin center preview turned on.</span></span> <span data-ttu-id="c917b-248">[新しい管理センター] というテキストの横にある **トグルをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="c917b-248">Turn on the toggle next to the text **The new admin center**.</span></span>

   ![新しい管理センターのプレビューがオンです。](../media/previewon.png)

<span data-ttu-id="c917b-250">テナントにカードを含む[セットアップ] ページがまだ表示されていない場合は、「Security & コンプライアンス センター」の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c917b-250">If you don't see the **Setup** page with cards in your tenant yet, see how to complete these steps in Security & Compliance Center.</span></span> <span data-ttu-id="c917b-251">「[セキュリティ セーフ](#set-up-safe-attachments-in-the-security--compliance-center)コンプライアンス センター&の添付ファイルを設定する」および「セキュリティ セーフ コンプライアンス センターのリンクを&[する」を参照してください](#set-up-safe-links-in-the-security--compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="c917b-251">See [Set up Safe Attachments in the Security & Compliance Center](#set-up-safe-attachments-in-the-security--compliance-center) and [Set up Safe Links in the Security & Compliance Center](#set-up-safe-links-in-the-security--compliance-center).</span></span>

1. <span data-ttu-id="c917b-252">左側のナビゲーションで、[セットアップ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-252">In the left nav, choose **Setup**.</span></span>
2. <span data-ttu-id="c917b-253">[セットアップ] **ページで** 、[ **高度な脅威からの** 保護を強化 **する] カードの [表示] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="c917b-253">On the **Setup** page, choose **View** on the **Increase protection from advanced threats** card.</span></span>

   ![[高度な脅威からの保護の強化] で [表示] を選択します。](../media/startatp.png)

3. <span data-ttu-id="c917b-255">[高度な **脅威からの保護の強化] ページで** 、[開始する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-255">On the **Increase protection from advanced threats** page, choose **Get started**.</span></span>
4. <span data-ttu-id="c917b-256">開くウィンドウで、[メール内のリンクと添付ファイル]  **、SharePoint、OneDrive、** および Teams のファイルのスキャン、および Office デスクトップアプリと **Office Online** アプリの [悪意のあるコンテンツのアイテムのスキャン] の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c917b-256">On the pane that opens, select the check boxes next to **Links and attachments in email**, **Scan files in SharePoint, OneDrive, and Teams**, and **Scan links in Office desktop and Office Online apps** under **Scan items for malicious content**.</span></span>

   <span data-ttu-id="c917b-257">[ **メールのリンクと添付ファイル]** で、[すべてのユーザー] またはメールをスキャンする特定のユーザーを入力します。</span><span class="sxs-lookup"><span data-stu-id="c917b-257">Under **Links and attachments in email**, Type in All Users, or the specific users whose email you want scanned.</span></span>

   ![[高度な脅威からの保護を強化する] で、すべてのチェック ボックスをオンにします。](../media/setatp.png)

5. <span data-ttu-id="c917b-259">[**ポリシーの作成] を** 選択して、[添付ファイルセーフリンクセーフします。</span><span class="sxs-lookup"><span data-stu-id="c917b-259">Choose **Create policies** to turn on Safe Attachments and Safe Links.</span></span>

### <a name="set-up-safe-attachments-in-the-security--compliance-center"></a><span data-ttu-id="c917b-260">セキュリティ セーフ コンプライアンス センターで添付ファイル&設定する</span><span class="sxs-lookup"><span data-stu-id="c917b-260">Set up Safe Attachments in the Security & Compliance Center</span></span>

<span data-ttu-id="c917b-261">ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを定期的に送信、受信、共有します。</span><span class="sxs-lookup"><span data-stu-id="c917b-261">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="c917b-262">電子メール メッセージを見ただけで、添付ファイルが安全か悪意かを判断するのは必ずしも簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="c917b-262">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="c917b-263">Microsoft Defender for Office 365添付セーフが含まれていますが、この保護は既定では有効にされません。</span><span class="sxs-lookup"><span data-stu-id="c917b-263">Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="c917b-264">この保護の使用を開始するには、新しいルールを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c917b-264">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="c917b-265">この保護は、SharePoint、OneDrive、およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="c917b-265">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="c917b-266">添付ファイル ポリシーをセーフするには、この短いビデオ[を見](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-266">To create an Safe Attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="c917b-267">管理者アカウント <https://protection.office.com> に移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c917b-267">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="c917b-268">セキュリティ コンプライアンス センター&左側のナビゲーション ウィンドウの [脅威の **管理]** で、[ポリシー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-268">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="c917b-269">[ポリシー] ページで、[添付ファイル]**をセーフします**。</span><span class="sxs-lookup"><span data-stu-id="c917b-269">On the Policy page, choose **Safe Attachments**.</span></span>

4. <span data-ttu-id="c917b-270">[添付ファイルセーフ] ページで、[atp for SharePoint、OneDrive、および Microsoft Teams] チェック ボックスをオンにして、この保護 **を広く適用** します。</span><span class="sxs-lookup"><span data-stu-id="c917b-270">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="c917b-271">新 **+** しいポリシーを作成する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-271">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="c917b-272">次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="c917b-272">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="c917b-273">設定を確認した後、必要に応じて [ **このポリシーの作成** ] または **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-273">After you review your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="c917b-274">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="c917b-274">Setting or option</span></span>|<span data-ttu-id="c917b-275">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="c917b-275">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="c917b-276">名前</span><span class="sxs-lookup"><span data-stu-id="c917b-276">Name</span></span>|<span data-ttu-id="c917b-277">検出されたマルウェアを使用して、現在および将来のメールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-277">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="c917b-278">説明</span><span class="sxs-lookup"><span data-stu-id="c917b-278">Description</span></span>|<span data-ttu-id="c917b-279">検出されたマルウェアを使用して、現在および将来の電子メールと添付ファイルをブロックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-279">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="c917b-280">添付ファイルの不明なマルウェアの応答を保存する</span><span class="sxs-lookup"><span data-stu-id="c917b-280">Save attachments unknown malware response</span></span>|<span data-ttu-id="c917b-281">[ **ブロック] を選択します。 検出されたマルウェアを使用して現在および将来のメールと添付ファイルをブロックします**。</span><span class="sxs-lookup"><span data-stu-id="c917b-281">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="c917b-282">検出時に添付ファイルをリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="c917b-282">Redirect attachment on detection</span></span>|<span data-ttu-id="c917b-283">リダイレクトを有効にする (このボックスを選択)</span><span class="sxs-lookup"><span data-stu-id="c917b-283">Enable redirection (select this box)</span></span> <br/> <span data-ttu-id="c917b-284">検疫用の管理者アカウントまたはメールボックスのセットアップを入力します。</span><span class="sxs-lookup"><span data-stu-id="c917b-284">Enter the admin account or a mailbox setup for quarantine.</span></span> <br/> <span data-ttu-id="c917b-285">添付ファイルのマルウェア スキャンが時間切れまたはエラーが発生した場合は、上記の選択項目を適用します (このボックスを選択します)。</span><span class="sxs-lookup"><span data-stu-id="c917b-285">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="c917b-286">適用先</span><span class="sxs-lookup"><span data-stu-id="c917b-286">Applied to</span></span>|<span data-ttu-id="c917b-287">受信者ドメインはです。</span><span class="sxs-lookup"><span data-stu-id="c917b-287">The recipient domain is .</span></span> <span data-ttu-id="c917b-288">.</span><span class="sxs-lookup"><span data-stu-id="c917b-288">.</span></span> <span data-ttu-id="c917b-289">.</span><span class="sxs-lookup"><span data-stu-id="c917b-289">.</span></span> <span data-ttu-id="c917b-290">ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-290">select your domain.</span></span>|

<span data-ttu-id="c917b-291">詳細については、「Defender [for Office 365」を参照してください](../security/office-365-security/set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c917b-291">For more information, see [Set up anti-phishing policies in Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

### <a name="set-up-safe-links-in-the-security--compliance-center"></a><span data-ttu-id="c917b-292">セキュリティ セーフ コンプライアンス センターでリンクを&設定する</span><span class="sxs-lookup"><span data-stu-id="c917b-292">Set up Safe Links in the Security & Compliance Center</span></span>

<span data-ttu-id="c917b-293">ハッカーは、メールや他のファイルのリンクに悪意のある Web サイトを非表示にしている場合があります。</span><span class="sxs-lookup"><span data-stu-id="c917b-293">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="c917b-294">セーフOffice 365 用 Microsoft Defender の一部であるリンクは、電子メール メッセージおよびドキュメント内の Web アドレス (URL) のクリック時の検証を提供することで、組織を保護Officeできます。</span><span class="sxs-lookup"><span data-stu-id="c917b-294">Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="c917b-295">保護は、リンク ポリシーセーフによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="c917b-295">Protection is defined through Safe Links policies.</span></span>

<span data-ttu-id="c917b-296">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c917b-296">We recommend that you do the following:</span></span>

- <span data-ttu-id="c917b-297">保護を強化するために既定のポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c917b-297">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="c917b-298">ドメイン内のすべての受信者を対象とする新しいポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="c917b-298">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="c917b-299">リンクを設定セーフ、この短いトレーニング ビデオ[を見](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)る、または次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-299">To set up Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="c917b-300">管理者アカウント <https://protection.office.com> に移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c917b-300">Go to <https://protection.office.com> and sign in with your admin account.</span></span>

2. <span data-ttu-id="c917b-301">セキュリティ コンプライアンス センター&左側のナビゲーション ウィンドウの [脅威の **管理]** で、[ポリシー] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-301">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="c917b-302">[ポリシー] ページで、[リンク]**セーフ選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-302">On the Policy page, choose **Safe Links**.</span></span>

<span data-ttu-id="c917b-303">既定のポリシーを変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-303">To modify the default policy:</span></span>

1. <span data-ttu-id="c917b-304">[リンクセーフ] ページの [組織全体に適用されるポリシー] で、[既定のポリシー]**を選択** します。</span><span class="sxs-lookup"><span data-stu-id="c917b-304">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="c917b-305">**[設定以外のコンテンツ** に適用する場合は、[iOS と Android **Microsoft 365 Apps for enterprise] Officeを選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-305">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="c917b-306">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-306">Click **Save**.</span></span>

<span data-ttu-id="c917b-307">ドメイン内のすべての受信者を対象とする新しいポリシーを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="c917b-307">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="c917b-308">[リンクセーフ] ページの [組織全体に適用されるポリシー] で、クリックして新しい **+** ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c917b-308">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span>

2. <span data-ttu-id="c917b-309">次の表に示す設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="c917b-309">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="c917b-310">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c917b-310">Click **Save**.</span></span>

|<span data-ttu-id="c917b-311">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="c917b-311">Setting or option</span></span>|<span data-ttu-id="c917b-312">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="c917b-312">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="c917b-313">名前</span><span class="sxs-lookup"><span data-stu-id="c917b-313">Name</span></span>|<span data-ttu-id="c917b-314">セーフのすべての受信者のリンク ポリシー</span><span class="sxs-lookup"><span data-stu-id="c917b-314">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="c917b-315">メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する</span><span class="sxs-lookup"><span data-stu-id="c917b-315">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="c917b-316">[ **オン] を選択すると、ユーザー** がリンクをクリックすると、URL が書き換えされ、既知の悪意のあるリンクの一覧に対してチェックされます。</span><span class="sxs-lookup"><span data-stu-id="c917b-316">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="c917b-317">[添付セーフを使用してダウンロード可能なコンテンツをスキャンする</span><span class="sxs-lookup"><span data-stu-id="c917b-317">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="c917b-318">このボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-318">Select this box.</span></span>|
|<span data-ttu-id="c917b-319">適用先</span><span class="sxs-lookup"><span data-stu-id="c917b-319">Applied to</span></span>|<span data-ttu-id="c917b-320">受信者ドメインはです。</span><span class="sxs-lookup"><span data-stu-id="c917b-320">The recipient domain is .</span></span> <span data-ttu-id="c917b-321">.</span><span class="sxs-lookup"><span data-stu-id="c917b-321">.</span></span> <span data-ttu-id="c917b-322">.</span><span class="sxs-lookup"><span data-stu-id="c917b-322">.</span></span> <span data-ttu-id="c917b-323">ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-323">select your domain.</span></span>|

<span data-ttu-id="c917b-324">詳細については、「Defender[セーフリンク」を参照Office 365。](../security/office-365-security/safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="c917b-324">For more information, see [Safe Links in Defender for Office 365](../security/office-365-security/safe-links.md).</span></span>

## <a name="turn-on-the-unified-audit-log"></a><span data-ttu-id="c917b-325">統合監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="c917b-325">Turn on the Unified Audit Log</span></span>

<span data-ttu-id="c917b-326">セキュリティ & コンプライアンス センターで監査ログ検索を有効にした後、管理者と他のユーザー アクティビティをログに保持して検索できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-326">After you turn on the audit log search in the Security & Compliance Center, you can retain the admin and other user activity in the log and search it.</span></span>

<span data-ttu-id="c917b-327">監査ログの検索をサブスクリプションでオンまたはオフExchange Onlineするには、監査ログロールを割り当てるMicrosoft 365必要があります。</span><span class="sxs-lookup"><span data-stu-id="c917b-327">You must be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 subscription.</span></span> <span data-ttu-id="c917b-328">既定では、この役割は、管理センターの [アクセス許可] ページの [コンプライアンス管理] および [組織の管理Exchange割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c917b-328">By default, this role is assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="c917b-329">既定では、Microsoft 365のグローバル管理者は、このグループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="c917b-329">Global admins in Microsoft 365 are members of this group by default.</span></span>

1. <span data-ttu-id="c917b-330">監査ログ検索を有効にする場合は、管理センターに移動し、左側のナビゲーションの [管理センター] で [セキュリティ <https://admin.microsoft.com> **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-330">To turn on the audit log search, go to the admin center at <https://admin.microsoft.com> and then choose **Security** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="c917b-331">[セキュリティの **Microsoft 365]** ページで、[その他のリソース]を選択し、[コンプライアンス センター] **Office 365[&] カードで開** きます。</span><span class="sxs-lookup"><span data-stu-id="c917b-331">On the **Microsoft 365 Security** page, choose **More resources**, and then **Open** on the **Office 365 Security & Compliance Center** card.</span></span>

    ![コンプライアンス 車のセキュリティ とセキュリティ &を選択します。](../media/gotosecandcomp.png)
3. <span data-ttu-id="c917b-333">[セキュリティとコンプライアンス] ページで、[検索] を選択 **し** 、[ログ検索 **の監査] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-333">On the security and compliance page, choose **Search** and then **Audit log search**.</span></span>
4. <span data-ttu-id="c917b-334">[監査ログ検索] ページ **の上部にある [** 監査 **を有効にする] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-334">On the top of the **Audit log search** page, choose **Turn on auditing**.</span></span>

<span data-ttu-id="c917b-335">機能を有効にすると、ファイル、フォルダー、および多くのアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-335">After the feature is turned on, you can search for files, folders, and many activities.</span></span> <span data-ttu-id="c917b-336">詳細については、「監査ログ [の検索」を参照してください](../compliance/search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="c917b-336">For more information, see [search the audit log](../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="tune-up-anonymous-sharing-settings-for-sharepoint-and-onedrive-files-and-folders"></a><span data-ttu-id="c917b-337">ファイルとフォルダーの共有と管理SharePoint匿名OneDrive設定を調整する</span><span class="sxs-lookup"><span data-stu-id="c917b-337">Tune-up anonymous sharing settings for SharePoint and OneDrive files and folders</span></span>

<span data-ttu-id="c917b-338">(既定の匿名リンクの有効期限を 14 日間に変更し、既定の共有の種類を "特定のユーザー" に変更する)ユーザーとユーザーの共有設定をOneDriveするにはSharePoint。</span><span class="sxs-lookup"><span data-stu-id="c917b-338">(change default anonymous link expiration to 14 days, change default sharing type to "Specific People") To change the sharing settings for OneDrive and SharePoint:</span></span>

1. <span data-ttu-id="c917b-339">管理センターに移動し、左側のナビゲーション <https://admin.microsoft.com> **SharePoint** **[管理センター** ] で [管理センター] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-339">Go to the admin center at <https://admin.microsoft.com> and then choose **SharePoint** under **Admin centers** in the left nav.</span></span>
2. <span data-ttu-id="c917b-340">管理センター SharePoint、[ポリシーの共有]**に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="c917b-340">In the SharePoint admin center, go to **Policies** \> **Sharing**.</span></span>
3. <span data-ttu-id="c917b-341">[共有] ページの [ファイルとフォルダーのリンク] で、[特定のユーザー] を選択し、[すべてのユーザー] リンクの [詳細設定 **]** で、[これらのリンクは、この数日以内に期限切れになる必要があります] を選択し、14 (またはリンクの有効期間を制限する別の日数) を入力します。  </span><span class="sxs-lookup"><span data-stu-id="c917b-341">On the **Sharing** page, under **File and folder links**, select **Specific people**, and under **Advanced settings for "Anyone" links**, select **These links must expire within this many days**, and type in 14 (or another number of days you want to restrict the link lifetime to).</span></span>

   ![[特定のユーザー] を選択し、リンクの有効期限を 14 日間に設定します。](../media/anyonelinks.png)

## <a name="activity-alerts"></a><span data-ttu-id="c917b-343">アクティビティ通知</span><span class="sxs-lookup"><span data-stu-id="c917b-343">Activity alerts</span></span>

<span data-ttu-id="c917b-344">アクティビティ通知を使用して、管理者とユーザーのアクティビティを追跡し、組織内のマルウェアやデータ損失防止インシデントを検出できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-344">You can use activity alerts to track admin and user activities and detect malware and data loss prevention incidents in your organization.</span></span> <span data-ttu-id="c917b-345">サブスクリプションには一連の既定のポリシーが含まれていますが、カスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-345">Your subscription includes a set of default policies, but you can also create custom ones.</span></span> <span data-ttu-id="c917b-346">詳細については、「アラート ポリシー [」を参照してください](../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c917b-346">For more information, see [alert policies](../compliance/alert-policies.md).</span></span> <span data-ttu-id="c917b-347">たとえば、誰も外部で共有したくない重要なファイルを SharePoint に保存する場合は、他のユーザーが共有した場合に通知する通知を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-347">For example, if you store an important file in SharePoint that you don't want anyone to share externally, you can create a notification that alerts you if someone does share it.</span></span>

<span data-ttu-id="c917b-348">次の図は、このポリシーに含まれる既定のポリシーをMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c917b-348">The following figure shows the default policies that are included with Microsoft 365.</span></span>

![既定のアラート ポリシーは、Microsoft 365](../media/alertpolicies.png)

## <a name="disable-or-manage-calendar-sharing"></a><span data-ttu-id="c917b-350">予定表の共有を無効または管理する</span><span class="sxs-lookup"><span data-stu-id="c917b-350">Disable or manage calendar sharing</span></span>

<span data-ttu-id="c917b-351">組織内のユーザーが予定表を共有したり、共有できるコンテンツを管理したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c917b-351">You can prevent people in your organization from sharing their calendars, or you can also manage what they can share.</span></span> <span data-ttu-id="c917b-352">たとえば、共有を空き時間に制限できます。</span><span class="sxs-lookup"><span data-stu-id="c917b-352">For example, you can restrict the sharing to free/busy times only.</span></span>

1. <span data-ttu-id="c917b-353">[管理センター] に移動し <https://admin.microsoft.com> 、[組織]**設定** \> **を設定。**</span><span class="sxs-lookup"><span data-stu-id="c917b-353">Go to the admin center at <https://admin.microsoft.com> and choose **Settings** \> **Org Settings**.</span></span>
2. <span data-ttu-id="c917b-354">[サービス **] ページで**、[予定表] を選択し、組織内のユーザーが、Office 365 または Exchange を持っている外部のユーザーと予定表を共有できるかどうかを選択します。 </span><span class="sxs-lookup"><span data-stu-id="c917b-354">On the **Services** page, choose **Calendar**, and choose whether people in your organization can share their calendars with people outside who have Office 365 or Exchange, or with anyone.</span></span>

   <span data-ttu-id="c917b-355">[すべてのユーザーと共有] オプションを選択した場合は、空き時間情報のみを共有することもできます。</span><span class="sxs-lookup"><span data-stu-id="c917b-355">If you choose the share with anyone option, you can decide to also only share free/busy information.</span></span>

3. <span data-ttu-id="c917b-356">ページの **下部にある** [変更の保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c917b-356">Choose **Save changes** on the bottom of the page.</span></span>

   <span data-ttu-id="c917b-357">次の図は、予定表の共有が許可されていないを示しています。</span><span class="sxs-lookup"><span data-stu-id="c917b-357">The following figure shows calendar sharing not allowed.</span></span>

   ![外部予定表の共有を許可しないとして表示するスクリーンショット。](../media/nocalendarsharing.png)

   <span data-ttu-id="c917b-359">次の図は、空き時間情報のみを含むメール リンクで予定表の共有が許可されている場合の設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="c917b-359">The following figure shows the settings when calendar sharing is allowed with an email link with only free/busy information.</span></span>

   ![予定表の空き時間情報を誰とでも共有するスクリーンショット。](../media/sharefreebusy.png)

<span data-ttu-id="c917b-361">ユーザーが予定表の共有を許可されている場合は、Web[](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5)上のユーザーから共有する方法Outlook参照してください。</span><span class="sxs-lookup"><span data-stu-id="c917b-361">If your users are allowed to share their calendars, see [these instructions](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for how to share from Outlook on the web.</span></span>
