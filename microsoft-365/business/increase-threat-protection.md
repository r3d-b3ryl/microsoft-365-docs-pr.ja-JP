---
title: Microsoft 365 for Business の脅威保護を強化する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Microsoft Defender for Office 365 を設定し、フィッシング、マルウェア、その他の脅威から機密データを保護します。
ms.openlocfilehash: 8fb2c3881876cabea6d8907a85bc9397212126dc
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580196"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="a0fcf-103">驚異の保護を強化する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-103">Increase threat protection</span></span>

<span data-ttu-id="a0fcf-104">この記事は、フィッシング、マルウェア、その他の脅威から保護するために、Microsoft 365 サブスクリプションの保護を強化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="a0fcf-105">これらの推奨事項は、法律事務所や医療クリニックなど、セキュリティの必要性が高い組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-105">These recommendations are appropriate for organizations with an increased need for security, like law offices and health care clinics.</span></span>

<span data-ttu-id="a0fcf-106">開始する前に、365 Secure Score Officeを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="a0fcf-107">Office 365 Secure Score は、通常のアクティビティとセキュリティ設定に基づいて組織のセキュリティを分析し、スコアを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-107">Office 365 Secure Score analyzes your organization's security based on your regular activities and security settings, and assigns a score.</span></span> <span data-ttu-id="a0fcf-108">まず、現在のスコアをメモします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="a0fcf-109">スコアを上げするには、この記事で推奨されるアクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-109">To increase your score, complete the actions recommended in this article.</span></span> <span data-ttu-id="a0fcf-110">目標は、最大スコアを達成するのではなく、ユーザーの生産性に悪影響を及ぼしない環境を保護する機会を認識する方法です。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-110">The goal isn't to achieve the maximum score, but to be aware of opportunities to protect your environment that don't negatively affect productivity for your users.</span></span>

