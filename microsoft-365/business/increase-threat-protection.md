---
title: Microsoft 365 Business の脅威保護を強化する
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Office 365 Advanced Threat Protection を設定し、機密データを保護します。
ms.openlocfilehash: 81197a8baf1c4d0cbfd898c41a305c1a99bab57c
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288117"
---
# <a name="increase-threat-protection"></a><span data-ttu-id="f6f3c-103">脅威保護を強化する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-103">Increase threat protection</span></span>

<span data-ttu-id="f6f3c-104">この記事は、Microsoft 365 サブスクリプションの保護を強化して、フィッシング、マルウェア、およびその他の脅威から保護するのに役立つ情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-104">This article helps you increase the protection in your Microsoft 365 subscription to protect against phishing, malware, and other threats.</span></span> <span data-ttu-id="f6f3c-105">これらの推奨事項は、法律事務所や健康保険クリニックなど、セキュリティの必要性が増大する組織に適しています。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-105">These recommendations are appropriate for organizations with an increased need for security, like law offices, and health care clinics.</span></span>

<span data-ttu-id="f6f3c-106">開始する前に、Office 365 のセキュリティスコアを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-106">Before you begin, check your Office 365 Secure Score.</span></span> <span data-ttu-id="f6f3c-107">Office 365 のセキュリティで保護されたスコアは、通常のアクティビティとセキュリティ設定に基づいて Office 365 組織のセキュリティを分析し、スコアを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-107">Office 365 Secure Score analyzes your Office 365 organization's security based on your regular activities and security settings and assigns a score.</span></span> <span data-ttu-id="f6f3c-108">最初に、現在のスコアをメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-108">Begin by taking note of your current score.</span></span> <span data-ttu-id="f6f3c-109">この記事で推奨されている操作を行うと、スコアが向上します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-109">Taking the actions recommended in this article increases your score.</span></span> <span data-ttu-id="f6f3c-110">目標は最大スコアを達成することではなく、ユーザーの生産性に悪影響を及ぼすことがない環境を保護する機会に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-110">The goal is not to achieve the max score, but to be aware of opportunities to protect your environment that do not negatively affect productivity for your users.</span></span> 

