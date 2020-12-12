---
title: Outlook ルールとカスタム フォーム インジェクション攻撃を検出して修復します。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 で Outlook ルールとカスタム フォーム インジェクション攻撃を認識して修復する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cbdc41315d64d341248d6900147aabc5a0b9877c
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663645"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a><span data-ttu-id="770dc-103">Outlook ルールとカスタム フォーム インジェクション攻撃を検出して修復する</span><span class="sxs-lookup"><span data-stu-id="770dc-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="770dc-104">**概要** Office 365 で Outlook ルールとカスタム フォーム インジェクション攻撃を認識して修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="770dc-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="770dc-105">Outlook ルールとカスタム フォーム 挿入攻撃とは</span><span class="sxs-lookup"><span data-stu-id="770dc-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="770dc-106">攻撃者がテナンシーのアカウントを侵害してログインした後、攻撃者が発見および削除された後に、その中に残る方法や戻る方法を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-106">After an attacker has breached an account in your tenancy and gets in, they're are going to try and establish a way to stay in or a way to get back in after they are discovered and removed.</span></span> <span data-ttu-id="770dc-107">これは、永続化メカニズムの確立と呼ばれる方法です。</span><span class="sxs-lookup"><span data-stu-id="770dc-107">This is called establishing a persistence mechanism.</span></span> <span data-ttu-id="770dc-108">これを行う 2 つの方法は、Outlook ルールを悪用するか、カスタム フォームを Outlook に挿入する方法です。</span><span class="sxs-lookup"><span data-stu-id="770dc-108">Two ways that they can do this are by exploiting Outlook rules or by injecting custom forms into Outlook.</span></span>
<span data-ttu-id="770dc-109">どちらの場合も、ルールまたはフォームはクラウド サービスからデスクトップ クライアントに同期されます。そのため、クライアント ソフトウェアの完全な形式と再インストールによって、インジェクション メカニズムは排除されません。</span><span class="sxs-lookup"><span data-stu-id="770dc-109">In both cases, the rule or form is synced from the cloud service down to the desktop client, so a full format and re-install of the client software doesn't eliminate the injection mechanism.</span></span> <span data-ttu-id="770dc-110">これは、Outlook クライアント ソフトウェアがクラウド内のメールボックスに再接続すると、ルールとフォームがクラウドから再ダウンロードされるためです。</span><span class="sxs-lookup"><span data-stu-id="770dc-110">This is because when the Outlook client software reconnects to the mailbox in the cloud it will re-download the rules and forms from the cloud.</span></span> <span data-ttu-id="770dc-111">ルールとフォームが設定された後、攻撃者はそれらを使用してリモート コードまたはカスタム コードを実行し、通常はローカル コンピューターにマルウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="770dc-111">Once the rules and forms are in place, the attacker uses them to execute remote or custom code, usually to install malware on the local machine.</span></span> <span data-ttu-id="770dc-112">マルウェアはその後、資格情報を再盗みするか、他の不正なアクティビティを実行します。</span><span class="sxs-lookup"><span data-stu-id="770dc-112">The malware then re-steals credentials or performs other illicit activity.</span></span>
<span data-ttu-id="770dc-113">ここでの良いニュースは、クライアントに最新バージョンのパッチを適用し続ける場合、現在の Outlook クライアントの既定値によって両方のメカニズムがブロックされるので、脅威に対して脆弱ではありません。</span><span class="sxs-lookup"><span data-stu-id="770dc-113">The good news here is that if you keep your clients patched to the latest version, you are not vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="770dc-114">通常、攻撃は次のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="770dc-114">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="770dc-115">**ルールの悪用**:</span><span class="sxs-lookup"><span data-stu-id="770dc-115">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="770dc-116">攻撃者は、ユーザーの 1 人のユーザー名とパスワードを盗んだ。</span><span class="sxs-lookup"><span data-stu-id="770dc-116">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="770dc-117">その後、攻撃者はそのユーザーの Exchange メールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="770dc-117">The attacker then signs in to that users Exchange mailbox.</span></span> <span data-ttu-id="770dc-118">メールボックスは、Exchange Online または Exchange オンプレミスのどちらかにできます。</span><span class="sxs-lookup"><span data-stu-id="770dc-118">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="770dc-119">その後、攻撃者は、メールボックスがルールの条件に一致する電子メールを受信するとトリガーされる転送ルールをメールボックスに作成します。</span><span class="sxs-lookup"><span data-stu-id="770dc-119">The attacker then creates a forwarding rule in the mailbox that is triggered when the mailbox receives an email that matches the criteria of the rule.</span></span> <span data-ttu-id="770dc-120">ルールの条件とトリガー メールの内容は、互いに合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="770dc-120">The criteria of rule and the contents of the trigger email are tailor-made for each other.</span></span>