<span data-ttu-id="a0fcf-111">詳細については [、「Microsoft Secure Score」を参照してください](../security/defender/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-111">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="a0fcf-112">メール内のマルウェアに対する保護のレベルを上げる</span><span class="sxs-lookup"><span data-stu-id="a0fcf-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="a0fcf-113">365 Office Microsoft 365 環境には、マルウェアに対する保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-113">Your Office 365 or Microsoft 365 environment includes protection against malware.</span></span> <span data-ttu-id="a0fcf-114">マルウェアに一般的に使用されるファイルの種類を含む添付ファイルをブロックすることで、この保護を強化できます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-114">You can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="a0fcf-115">電子メールのマルウェア保護を強化するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-115">To increase malware protection in email:</span></span>

1. <span data-ttu-id="a0fcf-116">管理者アカウント [https://protection.office.com](https://protection.office.com) の資格情報に移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-116">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span>

2. <span data-ttu-id="a0fcf-117">セキュリティ コンプライアンス センターの左側のナビゲーション ウィンドウの [脅威の管理] で、[ポリシー &amp; マルウェア対策 **]**  \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-117">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>

3. <span data-ttu-id="a0fcf-118">既定のポリシーをダブルクリックして、この会社全体のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-118">Double-click the default policy to edit this company-wide policy.</span></span>

4. <span data-ttu-id="a0fcf-119">[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-119">Select **Settings**.</span></span>

5. <span data-ttu-id="a0fcf-120">[共通 **の添付ファイルの種類フィルター] で**、[オン] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-120">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="a0fcf-121">ブロックされているファイルの種類は、このコントロールの直下のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-121">The file types that are blocked are listed in the window directly below this control.</span></span> <span data-ttu-id="a0fcf-122">次のファイルの種類を追加してください。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-122">Make sure that you add these file types:</span></span>

   `ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif`

   <span data-ttu-id="a0fcf-123">必要に応じて、後でファイルの種類を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-123">If necessary, you can add or delete file types later.</span></span>

6. <span data-ttu-id="a0fcf-124">[保存] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="a0fcf-124">Select **Save.**</span></span>

<span data-ttu-id="a0fcf-125">詳細については [、「EOP でのマルウェア対策保護」を参照してください](../security/office-365-security/anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-125">For more information, see [Anti-malware protection in EOP](../security/office-365-security/anti-malware-protection.md).</span></span>

## <a name="protect-against-ransomware"></a><span data-ttu-id="a0fcf-126">ランサムウェアから保護する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-126">Protect against ransomware</span></span>

<span data-ttu-id="a0fcf-127">ランサムウェアは、ファイルを暗号化するか、コンピューター画面をロックすることで、データへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="a0fcf-128">その後、データへのアクセスと引き換えに、通常はBitcoinのような暗号化の形で「身代金」を求め、被害者から金銭を強要しようとする。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-128">It then attempts to extort money from victims by asking for "ransom," usually in the form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span>

<span data-ttu-id="a0fcf-129">ランサムウェアから保護するには、1 つ以上のメール フロー ルールを作成して、ランサムウェアに一般的に使用されるファイル拡張子をブロックします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-129">To protect against ransomware, create one or more mail flow rules to block file extensions that are commonly used for ransomware.</span></span> <span data-ttu-id="a0fcf-130">(メール ステップでマルウェアに対する保護レベルを上げる段階で、これらの [ルールを追加](#raise-the-level-of-protection-against-malware-in-mail) しました。また、電子メールでこれらの添付ファイルを受け取ったユーザーに警告することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-130">(You added these rules in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step.) You can also warn users who receive these attachments in email.</span></span>

<span data-ttu-id="a0fcf-131">前の手順でブロックしたファイルに加えて、マクロを含む Office ファイル添付ファイルを開く前に、ユーザーに警告するルールを作成することをお試しください。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-131">In addition to the files that you blocked in the previous step, it's a good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="a0fcf-132">ランサムウェアはマクロ内に隠される可能性があります。そのため、ユーザーに知らない人からこれらのファイルを開かされないように警告します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-132">Ransomware can be hidden inside macros, so warn users not to open these files from people they don't know.</span></span>

<span data-ttu-id="a0fcf-133">メール トランスポート ルールを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-133">To create a mail transport rule:</span></span>

1. <span data-ttu-id="a0fcf-134">で管理センターに移動し <https://admin.microsoft.com> 、[管理センター Exchange] **を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-134">Go to the admin center at <https://admin.microsoft.com>, and choose **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="a0fcf-135">メール フロー **カテゴリで、[** ルール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-135">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="a0fcf-136">を **+** 選択し、[新しい **ルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-136">Select **+**, and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="a0fcf-137">ダイアログ **ボックスの下部** にある [その他のオプション] を選択して、オプションの完全なセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-137">Select **More options** at the bottom of the dialog box to see the full set of options.</span></span>

5. <span data-ttu-id="a0fcf-138">ルールの次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-138">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="a0fcf-139">設定を変更しない限り、残りの設定の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-139">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="a0fcf-140">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-140">Select **Save**.</span></span>

|<span data-ttu-id="a0fcf-141">設定</span><span class="sxs-lookup"><span data-stu-id="a0fcf-141">Setting</span></span>|<span data-ttu-id="a0fcf-142">ファイルの添付ファイルを開く前にユーザーにOfficeする</span><span class="sxs-lookup"><span data-stu-id="a0fcf-142">Warn users before opening attachments of Office files</span></span>||
|---|---|---|
|<span data-ttu-id="a0fcf-143">名前</span><span class="sxs-lookup"><span data-stu-id="a0fcf-143">Name</span></span>|<span data-ttu-id="a0fcf-144">ランサムウェア対策ルール: ユーザーに警告する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-144">Anti-ransomware rule: warn users</span></span>|
|<span data-ttu-id="a0fcf-145">場合は、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-145">Apply this rule if .</span></span> <span data-ttu-id="a0fcf-146">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-146">.</span></span> <span data-ttu-id="a0fcf-147">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-147">.</span></span>|<span data-ttu-id="a0fcf-148">任意の添付ファイル 。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-148">Any attachment .</span></span> <span data-ttu-id="a0fcf-149">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-149">.</span></span> <span data-ttu-id="a0fcf-150">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-150">.</span></span> <span data-ttu-id="a0fcf-151">ファイル拡張子が一致します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-151">file extension matches .</span></span> <span data-ttu-id="a0fcf-152">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-152">.</span></span> <span data-ttu-id="a0fcf-153">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-153">.</span></span>|
|<span data-ttu-id="a0fcf-154">単語または語句を指定する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-154">Specify words or phrases</span></span>|<span data-ttu-id="a0fcf-155">次のファイルの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-155">Add these file types:</span></span>  <br/> <span data-ttu-id="a0fcf-156">dotm、docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm</span><span class="sxs-lookup"><span data-stu-id="a0fcf-156">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>|
|<span data-ttu-id="a0fcf-157">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-157">Do the following .</span></span> <span data-ttu-id="a0fcf-158">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-158">.</span></span> <span data-ttu-id="a0fcf-159">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-159">.</span></span>|<span data-ttu-id="a0fcf-160">受信者にメッセージで通知します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-160">Notify the recipient with a message</span></span>|
|<span data-ttu-id="a0fcf-161">メッセージ テキストを提供する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-161">Provide message text</span></span>|<span data-ttu-id="a0fcf-162">これらの種類のファイルは、悪意のあるコードを含むマクロが含まれている可能性があるから、知らない人から開かれません。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-162">Do not open these types of files from people you do not know because they might contain macros with malicious code.</span></span>|

<span data-ttu-id="a0fcf-163">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-163">For more information, see:</span></span>

- [<span data-ttu-id="a0fcf-164">ランサムウェア: リスクを軽減する方法</span><span class="sxs-lookup"><span data-stu-id="a0fcf-164">Ransomware: how to reduce risk</span></span>](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [<span data-ttu-id="a0fcf-165">OneDrive を復元する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-165">Restore your OneDrive</span></span>](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)

## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="a0fcf-166">電子メールの自動転送を停止する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-166">Stop auto-forwarding for email</span></span>

<span data-ttu-id="a0fcf-167">ユーザーのメールボックスにアクセスするハッカーは、メールを自動的に転送するメールボックスを設定することでメールを盗む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-167">Hackers who gain access to a user's mailbox can steal mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="a0fcf-168">これは、ユーザーの認識がなくても発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-168">This can happen even without the user's awareness.</span></span> <span data-ttu-id="a0fcf-169">これを防止するには、メール フロー ルールを構成します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-169">To prevent this from happening, configure a mail flow rule.</span></span>

<span data-ttu-id="a0fcf-170">メール トランスポート ルールを作成するには、この短い [ビデオを見](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-170">To create a mail transport rule, either watch [this short video](https://support.microsoft.com/office/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>

1. <span data-ttu-id="a0fcf-171">Microsoft 365 管理センターで、[管理センター] \> **[Exchange] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-171">In the Microsoft 365 admin center, select **Admin centers** \> **Exchange**.</span></span>

2. <span data-ttu-id="a0fcf-172">メール フロー **カテゴリで、[** ルール] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-172">In the **mail flow** category, select **rules**.</span></span>

3. <span data-ttu-id="a0fcf-173">を **+** 選択し、[新しい **ルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-173">Select **+**, and then select **Create a new rule**.</span></span>

4. <span data-ttu-id="a0fcf-174">すべてのオプションを表示するには、ダイアログ ボックスの下部 **にある** [その他のオプション] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-174">To see all the options, select **More options** at the bottom of the dialog box.</span></span>

5. <span data-ttu-id="a0fcf-175">次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-175">Apply the settings in the following table.</span></span> <span data-ttu-id="a0fcf-176">設定を変更しない限り、残りの設定の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-176">Use the default values for the rest of the settings, unless you want to change them.</span></span>

6. <span data-ttu-id="a0fcf-177">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-177">Select **Save**.</span></span>

|<span data-ttu-id="a0fcf-178">設定</span><span class="sxs-lookup"><span data-stu-id="a0fcf-178">Setting</span></span>|<span data-ttu-id="a0fcf-179">ファイルの添付ファイルを開く前にユーザーにOfficeする</span><span class="sxs-lookup"><span data-stu-id="a0fcf-179">Warn users before opening attachments of Office files</span></span>|
|---|---|
|<span data-ttu-id="a0fcf-180">名前</span><span class="sxs-lookup"><span data-stu-id="a0fcf-180">Name</span></span>|<span data-ttu-id="a0fcf-181">外部ドメインへの電子メールの自動転送を防止する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-181">Prevent auto forwarding of email to external domains</span></span>|
|<span data-ttu-id="a0fcf-182">... の場合は、このルールを適用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-182">Apply this rule if ...</span></span>|<span data-ttu-id="a0fcf-183">送信者 。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-183">The sender .</span></span> <span data-ttu-id="a0fcf-184">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-184">.</span></span> <span data-ttu-id="a0fcf-185">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-185">.</span></span> <span data-ttu-id="a0fcf-186">は外部/内部です。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-186">is external/internal .</span></span> <span data-ttu-id="a0fcf-187">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-187">.</span></span> <span data-ttu-id="a0fcf-188">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-188">.</span></span> <span data-ttu-id="a0fcf-189">組織内</span><span class="sxs-lookup"><span data-stu-id="a0fcf-189">Inside the organization</span></span>|
|<span data-ttu-id="a0fcf-190">条件の追加</span><span class="sxs-lookup"><span data-stu-id="a0fcf-190">Add condition</span></span>|<span data-ttu-id="a0fcf-191">メッセージのプロパティ 。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-191">The message properties .</span></span> <span data-ttu-id="a0fcf-192">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-192">.</span></span> <span data-ttu-id="a0fcf-193">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-193">.</span></span> <span data-ttu-id="a0fcf-194">メッセージの種類を含める。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-194">include the message type .</span></span> <span data-ttu-id="a0fcf-195">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-195">.</span></span> <span data-ttu-id="a0fcf-196">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-196">.</span></span> <span data-ttu-id="a0fcf-197">自動転送</span><span class="sxs-lookup"><span data-stu-id="a0fcf-197">Auto-forward</span></span>|
|<span data-ttu-id="a0fcf-198">次の ..を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-198">Do the following ...</span></span>|<span data-ttu-id="a0fcf-199">メッセージをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-199">Block the message .</span></span> <span data-ttu-id="a0fcf-200">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-200">.</span></span> <span data-ttu-id="a0fcf-201">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-201">.</span></span> <span data-ttu-id="a0fcf-202">メッセージを拒否し、説明を含める。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-202">reject the message and include an explanation.</span></span>|
|<span data-ttu-id="a0fcf-203">メッセージ テキストを提供する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-203">Provide message text</span></span>|<span data-ttu-id="a0fcf-204">この組織外の電子メールの自動転送は、セキュリティ上の理由から防止されます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-204">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>|


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="a0fcf-205">フィッシング攻撃からメールを保護する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-205">Protect your email from phishing attacks</span></span>

<span data-ttu-id="a0fcf-206">Office 365 環境または Microsoft 365 環境用に 1 つ以上のカスタム ドメインを構成している場合は、ターゲットフィッシング対策保護を構成できます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-206">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="a0fcf-207">Office 365 用 Microsoft Defender の一部であるフィッシング対策保護は、悪意のある偽装ベースのフィッシング攻撃や他のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-207">Anti-phishing protection, part of Microsoft Defender for Office 365, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="a0fcf-208">カスタム ドメインを構成していない場合は、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-208">If you haven't configured a custom domain, you don't need to do this.</span></span>

<span data-ttu-id="a0fcf-209">最も重要なユーザーとカスタム ドメインを保護するためのポリシーを作成して、この保護を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-209">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span>

<span data-ttu-id="a0fcf-210">Microsoft Defender for Office 365 でフィッシング対策ポリシーを作成するには、[](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)この短いトレーニング ビデオをご覧ください。または次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-210">To create an anti-phishing policy in Microsoft Defender for Office 365, watch  [this short training video](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>

1. <span data-ttu-id="a0fcf-211">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-211">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="a0fcf-212">セキュリティ コンプライアンス センターの左側のナビゲーション ウィンドウの [脅威の管理] で、[ポリシー &amp; ] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="a0fcf-212">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="a0fcf-213">[ポリシー] **ページで** 、[フィッシング対策 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-213">On the **Policy** page, choose **Anti-phishing**.</span></span>

4. <span data-ttu-id="a0fcf-214">[フィッシング **対策] ページで、[+** 作成] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-214">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="a0fcf-215">ウィザードが起動し、フィッシング対策ポリシーを定義する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-215">A wizard launches that steps you through defining your anti-phishing policy.</span></span>

5. <span data-ttu-id="a0fcf-216">次の表で推奨されるポリシーの名前、説明、および設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-216">Specify the name, description, and settings for your policy as recommended in the following table.</span></span> <span data-ttu-id="a0fcf-217">詳細については、「365 オプションの Microsoft Defender でのフィッシング対策ポリシーについて [Office」を参照してください](../security/office-365-security/set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-217">For more details, see [Learn about anti-phishing policy in Microsoft Defender for Office 365 options](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

6. <span data-ttu-id="a0fcf-218">設定を確認した後、必要に応じて [このポリシーを作成する] または **[\*\*\*\*保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-218">After you've reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="a0fcf-219">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="a0fcf-219">Setting or option</span></span>|<span data-ttu-id="a0fcf-220">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="a0fcf-220">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="a0fcf-221">名前</span><span class="sxs-lookup"><span data-stu-id="a0fcf-221">Name</span></span>|<span data-ttu-id="a0fcf-222">ドメインと最も価値のあるキャンペーン スタッフ</span><span class="sxs-lookup"><span data-stu-id="a0fcf-222">Domain and most valuable campaign staff</span></span>|
|<span data-ttu-id="a0fcf-223">説明</span><span class="sxs-lookup"><span data-stu-id="a0fcf-223">Description</span></span>|<span data-ttu-id="a0fcf-224">最も重要なスタッフとドメインが偽装されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-224">Ensure most important staff and our domain are not being impersonated.</span></span>|
|<span data-ttu-id="a0fcf-225">保護対象のユーザーの追加</span><span class="sxs-lookup"><span data-stu-id="a0fcf-225">Add users to protect</span></span>|<span data-ttu-id="a0fcf-226">[+**条件の追加] を選択します。受信者は .**</span><span class="sxs-lookup"><span data-stu-id="a0fcf-226">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="a0fcf-227">ユーザー名を入力するか、候補者、キャンペーン マネージャー、その他の重要なスタッフ メンバーのメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-227">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="a0fcf-228">偽装から保護する最大 20 の内部アドレスと外部アドレスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-228">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>|
|<span data-ttu-id="a0fcf-229">保護対象のドメインの追加</span><span class="sxs-lookup"><span data-stu-id="a0fcf-229">Add domains to protect</span></span>|<span data-ttu-id="a0fcf-230">Select **+ Add a condition, the recipient domain is**.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-230">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="a0fcf-231">Microsoft 365 サブスクリプションに関連付けられているカスタム ドメイン (定義されている場合) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-231">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="a0fcf-232">複数のドメインを入力できます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-232">You can enter more than one domain.</span></span>|
|<span data-ttu-id="a0fcf-233">処理の選択</span><span class="sxs-lookup"><span data-stu-id="a0fcf-233">Choose actions</span></span>|<span data-ttu-id="a0fcf-234">偽装ユーザーによって電子メールが送信される場合: **[メッセージ** を別の電子メール アドレスにリダイレクトする] を選択し、セキュリティ管理者の電子メール アドレスを入力します。たとえば *、Alice <span> <span> @contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-234">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span> <span data-ttu-id="a0fcf-235">メールが偽装ドメインによって送信されている場合: **[メッセージを検疫]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-235">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>|
|<span data-ttu-id="a0fcf-236">メールボックス インテリジェンス</span><span class="sxs-lookup"><span data-stu-id="a0fcf-236">Mailbox intelligence</span></span>|<span data-ttu-id="a0fcf-237">既定では、新しいフィッシング対策ポリシーの作成時にはメールボックス インテリジェンスが選択されています。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-237">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="a0fcf-238">最適な結果が得られるように、この設定は **[オン]** のままにしておいてください。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-238">Leave this setting **On** for best results.</span></span>|
|<span data-ttu-id="a0fcf-239">信頼できる送信者とドメインの追加</span><span class="sxs-lookup"><span data-stu-id="a0fcf-239">Add trusted senders and domains</span></span>|<span data-ttu-id="a0fcf-240">ここでは、独自のドメイン、または他の信頼できるドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-240">Here you can add your own domain, or any other trusted domains.</span></span>|
|<span data-ttu-id="a0fcf-241">適用先</span><span class="sxs-lookup"><span data-stu-id="a0fcf-241">Applied to</span></span>|<span data-ttu-id="a0fcf-242">**[受信者のドメインが次の場合]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-242">Select **The recipient domain is**.</span></span> <span data-ttu-id="a0fcf-243">**[これらのいずれか]** では、**[選択]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-243">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="a0fcf-244">**[+ 追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-244">Select **+ Add**.</span></span> <span data-ttu-id="a0fcf-245">contoso など、ドメインの名前の横にあるチェック ボックスを *オンにします。 <span> <span>com* をクリックし、一覧で [追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-245">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="a0fcf-246">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-246">Select **Done**.</span></span>|

## <a name="protect-against-malicious-attachments-and-files-with-safe-attachments"></a><span data-ttu-id="a0fcf-247">安全な添付ファイルを使用して悪意のある添付ファイルやファイルから保護する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-247">Protect against malicious attachments and files with Safe Attachments</span></span>

<span data-ttu-id="a0fcf-248">ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを定期的に送信、受信、共有します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-248">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="a0fcf-249">電子メール メッセージを見ただけで、添付ファイルが安全か悪意かを判断するのは必ずしも簡単ではありません。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-249">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="a0fcf-250">Microsoft Defender for Office 365 には、安全な添付ファイル保護が含まれていますが、この保護は既定では有効にされません。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-250">Microsoft Defender for Office 365 includes Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="a0fcf-251">この保護の使用を開始するには、新しいルールを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-251">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="a0fcf-252">この保護は、SharePoint、OneDrive、および Microsoft Teams のファイルにまで拡張されます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-252">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>

<span data-ttu-id="a0fcf-253">安全な添付ファイル ポリシーを作成するには、この短 [いビデオを見](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-253">To create an Safe Attachment policy, either watch [this short video](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>

1. <span data-ttu-id="a0fcf-254">に移動 [https://protection.office.com](https://protection.office.com) し、管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-254">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="a0fcf-255">セキュリティ コンプライアンス センターの左側のナビゲーション ウィンドウの [脅威の管理] で、[ポリシー &amp; ] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="a0fcf-255">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="a0fcf-256">[ポリシー] ページで、[安全な添付ファイル] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-256">On the Policy page, choose **Safe Attachments**.</span></span>

4. <span data-ttu-id="a0fcf-257">[安全な添付ファイル] ページで **、[SharePoint、OneDrive、および Microsoft Teams** の ATP を有効にする] チェック ボックスをオンにして、この保護を広く適用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-257">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span>

5. <span data-ttu-id="a0fcf-258">新 **+** しいポリシーを作成する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-258">Select **+** to create a new policy.</span></span>

6. <span data-ttu-id="a0fcf-259">次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-259">Apply the settings in the following table.</span></span>

7. <span data-ttu-id="a0fcf-260">設定を確認した後、必要に応じて [このポリシー **の** 作成] または [ **保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-260">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>

|<span data-ttu-id="a0fcf-261">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="a0fcf-261">Setting or option</span></span>|<span data-ttu-id="a0fcf-262">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="a0fcf-262">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="a0fcf-263">名前</span><span class="sxs-lookup"><span data-stu-id="a0fcf-263">Name</span></span>|<span data-ttu-id="a0fcf-264">検出されたマルウェアを使用して、現在および将来のメールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-264">Block current and future emails with detected malware.</span></span>|
|<span data-ttu-id="a0fcf-265">説明</span><span class="sxs-lookup"><span data-stu-id="a0fcf-265">Description</span></span>|<span data-ttu-id="a0fcf-266">検出されたマルウェアを使用して、現在および将来の電子メールと添付ファイルをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-266">Block current and future emails and attachments with detected malware.</span></span>|
|<span data-ttu-id="a0fcf-267">添付ファイルの不明なマルウェアの応答を保存する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-267">Save attachments unknown malware response</span></span>|<span data-ttu-id="a0fcf-268">[ **ブロック] を選択します。 検出されたマルウェアを使用して現在および将来のメールと添付ファイルをブロックします**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-268">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>|
|<span data-ttu-id="a0fcf-269">検出時に添付ファイルをリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="a0fcf-269">Redirect attachment on detection</span></span>|<span data-ttu-id="a0fcf-270">リダイレクトを有効にする (このボックスを選択します) 管理者アカウントまたは検疫用のメールボックスのセットアップを入力します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-270">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="a0fcf-271">添付ファイルのマルウェア スキャンが時間切れまたはエラーが発生した場合は、上記の選択項目を適用します (このボックスを選択します)。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-271">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>|
|<span data-ttu-id="a0fcf-272">適用先</span><span class="sxs-lookup"><span data-stu-id="a0fcf-272">Applied to</span></span>|<span data-ttu-id="a0fcf-273">受信者ドメインはです。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-273">The recipient domain is .</span></span> <span data-ttu-id="a0fcf-274">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-274">.</span></span> <span data-ttu-id="a0fcf-275">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-275">.</span></span> <span data-ttu-id="a0fcf-276">ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-276">select your domain.</span></span>|

<span data-ttu-id="a0fcf-277">詳細については、「Microsoft Defender for microsoft Defender for Office [365」を参照してください](../security/office-365-security/set-up-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-277">For more information, see [Set up anti-phishing policies in Microsoft Defender for Office 365](../security/office-365-security/set-up-anti-phishing-policies.md).</span></span>

## <a name="protect-against-phishing-attacks-with-safe-links"></a><span data-ttu-id="a0fcf-278">セーフ リンクを使用したフィッシング攻撃からの保護</span><span class="sxs-lookup"><span data-stu-id="a0fcf-278">Protect against phishing attacks with Safe Links</span></span>

<span data-ttu-id="a0fcf-279">ハッカーは、メールや他のファイルのリンクに悪意のある Web サイトを非表示にしている場合があります。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-279">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="a0fcf-280">Office 365 用 Microsoft Defender の一部であるセーフ リンクは、電子メール メッセージおよび Office ドキュメントで Web アドレス (URL) のクリック時検証を提供することで、組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-280">Safe Links, part of Microsoft Defender for Office 365, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="a0fcf-281">保護は、セーフ リンク ポリシーを使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-281">Protection is defined through Safe Links policies.</span></span>

<span data-ttu-id="a0fcf-282">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-282">We recommend that you do the following:</span></span>

- <span data-ttu-id="a0fcf-283">保護を強化するために既定のポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-283">Modify the default policy to increase protection.</span></span>

- <span data-ttu-id="a0fcf-284">ドメイン内のすべての受信者を対象とする新しいポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-284">Add a new policy targeted to all recipients in your domain.</span></span>

<span data-ttu-id="a0fcf-285">セーフ リンクを設定するには、この [短いトレーニング ビデオを見る](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)、または次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-285">To set up Safe Links, watch [this short training video](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>

1. <span data-ttu-id="a0fcf-286">に移動 [https://protection.office.com](https://protection.office.com) し、管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-286">Go to [https://protection.office.com](https://protection.office.com), and sign in with your admin account.</span></span>

2. <span data-ttu-id="a0fcf-287">セキュリティ コンプライアンス センターの左側のナビゲーション ウィンドウの [脅威の管理] で、[ポリシー &amp; ] を **選択します**。 </span><span class="sxs-lookup"><span data-stu-id="a0fcf-287">In the Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="a0fcf-288">[ポリシー] ページで、[安全なリンク] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-288">On the Policy page, choose **Safe Links**.</span></span>

<span data-ttu-id="a0fcf-289">既定のポリシーを変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-289">To modify the default policy:</span></span>

1. <span data-ttu-id="a0fcf-290">[安全なリンク] ページの [組織 **全体** に適用されるポリシー] で、[既定のポリシー] **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-290">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span>

2. <span data-ttu-id="a0fcf-291">[ **メール以外のコンテンツに適用** される設定] で **、[Microsoft 365 Apps for enterprise,** Office iOS および Android 用] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-291">Under **Settings that apply to content except email**, select **Microsoft 365 Apps for enterprise, Office for iOS and Android**.</span></span>

3. <span data-ttu-id="a0fcf-292">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-292">Select **Save**.</span></span>

<span data-ttu-id="a0fcf-293">ドメイン内のすべての受信者を対象とする新しいポリシーを作成するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-293">To create a new policy targeted to all recipients in your domain:</span></span>

1. <span data-ttu-id="a0fcf-294">[安全なリンク] ページの **[組織** 全体に適用されるポリシー] で、新しいポリシー **+** を作成する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-294">On the Safe links page, under **Policies that apply to the entire organization**, select **+** to create a new policy.</span></span>

2. <span data-ttu-id="a0fcf-295">次の表に示す設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-295">Apply the settings listed in the following table.</span></span>

3. <span data-ttu-id="a0fcf-296">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-296">Select **Save**.</span></span>

|<span data-ttu-id="a0fcf-297">設定またはオプション</span><span class="sxs-lookup"><span data-stu-id="a0fcf-297">Setting or option</span></span>|<span data-ttu-id="a0fcf-298">推奨される設定値</span><span class="sxs-lookup"><span data-stu-id="a0fcf-298">Recommended setting</span></span>|
|---|---|
|<span data-ttu-id="a0fcf-299">名前</span><span class="sxs-lookup"><span data-stu-id="a0fcf-299">Name</span></span>|<span data-ttu-id="a0fcf-300">ドメイン内のすべての受信者の安全なリンク ポリシー</span><span class="sxs-lookup"><span data-stu-id="a0fcf-300">Safe links policy for all recipients in the domain</span></span>|
|<span data-ttu-id="a0fcf-301">メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-301">Select the action for unknown potentially malicious URLs in messages</span></span>|<span data-ttu-id="a0fcf-302">[ **オン] を選択すると、ユーザー** がリンクをクリックすると、URL が書き換えされ、既知の悪意のあるリンクの一覧に対してチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-302">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>|
|<span data-ttu-id="a0fcf-303">安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする</span><span class="sxs-lookup"><span data-stu-id="a0fcf-303">Use Safe Attachments to scan downloadable content</span></span>|<span data-ttu-id="a0fcf-304">このボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-304">Select this box.</span></span>|
|<span data-ttu-id="a0fcf-305">適用先</span><span class="sxs-lookup"><span data-stu-id="a0fcf-305">Applied to</span></span>|<span data-ttu-id="a0fcf-306">受信者ドメインはです。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-306">The recipient domain is .</span></span> <span data-ttu-id="a0fcf-307">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-307">.</span></span> <span data-ttu-id="a0fcf-308">.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-308">.</span></span> <span data-ttu-id="a0fcf-309">ドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-309">select your domain.</span></span>|

<span data-ttu-id="a0fcf-310">詳細については、「セーフ リンク [」を参照してください](../security/office-365-security/safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-310">For more information, see [Safe Links](../security/office-365-security/safe-links.md).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="a0fcf-311">Intune 管理センターに移動する</span><span class="sxs-lookup"><span data-stu-id="a0fcf-311">Go to Intune admin center</span></span>

1. <span data-ttu-id="a0fcf-312">Azure portal に [サインインします](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-312">Sign in to [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="a0fcf-313">[すべての **サービス] を** 選択し、 *検索ボックスに Intune* と **入力します**。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-313">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="a0fcf-314">結果が表示されたら **、Microsoft Intune** の横にある開始を選択して、後で簡単に見つけやすくします。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-314">Once the results appear, select the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="a0fcf-315">管理センターに加えて、Intune を使用して組織のデバイスを登録および管理できます。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-315">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="a0fcf-316">詳細については、「Windows デバイスの登録方法による機能」および [「Intune](/intune/enrollment/enrollment-method-capab) で管理されるデバイスの登録 [オプション」を参照してください](/intune/enrollment-options)。</span><span class="sxs-lookup"><span data-stu-id="a0fcf-316">For more information, see [Capabilities by enrollment method for Windows devices](/intune/enrollment/enrollment-method-capab) and [Enrollment options for devices managed by Intune](/intune/enrollment-options).</span></span>
