---
title: ルールとカスタム フォームOutlook攻撃を検出して修復します。
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
localization_priority: Normal
search.appverid:
- MET150
description: カスタム フォーム のルールとカスタム フォームOutlook攻撃を認識して修復する方法について説明Office 365
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205919"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a><span data-ttu-id="55f97-103">ルールとカスタム フォームOutlook攻撃を検出して修復する</span><span class="sxs-lookup"><span data-stu-id="55f97-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="55f97-104">**概要** このページでは、フォーム ルールとカスタムフォームOutlook攻撃を認識して修復する方法についてOffice 365。</span><span class="sxs-lookup"><span data-stu-id="55f97-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="55f97-105">ルールとカスタム フォームOutlook攻撃とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="55f97-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="55f97-106">攻撃者が組織へのアクセス権を取得した後、攻撃者は、発見された後もその場所に滞在するか、または戻って行く足場を確立しようと試みる。</span><span class="sxs-lookup"><span data-stu-id="55f97-106">After an attacker gains access to your organization, they'll try to establish a foothold to stay in or get back in after they've been discovered.</span></span> <span data-ttu-id="55f97-107">このアクティビティは、永続 *化メカニズムの確立と呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="55f97-107">This activity is called *establishing a persistence mechanism*.</span></span> <span data-ttu-id="55f97-108">攻撃者がデータベースを使用して、Outlookメカニズムを確立するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-108">There are two ways that an attacker can use Outlook to establish a persistence mechanism:</span></span>

- <span data-ttu-id="55f97-109">ルールを悪用Outlook使用します。</span><span class="sxs-lookup"><span data-stu-id="55f97-109">By exploiting Outlook rules.</span></span>
- <span data-ttu-id="55f97-110">カスタム フォームをカスタム フォームに挿入Outlook。</span><span class="sxs-lookup"><span data-stu-id="55f97-110">By injecting custom forms into Outlook.</span></span>

<span data-ttu-id="55f97-111">ユーザー Outlook再インストールしたり、影響を受けるユーザーに新しいコンピューターを与えても、問題はありません。</span><span class="sxs-lookup"><span data-stu-id="55f97-111">Reinstalling Outlook, or even giving the affected person a new computer won't help.</span></span> <span data-ttu-id="55f97-112">サーバーの新しいインストールOutlookメールボックスに接続すると、すべてのルールとフォームがクラウドから同期されます。</span><span class="sxs-lookup"><span data-stu-id="55f97-112">When the fresh installation of Outlook connects to the mailbox, all rules and forms are synchronized from the cloud.</span></span> <span data-ttu-id="55f97-113">通常、ルールまたはフォームは、リモート コードを実行し、ローカル コンピューターにマルウェアをインストールするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="55f97-113">The rules or forms are typically designed to run remote code and install malware on the local machine.</span></span> <span data-ttu-id="55f97-114">マルウェアは資格情報を盗んだり、他の不正なアクティビティを実行したりします。</span><span class="sxs-lookup"><span data-stu-id="55f97-114">The malware steals credentials or performs other illicit activity.</span></span>

<span data-ttu-id="55f97-115">良いニュースは、Outlook クライアントに最新バージョンへのパッチを適用し続ける場合、現在の Outlook クライアントの既定値が両方のメカニズムをブロックする脅威に対して脆弱ではありません。</span><span class="sxs-lookup"><span data-stu-id="55f97-115">The good news is: if you keep your Outlook clients patched to the latest version, you aren't vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="55f97-116">通常、攻撃は次のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="55f97-116">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="55f97-117">**ルールの悪用**:</span><span class="sxs-lookup"><span data-stu-id="55f97-117">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="55f97-118">攻撃者はユーザーの資格情報を盗む。</span><span class="sxs-lookup"><span data-stu-id="55f97-118">The attacker steals a user's credentials.</span></span>

2. <span data-ttu-id="55f97-119">攻撃者は、そのユーザーのメールボックス (ExchangeまたはExchange Online) にサインインExchange。</span><span class="sxs-lookup"><span data-stu-id="55f97-119">The attacker signs in to that user's Exchange mailbox (Exchange Online or on-premises Exchange).</span></span>