4. <span data-ttu-id="770dc-121">攻撃者は、通常はメールボックスを使用しているユーザーにトリガー メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="770dc-121">The attacker sends the trigger email to the user who is using their mailbox normally.</span></span>

5. <span data-ttu-id="770dc-122">電子メールを受信すると、ルールがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="770dc-122">When the email is received, the rule is triggered.</span></span> <span data-ttu-id="770dc-123">通常、ルールのアクションは、リモート (WebDAV) サーバー上でアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="770dc-123">The action of the rule is usually to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="770dc-124">アプリケーションは、通常 [、Powershell The"](https://www.powershellempire.com/)などのマルウェアをユーザーのコンピューターにローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="770dc-124">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="770dc-125">マルウェアにより、攻撃者はユーザーのユーザー名とパスワード、または他の資格情報をローカル コンピューターから再び盗み、その他の悪意のあるアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="770dc-125">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="770dc-126">**Forms Exploit**:</span><span class="sxs-lookup"><span data-stu-id="770dc-126">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="770dc-127">攻撃者は、ユーザーの 1 人のユーザー名とパスワードを盗んだ。</span><span class="sxs-lookup"><span data-stu-id="770dc-127">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="770dc-128">その後、攻撃者はそのユーザーの Exchange メールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="770dc-128">The attacker then sign in to that users Exchange mailbox.</span></span> <span data-ttu-id="770dc-129">メールボックスは、Exchange Online または Exchange オンプレミスのどちらかにできます。</span><span class="sxs-lookup"><span data-stu-id="770dc-129">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="770dc-130">その後、攻撃者はカスタム メール フォーム テンプレートを作成し、ユーザーのメールボックスに挿入します。</span><span class="sxs-lookup"><span data-stu-id="770dc-130">The attacker then creates a custom mail form template and inserts it into the user's mailbox.</span></span> <span data-ttu-id="770dc-131">カスタム フォームは、メールボックスがカスタム フォームを読み込む必要がある電子メールを受信するとトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="770dc-131">The custom form is triggered when the mailbox receives an email that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="770dc-132">カスタム フォームと電子メールの形式は、お互いに合わせて調整されます。</span><span class="sxs-lookup"><span data-stu-id="770dc-132">The custom form and the format of email are tailor-made for each other.</span></span>
4. <span data-ttu-id="770dc-133">攻撃者は、通常はメールボックスを使用しているユーザーにトリガー メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="770dc-133">The attacker sends the trigger email to the user, who is using their mailbox normally.</span></span>

5. <span data-ttu-id="770dc-134">電子メールを受信すると、フォームが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="770dc-134">When the email is received, the form is loaded.</span></span> <span data-ttu-id="770dc-135">フォームは、リモート (WebDAV) サーバー上でアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="770dc-135">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="770dc-136">アプリケーションは、通常 [、Powershell The"](https://www.powershellempire.com/)などのマルウェアをユーザーのコンピューターにローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="770dc-136">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="770dc-137">マルウェアにより、攻撃者はユーザーのユーザー名とパスワード、または他の資格情報をローカル コンピューターから再び盗み、その他の悪意のあるアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="770dc-137">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="770dc-138">ルールとカスタム フォーム 挿入攻撃は 365 Officeしますか?</span><span class="sxs-lookup"><span data-stu-id="770dc-138">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="770dc-139">これらの永続化メカニズムは、ユーザーが気付く可能性が低く、場合によってはユーザーに見えない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="770dc-139">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="770dc-140">この記事では、以下に示す 7 つの兆候 (侵害インジケーター) を探す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="770dc-140">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="770dc-141">これらが見つけた場合は、修復手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-141">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="770dc-142">ルールの侵害を示すインジケーター:</span><span class="sxs-lookup"><span data-stu-id="770dc-142">Indicators of the Rules compromise:</span></span>

  - <span data-ttu-id="770dc-143">ルールの処理として、アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="770dc-143">Rule Action is to start an application.</span></span>

  - <span data-ttu-id="770dc-144">ルールは、EXE、ZIP、または URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="770dc-144">Rule References an EXE, ZIP, or URL.</span></span>

  - <span data-ttu-id="770dc-145">ローカル コンピューターで、Outlook PID から始まる新しいプロセスの開始を探します。</span><span class="sxs-lookup"><span data-stu-id="770dc-145">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="770dc-146">ユーザー設定フォームの侵害を示すインジケーター:</span><span class="sxs-lookup"><span data-stu-id="770dc-146">Indicators of the Custom forms compromise:</span></span>

  - <span data-ttu-id="770dc-147">独自のメッセージ クラスとして保存されたユーザー設定フォーム。</span><span class="sxs-lookup"><span data-stu-id="770dc-147">Custom form present saved as their own message class.</span></span>

  - <span data-ttu-id="770dc-148">メッセージ クラスに実行可能コードが含まれている。</span><span class="sxs-lookup"><span data-stu-id="770dc-148">Message class contains executable code.</span></span>

  - <span data-ttu-id="770dc-149">通常、個人用フォーム ライブラリまたは受信トレイ フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="770dc-149">Usually stored in Personal Forms Library or Inbox folders.</span></span>

  - <span data-ttu-id="770dc-150">フォームの名前は IPM です。注:[custom name].</span><span class="sxs-lookup"><span data-stu-id="770dc-150">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="770dc-151">この攻撃の兆候を見つけて確認するための手順</span><span class="sxs-lookup"><span data-stu-id="770dc-151">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="770dc-152">攻撃を確認するには、次の 2 つの方法のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="770dc-152">You can use either of these two methods to confirm the attack:</span></span>

- <span data-ttu-id="770dc-153">Outlook クライアントを使用して、各メールボックスのルールとフォームを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="770dc-153">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="770dc-154">この方法は徹底的ですが、確認するユーザーが多い場合は、一度にしかメールボックス ユーザーをチェックできませんが、非常に時間がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-154">This method is thorough, but you can only check mailbox user at a time which can be very time consuming if you have many users to check.</span></span> <span data-ttu-id="770dc-155">また、チェックを実行しているコンピューターが侵害される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-155">It can also result in a breach of the computer that you are running the check from.</span></span>

- <span data-ttu-id="770dc-156">PowerShell [ スクリプトGet-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) 使用して、テナンシー内のすべてのユーザーのすべてのメール転送ルールとカスタム フォームを自動的にダンプします。</span><span class="sxs-lookup"><span data-stu-id="770dc-156">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="770dc-157">これは、オーバーヘッドが最も少ない最も速く安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="770dc-157">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="770dc-158">Outlook クライアントを使用してルール攻撃を確認する</span><span class="sxs-lookup"><span data-stu-id="770dc-158">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="770dc-159">ユーザーとして Outlook クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="770dc-159">Open the users Outlook client as the user.</span></span> <span data-ttu-id="770dc-160">ユーザーは、自分のメールボックスのルールを調べる上でヘルプが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-160">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="770dc-161">Outlook で [ルール インターフェイスを開](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) く方法の手順については、「ルールを使用して電子メール メッセージを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="770dc-161">Refer to [Manage email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="770dc-162">ユーザーが作成しなかったルール、または不審な名前を持つ予期しないルールやルールを探します。</span><span class="sxs-lookup"><span data-stu-id="770dc-162">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="770dc-163">ルールの説明で、ルールの処理を開始し、適用または参照するルールの説明を確認します。EXE, .ZIP ファイルまたは URL の起動。</span><span class="sxs-lookup"><span data-stu-id="770dc-163">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="770dc-164">Outlook プロセス ID の使用を開始する新しいプロセスを探します。</span><span class="sxs-lookup"><span data-stu-id="770dc-164">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="770dc-165">「プロセス [ID の検索」を参照してください](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)。</span><span class="sxs-lookup"><span data-stu-id="770dc-165">Refer to [Find the Process ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="770dc-166">Outlook クライアントを使用してフォーム攻撃を確認する手順</span><span class="sxs-lookup"><span data-stu-id="770dc-166">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="770dc-167">ユーザーとして Outlook クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="770dc-167">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="770dc-168">Outlook のユーザー バージョンの [開発] [タブ](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="770dc-168">Follow the steps in, [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the users version of Outlook.</span></span>

3. <span data-ttu-id="770dc-169">Outlook で表示されている [開発] タブを開き、フォーム **のデザインをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="770dc-169">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="770dc-170">[参照 **先]** ボックスの一 **覧から受信トレイを選択** します。</span><span class="sxs-lookup"><span data-stu-id="770dc-170">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="770dc-171">ユーザー設定フォームを探します。</span><span class="sxs-lookup"><span data-stu-id="770dc-171">Look for any custom forms.</span></span> <span data-ttu-id="770dc-172">ユーザー設定フォームはまれであり、ユーザー設定フォームがある場合は、より深く見る価値があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-172">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="770dc-173">カスタム フォーム (特に非表示としてマークされているフォーム) を調査します。</span><span class="sxs-lookup"><span data-stu-id="770dc-173">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="770dc-174">ユーザー設定フォームを開き、フォーム グループで [コードの表示] をクリックして、フォームが読み込まれたときに実行される動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="770dc-174">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="770dc-175">PowerShell を使用してルールとフォーム攻撃を確認する手順</span><span class="sxs-lookup"><span data-stu-id="770dc-175">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="770dc-176">ルールまたはカスタム フォーム攻撃を確認する最も簡単な方法は、PowerShell [ スクリプトGet-AllTenantRulesAndForms.ps1実行 ](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) する方法です。</span><span class="sxs-lookup"><span data-stu-id="770dc-176">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="770dc-177">このスクリプトはテナント内のすべてのメールボックスに接続し、すべてのルールとフォームを 2 つの .csv ファイルにダンプします。</span><span class="sxs-lookup"><span data-stu-id="770dc-177">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="770dc-178">前提条件</span><span class="sxs-lookup"><span data-stu-id="770dc-178">Pre-requisites</span></span>

<span data-ttu-id="770dc-179">スクリプトはテナント内のすべてのメールボックスに接続してルールとフォームを読み取るので、スクリプトを実行するにはグローバル管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="770dc-179">You will need to have a global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="770dc-180">ローカル管理者権限でスクリプトを実行するコンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="770dc-180">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="770dc-181">GitHub からGet-AllTenantRulesAndForms.ps1スクリプトを、実行するフォルダーにダウンロードまたはコピーします。</span><span class="sxs-lookup"><span data-stu-id="770dc-181">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="770dc-182">このスクリプトは、このフォルダーに 2 つの日付スタンプ付きファイルを作成し、MailboxFormsExport-yyyy-mm-dd.csv、MailboxRulesExport-yyyy-mm-dd.csv。</span><span class="sxs-lookup"><span data-stu-id="770dc-182">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="770dc-183">管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="770dc-183">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="770dc-184">次のコマンドを使用して、この PowerShell コマンド `.\Get-AllTenantRulesAndForms.ps1` ラインを.\Get-AllTenantRulesAndForms.ps1</span><span class="sxs-lookup"><span data-stu-id="770dc-184">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="770dc-185">出力の解釈</span><span class="sxs-lookup"><span data-stu-id="770dc-185">Interpreting the output</span></span>

- <span data-ttu-id="770dc-186">**MailboxRulesExport-*yyyy-mm-dd*.csv**: アプリケーションまたは実行可能ファイルを含むアクション条件のルール (1 行に 1 つ) を調べてください。</span><span class="sxs-lookup"><span data-stu-id="770dc-186">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="770dc-187">**ActionType (列 A)**: 値 "ID_ACTION_CUSTOM" が表示される場合、ルールは悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-187">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="770dc-188">**IsPotentiallyMalicious (列 D)**: この値が "TRUE" の場合、ルールは悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-188">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="770dc-189">**ActionCommand (列 G)**: .exe、.zip 拡張子、または URL を参照するエントリを持つアプリケーションまたはファイルの一覧が表示される場合、その URL とは見なされない場合、ルールは悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-189">**ActionCommand (column G)**: If this lists an application or any file with a .exe, .zip extension or an entry that refers to a URL, that is not supposed to be there, the rule is likely malicious.</span></span>

- <span data-ttu-id="770dc-190">**MailboxFormsExport-*yyyy-mm-dd*.csv**: 一般に、ユーザー設定フォームの使用は非常にまれです。</span><span class="sxs-lookup"><span data-stu-id="770dc-190">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is very rare.</span></span> <span data-ttu-id="770dc-191">このブックに何か見つけた場合は、そのユーザーのメールボックスを開き、フォーム自体を調べてください。</span><span class="sxs-lookup"><span data-stu-id="770dc-191">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="770dc-192">組織が意図的にそこに置かなかった場合は、悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-192">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="770dc-193">Outlook のルールとフォーム攻撃を停止して修復する方法</span><span class="sxs-lookup"><span data-stu-id="770dc-193">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="770dc-194">これらの攻撃のどちらかの証拠が見つかった場合、修復は簡単で、メールボックスからルールまたはフォームを削除します。</span><span class="sxs-lookup"><span data-stu-id="770dc-194">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="770dc-195">これを行うには、Outlook クライアントまたはリモート PowerShell を使用してルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="770dc-195">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="770dc-196">Outlook の使用</span><span class="sxs-lookup"><span data-stu-id="770dc-196">Using Outlook</span></span>

1. <span data-ttu-id="770dc-197">ユーザーが Outlook で使用したデバイスを識別します。</span><span class="sxs-lookup"><span data-stu-id="770dc-197">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="770dc-198">これらはすべて、潜在的なマルウェアを除去する必要があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-198">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="770dc-199">すべてのデバイスがクリーンアップされるまで、ユーザーがサインオンして電子メールを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="770dc-199">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="770dc-200">「デバイスごとにルールを [削除する」の](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) 手順に従います。</span><span class="sxs-lookup"><span data-stu-id="770dc-200">Follow the steps in [Delete a rule](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="770dc-201">他のマルウェアの存在が不明な場合は、デバイス上のすべてのソフトウェアのフォーマットと再インストールを行います。</span><span class="sxs-lookup"><span data-stu-id="770dc-201">If you are unsure about the presence of other malware, you can format and re-install all the software on the device.</span></span> <span data-ttu-id="770dc-202">モバイル デバイスの場合は、製造元の手順に従って、デバイスを出荷時のイメージにリセットできます。</span><span class="sxs-lookup"><span data-stu-id="770dc-202">For mobile devices you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="770dc-203">最新バージョンの Outlook をインストールします。</span><span class="sxs-lookup"><span data-stu-id="770dc-203">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="770dc-204">現在のバージョンの Outlook では、既定でこの両方の種類の攻撃がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="770dc-204">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="770dc-205">メールボックスのすべてのオフライン コピーが削除された後、ユーザーのパスワードをリセットし (高品質のパスワードを使用)、MFA が有効になっていない場合[](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)は、ユーザーの多要素認証をセットアップする手順に従います。</span><span class="sxs-lookup"><span data-stu-id="770dc-205">Once all offline copies of the mailbox have been removed, reset the user's password (use a high-quality one) and follow the steps in [Setup multi-factor authentication for users](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) if MFA has not already been enabled.</span></span> <span data-ttu-id="770dc-206">これにより、ユーザーの資格情報が他の手段 (フィッシングやパスワードの再使用など) によって公開されません。</span><span class="sxs-lookup"><span data-stu-id="770dc-206">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="770dc-207">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="770dc-207">Using PowerShell</span></span>

<span data-ttu-id="770dc-208">危険なルールを削除または無効化するには、2 つのリモート PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="770dc-208">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="770dc-209">手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="770dc-209">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="770dc-210">Exchange サーバー上のメールボックスの手順</span><span class="sxs-lookup"><span data-stu-id="770dc-210">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="770dc-211">リモート PowerShell を使用して Exchange サーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="770dc-211">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="770dc-212">リモート PowerShell を使用 [して Exchange サーバーに接続する手順に従います](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="770dc-212">Follow the steps in [Connect to Exchange servers using remote PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="770dc-213">メールボックスから 1 つのルール、複数のルール、またはすべてのルールを完全に削除する場合は [、Remove-InboxRule コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) します。</span><span class="sxs-lookup"><span data-stu-id="770dc-213">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="770dc-214">詳細な調査のためにルールとその内容を保持する場合は [、Disable-InboxRule コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) します。</span><span class="sxs-lookup"><span data-stu-id="770dc-214">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="770dc-215">Exchange Online のメールボックスの手順</span><span class="sxs-lookup"><span data-stu-id="770dc-215">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="770dc-216">PowerShell を使用して [Exchange Online に接続する手順に従います](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="770dc-216">Follow the steps in [Connect to Exchange Online using PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="770dc-217">メールボックスから 1 つのルール、複数のルール、またはすべてのルールを完全に削除する場合は [、Remove-Inbox Rule コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) します。</span><span class="sxs-lookup"><span data-stu-id="770dc-217">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="770dc-218">詳細な調査のためにルールとその内容を保持する場合は [、Disable-InboxRule コマンドレットを使用](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) します。</span><span class="sxs-lookup"><span data-stu-id="770dc-218">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="770dc-219">今後の攻撃を最小限にする方法</span><span class="sxs-lookup"><span data-stu-id="770dc-219">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="770dc-220">最初に:アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="770dc-220">First: protect your accounts</span></span>

<span data-ttu-id="770dc-221">ルールとフォームの悪用は、攻撃者がユーザーのアカウントの 1 つを盗難または侵害した後にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="770dc-221">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="770dc-222">そのため、組織に対するこれらの悪用の使用を防ぐための最初の手順は、ユーザー アカウントを積極的に保護する方法です。</span><span class="sxs-lookup"><span data-stu-id="770dc-222">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="770dc-223">アカウントが侵害される最も一般的な方法のいくつかは、フィッシング攻撃またはパスワード スプレー [攻撃](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) です。</span><span class="sxs-lookup"><span data-stu-id="770dc-223">Some of the most common ways that accounts are breached are through phishing or [password spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) attacks.</span></span>

<span data-ttu-id="770dc-224">ユーザー アカウント、特に管理者アカウントを保護する最善の方法は、ユーザーの多要素認証 [を設定する方法です](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="770dc-224">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for users](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span> <span data-ttu-id="770dc-225">また、以下も行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-225">You should also:</span></span>

- <span data-ttu-id="770dc-226">ユーザー アカウントのアクセス方法と使用 [方法を監視します](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)。</span><span class="sxs-lookup"><span data-stu-id="770dc-226">Monitor how your user accounts are [accessed and used](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="770dc-227">最初の違反を防ぐことはできない場合がありますが、違反を早く検出することで、その期間と影響を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="770dc-227">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="770dc-228">これらの [365 Cloud App Security Officeを](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 使用して、アカウントを監視し、異常なアクティビティについて警告することができます。</span><span class="sxs-lookup"><span data-stu-id="770dc-228">You can use these [Office 365 Cloud App Security policies](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="770dc-229">複数 **の** ログイン試行の失敗 : このポリシーは、環境のプロファイルを作成し、ユーザーが 1 つのセッションで複数の失敗したログイン アクティビティを実行するときにアラートをトリガーします。このアクティビティは、侵害の試行を示している可能性がある、学習済みベースラインに関して実行されます。</span><span class="sxs-lookup"><span data-stu-id="770dc-229">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="770dc-230">**移動** 不可能 : このポリシーは、環境のプロファイルを作成し、2 つの場所間の予想される移動時間よりも短い期間に、同じユーザーから異なる場所でアクティビティが検出された場合にアラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="770dc-230">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="770dc-231">これは、別のユーザーが同じ資格情報を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-231">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="770dc-232">この異常な動作を検出するには、新しいユーザーのアクティビティ パターンを学習する最初の学習期間が 7 日間必要です。</span><span class="sxs-lookup"><span data-stu-id="770dc-232">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="770dc-233">**(** ユーザーによる) 異常な偽装アクティビティ: このポリシーは、ユーザーが学習したベースラインに関して 1 つのセッションで複数の偽装アクティビティを実行すると、環境のプロファイルを作成し、アラートをトリガーします。これは、侵害の試行を示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-233">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="770dc-234">365 セキュア スコアOffice [ツールを利用](https://securescore.office.com/) して、アカウントのセキュリティ構成と動作を管理します。</span><span class="sxs-lookup"><span data-stu-id="770dc-234">Leverage a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="770dc-235">2 番目: Outlook クライアントを最新の状態に保つ</span><span class="sxs-lookup"><span data-stu-id="770dc-235">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="770dc-236">Outlook 2013 および 2016 の完全に更新および修正されたバージョンでは、"アプリケーションの開始" ルール/フォーム アクションが既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="770dc-236">Fully-updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="770dc-237">これにより、攻撃者がアカウントを侵害した場合でも、ルールとフォームのアクションがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="770dc-237">This will ensure that, even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="770dc-238">「更新プログラムのインストール」の手順に従って、最新の更新プログラムとセキュリティ 修正 [プログラムOfficeできます](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)。</span><span class="sxs-lookup"><span data-stu-id="770dc-238">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="770dc-239">Outlook 2013 および 2016 クライアントの修正プログラムのバージョンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="770dc-239">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="770dc-240">**Outlook 2016**: 16.0.4534.1001 以上。</span><span class="sxs-lookup"><span data-stu-id="770dc-240">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="770dc-241">**Outlook 2013**: 15.0.4937.1000 以上。</span><span class="sxs-lookup"><span data-stu-id="770dc-241">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="770dc-242">個々のセキュリティ 修正プログラムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="770dc-242">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="770dc-243">Outlook 2016 セキュリティ更新プログラム</span><span class="sxs-lookup"><span data-stu-id="770dc-243">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="770dc-244">Outlook 2013 セキュリティ更新プログラム</span><span class="sxs-lookup"><span data-stu-id="770dc-244">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="770dc-245">3 番目: Outlook クライアントを監視する</span><span class="sxs-lookup"><span data-stu-id="770dc-245">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="770dc-246">修正プログラムと更新プログラムがインストールされている場合でも、攻撃者はローカル コンピューターの構成を変更して "アプリケーションの起動" 動作を再び有効にできる点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="770dc-246">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="770dc-247">Advanced [Group Policy Management を使用すると](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) 、クライアントでローカル コンピューター ポリシーを監視および適用できます。</span><span class="sxs-lookup"><span data-stu-id="770dc-247">You can use [Advanced Group Policy Management](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="770dc-248">[「64](https://support.microsoft.com/help/305097)ビット バージョンの Windows を使用してシステム レジストリを表示する方法」の情報を使用して、レジストリ内のオーバーライドによって "アプリケーションの起動" が再び有効になっているか確認できます。</span><span class="sxs-lookup"><span data-stu-id="770dc-248">You can to see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097).</span></span> <span data-ttu-id="770dc-249">次のサブキーを確認します。</span><span class="sxs-lookup"><span data-stu-id="770dc-249">Check these subkeys:</span></span>

- <span data-ttu-id="770dc-250">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="770dc-250">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="770dc-251">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="770dc-251">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="770dc-252">EnableUnsafeClientMailRules キーを探します。</span><span class="sxs-lookup"><span data-stu-id="770dc-252">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="770dc-253">この更新プログラムがインストールされ、1 に設定されている場合、Outlook セキュリティ更新プログラムは上書きされ、コンピューターはフォーム/ルール攻撃に対して脆弱です。</span><span class="sxs-lookup"><span data-stu-id="770dc-253">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="770dc-254">値が 0 の場合、"アプリケーションの開始" アクションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="770dc-254">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="770dc-255">更新および修正プログラムが適用されたバージョンの Outlook がインストールされ、このレジストリ キーが存在しない場合、システムはこれらの攻撃に対して脆弱ではありません。</span><span class="sxs-lookup"><span data-stu-id="770dc-255">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="770dc-256">オンプレミスの Exchange インストールを使用しているお客様は、利用可能な修正プログラムを含めずに古いバージョンの Outlook をブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="770dc-256">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="770dc-257">このプロセスの詳細については、「Outlook クライアントのブロックを構成する」 [を参照してください](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="770dc-257">Details on this process can be found in the article [Configure Outlook client blocking](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="770dc-258">サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="770dc-258">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="770dc-259">Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="770dc-259">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="770dc-260">[Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="770dc-260">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="770dc-261">最初の 30 日以内に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="770dc-261">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="770dc-262">これらはすぐに影響を受け、ユーザーへの影響は低い。</span><span class="sxs-lookup"><span data-stu-id="770dc-262">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="770dc-p135">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="770dc-p135">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="770dc-p136">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="770dc-p136">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="770dc-267">関連項目:</span><span class="sxs-lookup"><span data-stu-id="770dc-267">See also:</span></span>

- <span data-ttu-id="770dc-268">[Rules Vector に関](https://silentbreaksecurity.com/malicious-outlook-rules/) する SilentBreak セキュリティ投稿による悪意のある Outlook ルールは、Outlook ルールの詳細なレビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="770dc-268">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="770dc-269">Mailrule Pwnage に関する Sensepost ブログの MAPI over HTTP および[Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)では、Outlook ルールを使用してメールボックスを悪用できる Ruler というツールについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="770dc-269">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="770dc-270">Forms Threat Vector[に関する](https://sensepost.com/blog/2017/outlook-forms-and-shells/)Sensepost ブログの Outlook フォームとシェル。</span><span class="sxs-lookup"><span data-stu-id="770dc-270">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="770dc-271">Ruler Codebase</span><span class="sxs-lookup"><span data-stu-id="770dc-271">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="770dc-272">侵害のルーラー インジケーター</span><span class="sxs-lookup"><span data-stu-id="770dc-272">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)
