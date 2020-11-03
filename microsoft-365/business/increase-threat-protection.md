---
title: Microsoft 365 for Business の脅威保護を強化する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Microsoft Defender for Office 365 をセットアップし、機密データをフィッシング、マルウェア、およびその他の脅威から保護します。
ms.openlocfilehash: 2f1a26b5a2c5678871502d441b6ba64c9b011e1c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842258"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="9520c-103">驚異の保護を強化する</span><span class="sxs-lookup"><span data-stu-id="9520c-103">Increase threat protection</span></span>

<span data-ttu-id="9520c-104">この記事は、Microsoft 365 サブスクリプションの保護を強化して、フィッシング、マルウェア、およびその他の脅威から保護するのに役立つ情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="9520c-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="9520c-105">これらの推奨事項は、法律事務所や健康ケアクリニックなど、セキュリティのニーズが高まる組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="9520c-105">These recommendations are appropriate for organizations with an increased need for security, like law offices and health care clinics.</span></span>

<span data-ttu-id="9520c-106">開始する前に、Office 365 のセキュリティスコアを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="9520c-107">Office 365 のセキュリティで保護されたスコアは、定期的なアクティビティおよびセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9520c-107">Office 365 Secure Score analyzes your organization's security based on your regular activities and security settings, and assigns a score.</span></span> <span data-ttu-id="9520c-108">最初に、現在のスコアをメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="9520c-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="9520c-109">スコアを増やすには、この記事で推奨されている操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="9520c-109">To increase your score, complete the actions recommended in this article.</span></span> <span data-ttu-id="9520c-110">目標は最大スコアを達成することではなく、ユーザーの生産性に悪影響を及ぼすことがない環境を保護する機会に注意してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-110">The goal isn't to achieve the maximum score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="9520c-111">詳細については、「 [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="9520c-112">メールのマルウェアに対する保護レベルを上げる</span><span class="sxs-lookup"><span data-stu-id="9520c-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="9520c-113">Office 365 または Microsoft 365 環境には、マルウェアからの保護が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9520c-113">Your Office 365 or Microsoft 365 environment includes protection against malware.</span></span> <span data-ttu-id="9520c-114">マルウェアによく使用されるファイルの種類の添付ファイルをブロックすることにより、この保護を強化することができます。</span><span class="sxs-lookup"><span data-stu-id="9520c-114">You can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="9520c-115">電子メールでのマルウェア保護を向上させるには:</span><span class="sxs-lookup"><span data-stu-id="9520c-115">To increase malware protection in email:</span></span>