3. <span data-ttu-id="55f97-120">攻撃者はメールボックスに転送受信トレイ ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="55f97-120">The attacker creates a forwarding Inbox rule in the mailbox.</span></span> <span data-ttu-id="55f97-121">転送ルールは、メールボックスがルールの条件に一致する特定のメッセージを攻撃者から受信するとトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="55f97-121">The forwarding rule is triggered when the mailbox receives a specific message from the attacker that matches the conditions of the rule.</span></span> <span data-ttu-id="55f97-122">ルールの条件とメッセージ形式は、お互いに合わせてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="55f97-122">The rule conditions and message format are tailor-made for each other.</span></span>

4. <span data-ttu-id="55f97-123">攻撃者は侵害されたメールボックスにトリガー 電子メールを送信します。これは、疑いのないユーザーが通常通り使用しています。</span><span class="sxs-lookup"><span data-stu-id="55f97-123">The attacker sends the trigger email to the compromised mailbox, which is still being used as normal by the unsuspecting user.</span></span>

5. <span data-ttu-id="55f97-124">メールボックスがルールの条件に一致するメッセージを受信すると、ルールのアクションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="55f97-124">When the mailbox receives a message that matches the conditions of rule, the action of the rule is applied.</span></span> <span data-ttu-id="55f97-125">通常、ルールアクションは、リモート (WebDAV) サーバー上でアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="55f97-125">Typically, the rule action is to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="55f97-126">通常、アプリケーションはユーザーのコンピューター (PowerShell Empire など) に [マルウェアをインストールします](https://www.powershellempire.com/)。</span><span class="sxs-lookup"><span data-stu-id="55f97-126">Typically, the application installs malware on the user's machine (for example, [PowerShell Empire](https://www.powershellempire.com/)).</span></span>

7. <span data-ttu-id="55f97-127">このマルウェアにより、攻撃者はユーザーのユーザー名とパスワード、または他の資格情報をローカル コンピューターから盗んだり、その他の悪意のあるアクティビティを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="55f97-127">The malware allows the attacker to steal (or steal again) the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="55f97-128">**フォームエクスプロイト**:</span><span class="sxs-lookup"><span data-stu-id="55f97-128">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="55f97-129">攻撃者はユーザーの資格情報を盗む。</span><span class="sxs-lookup"><span data-stu-id="55f97-129">The attacker steals a user's credentials.</span></span>

2. <span data-ttu-id="55f97-130">攻撃者は、そのユーザーのメールボックス (ExchangeまたはExchange Online) にサインインExchange。</span><span class="sxs-lookup"><span data-stu-id="55f97-130">The attacker signs in to that user's Exchange mailbox (Exchange Online or on-premises Exchange).</span></span>

3. <span data-ttu-id="55f97-131">攻撃者はユーザーのメールボックスにカスタム メール フォーム テンプレートを挿入します。</span><span class="sxs-lookup"><span data-stu-id="55f97-131">The attacker inserts a custom mail form template into the user's mailbox.</span></span> <span data-ttu-id="55f97-132">カスタム フォームは、メールボックスがカスタム フォームを読み込む必要がある攻撃者から特定のメッセージを受信するとトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="55f97-132">The custom form is triggered when the mailbox receives a specific message from the attacker that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="55f97-133">カスタム フォームとメッセージ形式は、お互いに合わせてカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="55f97-133">The custom form and the message format are tailor-made for each other.</span></span>

4. <span data-ttu-id="55f97-134">攻撃者は侵害されたメールボックスにトリガー 電子メールを送信します。これは、疑いのないユーザーが通常通り使用しています。</span><span class="sxs-lookup"><span data-stu-id="55f97-134">The attacker sends the trigger email to the compromised mailbox, which is still being used as normal by the unsuspecting user.</span></span>

5. <span data-ttu-id="55f97-135">メールボックスがメッセージを受信すると、メールボックスは必要なフォームを読み込む。</span><span class="sxs-lookup"><span data-stu-id="55f97-135">When the mailbox receives the message, the mailbox loads the required form.</span></span> <span data-ttu-id="55f97-136">フォームは、リモート (WebDAV) サーバー上でアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="55f97-136">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="55f97-137">通常、アプリケーションはユーザーのコンピューター (PowerShell Empire など) に [マルウェアをインストールします](https://www.powershellempire.com/)。</span><span class="sxs-lookup"><span data-stu-id="55f97-137">Typically, the application installs malware on the user's machine (for example, [PowerShell Empire](https://www.powershellempire.com/)).</span></span>

7. <span data-ttu-id="55f97-138">このマルウェアにより、攻撃者はユーザーのユーザー名とパスワード、または他の資格情報をローカル コンピューターから盗んだり、その他の悪意のあるアクティビティを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="55f97-138">The malware allows the attacker to steal (or steal again) the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="55f97-139">ルールとカスタム フォームインジェクション攻撃は、次のようなOffice 365?</span><span class="sxs-lookup"><span data-stu-id="55f97-139">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="55f97-140">これらの永続化メカニズムは、ユーザーが気付く可能性は低く、場合によってはユーザーに見えない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="55f97-140">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="55f97-141">この記事では、以下に示す 7 つの兆候 (侵害の指標) を探す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55f97-141">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="55f97-142">これらが見つけた場合は、修復手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-142">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="55f97-143">**ルールの侵害のインジケーター**:</span><span class="sxs-lookup"><span data-stu-id="55f97-143">**Indicators of the Rules compromise**:</span></span>
  - <span data-ttu-id="55f97-144">ルール アクションは、アプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="55f97-144">Rule Action is to start an application.</span></span>
  - <span data-ttu-id="55f97-145">ルール EXE、ZIP、または URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="55f97-145">Rule References an EXE, ZIP, or URL.</span></span>
  - <span data-ttu-id="55f97-146">ローカル コンピューターで、PID から始まる新しいプロセスの開始Outlookします。</span><span class="sxs-lookup"><span data-stu-id="55f97-146">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="55f97-147">**カスタム フォームの侵害のインジケーター**:</span><span class="sxs-lookup"><span data-stu-id="55f97-147">**Indicators of the Custom forms compromise**:</span></span>
  - <span data-ttu-id="55f97-148">カスタム フォームは、独自のメッセージ クラスとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="55f97-148">Custom forms present saved as their own message class.</span></span>
  - <span data-ttu-id="55f97-149">メッセージ クラスには、実行可能コードが含まれている。</span><span class="sxs-lookup"><span data-stu-id="55f97-149">Message class contains executable code.</span></span>
  - <span data-ttu-id="55f97-150">通常、悪意のあるフォームは個人用フォーム ライブラリまたは受信トレイ フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="55f97-150">Typically, malicious forms are stored in Personal Forms Library or Inbox folders.</span></span>
  - <span data-ttu-id="55f97-151">Form は IPM という名前です。注。[カスタム名]</span><span class="sxs-lookup"><span data-stu-id="55f97-151">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="55f97-152">この攻撃の兆候を見つけて確認するための手順</span><span class="sxs-lookup"><span data-stu-id="55f97-152">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="55f97-153">攻撃を確認するには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="55f97-153">You can use either of the following methods to confirm the attack:</span></span>

- <span data-ttu-id="55f97-154">クライアントを使用して、各メールボックスのルールとフォームを手動でOutlookします。</span><span class="sxs-lookup"><span data-stu-id="55f97-154">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="55f97-155">この方法は完全ですが、一度に確認できるメールボックスは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="55f97-155">This method is thorough, but you can only check one mailbox at a time.</span></span> <span data-ttu-id="55f97-156">このメソッドは、多くのユーザーが確認する必要があり、使用しているコンピューターに感染する可能性がある場合、非常に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-156">This method can be very time consuming if you have many users to check, and might also infect the computer that you're using.</span></span>

- <span data-ttu-id="55f97-157">PowerShell スクリプト [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) 使用して、テナント内のすべてのユーザーに対してすべてのメール転送ルールとカスタム フォームを自動的にダンプします。</span><span class="sxs-lookup"><span data-stu-id="55f97-157">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="55f97-158">これは、オーバーヘッドの量が最も少ない最も高速で安全なメソッドです。</span><span class="sxs-lookup"><span data-stu-id="55f97-158">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="55f97-159">クライアントを使用してルール攻撃をOutlookする</span><span class="sxs-lookup"><span data-stu-id="55f97-159">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="55f97-160">クライアントのユーザー Outlookユーザーとして開きます。</span><span class="sxs-lookup"><span data-stu-id="55f97-160">Open the users Outlook client as the user.</span></span> <span data-ttu-id="55f97-161">ユーザーが自分のメールボックスのルールを調べるのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-161">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="55f97-162">ルール インターフェイス[を開く](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)方法については、「ルールを使用して電子メール メッセージを管理する」を参照Outlook。</span><span class="sxs-lookup"><span data-stu-id="55f97-162">Refer to [Manage email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="55f97-163">ユーザーが作成しなかったルール、または不審な名前を持つ予期しないルールを探します。</span><span class="sxs-lookup"><span data-stu-id="55f97-163">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="55f97-164">ルールの説明を参照して、ルールアクションを開始および適用するか、.EXE、.ZIPを参照するか、URL を起動します。</span><span class="sxs-lookup"><span data-stu-id="55f97-164">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="55f97-165">プロセス ID の使用を開始する新しいOutlook探します。</span><span class="sxs-lookup"><span data-stu-id="55f97-165">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="55f97-166">「プロセス [ID の検索」を参照してください](/windows-hardware/drivers/debugger/finding-the-process-id)。</span><span class="sxs-lookup"><span data-stu-id="55f97-166">Refer to [Find the Process ID](/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="55f97-167">クライアントを使用して Forms 攻撃を確認Outlook手順</span><span class="sxs-lookup"><span data-stu-id="55f97-167">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="55f97-168">クライアントのユーザー Outlookユーザーとして開きます。</span><span class="sxs-lookup"><span data-stu-id="55f97-168">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="55f97-169">「ユーザーのバージョンの [[開発者]](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45)タブを表示する」の手順に従Outlook。</span><span class="sxs-lookup"><span data-stu-id="55f97-169">Follow the steps in, [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the user's version of Outlook.</span></span>

3. <span data-ttu-id="55f97-170">[フォーム] の [現在表示されている開発者] タブOutlookを開き、[フォーム **のデザイン] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="55f97-170">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="55f97-171">[参照 **先] リスト** から **受信トレイを選択** します。</span><span class="sxs-lookup"><span data-stu-id="55f97-171">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="55f97-172">カスタム フォームを探します。</span><span class="sxs-lookup"><span data-stu-id="55f97-172">Look for any custom forms.</span></span> <span data-ttu-id="55f97-173">カスタム フォームはまれであり、カスタム フォームが全くある場合は、より深い外観を見る価値があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-173">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="55f97-174">カスタム フォーム、特に非表示としてマークされているフォームを調査します。</span><span class="sxs-lookup"><span data-stu-id="55f97-174">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="55f97-175">カスタム フォームを開き、[ **フォーム** ] グループで [コードの表示] **をクリック** して、フォームが読み込まれたときに実行される動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="55f97-175">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="55f97-176">PowerShell を使用してルールとフォーム攻撃を確認する手順</span><span class="sxs-lookup"><span data-stu-id="55f97-176">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="55f97-177">ルールまたはカスタム フォーム攻撃を確認する最も簡単な方法は、PowerShell [ スクリプト ](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1)Get-AllTenantRulesAndForms.ps1実行します。</span><span class="sxs-lookup"><span data-stu-id="55f97-177">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="55f97-178">このスクリプトは、テナント内のすべてのメールボックスに接続し、すべてのルールとフォームを 2 つのファイルに.csvします。</span><span class="sxs-lookup"><span data-stu-id="55f97-178">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="55f97-179">前提条件</span><span class="sxs-lookup"><span data-stu-id="55f97-179">Pre-requisites</span></span>

<span data-ttu-id="55f97-180">スクリプトはテナンシー内のすべてのメールボックスに接続してルールとフォームを読み取るので、スクリプトを実行するにはグローバル管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="55f97-180">You will need to have global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="55f97-181">ローカル管理者権限でスクリプトを実行するコンピューターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="55f97-181">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="55f97-182">スクリプトをダウンロードGet-AllTenantRulesAndForms.ps1からGitHub実行するフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="55f97-182">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="55f97-183">このスクリプトは、このフォルダー、日付スタンプ付きファイル、および日付のMailboxFormsExport-yyyy-mm-dd.csv作成MailboxRulesExport-yyyy-mm-dd.csv。</span><span class="sxs-lookup"><span data-stu-id="55f97-183">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="55f97-184">PowerShell インスタンスを管理者として開き、スクリプトを保存したフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="55f97-184">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="55f97-185">次のようにこの PowerShell コマンド ラインを `.\Get-AllTenantRulesAndForms.ps1` 実行.\Get-AllTenantRulesAndForms.ps1</span><span class="sxs-lookup"><span data-stu-id="55f97-185">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="55f97-186">出力の解釈</span><span class="sxs-lookup"><span data-stu-id="55f97-186">Interpreting the output</span></span>

- <span data-ttu-id="55f97-187">**MailboxRulesExport-*yyyy-mm-dd*.csv**: アプリケーションまたは実行可能ファイルを含むアクション条件のルール (行ごとに 1 つ) を調べてください。</span><span class="sxs-lookup"><span data-stu-id="55f97-187">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="55f97-188">**ActionType (列 A)**: "ID_ACTION_CUSTOM" という値が表示された場合、ルールは悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-188">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="55f97-189">**IsPotentiallyMalicious (列 D)**: この値が "TRUE" の場合、ルールは悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-189">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="55f97-190">**ActionCommand (列 G)**: この列に、.exe または .zip 拡張子を持つアプリケーションまたはファイル、または URL を参照する不明なエントリが一覧表示されている場合、ルールは悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-190">**ActionCommand (column G)**: If this column lists an application or any file with .exe or .zip extensions, or an unknown entry that refers to a URL, the rule is likely malicious.</span></span>

- <span data-ttu-id="55f97-191">\**MailboxFormsExport-*yyyy-mm-dd\*\*\*.csv: 一般に、カスタム フォームの使用はまれです。</span><span class="sxs-lookup"><span data-stu-id="55f97-191">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is rare.</span></span> <span data-ttu-id="55f97-192">このブックに何か見つけた場合は、そのユーザーのメールボックスを開き、フォーム自体を調べてください。</span><span class="sxs-lookup"><span data-stu-id="55f97-192">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="55f97-193">組織が意図的にそこに置かなかった場合は、悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-193">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="55f97-194">ルールとフォームの攻撃を停止Outlook修復する方法</span><span class="sxs-lookup"><span data-stu-id="55f97-194">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="55f97-195">これらの攻撃の証拠が見当たっている場合、修復は簡単です。メールボックスからルールまたはフォームを削除してください。</span><span class="sxs-lookup"><span data-stu-id="55f97-195">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="55f97-196">これを行うには、クライアントまたはリモート powerShell Outlookルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="55f97-196">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="55f97-197">データOutlook</span><span class="sxs-lookup"><span data-stu-id="55f97-197">Using Outlook</span></span>

1. <span data-ttu-id="55f97-198">ユーザーがユーザーと一緒に使用したデバイスをOutlook。</span><span class="sxs-lookup"><span data-stu-id="55f97-198">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="55f97-199">これらはすべて、潜在的なマルウェアをクリーンアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-199">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="55f97-200">すべてのデバイスがクリーンアップされるまで、ユーザーがサインオンして電子メールを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="55f97-200">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="55f97-201">「デバイスごとにルール [を削除する」の手順](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) に従います。</span><span class="sxs-lookup"><span data-stu-id="55f97-201">Follow the steps in [Delete a rule](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="55f97-202">他のマルウェアの存在が不明な場合は、デバイス上のすべてのソフトウェアをフォーマットして再インストールできます。</span><span class="sxs-lookup"><span data-stu-id="55f97-202">If you are unsure about the presence of other malware, you can format and reinstall all the software on the device.</span></span> <span data-ttu-id="55f97-203">モバイル デバイスの場合は、製造元の手順に従ってデバイスを工場出荷時のイメージにリセットできます。</span><span class="sxs-lookup"><span data-stu-id="55f97-203">For mobile devices, you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="55f97-204">最新のバージョンのコンピューターをインストールOutlook。</span><span class="sxs-lookup"><span data-stu-id="55f97-204">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="55f97-205">既定では、現在のバージョンの Outlook両方の種類の攻撃がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="55f97-205">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="55f97-206">メールボックスのすべてのオフライン コピーを削除したら、ユーザーのパスワードをリセットし (高品質のパスワードを使用する)、MFA が有効になっていない[](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)場合は、ユーザーの多要素認証をセットアップするの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="55f97-206">Once all offline copies of the mailbox have been removed, reset the user's password (use a high quality one) and follow the steps in [Setup multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) if MFA has not already been enabled.</span></span> <span data-ttu-id="55f97-207">これにより、ユーザーの資格情報が他の手段 (フィッシングやパスワードの再使用など) によって公開されません。</span><span class="sxs-lookup"><span data-stu-id="55f97-207">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="55f97-208">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="55f97-208">Using PowerShell</span></span>

<span data-ttu-id="55f97-209">危険なルールを削除または無効化するために使用できる 2 つのリモート PowerShell コマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="55f97-209">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="55f97-210">手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="55f97-210">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="55f97-211">サーバー上のメールボックスExchange手順</span><span class="sxs-lookup"><span data-stu-id="55f97-211">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="55f97-212">Connect PowerShell を使用Exchangeサーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="55f97-212">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="55f97-213">リモート PowerShell を使用してサーバー [ConnectをExchange手順に従います](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="55f97-213">Follow the steps in [Connect to Exchange servers using remote PowerShell](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="55f97-214">1 つのルール、複数のルール、またはすべてのルールをメールボックスから完全に削除する場合は [、Remove-InboxRule コマンドレットを使用](/powershell/module/exchange/Remove-InboxRule) します。</span><span class="sxs-lookup"><span data-stu-id="55f97-214">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="55f97-215">詳細な調査のためにルールとその内容を保持する場合は [、Disable-InboxRule コマンドレットを使用](/powershell/module/exchange/disable-inboxrule) します。</span><span class="sxs-lookup"><span data-stu-id="55f97-215">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="55f97-216">サーバー内のメールボックスExchange Online</span><span class="sxs-lookup"><span data-stu-id="55f97-216">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="55f97-217">PowerShell を使用してConnect[をExchange Online手順に従います](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="55f97-217">Follow the steps in [Connect to Exchange Online using PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="55f97-218">1 つのルール、複数のルール、またはすべてのルールをメールボックスから完全に削除する場合は [、Remove-Inbox Rule コマンドレットを使用](/powershell/module/exchange/Remove-InboxRule) します。</span><span class="sxs-lookup"><span data-stu-id="55f97-218">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="55f97-219">詳細な調査のためにルールとその内容を保持する場合は [、Disable-InboxRule コマンドレットを使用](/powershell/module/exchange/disable-inboxrule) します。</span><span class="sxs-lookup"><span data-stu-id="55f97-219">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="55f97-220">将来の攻撃を最小限に抑える方法</span><span class="sxs-lookup"><span data-stu-id="55f97-220">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="55f97-221">まず、アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="55f97-221">First: protect your accounts</span></span>

<span data-ttu-id="55f97-222">ルールとフォームの悪用は、ユーザーのアカウントの 1 つを盗まれたり侵害したりした後にのみ、攻撃者によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="55f97-222">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="55f97-223">そのため、組織に対するこれらの悪用の使用を防ぐための最初の手順は、ユーザー アカウントを積極的に保護する方法です。</span><span class="sxs-lookup"><span data-stu-id="55f97-223">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="55f97-224">アカウントが侵害される最も一般的な方法のいくつかは、フィッシング攻撃またはパスワード スプレー攻撃 [です](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)。</span><span class="sxs-lookup"><span data-stu-id="55f97-224">Some of the most common ways that accounts are breached are through phishing or [password spray attacks](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/).</span></span>

<span data-ttu-id="55f97-225">ユーザー アカウント、特に管理者アカウントを保護する最善の方法は、ユーザーの多要素認証を [設定する方法です](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="55f97-225">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="55f97-226">また、次の情報も必要です。</span><span class="sxs-lookup"><span data-stu-id="55f97-226">You should also:</span></span>

- <span data-ttu-id="55f97-227">ユーザー アカウントへのアクセス方法と使用 [方法を監視します](/azure/active-directory/active-directory-view-access-usage-reports)。</span><span class="sxs-lookup"><span data-stu-id="55f97-227">Monitor how your user accounts are [accessed and used](/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="55f97-228">最初の違反を防ぐことはできない場合がありますが、違反を早く検出することで、違反の期間と影響を短くします。</span><span class="sxs-lookup"><span data-stu-id="55f97-228">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="55f97-229">以下のポリシーを使用[Office 365 Cloud App Security、](/cloud-app-security/what-is-cloud-app-security)アカウントを監視し、異常なアクティビティに関する警告を表示できます。</span><span class="sxs-lookup"><span data-stu-id="55f97-229">You can use these [Office 365 Cloud App Security policies](/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="55f97-230">**複数の** 失敗したログイン試行: このポリシーは、ユーザーが学習したベースラインに関して 1 つのセッションで複数の失敗したログイン アクティビティを実行すると、環境をプロファイルし、アラートをトリガーします。これは、違反の試行を示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-230">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="55f97-231">**不可能** な移動: このポリシーは、環境をプロファイルし、2 つの場所間の予想される移動時間よりも短い時間内に異なる場所で同じユーザーからアクティビティが検出されると、アラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="55f97-231">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="55f97-232">これは、別のユーザーが同じ資格情報を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-232">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="55f97-233">この異常な動作を検出するには、新しいユーザーのアクティビティ パターンを学習する最初の 7 日間の学習期間が必要です。</span><span class="sxs-lookup"><span data-stu-id="55f97-233">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="55f97-234">**異常な** 偽装アクティビティ (ユーザー別) : このポリシーは、ユーザーが学習したベースラインに関して 1 つのセッションで複数の偽装アクティビティを実行すると、環境をプロファイルし、アラートをトリガーします。違反の試行を示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-234">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="55f97-235">Secure Score のようなツール[をOffice 365して](https://securescore.office.com/)、アカウントのセキュリティ構成と動作を管理します。</span><span class="sxs-lookup"><span data-stu-id="55f97-235">Use a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="55f97-236">2 つ目: クライアントのOutlookを維持する</span><span class="sxs-lookup"><span data-stu-id="55f97-236">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="55f97-237">2013 年 2013 年および 2016 年の Outlook完全に更新および修正プログラムが適用されたバージョンでは、既定で "アプリケーションの開始" ルール/フォーム アクションが無効になります。</span><span class="sxs-lookup"><span data-stu-id="55f97-237">Fully updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="55f97-238">これにより、攻撃者がアカウントを侵害した場合でも、ルールとフォームのアクションがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="55f97-238">This will ensure that even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="55f97-239">「更新プログラムのインストール」の手順に従って、最新の更新プログラム[とセキュリティ パッチOfficeできます](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)。</span><span class="sxs-lookup"><span data-stu-id="55f97-239">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="55f97-240">2013 および 2016 のクライアントOutlook更新プログラムのバージョンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="55f97-240">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="55f97-241">**Outlook 2016**: 16.0.4534.1001 以上。</span><span class="sxs-lookup"><span data-stu-id="55f97-241">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="55f97-242">**Outlook 2013**: 15.0.4937.1000 以上。</span><span class="sxs-lookup"><span data-stu-id="55f97-242">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="55f97-243">個々のセキュリティ パッチの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55f97-243">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="55f97-244">Outlook 2016セキュリティ パッチ</span><span class="sxs-lookup"><span data-stu-id="55f97-244">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="55f97-245">Outlook 2013 セキュリティ パッチ</span><span class="sxs-lookup"><span data-stu-id="55f97-245">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="55f97-246">3 つ目: クライアントOutlook監視する</span><span class="sxs-lookup"><span data-stu-id="55f97-246">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="55f97-247">パッチと更新プログラムがインストールされている場合でも、攻撃者がローカル コンピューターの構成を変更して"アプリケーションの起動" 動作を再び有効にできる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-247">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="55f97-248">Advanced Group [Policy Management を使用して](/microsoft-desktop-optimization-pack/agpm/) 、クライアントにローカル コンピューター ポリシーを監視および適用できます。</span><span class="sxs-lookup"><span data-stu-id="55f97-248">You can use [Advanced Group Policy Management](/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="55f97-249">「64 ビット バージョンの Windows を使用してシステム レジストリを表示する方法」の情報を使用して、レジストリ内のオーバーライドを通じて "アプリケーションの起動" が再び有効[になっているか確認できます](https://support.microsoft.com/help/305097)。</span><span class="sxs-lookup"><span data-stu-id="55f97-249">You can see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097).</span></span> <span data-ttu-id="55f97-250">次のサブキーを確認します。</span><span class="sxs-lookup"><span data-stu-id="55f97-250">Check these subkeys:</span></span>

- <span data-ttu-id="55f97-251">**Outlook 2016:**`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="55f97-251">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="55f97-252">**Outlook 2013:**`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="55f97-252">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="55f97-253">EnableUnsafeClientMailRules キーを探します。</span><span class="sxs-lookup"><span data-stu-id="55f97-253">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="55f97-254">このセキュリティ 更新プログラムが 1 に設定されている場合、Outlook更新プログラムは上書きされ、コンピューターは Form/Rules 攻撃に対して脆弱です。</span><span class="sxs-lookup"><span data-stu-id="55f97-254">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="55f97-255">値が 0 の場合、[アプリケーションの開始] アクションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="55f97-255">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="55f97-256">更新および修正プログラムが適用されたバージョンの Outlook がインストールされ、このレジストリ キーが存在しない場合、システムはこれらの攻撃に対して脆弱ではありません。</span><span class="sxs-lookup"><span data-stu-id="55f97-256">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="55f97-257">オンプレミスのインストールを使用しているExchangeは、利用可能なパッチを持Outlook古いバージョンのデバイスをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55f97-257">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="55f97-258">このプロセスの詳細については、「Configure [Outlook」を参照してください](/exchange/configure-outlook-client-blocking-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="55f97-258">Details on this process can be found in the article [Configure Outlook client blocking](/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="55f97-259">サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="55f97-259">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="55f97-260">Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="55f97-260">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="55f97-261">[Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="55f97-261">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="55f97-262">最初の 30 日間に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="55f97-262">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="55f97-263">これらは即座に影響を及ぼすので、ユーザーに与える影響は低いです。</span><span class="sxs-lookup"><span data-stu-id="55f97-263">These have immediate effect and are low-impact to your users.</span></span>

- <span data-ttu-id="55f97-p134">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="55f97-p134">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="55f97-p135">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="55f97-p135">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="55f97-268">関連項目:</span><span class="sxs-lookup"><span data-stu-id="55f97-268">See also:</span></span>

- <span data-ttu-id="55f97-269">[ルール Outlookに](https://silentbreaksecurity.com/malicious-outlook-rules/)関する SilentBreak セキュリティ 投稿による悪意のあるセキュリティ ルールには、ルールの詳細なレビュー Outlookがあります。</span><span class="sxs-lookup"><span data-stu-id="55f97-269">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="55f97-270">[Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)に関する Sensepost ブログの MAPI over HTTP と Mailrule Pwnage では、ルールを使用してメールボックスを悪用できる Ruler というツールについてOutlookしています。</span><span class="sxs-lookup"><span data-stu-id="55f97-270">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="55f97-271">[Outlook脅威ベクトルに](https://sensepost.com/blog/2017/outlook-forms-and-shells/)関する Sensepost ブログでフォームとシェルを作成します。</span><span class="sxs-lookup"><span data-stu-id="55f97-271">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="55f97-272">Ruler Codebase</span><span class="sxs-lookup"><span data-stu-id="55f97-272">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="55f97-273">侵害のルーラーインジケーター</span><span class="sxs-lookup"><span data-stu-id="55f97-273">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)