<span data-ttu-id="f6f3c-111">詳細については、「 [Microsoft Secure Score](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-111">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/en-us/office365/securitycompliance/microsoft-secure-score).</span></span>

## <a name="raise-the-level-of-protection-against-malware-in-mail"></a><span data-ttu-id="f6f3c-112">メールのマルウェアに対する保護レベルを上げる</span><span class="sxs-lookup"><span data-stu-id="f6f3c-112">Raise the level of protection against malware in mail</span></span>

<span data-ttu-id="f6f3c-113">Office 365 または Microsoft 365 環境にはマルウェアからの保護が含まれていますが、マルウェアによく使用されるファイルの種類の添付ファイルをブロックすることによって、この保護を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-113">Your Office 365 or Microsoft 365 environment includes protection against malware, but you can increase this protection by blocking attachments with file types that are commonly used for malware.</span></span> <span data-ttu-id="f6f3c-114">電子メールでのマルウェア保護を向上させるには:</span><span class="sxs-lookup"><span data-stu-id="f6f3c-114">To increase malware protection in email:</span></span>
  
1. <span data-ttu-id="f6f3c-115">に[https://protection.office.com](https://protection.office.com)移動し、管理者アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-115">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account credentials.</span></span> 
    
2. <span data-ttu-id="f6f3c-116">Office 365 &amp;セキュリティ/コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下にある [**ポリシー** \> **のマルウェア対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-116">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Anti-Malware**.</span></span>
    
3. <span data-ttu-id="f6f3c-117">この会社全体のポリシーを編集するには、既定のポリシーをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-117">Double-click the default policy to edit this company-wide policy.</span></span>
    
4. <span data-ttu-id="f6f3c-118">[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-118">Click **Settings**.</span></span>
    
5. <span data-ttu-id="f6f3c-119">[**一般的な添付ファイルの種類のフィルター**] で、 **[オン] を選択し**ます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-119">Under **Common Attachment Types Filter**, select **On**.</span></span> <span data-ttu-id="f6f3c-120">ブロックされているファイルの種類は、このコントロールのすぐ下のウィンドウに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-120">The file types that are blocked are listed in the window directly below this control.</span></span>  <span data-ttu-id="f6f3c-121">次の filetypes を追加してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-121">Make sure you add these filetypes:</span></span>
   - <span data-ttu-id="f6f3c-122">ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、ジョブ、js、jse、lnk、pcd、[mdb]、[mde]、[]、[reg]、[shs]、[mst]、[]、[url]、[wsh]、[]、[wsc</span><span class="sxs-lookup"><span data-stu-id="f6f3c-122">ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh, exe, pif</span></span>  <br/> <span data-ttu-id="f6f3c-123">必要に応じて、後でファイルの種類を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-123">You can add or delete file types later, if needed.</span></span>
    
6. <span data-ttu-id="f6f3c-124">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-124">Click **Save.**</span></span>
    
<span data-ttu-id="f6f3c-125">詳細については、「[マルウェア対策保護](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-125">For more information, see [Anti-malware protection](https://go.microsoft.com/fwlink/?linkid=2015692&amp;clcid=0x409).</span></span>
  
## <a name="protect-against-ransomware"></a><span data-ttu-id="f6f3c-126">ランサムウェアから保護する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-126">Protect against ransomware</span></span>

<span data-ttu-id="f6f3c-127">ランサムウェアは、ファイルの暗号化またはコンピューター画面のロックによってデータへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-127">Ransomware restricts access to data by encrypting files or locking computer screens.</span></span> <span data-ttu-id="f6f3c-128">その後、データにアクセスするために exchange では、通常、ビットコインのような cryptocurrencies のような形式で "ransom" を要求することによって、被害からのデータを組み込みます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-128">It then attempts to extort money from victims by asking for "ransom," usually in form of cryptocurrencies like Bitcoin, in exchange for access to data.</span></span> 
  
<span data-ttu-id="f6f3c-129">ランサムウェアから保護するには、1つまたは複数のメールフロールールを作成して、ランサムウェアに対してよく使用されるファイル拡張子をブロックするか (「[メールでマルウェアに対する保護レベルを高める](#raise-the-level-of-protection-against-malware-in-mail)」で追加されたもの)、またはこれらを受信するユーザーに警告を出すことができます。電子メールの添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-129">You can protect against ransomware by creating one or more mail flow rules to block file extensions that are commonly used for ransomware (these were added in the [raise the level of protection against malware in mail](#raise-the-level-of-protection-against-malware-in-mail) step), or to warn users who receive these attachments in email.</span></span>

<span data-ttu-id="f6f3c-130">前の手順でブロックしたファイルに加えて、マクロを含む Office ファイル添付ファイルを開く前に、ユーザーに警告するルールを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-130">In addition to the files that you blocked in the previous step, it is also good practice to create a rule to warn users before opening Office file attachments that include macros.</span></span> <span data-ttu-id="f6f3c-131">ランサムウェアは、マクロ内で非表示にすることができます。そうしないと、ユーザーが知らないユーザーからこれらのファイルを開かないように警告されます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-131">Ransomware can be hidden inside macros, so we'll warn users to not open these files from people they do not know.</span></span>

<span data-ttu-id="f6f3c-132">メールトランスポートルールを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-132">To create a mail transport rule:</span></span>
  
1. <span data-ttu-id="f6f3c-133">管理<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>センターに移動し、[**管理センター** \> ] [ **Exchange**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-133">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="f6f3c-134">[**メールフロー** ] カテゴリで、[**ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-134">In the **mail flow** category, click **rules**.</span></span>
    
3. <span data-ttu-id="f6f3c-135">[ **+**] をクリックし、[**新しいルールの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-135">Click **+**, and then click **Create a new rule**.</span></span>
    
4. <span data-ttu-id="f6f3c-136">ダイアログボックスの下部にある [**その他のオプション**] をクリックして、オプションの完全なセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-136">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="f6f3c-137">ルールの次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-137">Apply the settings in the following table for the rule.</span></span> <span data-ttu-id="f6f3c-138">これらの設定を変更しない場合は、既定の設定のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-138">Leave the rest of the settings at the default, unless you want to change these.</span></span>
    
6. <span data-ttu-id="f6f3c-139">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-139">Click **Save**.</span></span>
    
|<span data-ttu-id="f6f3c-140">**設定**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-140">**Setting**</span></span>|<span data-ttu-id="f6f3c-141">**Office ファイルの添付ファイルを開く前にユーザーに警告を発する**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-141">**Warn users before opening attachments of Office files**</span></span>||
|:-----|:-----|:-----|
|<span data-ttu-id="f6f3c-142">名前</span><span class="sxs-lookup"><span data-stu-id="f6f3c-142">Name</span></span>  <br/> |<span data-ttu-id="f6f3c-143">ランサムウェア対策ルール: ユーザーに警告を発する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-143">Anti-ransomware rule: warn users</span></span>  <br/>  |
|<span data-ttu-id="f6f3c-144">このルールを適用する条件</span><span class="sxs-lookup"><span data-stu-id="f6f3c-144">Apply this rule if .</span></span> <span data-ttu-id="f6f3c-145">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-145"></span></span> <span data-ttu-id="f6f3c-146">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-146"></span></span>  <br/> |<span data-ttu-id="f6f3c-147">任意の添付ファイル。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-147">Any attachment .</span></span> <span data-ttu-id="f6f3c-148">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-148"></span></span> <span data-ttu-id="f6f3c-149">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-149"></span></span> <span data-ttu-id="f6f3c-150">ファイル拡張子が一致する。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-150">file extension matches .</span></span> <span data-ttu-id="f6f3c-151">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-151"></span></span> <span data-ttu-id="f6f3c-152">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-152"></span></span>  <br/> |
|<span data-ttu-id="f6f3c-153">単語または語句を指定する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-153">Specify words or phrases</span></span>  <br/> |<span data-ttu-id="f6f3c-154">次のファイルの種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-154">Add these file types:</span></span>  <br/> <span data-ttu-id="f6f3c-155">normal.dotm、.docm、.xlsm、sltm、.xla、xlam、xll、pptm、potm、ppam、pptm、sldm</span><span class="sxs-lookup"><span data-stu-id="f6f3c-155">dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm</span></span>  <br/>|
|<span data-ttu-id="f6f3c-156">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-156">Do the following .</span></span> <span data-ttu-id="f6f3c-157">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-157"></span></span> <span data-ttu-id="f6f3c-158">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-158"></span></span>  <br/> |<span data-ttu-id="f6f3c-159">受信者にメッセージで通知します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-159">Notify the recipient with a message</span></span>  <br/> |
|<span data-ttu-id="f6f3c-160">メッセージテキストを指定する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-160">Provide message text</span></span>  <br/> |<span data-ttu-id="f6f3c-161">これらの種類のファイルは、悪意のあるコードを含むマクロを含んでいる可能性があるため、知られていないユーザーから開かないでください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-161">Do not open these type of files from people you do not know because they might contain macros with malicious code.</span></span>  <br/> |
   
<span data-ttu-id="f6f3c-162">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-162">For more information, see:</span></span>
  
- [<span data-ttu-id="f6f3c-163">ランサムウェアの処理方法</span><span class="sxs-lookup"><span data-stu-id="f6f3c-163">How to deal with ransomware</span></span>](https://go.microsoft.com/fwlink/?linkid=2016501&amp;clcid=0x409)
    
- [<span data-ttu-id="f6f3c-164">OneDrive を復元する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-164">Restore your OneDrive</span></span>](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15.aspx)
    


## <a name="stop-auto-forwarding-for-email"></a><span data-ttu-id="f6f3c-165">電子メールの自動転送を停止する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-165">Stop auto-forwarding for email</span></span>

<span data-ttu-id="f6f3c-166">ユーザーのメールボックスにアクセスできるハッカーは、メールボックスを自動的に転送するように設定することにより、メールを盗むことができます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-166">Hackers who gain access to a user's mailbox can steal your mail by setting the mailbox to automatically forward email.</span></span> <span data-ttu-id="f6f3c-167">これは、ユーザーの認識なしでも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-167">This can happen even without the user's awareness.</span></span> <span data-ttu-id="f6f3c-168">メールフロールールを構成することによって、このような事態を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-168">You can prevent this from happening by configuring a mail flow rule.</span></span> 
  
<span data-ttu-id="f6f3c-169">メールトランスポートルールを作成するには、[この短いビデオ](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7)を見るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-169">To create a mail transport rule, either watch [this short video](https://support.office.com/article/f9d693ba-5c78-47c0-b156-8e461e062aa7) or follow these steps:</span></span>
  
1. <span data-ttu-id="f6f3c-170">Microsoft 365 管理センターで、[**管理センター** \> ] [ **Exchange**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-170">In the Microsoft 365 admin center, click **Admin centers** \> **Exchange**.</span></span>
    
2. <span data-ttu-id="f6f3c-171">[**メールフロー** ] カテゴリで、[**ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-171">In the **mail flow** category, click **rules**.</span></span>
    
3. <span data-ttu-id="f6f3c-172">[ **+**] をクリックし、[**新しいルールの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-172">Click **+**, and then click **Create a new rule**.</span></span>
    
4. <span data-ttu-id="f6f3c-173">ダイアログボックスの下部にある [**その他のオプション**] をクリックして、オプションの完全なセットを表示します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-173">Click **More options** at the bottom of the dialog box to see the full set of options.</span></span> 
    
5. <span data-ttu-id="f6f3c-174">次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-174">Apply the settings in the following table.</span></span> <span data-ttu-id="f6f3c-175">これらの設定を変更しない場合は、既定の設定のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-175">Leave the rest of the settings at the default, unless you want to change these.</span></span>
    
6. <span data-ttu-id="f6f3c-176">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-176">Click **Save**.</span></span>
    
|<span data-ttu-id="f6f3c-177">**設定**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-177">**Setting**</span></span>|<span data-ttu-id="f6f3c-178">**Office ファイルの添付ファイルを開く前にユーザーに警告を発する**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-178">**Warn users before opening attachments of Office files**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f6f3c-179">名前</span><span class="sxs-lookup"><span data-stu-id="f6f3c-179">Name</span></span>  <br/> |<span data-ttu-id="f6f3c-180">外部ドメインへの電子メールの自動転送を禁止する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-180">Prevent auto forwarding of email to external domains</span></span>  <br/> |
|<span data-ttu-id="f6f3c-181">次の場合にこのルールを適用する...</span><span class="sxs-lookup"><span data-stu-id="f6f3c-181">Apply this rule if ...</span></span>  <br/> |<span data-ttu-id="f6f3c-182">送信者。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-182">The sender .</span></span> <span data-ttu-id="f6f3c-183">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-183"></span></span> <span data-ttu-id="f6f3c-184">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-184"></span></span> <span data-ttu-id="f6f3c-185">外部/内部。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-185">is external/internal .</span></span> <span data-ttu-id="f6f3c-186">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-186"></span></span> <span data-ttu-id="f6f3c-187">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-187"></span></span> <span data-ttu-id="f6f3c-188">組織内</span><span class="sxs-lookup"><span data-stu-id="f6f3c-188">Inside the organization</span></span>  <br/> |
|<span data-ttu-id="f6f3c-189">条件を追加する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-189">Add condition</span></span>  <br/> |<span data-ttu-id="f6f3c-190">メッセージのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-190">The message properties .</span></span> <span data-ttu-id="f6f3c-191">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-191"></span></span> <span data-ttu-id="f6f3c-192">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-192"></span></span> <span data-ttu-id="f6f3c-193">メッセージの種類を含めます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-193">include the message type .</span></span> <span data-ttu-id="f6f3c-194">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-194"></span></span> <span data-ttu-id="f6f3c-195">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-195"></span></span> <span data-ttu-id="f6f3c-196">自動転送</span><span class="sxs-lookup"><span data-stu-id="f6f3c-196">Auto-forward</span></span>  <br/> |
|<span data-ttu-id="f6f3c-197">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-197">Do the following ...</span></span>  <br/> |<span data-ttu-id="f6f3c-198">[メッセージをブロックする。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-198">Block the message .</span></span> <span data-ttu-id="f6f3c-199">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-199"></span></span> <span data-ttu-id="f6f3c-200">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-200"></span></span> <span data-ttu-id="f6f3c-201">メッセージを拒否し、説明を含めます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-201">reject the message and include an explanation.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-202">メッセージテキストを指定する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-202">Provide message text</span></span>  <br/> |<span data-ttu-id="f6f3c-203">この組織外の電子メールの自動転送は、セキュリティ上の理由から禁止されています。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-203">Auto-forwarding email outside this organization is prevented for security reasons.</span></span>  <br/> |


## <a name="protect-your-email-from-phishing-attacks"></a><span data-ttu-id="f6f3c-204">フィッシング攻撃からメールを保護する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-204">Protect your email from phishing attacks</span></span>

<span data-ttu-id="f6f3c-205">Office 365 または Microsoft 365 環境用に1つ以上のカスタムドメインを構成した場合は、対象となるフィッシング対策保護を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-205">If you've configured one or more custom domains for your Office 365 or Microsoft 365 environment, you can configure targeted anti-phishing protection.</span></span> <span data-ttu-id="f6f3c-206">ATP のフィッシング対策保護 (Office 365 Advanced Threat Protection の一部) は、悪意のある偽造ベースのフィッシング攻撃やその他のフィッシング攻撃から組織を保護するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-206">ATP anti-phishing protection, part of Office 365 Advanced Threat Protection, can help protect your organization from malicious impersonation-based phishing attacks and other phishing attacks.</span></span> <span data-ttu-id="f6f3c-207">カスタムドメインを構成していない場合は、この手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-207">If you haven't configured a custom domain, you do not need to do this.</span></span>
  
<span data-ttu-id="f6f3c-208">最も重要なユーザーとカスタムドメインを保護するためのポリシーを作成して、この保護を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-208">We recommend that you get started with this protection by creating a policy to protect your most important users and your custom domain.</span></span> 

  
<span data-ttu-id="f6f3c-209">ATP のフィッシング対策ポリシーを作成するには、[この短いトレーニングビデオ](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)をご覧ください。または、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-209">To create an ATP anti-phishing policy, watch  [this short training video](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c), or complete the following steps:</span></span>
  
1. <span data-ttu-id="f6f3c-210">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-210">Go to [https://protection.office.com](https://protection.office.com).</span></span> 
    
2. <span data-ttu-id="f6f3c-211">Office 365 セキュリティ&amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下にある [**ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-211">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="f6f3c-212">[**ポリシー** ] ページで、[ **ATP のフィッシング対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-212">On the **Policy** page, choose **ATP anti-phishing**.</span></span>
    
4. <span data-ttu-id="f6f3c-213">[**フィッシング対策**] ページで、[ **+ 作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-213">On the **Anti-phishing** page, select **+ Create**.</span></span> <span data-ttu-id="f6f3c-214">ウィザードが起動して、フィッシング対策ポリシーを定義する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-214">A wizard launches that steps you through defining your anti-phishing policy.</span></span>
    
5. <span data-ttu-id="f6f3c-215">下の表に示す推奨事項に従って、ポリシーの名前、説明、および設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-215">Specify the name, description, and settings for your policy as recommended in the chart below.</span></span> <span data-ttu-id="f6f3c-216">詳細については、「 [ATP のフィッシング対策ポリシーのオプションについ](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-216">See [Learn about ATP anti-phishing policy options](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409) for more details.</span></span> 
    
6. <span data-ttu-id="f6f3c-217">設定を確認した後、必要に応じて [**このポリシーを作成**する] または [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-217">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="f6f3c-218">**設定またはオプション**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-218">**Setting or option**</span></span><br/>|<span data-ttu-id="f6f3c-219">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-219">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="f6f3c-220">名前</span><span class="sxs-lookup"><span data-stu-id="f6f3c-220">Name</span></span>  <br/> |<span data-ttu-id="f6f3c-221">ドメインおよび最も重要なキャンペーンスタッフ</span><span class="sxs-lookup"><span data-stu-id="f6f3c-221">Domain and most valuable campaign staff</span></span>  <br/> |
|<span data-ttu-id="f6f3c-222">説明</span><span class="sxs-lookup"><span data-stu-id="f6f3c-222">Description</span></span>  <br/> |<span data-ttu-id="f6f3c-223">最も重要なスタッフとドメインが偽装されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-223">Ensure most important staff and our domain are not being impersonated.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-224">保護するユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-224">Add users to protect</span></span>  <br/> |<span data-ttu-id="f6f3c-225">[ **+ 条件の追加**] を選択すると、受信者はになります。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-225">Select **+ Add a condition, The recipient is**.</span></span> <span data-ttu-id="f6f3c-226">ユーザー名を入力するか、候補、キャンペーンマネージャー、およびその他の重要なスタッフメンバーの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-226">Type user names or enter the email address of the candidate, campaign manager, and other important staff members.</span></span> <span data-ttu-id="f6f3c-227">偽装から保護する内部および外部アドレスを最大20個まで追加できます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-227">You can add up to 20 internal and external addresses that you want to protect from impersonation.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-228">保護するドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-228">Add domains to protect</span></span>  <br/> |<span data-ttu-id="f6f3c-229">[ **+ 条件を追加する] を選択すると、受信者のドメインは**になります。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-229">Select **+ Add a condition, The recipient domain is**.</span></span> <span data-ttu-id="f6f3c-230">Microsoft 365 サブスクリプションに関連付けられているカスタムドメインを入力します (定義されている場合)。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-230">Enter the custom domain associated with your Microsoft 365 subscription, if you defined one.</span></span> <span data-ttu-id="f6f3c-231">複数のドメインを入力できます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-231">You can enter more than one domain.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-232">アクションの選択</span><span class="sxs-lookup"><span data-stu-id="f6f3c-232">Choose actions</span></span>  <br/> |<span data-ttu-id="f6f3c-233">偽装ユーザーによって電子メールが送信される場合: [**メッセージを別の電子メールアドレスにリダイレクトする**] を選択し、セキュリティ管理者の電子メールアドレスを入力します。たとえば、 *<span><span>Alice は @contoso .com*のようになります。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-233">If email is sent by an impersonated user: Choose **Redirect message to another email address**, and then type the email address of the security administrator; for example, *Alice<span><span>@contoso.com*.</span></span>          <span data-ttu-id="f6f3c-234">偽装ドメインによって電子メールが送信される場合: [**検疫メッセージ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-234">If email is sent by an impersonated domain: Choose **Quarantine message**.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-235">メールボックスインテリジェンス</span><span class="sxs-lookup"><span data-stu-id="f6f3c-235">Mailbox intelligence</span></span>  <br/> |<span data-ttu-id="f6f3c-236">既定では、新しいフィッシング対策ポリシーを作成すると、メールボックスインテリジェンスが選択されます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-236">By default, mailbox intelligence is selected when you create a new anti-phishing policy.</span></span> <span data-ttu-id="f6f3c-237">最良の結果を得るために、この設定**をオンのままにして**おきます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-237">Leave this setting **On** for best results.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-238">信頼できる差出人とドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-238">Add trusted senders and domains</span></span>  <br/> |<span data-ttu-id="f6f3c-239">ここでは、独自のドメインまたは他の信頼されたドメインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-239">Here you can add your own domain, or any other trusted domains.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-240">適用対象</span><span class="sxs-lookup"><span data-stu-id="f6f3c-240">Applied to</span></span>  <br/> |<span data-ttu-id="f6f3c-241">[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-241">Select **The recipient domain is**.</span></span> <span data-ttu-id="f6f3c-242">**これらのいずれかの**下で、[**選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-242">Under **Any of these**, select **Choose**.</span></span> <span data-ttu-id="f6f3c-243">[ **+ 追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-243">Select **+ Add**.</span></span> <span data-ttu-id="f6f3c-244">ドメインの名前の横にあるチェックボックスをオンにします (例: *contoso)。<span>[ <span>com*] の一覧で、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-244">Select the check box next to the name of the domain, for example, *contoso.<span><span>com*, in the list, and then select **Add**.</span></span> <span data-ttu-id="f6f3c-245">[ **Done**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-245">Select **Done**.</span></span>  <br/> |
   
<span data-ttu-id="f6f3c-246">詳細については、「 [Office 365 ATP のフィッシング対策ポリシーを](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)セットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-246">For more information, see [Set up Office 365 ATP anti-phishing policies](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).</span></span>
  
## <a name="protect-against-malicious-attachments-and-files-with-atp-safe-attachments"></a><span data-ttu-id="f6f3c-247">ATP の安全な添付ファイルを使用して悪意のある添付ファイルやファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-247">Protect against malicious attachments and files with ATP Safe Attachments</span></span>

<span data-ttu-id="f6f3c-248">ユーザーは、ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを日常的に送信、受信、共有します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-248">People regularly send, receive, and share attachments, such as documents, presentations, spreadsheets, and more.</span></span> <span data-ttu-id="f6f3c-249">電子メールメッセージを見るだけで、添付ファイルが安全か悪意かを知ることは常に容易ではありません。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-249">It's not always easy to tell whether an attachment is safe or malicious just by looking at an email message.</span></span> <span data-ttu-id="f6f3c-250">Office 365 Advanced Threat Protection には、ATP の安全な添付ファイルの保護が含まれていますが、既定ではこの保護は有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-250">Office 365 Advanced Threat Protection includes ATP Safe Attachment protection, but this protection is not turned on by default.</span></span> <span data-ttu-id="f6f3c-251">この保護の使用を開始するには、新しいルールを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-251">We recommend that you create a new rule to begin using this protection.</span></span> <span data-ttu-id="f6f3c-252">この保護は、SharePoint、OneDrive、Microsoft Teams のファイルにまで及びます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-252">This protection extends to files in SharePoint, OneDrive, and Microsoft Teams.</span></span>
  
<span data-ttu-id="f6f3c-253">ATP の安全な添付ファイルポリシーを作成するには、[この短いビデオ](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)を見るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-253">To create an ATP safe attachment policy, either watch [this short video](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), or complete the following steps:</span></span>
  
1. <span data-ttu-id="f6f3c-254">に[https://protection.office.com](https://protection.office.com)移動し、管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-254">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="f6f3c-255">Office 365 セキュリティ&amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下にある [**ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-255">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="f6f3c-256">[ポリシー] ページで、[ **ATP の安全な添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-256">On the Policy page, choose **ATP safe attachments**.</span></span>
    
4. <span data-ttu-id="f6f3c-257">[安全な添付ファイル] ページで、[ **SharePoint、OneDrive、Microsoft Teams 用の ATP を有効**にする] チェックボックスをオンにして、この保護を広く適用します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-257">On the Safe attachments page, apply this protection broadly by selecting the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** check box.</span></span> 
    
5. <span data-ttu-id="f6f3c-258">新しい**+** ポリシーを作成する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-258">Select **+** to create a new policy.</span></span> 
    
6. <span data-ttu-id="f6f3c-259">次の表の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-259">Apply the settings in the following table.</span></span> 
    
7. <span data-ttu-id="f6f3c-260">設定を確認した後、必要に応じて [**このポリシーを作成**する] または [**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-260">After you have reviewed your settings, choose **Create this policy** or **Save**, as appropriate.</span></span>
    

|<span data-ttu-id="f6f3c-261">**設定またはオプション**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-261">**Setting or option**</span></span>|<span data-ttu-id="f6f3c-262">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-262">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="f6f3c-263">名前</span><span class="sxs-lookup"><span data-stu-id="f6f3c-263">Name</span></span>  <br/> |<span data-ttu-id="f6f3c-264">検出されたマルウェアを含む現在および今後の電子メールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-264">Block current and future emails with detected malware.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-265">説明</span><span class="sxs-lookup"><span data-stu-id="f6f3c-265">Description</span></span>  <br/> |<span data-ttu-id="f6f3c-266">検出されたマルウェアを含む、現在および今後の電子メールと添付ファイルをブロックする。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-266">Block current and future emails and attachments with detected malware.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-267">添付ファイルの保存に関する不明なマルウェア応答</span><span class="sxs-lookup"><span data-stu-id="f6f3c-267">Save attachments unknown malware response</span></span>  <br/> |<span data-ttu-id="f6f3c-268">**検出されたマルウェアを含む現在および今後の電子メールと添付ファイルをブロックする**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-268">Select **Block - Block the current and future emails and attachments with detected malware**.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-269">検出時に添付ファイルをリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="f6f3c-269">Redirect attachment on detection</span></span>  <br/> |<span data-ttu-id="f6f3c-270">リダイレクトを有効にする (このボックスをオンにする) 管理者アカウントまたは検疫用のメールボックスのセットアップを入力します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-270">Enable redirection (select this box)          Enter the admin account or a mailbox setup for quarantine.</span></span>          <span data-ttu-id="f6f3c-271">マルウェアスキャンによる添付ファイルのタイムアウトまたはエラーが発生した場合は、上記の選択を適用します (このチェックボックスをオンにします)。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-271">Apply the above selection if malware scanning for attachments times out or error occurs (select this box).</span></span>  <br/> |
|<span data-ttu-id="f6f3c-272">適用対象</span><span class="sxs-lookup"><span data-stu-id="f6f3c-272">Applied to</span></span>  <br/> |<span data-ttu-id="f6f3c-273">受信者のドメインはです。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-273">The recipient domain is .</span></span> <span data-ttu-id="f6f3c-274">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-274"></span></span> <span data-ttu-id="f6f3c-275">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-275"></span></span> <span data-ttu-id="f6f3c-276">ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-276">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="f6f3c-277">詳細については、「 [Office 365 ATP のフィッシング対策ポリシーを](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409)セットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-277">For more information, see [Set up Office 365 ATP anti-phishing policies](https://go.microsoft.com/fwlink/?linkid=2016505&amp;clcid=0x409).</span></span>
  


## <a name="protect-against-phishing-attacks-with-atp-safe-links"></a><span data-ttu-id="f6f3c-278">ATP の安全なリンクによるフィッシング攻撃から保護する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-278">Protect against phishing attacks with ATP Safe Links</span></span>

<span data-ttu-id="f6f3c-279">ハッカーは、電子メールやその他のファイル内のリンクに悪意のある web サイトを表示しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-279">Hackers sometimes hide malicious websites in links in email or other files.</span></span> <span data-ttu-id="f6f3c-280">Office 365 の ATP の安全なリンク (ATP の安全なリンク)、Office 365 Advanced Threat Protection の一部では、電子メールメッセージや Office ドキュメント内の web アドレス (Url) をクリックすると、組織の保護に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-280">Office 365 ATP Safe Links (ATP Safe Links), part of Office 365 Advanced Threat Protection, can help protect your organization by providing time-of-click verification of web addresses (URLs) in email messages and Office documents.</span></span> <span data-ttu-id="f6f3c-281">保護は、ATP の安全なリンクポリシーによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-281">Protection is defined through ATP Safe Links policies.</span></span>
  
<span data-ttu-id="f6f3c-282">次の手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-282">We recommend that you do the following:</span></span>
  
- <span data-ttu-id="f6f3c-283">既定のポリシーを変更して、保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-283">Modify the default policy to increase protection.</span></span>
    
- <span data-ttu-id="f6f3c-284">ドメイン内のすべての受信者を対象とした新しいポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-284">Add a new policy targeted to all recipients in your domain.</span></span>
    
<span data-ttu-id="f6f3c-285">ATP の安全なリンクを設定するには、[この短いトレーニングビデオ](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)を見るか、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-285">To set up ATP Safe Links, watch [this short training video](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), or complete the following steps:</span></span>
  
1. <span data-ttu-id="f6f3c-286">に[https://protection.office.com](https://protection.office.com)移動し、管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-286">Go to [https://protection.office.com](https://protection.office.com) and sign in with your admin account.</span></span> 
    
2. <span data-ttu-id="f6f3c-287">Office 365 セキュリティ&amp; /コンプライアンスセンターの左側のナビゲーションウィンドウで、[**脅威の管理**] の下にある [**ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-287">In the Office 365 Security &amp; Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="f6f3c-288">[ポリシー] ページで、[ **ATP 安全なリンク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-288">On the Policy page, choose **ATP Safe Links**.</span></span>
    
<span data-ttu-id="f6f3c-289">既定のポリシーを変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-289">To modify the default policy:</span></span>
  
1. <span data-ttu-id="f6f3c-290">[安全なリンク] ページの [**組織全体に適用されるポリシー**] で、[**既定**のポリシー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-290">On the Safe links page, under **Policies that apply to the entire organization**, select the **Default** policy.</span></span> 
    
2. <span data-ttu-id="f6f3c-291">[**電子メール以外のコンテンツに適用する設定**] で、[ **office 365 ProPlus]、[office for IOS、および Android**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-291">Under **Settings that apply to content except email**, select **Office 365 ProPlus, Office for iOS and Android**.</span></span>
    
3. <span data-ttu-id="f6f3c-292">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-292">Click **Save**.</span></span> 
    
<span data-ttu-id="f6f3c-293">ドメイン内のすべての受信者を対象とした新しいポリシーを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-293">To create a new policy targeted to all recipients in your domain:</span></span>
  
1. <span data-ttu-id="f6f3c-294">[安全なリンク] ページの [**組織全体に適用されるポリシー**] **+** で、[] をクリックして新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-294">On the Safe links page, under **Policies that apply to the entire organization**, click **+** to create a new policy.</span></span> 
    
2. <span data-ttu-id="f6f3c-295">次の表に示す設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-295">Apply the settings listed in the following table.</span></span>
    
3. <span data-ttu-id="f6f3c-296">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-296">Click **Save**.</span></span> 

|<span data-ttu-id="f6f3c-297">**設定またはオプション**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-297">**Setting or option**</span></span>|<span data-ttu-id="f6f3c-298">**推奨設定**</span><span class="sxs-lookup"><span data-stu-id="f6f3c-298">**Recommended setting**</span></span> <br/>|
|:-----|:-----|
|<span data-ttu-id="f6f3c-299">名前</span><span class="sxs-lookup"><span data-stu-id="f6f3c-299">Name</span></span>  <br/> |<span data-ttu-id="f6f3c-300">ドメイン内のすべての受信者に対する安全なリンクポリシー</span><span class="sxs-lookup"><span data-stu-id="f6f3c-300">Safe links policy for all recipients in the domain</span></span>  <br/> |
|<span data-ttu-id="f6f3c-301">メッセージ内の不明な潜在的な悪意のある Url に対するアクションを選択する</span><span class="sxs-lookup"><span data-stu-id="f6f3c-301">Select the action for unknown potentially malicious URLs in messages</span></span>  <br/> |<span data-ttu-id="f6f3c-302">[オン] を選択すると **、ユーザーがリンクをクリックしたときに、既知の悪意のあるリンクの一覧に対して、url が書き換えられ、チェックされ**ます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-302">Select **On - URLs will be rewritten and checked against a list of known malicious links when user clicks on the link**.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-303">安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする</span><span class="sxs-lookup"><span data-stu-id="f6f3c-303">Use Safe Attachments to scan downloadable content</span></span>  <br/> |<span data-ttu-id="f6f3c-304">このボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-304">Select this box.</span></span>  <br/> |
|<span data-ttu-id="f6f3c-305">適用対象</span><span class="sxs-lookup"><span data-stu-id="f6f3c-305">Applied to</span></span>  <br/> |<span data-ttu-id="f6f3c-306">受信者のドメインはです。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-306">The recipient domain is .</span></span> <span data-ttu-id="f6f3c-307">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-307"></span></span> <span data-ttu-id="f6f3c-308">.</span><span class="sxs-lookup"><span data-stu-id="f6f3c-308"></span></span> <span data-ttu-id="f6f3c-309">ドメインを選びます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-309">select your domain.</span></span>  <br/> |
   
<span data-ttu-id="f6f3c-310">詳細については、「 [Office 365 ATP safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-310">For more information, see [Office 365 ATP safe links](https://go.microsoft.com/fwlink/?linkid=2016138&amp;clcid=0x409).</span></span>

## <a name="go-to-intune-admin-center"></a><span data-ttu-id="f6f3c-311">Intune 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-311">Go to Intune admin center</span></span>

1. <span data-ttu-id="f6f3c-312">[Azure portal](https://portal.azure.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-312">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="f6f3c-313">[**すべてのサービス**] を選択し、**検索ボックス**に「 *Intune* 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-313">Select **All services** and type in *Intune* in the **Search Box**.</span></span>

3. <span data-ttu-id="f6f3c-314">結果が表示されたら、[ **Microsoft Intune** ] の横にある [開始] をクリックして、お気に入りにし、後で見つけやすいようにします。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-314">Once the results display, click the start next to **Microsoft Intune** to make it a favorite and easy to find later.</span></span>

<span data-ttu-id="f6f3c-315">管理センターに加えて、Intune を使用して組織のデバイスを登録および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-315">In addition to the admin center, you can use Intune to enroll and manage your organization's devices.</span></span> <span data-ttu-id="f6f3c-316">詳細については、「 [Windows デバイスの登録方法](https://docs.microsoft.com/intune/enrollment-method-capabs)」および「 [Intune によって管理されるデバイスの登録オプション](https://docs.microsoft.com/intune/enrollment-options)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f3c-316">For more information, see [Capabilities by enrollment method for Windows devices](https://docs.microsoft.com/intune/enrollment-method-capabs) and [Enrollment options for devices managed by Intune](https://docs.microsoft.com/intune/enrollment-options).</span></span>