1. <span data-ttu-id="9520c-116">に移動 [https://protection.office.com](https://protection.office.com) し、管理者アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="9520c-116">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="9520c-117">セキュリティ &amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[ **脅威の管理** ] の下にある [ **ポリシー** \> **のマルウェア対策** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-117">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management** , choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="9520c-118">この会社全体のポリシーを編集するには、既定のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9520c-118">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="9520c-119">[ **設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-119">Select **Settings**.</span></span>

5. <span data-ttu-id="9520c-120">[ **一般的な添付ファイルの種類のフィルター** ] で、 **[オン] を選択し** ます。</span><span class="sxs-lookup"><span data-stu-id="9520c-120">Under **Common Attachment Types Filter** , select **On**.</span></span> <span data-ttu-id="9520c-121">ブロックされているファイルの種類は、このコントロールのすぐ下のウィンドウに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="9520c-121">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="9520c-122">これらのファイルの種類を追加していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-122">Make sure that you add these file types:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="9520c-123">必要に応じて、後でファイルの種類を追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9520c-123">If necessary, you can add or delete file types later.</span></span>

6. <span data-ttu-id="9520c-124">[保存] を選択し **ます。**</span><span class="sxs-lookup"><span data-stu-id="9520c-124">Select **Save.**</span></span>

<span data-ttu-id="9520c-125">詳細については、「 [EOP でのマルウェア対策保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-125">For more information, see [Anti-malware protection in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-malware-protection).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="9520c-126">ランサムウェアから保護する</span><span class="sxs-lookup"><span data-stu-id="9520c-126">Protect against ransomware</span></span>

<span data-ttu-id="9520c-127">ランサムウェアは、ファイルの暗号化またはコンピューター画面のロックによってデータへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="9520c-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="9520c-128">その後、データへのアクセスについては、通常はビットコインのような cryptocurrencies の形式で "ransom" を要求することによって、被害からの外に対して extort を試行します。</span><span class="sxs-lookup"><span data-stu-id="9520c-128">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="9520c-129">ランサムウェアから保護するには、1つまたは複数のメールフロールールを作成して、ランサムウェアとして一般的に使用されるファイル拡張子をブロックします。</span><span class="sxs-lookup"><span data-stu-id="9520c-129">To protect against ransomware, create one or more mail flow rules to block file extensions that are commonly used for ransomware.</span></span> <span data-ttu-id="9520c-130">(これらのルールは、「 [メールでマルウェアに対する保護レベルを高める](#raise-the-level-of-protection-against-malware-in-mail) 」に記載されています)。また、電子メールにこれらの添付ファイルを受信するユーザーに警告することもできます。</span><span class="sxs-lookup"><span data-stu-id="9520c-130">(You added these rules in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step.) You can also warn users who receive these attachments in email.</span></span>

<span data-ttu-id="9520c-131">前の手順でブロックしたファイルに加えて、マクロを含む Office ファイル添付ファイルを開く前に、ユーザーに警告するルールを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9520c-131">In addition to the files that you blocked in the previous step, it's a good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="9520c-132">ランサムウェアは、マクロ内で非表示にすることができるので、知らない人から開かないようにユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="9520c-132">Ransomware can be hidden inside macros, so warn users not to open these files from people they don't know.</span></span>

<span data-ttu-id="9520c-133">メールトランスポートルールを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9520c-133">To create a mail transport rule:</span></span>

1. <span data-ttu-id="9520c-134">の管理センターに移動 <https://admin.microsoft.com> し、[ **管理センター** Exchange] を選択し \> **Exchange** ます。</span><span class="sxs-lookup"><span data-stu-id="9520c-134">Go to the admin center at <https://admin.microsoft.com>, and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="9520c-135">[ **メールフロー** ] カテゴリで、[ **ルール** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-135">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="9520c-136">[] を選択し **+** 、[ **新しいルールを作成する** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-136">Select **+** , and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="9520c-137">ダイアログボックスの下部にある [ **その他のオプション** ] を選択すると、オプションの完全なセットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9520c-137">Select **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="9520c-138">ルールの次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="9520c-138">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="9520c-139">その他の設定を変更しない場合は、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="9520c-139">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="9520c-140">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-140">Select **Save**.</span></span>

|<span data-ttu-id="9520c-141">設定</span><span class="sxs-lookup"><span data-stu-id="9520c-141">Setting</span></span>|<span data-ttu-id="9520c-142">Office ファイルの添付ファイルを開く前にユーザーに警告を発する</span><span class="sxs-lookup"><span data-stu-id="9520c-142">Warn users before opening attachments of Office files</span></span>||
|---|---|---|
|<span data-ttu-id="9520c-143">名前</span><span class="sxs-lookup"><span data-stu-id="9520c-143">Name</span></span>|<span data-ttu-id="9520c-144">ランサムウェア対策ルール: ユーザーに警告を発する</span><span class="sxs-lookup"><span data-stu-id="9520c-144">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="9520c-145">このルールを適用する条件</span><span class="sxs-lookup"><span data-stu-id="9520c-145">Apply this rule if .</span></span> <span data-ttu-id="9520c-146">.</span><span class="sxs-lookup"><span data-stu-id="9520c-146">.</span></span> <span data-ttu-id="9520c-147">.</span><span class="sxs-lookup"><span data-stu-id="9520c-147">.</span></span>|<span data-ttu-id="9520c-148">任意の添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="9520c-148">Any attachment .</span></span> <span data-ttu-id="9520c-149">.</span><span class="sxs-lookup"><span data-stu-id="9520c-149">.</span></span> <span data-ttu-id="9520c-150">.</span><span class="sxs-lookup"><span data-stu-id="9520c-150">.</span></span> <span data-ttu-id="9520c-151">ファイル拡張子が一致する。</span><span class="sxs-lookup"><span data-stu-id="9520c-151">file extension matches .</span></span> <span data-ttu-id="9520c-152">.</span><span class="sxs-lookup"><span data-stu-id="9520c-152">.</span></span> <span data-ttu-id="9520c-153">.</span><span class="sxs-lookup"><span data-stu-id="9520c-153">.</span></span>|
|<span data-ttu-id="9520c-154">単語または語句を指定する</span><span class="sxs-lookup"><span data-stu-id="9520c-154">Specify words or phrases</span></span>|<span data-ttu-id="9520c-155">次のファイルの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="9520c-155">Add these file types:</span></span>  <br/> <span data-ttu-id="9520c-156">normal.dotm、.docm、.xlsm、sltm、.xla、xlam、xll、pptm、potm、ppam、pptm、sldm</span><span class="sxs-lookup"><span data-stu-id="9520c-156">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>|
|<span data-ttu-id="9520c-157">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9520c-157">Do the following .</span></span> <span data-ttu-id="9520c-158">.</span><span class="sxs-lookup"><span data-stu-id="9520c-158">.</span></span> <span data-ttu-id="9520c-159">.</span><span class="sxs-lookup"><span data-stu-id="9520c-159">.</span></span>|<span data-ttu-id="9520c-160">受信者にメッセージで通知します。</span><span class="sxs-lookup"><span data-stu-id="9520c-160">Notify the recipient with a message</span></span>|
|<span data-ttu-id="9520c-161">メッセージテキストを指定する</span><span class="sxs-lookup"><span data-stu-id="9520c-161">Provide message text</span></span>|<span data-ttu-id="9520c-162">これらの種類のファイルは、悪意のあるコードを含むマクロを含んでいる可能性があるため、知られていないユーザーから開かないでください。</span><span class="sxs-lookup"><span data-stu-id="9520c-162">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="9520c-163">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-163">For more information, see:</span></span>

- [<span data-ttu-id="9520c-164">ランサムウェア: リスクを軽減する方法</span><span class="sxs-lookup"><span data-stu-id="9520c-164">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="9520c-165">OneDrive を復元する</span><span class="sxs-lookup"><span data-stu-id="9520c-165">Restore your OneDrive</span></span>](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="9520c-166">電子メールの自動転送を停止する</span><span class="sxs-lookup"><span data-stu-id="9520c-166">Stop auto-forwarding for email</span></span>

<span data-ttu-id="9520c-167">ユーザーのメールボックスにアクセスできるハッカーは、メールボックスを自動的に転送するようにメールボックスを設定することにより、メールを盗むことができます。</span><span class="sxs-lookup"><span data-stu-id="9520c-167">Hackers who gain access to a user's mailbox can steal mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="9520c-168">これは、ユーザーの認識なしでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9520c-168">This can happen even without the user's awareness.</span></span> <span data-ttu-id="9520c-169">この問題が発生しないようにするには、メールフロールールを構成します。</span><span class="sxs-lookup"><span data-stu-id="9520c-169">To prevent this from happening, configure a mail flow rule.</span></span>

<span data-ttu-id="9520c-170">メールトランスポートルールを作成するには、 [この短いビデオ](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) を見るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9520c-170">To create a mail transport rule, either watch [this short video](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="9520c-171">Microsoft 365 管理センターで、[ **管理センター** Exchange] を選択し \> **Exchange** ます。</span><span class="sxs-lookup"><span data-stu-id="9520c-171">In the Microsoft 365 admin center, select **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="9520c-172">[ **メールフロー** ] カテゴリで、[ **ルール** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-172">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="9520c-173">[] を選択し **+** 、[ **新しいルールを作成する** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-173">Select **+** , and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="9520c-174">すべてのオプションを表示するには、ダイアログボックスの下部にある [ **その他のオプション** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-174">To see all the options, select **More options** at the bottom of the dialog box.</span></span>

5. <span data-ttu-id="9520c-175">次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="9520c-175">Apply the settings in the following table.</span></span> <span data-ttu-id="9520c-176">その他の設定を変更しない場合は、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="9520c-176">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="9520c-177">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-177">Select **Save**.</span></span>

|<span data-ttu-id="9520c-178">設定</span><span class="sxs-lookup"><span data-stu-id="9520c-178">Setting</span></span>|<span data-ttu-id="9520c-179">Office ファイルの添付ファイルを開く前にユーザーに警告を発する</span><span class="sxs-lookup"><span data-stu-id="9520c-179">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="9520c-180">名前</span><span class="sxs-lookup"><span data-stu-id="9520c-180">Name</span></span>|<span data-ttu-id="9520c-181">外部ドメインへの電子メールの自動転送を禁止する</span><span class="sxs-lookup"><span data-stu-id="9520c-181">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="9520c-182">次の場合にこのルールを適用する...</span><span class="sxs-lookup"><span data-stu-id="9520c-182">Apply this rule if ...</span></span>|<span data-ttu-id="9520c-183">送信者。</span><span class="sxs-lookup"><span data-stu-id="9520c-183">The sender .</span></span> <span data-ttu-id="9520c-184">.</span><span class="sxs-lookup"><span data-stu-id="9520c-184">.</span></span> <span data-ttu-id="9520c-185">.</span><span class="sxs-lookup"><span data-stu-id="9520c-185">.</span></span> <span data-ttu-id="9520c-186">外部/内部。</span><span class="sxs-lookup"><span data-stu-id="9520c-186">is external/internal .</span></span> <span data-ttu-id="9520c-187">.</span><span class="sxs-lookup"><span data-stu-id="9520c-187">.</span></span> <span data-ttu-id="9520c-188">.</span><span class="sxs-lookup"><span data-stu-id="9520c-188">.</span></span> <span data-ttu-id="9520c-189">組織内</span><span class="sxs-lookup"><span data-stu-id="9520c-189">Inside the organization</span></span>|
|<span data-ttu-id="9520c-190">条件を追加する</span><span class="sxs-lookup"><span data-stu-id="9520c-190">Add condition</span></span>|<span data-ttu-id="9520c-191">メッセージのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="9520c-191">The message properties .</span></span> <span data-ttu-id="9520c-192">.</span><span class="sxs-lookup"><span data-stu-id="9520c-192">.</span></span> <span data-ttu-id="9520c-193">.</span><span class="sxs-lookup"><span data-stu-id="9520c-193">.</span></span> <span data-ttu-id="9520c-194">メッセージの種類を含めます。</span><span class="sxs-lookup"><span data-stu-id="9520c-194">include the message type .</span></span> <span data-ttu-id="9520c-195">.</span><span class="sxs-lookup"><span data-stu-id="9520c-195">.</span></span> <span data-ttu-id="9520c-196">.</span><span class="sxs-lookup"><span data-stu-id="9520c-196">.</span></span> <span data-ttu-id="9520c-197">自動転送</span><span class="sxs-lookup"><span data-stu-id="9520c-197">Auto-forward</span></span>|
|<span data-ttu-id="9520c-198">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9520c-198">Do the following ...</span></span>|<span data-ttu-id="9520c-199">[メッセージをブロックする。</span><span class="sxs-lookup"><span data-stu-id="9520c-199">Block the message .</span></span> <span data-ttu-id="9520c-200">.</span><span class="sxs-lookup"><span data-stu-id="9520c-200">.</span></span> <span data-ttu-id="9520c-201">.</span><span class="sxs-lookup"><span data-stu-id="9520c-201">.</span></span> <span data-ttu-id="9520c-202">メッセージを拒否し、説明を含めます。</span><span class="sxs-lookup"><span data-stu-id="9520c-202">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="9520c-203">メッセージテキストを指定する</span><span class="sxs-lookup"><span data-stu-id="9520c-203">Provide message text</span></span>|<span data-ttu-id="9520c-204">この組織外の電子メールの自動転送は、セキュリティ上の理由から禁止されています。</span><span class="sxs-lookup"><span data-stu-id="9520c-204">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="9520c-205">フィッシング攻撃からメールを保護する</span><span class="sxs-lookup"><span data-stu-id="9520c-205">Protect your email from phishing attacks</span></span>

<span data-ttu-id="9520c-206">Office 365 または Microsoft 365 環境用に1つ以上のカスタムドメインを構成した場合は、対象となるフィッシング対策保護を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9520c-206">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="9520c-207">Microsoft Defender for Office 365 の一部のフィッシング対策保護は、悪意のある偽造ベースのフィッシング攻撃やその他のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9520c-207">Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="9520c-208">カスタムドメインを構成していない場合は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9520c-208">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="9520c-209">最も重要なユーザーとカスタムドメインを保護するためのポリシーを作成して、この保護を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9520c-209">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="9520c-210">Microsoft Defender for Office 365 でフィッシング対策ポリシーを作成するには、  [この短いトレーニングビデオ](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)を見るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9520c-210">To create an anti-phishing policy in Microsoft Defender for Office 365, watch  [this short training video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="9520c-211">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="9520c-211">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="9520c-212">セキュリティ &amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[ **脅威の管理** ] の下にある [ **ポリシー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-212">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management** , choose **Policy**.</span></span>

3. <span data-ttu-id="9520c-213">[ **ポリシー** ] ページで、[ **フィッシング対策** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-213">On the **Policy** page, choose **Anti-phishing**.</span></span>

4. <span data-ttu-id="9520c-214">[ **フィッシング対策** ] ページで、[ **+ 作成** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-214">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="9520c-215">ウィザードが起動して、フィッシング対策ポリシーを定義する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9520c-215">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="9520c-216">次の表で推奨されているとおりに、ポリシーの名前、説明、および設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="9520c-216">Specify the name, description, and settings for your policy as recommended in the following table.</span></span> <span data-ttu-id="9520c-217">詳細については、「 [Microsoft Defender For Office 365 のオプション」の「フィッシング対策ポリシーについ](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-217">For more details, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>

6. <span data-ttu-id="9520c-218">設定を確認した後、必要に応じて [ **このポリシーを作成** する] または [ **保存** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-218">After you've reviewed your settings, choose **Create this policy** or **Save** , as appropriate.</span></span>

|<span data-ttu-id="9520c-219">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="9520c-219">Setting or option</span></span>|<span data-ttu-id="9520c-220">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="9520c-220">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="9520c-221">名前</span><span class="sxs-lookup"><span data-stu-id="9520c-221">Name</span></span>|<span data-ttu-id="9520c-222">ドメインおよび最も重要なキャンペーンスタッフ</span><span class="sxs-lookup"><span data-stu-id="9520c-222">Domain and most valuable campaign staff</span></span>|
|<span data-ttu-id="9520c-223">説明</span><span class="sxs-lookup"><span data-stu-id="9520c-223">Description</span></span>|<span data-ttu-id="9520c-224">最も重要なスタッフとドメインが偽装されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9520c-224">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="9520c-225">保護対象のユーザーの追加</span><span class="sxs-lookup"><span data-stu-id="9520c-225">Add users to protect</span></span>|<span data-ttu-id="9520c-226">[ **+ 条件の追加** ] を選択すると、受信者はになります。</span><span class="sxs-lookup"><span data-stu-id="9520c-226">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="9520c-227">ユーザー名を入力するか、候補、キャンペーンマネージャー、およびその他の重要なスタッフメンバーの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="9520c-227">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="9520c-228">偽装から保護する内部および外部アドレスを最大20個まで追加できます。</span><span class="sxs-lookup"><span data-stu-id="9520c-228">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="9520c-229">保護対象のドメインの追加</span><span class="sxs-lookup"><span data-stu-id="9520c-229">Add domains to protect</span></span>|<span data-ttu-id="9520c-230">[ **+ 条件を追加する] を選択すると、受信者のドメインは** になります。</span><span class="sxs-lookup"><span data-stu-id="9520c-230">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="9520c-231">Microsoft 365 サブスクリプションに関連付けられているカスタムドメインを入力します (定義されている場合)。</span><span class="sxs-lookup"><span data-stu-id="9520c-231">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="9520c-232">複数のドメインを入力できます。</span><span class="sxs-lookup"><span data-stu-id="9520c-232">You can enter more than one domain.</span></span>|
|<span data-ttu-id="9520c-233">処理の選択</span><span class="sxs-lookup"><span data-stu-id="9520c-233">Choose actions</span></span>|<span data-ttu-id="9520c-234">偽装ユーザーによって電子メールが送信される場合: [ **メッセージを別の電子メールアドレスにリダイレクトする** ] を選択し、セキュリティ管理者の電子メールアドレスを入力します。たとえば、 *Alice は <span> <span> @contoso .com* のようになります。</span><span class="sxs-lookup"><span data-stu-id="9520c-234">If email is sent by an impersonated user: Choose **Redirect message to another email address** , and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <span data-ttu-id="9520c-235">メールが偽装ドメインによって送信されている場合: **[メッセージを検疫]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-235">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="9520c-236">メールボックス インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="9520c-236">Mailbox intelligence</span></span>|<span data-ttu-id="9520c-237">既定では、新しいフィッシング対策ポリシーの作成時にはメールボックス インテリジェンスが選択されています。</span><span class="sxs-lookup"><span data-stu-id="9520c-237">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="9520c-238">最適な結果が得られるように、この設定は **[オン]** のままにしておいてください。</span><span class="sxs-lookup"><span data-stu-id="9520c-238">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="9520c-239">信頼できる送信者とドメインの追加</span><span class="sxs-lookup"><span data-stu-id="9520c-239">Add trusted senders and domains</span></span>|<span data-ttu-id="9520c-240">ここでは、独自のドメインまたは他の信頼されたドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9520c-240">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="9520c-241">適用先</span><span class="sxs-lookup"><span data-stu-id="9520c-241">Applied to</span></span>|<span data-ttu-id="9520c-242">**[受信者のドメインが次の場合]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-242">Select **The recipient domain is**.</span></span> <span data-ttu-id="9520c-243">**[これらのいずれか]** では、 **[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-243">Under **Any of these** , select **Choose**.</span></span> <span data-ttu-id="9520c-244">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-244">Select **+ Add**.</span></span> <span data-ttu-id="9520c-245">ドメインの名前の横にあるチェックボックスをオンにします (例: *contoso)。 <span> <span>[com* ] の一覧で、[ **追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-245">Select the check box next to the name of the domain, for example, *contoso.<span><span>com* , in the list, and then select **Add**.</span></span> <span data-ttu-id="9520c-246">[ **完了** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-246">Select **Done**.</span></span>|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a><span data-ttu-id="9520c-247">安全な添付ファイルを含む悪意のある添付ファイルやファイルから保護する</span><span class="sxs-lookup"><span data-stu-id="9520c-247">Protect against malicious attachments and files with Safe Attachments</span></span>

<span data-ttu-id="9520c-248">ユーザーは、ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを日常的に送信、受信、共有します。</span><span class="sxs-lookup"><span data-stu-id="9520c-248">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="9520c-249">電子メールメッセージを見るだけで、添付ファイルが安全か悪意かを知ることは常に容易ではありません。</span><span class="sxs-lookup"><span data-stu-id="9520c-249">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="9520c-250">Microsoft Defender for Office 365 には安全な添付ファイルによる保護が含まれていますが、この保護は既定では有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="9520c-250">Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="9520c-251">この保護の使用を開始するには、新しいルールを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9520c-251">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="9520c-252">この保護は、SharePoint、OneDrive、Microsoft Teams のファイルにまで及びます。</span><span class="sxs-lookup"><span data-stu-id="9520c-252">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="9520c-253">安全添付ファイルポリシーを作成するには、 [この短いビデオ](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)を見るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9520c-253">To create an Safe Attachment policy, either watch [this short video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="9520c-254">に移動 [https://protection.office.com](https://protection.office.com) し、管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9520c-254">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="9520c-255">セキュリティ &amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[ **脅威の管理** ] の下にある [ **ポリシー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-255">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management** , choose **Policy**.</span></span>

3. <span data-ttu-id="9520c-256">[ポリシー] ページで、[ **安全な添付ファイル** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-256">On the Policy page, choose **Safe Attachments**.</span></span>

4. <span data-ttu-id="9520c-257">[安全な添付ファイル] ページで、[ **SharePoint、OneDrive、Microsoft Teams 用の ATP を有効** にする] チェックボックスをオンにして、この保護を広く適用します。</span><span class="sxs-lookup"><span data-stu-id="9520c-257">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="9520c-258">**+** 新しいポリシーを作成する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-258">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="9520c-259">次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="9520c-259">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="9520c-260">設定を確認した後、必要に応じて [ **このポリシーを作成** する] または [ **保存** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-260">After you have reviewed your settings, choose **Create this policy** or **Save** , as appropriate.</span></span>

|<span data-ttu-id="9520c-261">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="9520c-261">Setting or option</span></span>|<span data-ttu-id="9520c-262">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="9520c-262">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="9520c-263">名前</span><span class="sxs-lookup"><span data-stu-id="9520c-263">Name</span></span>|<span data-ttu-id="9520c-264">検出されたマルウェアを含む現在および今後の電子メールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="9520c-264">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="9520c-265">説明</span><span class="sxs-lookup"><span data-stu-id="9520c-265">Description</span></span>|<span data-ttu-id="9520c-266">検出されたマルウェアを含む、現在および今後の電子メールと添付ファイルをブロックする。</span><span class="sxs-lookup"><span data-stu-id="9520c-266">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="9520c-267">添付ファイルの保存に関する不明なマルウェア応答</span><span class="sxs-lookup"><span data-stu-id="9520c-267">Save attachments unknown malware response</span></span>|<span data-ttu-id="9520c-268">**検出されたマルウェアを含む現在および今後の電子メールと添付ファイルをブロックする** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-268">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="9520c-269">検出時に添付ファイルをリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="9520c-269">Redirect attachment on detection</span></span>|<span data-ttu-id="9520c-270">リダイレクトを有効にする (このボックスをオンにする) 管理者アカウントまたは検疫用のメールボックスのセットアップを入力します。</span><span class="sxs-lookup"><span data-stu-id="9520c-270">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="9520c-271">マルウェアスキャンによる添付ファイルのタイムアウトまたはエラーが発生した場合は、上記の選択を適用します (このチェックボックスをオンにします)。</span><span class="sxs-lookup"><span data-stu-id="9520c-271">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="9520c-272">適用先</span><span class="sxs-lookup"><span data-stu-id="9520c-272">Applied to</span></span>|<span data-ttu-id="9520c-273">受信者のドメインはです。</span><span class="sxs-lookup"><span data-stu-id="9520c-273">The recipient domain is .</span></span> <span data-ttu-id="9520c-274">.</span><span class="sxs-lookup"><span data-stu-id="9520c-274">.</span></span> <span data-ttu-id="9520c-275">.</span><span class="sxs-lookup"><span data-stu-id="9520c-275">.</span></span> <span data-ttu-id="9520c-276">ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="9520c-276">select your domain.</span></span>|

<span data-ttu-id="9520c-277">詳細については、「 [office 365 の Microsoft Defender でマルウェア対策ポリシーをセットアップする](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-277">For more information, see [Set up anti-phishing policies in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-anti-phishing-policies).</span></span>

## <a name="protect-against-phishing-attacks-with-safe-links"></a><span data-ttu-id="9520c-278">安全なリンクによるフィッシング攻撃から保護する</span><span class="sxs-lookup"><span data-stu-id="9520c-278">Protect against phishing attacks with Safe Links</span></span>

<span data-ttu-id="9520c-279">ハッカーは、電子メールやその他のファイル内のリンクに悪意のある web サイトを表示しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="9520c-279">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="9520c-280">「安全なリンク」は、Microsoft Defender for Office 365 の一部であり、電子メールメッセージや Office ドキュメント内の web アドレス (Url) をクリックすると、組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9520c-280">Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="9520c-281">保護は、安全なリンクのポリシーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="9520c-281">Protection is defined through Safe Links policies.</span></span>

<span data-ttu-id="9520c-282">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9520c-282">We recommend that you do the following:</span></span>

- <span data-ttu-id="9520c-283">既定のポリシーを変更して、保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="9520c-283">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="9520c-284">ドメイン内のすべての受信者を対象とした新しいポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9520c-284">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="9520c-285">安全なリンクを設定するには、 [この短いトレーニングビデオ](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)を見るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9520c-285">To set up Safe Links, watch [this short training video](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="9520c-286">に移動 [https://protection.office.com](https://protection.office.com) し、管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="9520c-286">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="9520c-287">セキュリティ &amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[ **脅威の管理** ] の下にある [ **ポリシー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-287">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management** , choose **Policy**.</span></span>

3. <span data-ttu-id="9520c-288">[ポリシー] ページで、[ **安全なリンク** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-288">On the Policy page, choose **Safe Links**.</span></span>

<span data-ttu-id="9520c-289">既定のポリシーを変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9520c-289">To modify the default policy:</span></span>

1. <span data-ttu-id="9520c-290">[安全なリンク] ページの [ **組織全体に適用されるポリシー** ] で、[ **既定** のポリシー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-290">On the Safe links page, under **Policies that apply to the entire organization** , select the **Default** policy.</span></span>

2. <span data-ttu-id="9520c-291">[ **電子メール以外のコンテンツに適用する設定** ] で、[ **Microsoft 365 Apps for enterprise]、[Office for IOS、および Android** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-291">Under **Settings that apply to content except email** , select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="9520c-292">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-292">Select **Save**.</span></span>

<span data-ttu-id="9520c-293">ドメイン内のすべての受信者を対象とした新しいポリシーを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9520c-293">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="9520c-294">[安全なリンク] ページの [ **組織全体に適用されるポリシー** ] で、[ **+** 新しいポリシーの作成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-294">On the Safe links page, under **Policies that apply to the entire organization** , select **+** to create a new policy.</span></span>

2. <span data-ttu-id="9520c-295">次の表に示す設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="9520c-295">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="9520c-296">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-296">Select **Save**.</span></span>

|<span data-ttu-id="9520c-297">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="9520c-297">Setting or option</span></span>|<span data-ttu-id="9520c-298">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="9520c-298">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="9520c-299">名前</span><span class="sxs-lookup"><span data-stu-id="9520c-299">Name</span></span>|<span data-ttu-id="9520c-300">ドメイン内のすべての受信者に対する安全なリンクポリシー</span><span class="sxs-lookup"><span data-stu-id="9520c-300">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="9520c-301">メッセージ内の不明な潜在的な悪意のある Url に対するアクションを選択する</span><span class="sxs-lookup"><span data-stu-id="9520c-301">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="9520c-302">[オン] を選択すると **、ユーザーがリンクをクリックしたときに、既知の悪意のあるリンクの一覧に対して、url が書き換えられ、チェックされ** ます。</span><span class="sxs-lookup"><span data-stu-id="9520c-302">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="9520c-303">安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする</span><span class="sxs-lookup"><span data-stu-id="9520c-303">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="9520c-304">このボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9520c-304">Select this box.</span></span>|
|<span data-ttu-id="9520c-305">適用先</span><span class="sxs-lookup"><span data-stu-id="9520c-305">Applied to</span></span>|<span data-ttu-id="9520c-306">受信者のドメインはです。</span><span class="sxs-lookup"><span data-stu-id="9520c-306">The recipient domain is .</span></span> <span data-ttu-id="9520c-307">.</span><span class="sxs-lookup"><span data-stu-id="9520c-307">.</span></span> <span data-ttu-id="9520c-308">.</span><span class="sxs-lookup"><span data-stu-id="9520c-308">.</span></span> <span data-ttu-id="9520c-309">ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="9520c-309">select your domain.</span></span>|

<span data-ttu-id="9520c-310">詳細については、「 [安全なリンク](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-310">For more information, see [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="9520c-311">Intune 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="9520c-311">Go to Intune admin center</span></span>

1. <span data-ttu-id="9520c-312">[Azure portal](https://portal.azure.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="9520c-312">Sign in to [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="9520c-313">[ **すべてのサービス** ] を選択し、 **検索ボックス** に「 *Intune* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9520c-313">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="9520c-314">結果が表示されたら、 **Microsoft Intune** の横にある [開始] を選択して、後で見つけやすいようにします。</span><span class="sxs-lookup"><span data-stu-id="9520c-314">Once the results appear, select the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="9520c-315">管理センターに加えて、Intune を使用して組織のデバイスを登録および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="9520c-315">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="9520c-316">詳細については、「 [Windows デバイスの登録方法](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) 」および「 [Intune によって管理されるデバイスの登録オプション](https://docs.microsoft.com/intune/enrollment-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9520c-316">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment/enrollment-method-capab) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>
