---
title: Office 365 で Outlook のルールとユーザー設定フォームの挿入攻撃を検出して修復する
ms.author: chrfox
author: chrfox
manager: laurawi
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
description: Office 365 で Outlook のルールとユーザー設定フォームのインジェクション攻撃を認識して修復する方法について説明します。
ms.openlocfilehash: d5f4a653463f4105df025bf29679465ca5335098
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970793"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a><span data-ttu-id="21cfd-103">Office 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う</span><span class="sxs-lookup"><span data-stu-id="21cfd-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>

<span data-ttu-id="21cfd-104">**概要**Office 365 で Outlook のルールとユーザー設定フォームのインジェクション攻撃を認識して修復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="21cfd-105">Outlook のルールとユーザー設定フォームの挿入攻撃とは</span><span class="sxs-lookup"><span data-stu-id="21cfd-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="21cfd-106">攻撃者がテナント内のアカウントを侵害してから、を取得した後は、そのアカウントが検出されて削除された後に再び取得する方法を確立しようとしています。</span><span class="sxs-lookup"><span data-stu-id="21cfd-106">After an attacker has breached an account in your tenancy and gets in, they're are going to try and establish a way to stay in or a way to get back in after they are discovered and removed.</span></span> <span data-ttu-id="21cfd-107">これは、「持続性メカニズムの確立」と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-107">This is called establishing a persistence mechanism.</span></span> <span data-ttu-id="21cfd-108">これを行うには、2つの方法として、Outlook のルールを活用するか、Outlook にカスタムフォームを挿入します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-108">Two ways that they can do this are by exploiting Outlook rules or by injecting custom forms into Outlook.</span></span>
<span data-ttu-id="21cfd-109">どちらの場合も、ルールまたはフォームは cloud service からデスクトップクライアントに同期されるので、クライアントソフトウェアを完全にフォーマットして再インストールしても、挿入メカニズムは不要になります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-109">In both cases, the rule or form is synced from the cloud service down to the desktop client, so a full format and re-install of the client software doesn't eliminate the injection mechanism.</span></span> <span data-ttu-id="21cfd-110">これは、Outlook クライアントソフトウェアがクラウド内のメールボックスに再接続すると、そのルールとフォームがクラウドから再ダウンロードされるためです。</span><span class="sxs-lookup"><span data-stu-id="21cfd-110">This is because when the Outlook client software reconnects to the mailbox in the cloud it will re-download the rules and forms from the cloud.</span></span> <span data-ttu-id="21cfd-111">ルールとフォームが配置されると、攻撃者はそれらを使用してリモートまたはカスタムのコードを実行します。通常、マルウェアをローカルコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-111">Once the rules and forms are in place, the attacker uses them to execute remote or custom code, usually to install malware on the local machine.</span></span> <span data-ttu-id="21cfd-112">その後、マルウェアは資格情報を再盗んで、またはその他の不法な動作を実行します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-112">The malware then re-steals credentials or performs other illicit activity.</span></span>
<span data-ttu-id="21cfd-113">ここでの朗報は、クライアントの最新バージョンにパッチを適用したままにしておくと、現在の Outlook クライアントの既定では両方のメカニズムをブロックするため、脅威に対して脆弱ではないということです。</span><span class="sxs-lookup"><span data-stu-id="21cfd-113">The good news here is that if you keep your clients patched to the latest version, you are not vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="21cfd-114">攻撃は通常、次のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="21cfd-114">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="21cfd-115">**ルールは次のように**なります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-115">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="21cfd-116">攻撃者は、ユーザーの1人のユーザー名とパスワードを盗みます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-116">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="21cfd-117">その後、攻撃者はそのユーザーの Exchange メールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-117">The attacker then signs in to that users Exchange mailbox.</span></span> <span data-ttu-id="21cfd-118">メールボックスは、Exchange online または Exchange オンプレミスのいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-118">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="21cfd-119">その後、攻撃者はメールボックスに、ルールの条件に一致するメールを受信したときにトリガーされる転送ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-119">The attacker then creates a forwarding rule in the mailbox that is triggered when the mailbox receives an email that matches the criteria of the rule.</span></span> <span data-ttu-id="21cfd-120">ルールの条件とトリガー電子メールの内容は、互いに対して個別に作成されます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-120">The criteria of rule and the contents of the trigger email are tailor-made for each other.</span></span>

4. <span data-ttu-id="21cfd-121">攻撃者は、メールボックスを通常どおりに使用しているユーザーに、トリガーの電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-121">The attacker sends the trigger email to the user who is using their mailbox normally.</span></span>

5. <span data-ttu-id="21cfd-122">電子メールが受信されると、ルールがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-122">When the email is received, the rule is triggered.</span></span> <span data-ttu-id="21cfd-123">ルールのアクションは、通常、リモート (WebDAV) サーバー上でアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-123">The action of the rule is usually to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="21cfd-124">通常、アプリケーションは、 [Powershell 帝国](https://www.powershellempire.com/)などのマルウェアをユーザーのコンピューターにローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-124">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="21cfd-125">マルウェアは、攻撃者がユーザーのユーザー名とパスワードまたはその他の資格情報をローカルコンピューターから再利用して、他の悪意のあるアクティビティを実行することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-125">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="21cfd-126">**フォームの活用**:</span><span class="sxs-lookup"><span data-stu-id="21cfd-126">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="21cfd-127">攻撃者は、ユーザーの1人のユーザー名とパスワードを盗みます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-127">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="21cfd-128">その後、攻撃者はそのユーザーの Exchange メールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-128">The attacker then sign in to that users Exchange mailbox.</span></span> <span data-ttu-id="21cfd-129">メールボックスは、Exchange online または Exchange オンプレミスのいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-129">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="21cfd-130">その後、攻撃者はカスタムのメールフォームテンプレートを作成し、それをユーザーのメールボックスに挿入します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-130">The attacker then creates a custom mail form template and inserts it into the user's mailbox.</span></span> <span data-ttu-id="21cfd-131">ユーザー設定フォームは、メールボックスがユーザー設定フォームを読み込む必要がある電子メールを受信したときにトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-131">The custom form is triggered when the mailbox receives an email that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="21cfd-132">ユーザー設定フォームと電子メールの形式は、互いに対してカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-132">The custom form and the format of email are tailor-made for each other.</span></span>
4. <span data-ttu-id="21cfd-133">攻撃者は、自分のメールボックスを通常どおりに使用しているユーザーに、トリガーの電子メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-133">The attacker sends the trigger email to the user, who is using their mailbox normally.</span></span>

5. <span data-ttu-id="21cfd-134">電子メールを受信すると、フォームがロードされます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-134">When the email is received, the form is loaded.</span></span> <span data-ttu-id="21cfd-135">フォームは、リモート (WebDAV) サーバー上でアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-135">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="21cfd-136">通常、アプリケーションは、 [Powershell 帝国](https://www.powershellempire.com/)などのマルウェアをユーザーのコンピューターにローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-136">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="21cfd-137">マルウェアは、攻撃者がユーザーのユーザー名とパスワードまたはその他の資格情報をローカルコンピューターから再利用して、他の悪意のあるアクティビティを実行することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-137">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="21cfd-138">Office 365 のように、ルールおよびユーザー設定フォームの注入攻撃を考えるか</span><span class="sxs-lookup"><span data-stu-id="21cfd-138">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="21cfd-139">ユーザーがこれらの永続化メカニズムを認識することはほとんどありませんが、場合によっては非表示になることがあります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-139">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="21cfd-140">この記事では、以下に示す7つの記号 (妥協の兆候) を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-140">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="21cfd-141">これらのいずれかが見つかった場合は、修復手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-141">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="21cfd-142">ルールが侵害されたことを示すインジケーター:</span><span class="sxs-lookup"><span data-stu-id="21cfd-142">Indicators of the Rules compromise:</span></span>

  - <span data-ttu-id="21cfd-143">ルールの処理として、アプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-143">Rule Action is to start an application.</span></span>

  - <span data-ttu-id="21cfd-144">ルールは、EXE、ZIP、または URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-144">Rule References an EXE, ZIP, or URL.</span></span>

  - <span data-ttu-id="21cfd-145">ローカルコンピューターで、Outlook PID から始まる新しいプロセスが開始されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-145">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="21cfd-146">ユーザー設定フォームが侵害されたことを示すインジケーター:</span><span class="sxs-lookup"><span data-stu-id="21cfd-146">Indicators of the Custom forms compromise:</span></span>

  - <span data-ttu-id="21cfd-147">カスタムフォームは独自のメッセージクラスとして保存されています。</span><span class="sxs-lookup"><span data-stu-id="21cfd-147">Custom form present saved as their own message class.</span></span>

  - <span data-ttu-id="21cfd-148">メッセージクラスには、実行可能コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21cfd-148">Message class contains executable code.</span></span>

  - <span data-ttu-id="21cfd-149">通常、個人用フォームライブラリまたは受信トレイフォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-149">Usually stored in Personal Forms Library or Inbox folders.</span></span>

  - <span data-ttu-id="21cfd-150">Form には、IPM という名前が付けられます。こと.[カスタム名]。</span><span class="sxs-lookup"><span data-stu-id="21cfd-150">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="21cfd-151">この攻撃の兆候を見つけて確認するための手順</span><span class="sxs-lookup"><span data-stu-id="21cfd-151">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="21cfd-152">攻撃を確認するには、次の2つの方法のどちらかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-152">You can use either of these two methods to confirm the attack:</span></span>

- <span data-ttu-id="21cfd-153">Outlook クライアントを使用して、各メールボックスのルールとフォームを手動でチェックします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-153">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="21cfd-154">この方法は完全ですが、多くのユーザーが確認できるようにする場合には、メールボックスユーザーを一度にチェックするだけで十分に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-154">This method is thorough, but you can only check mailbox user at a time which can be very time consuming if you have many users to check.</span></span> <span data-ttu-id="21cfd-155">また、チェックを実行しているコンピューターが侵害されてしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-155">It can also result in a breach of the computer that you are running the check from.</span></span>

- <span data-ttu-id="21cfd-156">[Get-AllTenantRulesAndForms](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell スクリプトを使用して、テナント内のすべてのユーザーのメール転送ルールおよびカスタムフォームを自動的にダンプします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-156">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="21cfd-157">これは、最もオーバーヘッドが少ない最も高速で最も安全な方法です。</span><span class="sxs-lookup"><span data-stu-id="21cfd-157">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="21cfd-158">Outlook クライアントを使用してルールが攻撃されたことを確認する</span><span class="sxs-lookup"><span data-stu-id="21cfd-158">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="21cfd-159">ユーザーとしてユーザーの Outlook クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-159">Open the users Outlook client as the user.</span></span> <span data-ttu-id="21cfd-160">ユーザーは、自分のメールボックスのルールを調べるためにヘルプを必要とする場合があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-160">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="21cfd-161">Outlook でルールインターフェイスを開く方法の手順については、「[ルールを使用してメールメッセージを管理](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59)する」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21cfd-161">Refer to [Manage email messages by using rules](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="21cfd-162">ユーザーが作成しなかったルール、または不審な名前のルールがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-162">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="21cfd-163">ルールの説明で、を起動して、アプリケーションまたはを参照するルールの処理を確認します。EXE、。ZIP ファイルを開くか、URL を起動します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-163">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="21cfd-164">Outlook プロセス ID の使用を開始する新しいプロセスを探します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-164">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="21cfd-165">「[プロセス ID を検索](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21cfd-165">Refer to [Find the Process ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="21cfd-166">Outlook クライアントを使用してフォームの攻撃を確認する手順</span><span class="sxs-lookup"><span data-stu-id="21cfd-166">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="21cfd-167">ユーザーとしてユーザーの Outlook クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-167">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="21cfd-168">の手順に従い、ユーザーのバージョンの Outlook の [[開発] タブを表示](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45)します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-168">Follow the steps in, [Show the Developer tab](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the users version of Outlook.</span></span>

3. <span data-ttu-id="21cfd-169">Outlook で [現在表示されている開発] タブを開き、[**フォームのデザイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-169">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="21cfd-170">[**検索**先] の一覧から [**受信トレイ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-170">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="21cfd-171">ユーザー設定フォームを検索します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-171">Look for any custom forms.</span></span> <span data-ttu-id="21cfd-172">ユーザー設定フォームがある場合は、ユーザー設定フォームを使用するだけで十分な場合があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-172">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="21cfd-173">特に非表示に設定されたカスタムフォームを調査します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-173">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="21cfd-174">任意のユーザー設定フォームを開き、**フォーム**グループの [**コードの表示**] をクリックして、フォームが読み込まれたときに実行される内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-174">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="21cfd-175">PowerShell を使用してルールとフォームの攻撃を確認する手順</span><span class="sxs-lookup"><span data-stu-id="21cfd-175">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="21cfd-176">ルールまたはユーザー設定フォームの攻撃を確認する最も簡単な方法は、 [Get-AllTenantRulesAndForms](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell スクリプトを実行することです。</span><span class="sxs-lookup"><span data-stu-id="21cfd-176">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="21cfd-177">このスクリプトは、テナント内のすべてのメールボックスに接続し、すべてのルールとフォームを2つの .csv ファイルにダンプします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-177">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="21cfd-178">前提条件</span><span class="sxs-lookup"><span data-stu-id="21cfd-178">Pre-requisites</span></span>

<span data-ttu-id="21cfd-179">スクリプトは、ルールとフォームを読み取るために、テナント内のすべてのメールボックスに接続するため、スクリプトを実行するためのグローバル管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-179">You will need to have a global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="21cfd-180">スクリプトを実行するコンピューターに、ローカル管理者権限を使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-180">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="21cfd-181">Get-AllTenantRulesAndForms スクリプトを GitHub から、実行するフォルダーにダウンロードまたはコピーします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-181">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="21cfd-182">このスクリプトは、2つの日付のスタンプ付きファイルをこのフォルダー、MailboxFormsExport-yyyy-mm-dd、および MailboxRulesExport-yyyy-mm-dd に作成します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-182">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="21cfd-183">管理者として PowerShell インスタンスを開き、スクリプトを保存したフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-183">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="21cfd-184">次`.\Get-AllTenantRulesAndForms.ps1`のように、この PowerShell コマンドラインを実行します。 .\Get-AllTenantRulesAndForms.ps1</span><span class="sxs-lookup"><span data-stu-id="21cfd-184">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="21cfd-185">出力の解釈</span><span class="sxs-lookup"><span data-stu-id="21cfd-185">Interpreting the output</span></span>

- <span data-ttu-id="21cfd-186">\*\*MailboxRulesExport:\*\*\*\*(行ごとに1つずつ) アプリケーションまたは実行可能ファイルが含まれるアクション条件を調べます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-186">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="21cfd-187">**ActionType (列 A)**: 値 "ID_ACTION_CUSTOM" が表示される場合、そのルールは悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-187">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="21cfd-188">悪意のある人物 **(列 D)**: この値が "TRUE" の場合、ルールは悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-188">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="21cfd-189">**Actioncommand (列 G)**: .exe、.zip 拡張子、または URL を参照するファイルを一覧表示する場合は、そのルールは悪意のある可能性があると考えられます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-189">**ActionCommand (column G)**: If this lists an application or any file with a .exe, .zip extension or an entry that refers to a URL, that is not supposed to be there, the rule is likely malicious.</span></span>

- <span data-ttu-id="21cfd-190">\**MailboxFormsExport-*yyyy-mm-dd\*\*\*: 一般に、ユーザー設定フォームの使用は非常にまれです。</span><span class="sxs-lookup"><span data-stu-id="21cfd-190">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is very rare.</span></span> <span data-ttu-id="21cfd-191">このブック内に見つかった場合は、そのユーザーのメールボックスを開き、フォーム自体を調べます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-191">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="21cfd-192">組織で意図的に配置しなかった場合は、悪意のある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-192">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="21cfd-193">Outlook のルールとフォームの攻撃を停止および修復する方法</span><span class="sxs-lookup"><span data-stu-id="21cfd-193">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="21cfd-194">このような攻撃のいずれかの証拠を見つけた場合は、単にメールボックスからルールまたはフォームを削除するだけで修復が容易になります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-194">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="21cfd-195">これを行うには、Outlook クライアントまたはリモート PowerShell を使用してルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-195">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="21cfd-196">Outlook を使用する</span><span class="sxs-lookup"><span data-stu-id="21cfd-196">Using Outlook</span></span>

1. <span data-ttu-id="21cfd-197">ユーザーが Outlook で使用したすべてのデバイスを特定します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-197">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="21cfd-198">これらはすべて、潜在的なマルウェアを駆除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-198">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="21cfd-199">すべてのデバイスがクリーニングされるまで、ユーザーはサインオンして電子メールを使用できません。</span><span class="sxs-lookup"><span data-stu-id="21cfd-199">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="21cfd-200">「各デバイスの[ルールを削除する](https://support.office.com/article/2f0e7139-f696-4422-8498-44846db9067f)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="21cfd-200">Follow the steps in [Delete a rule](https://support.office.com/article/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="21cfd-201">他のマルウェアが存在することが不明な場合は、デバイス上のすべてのソフトウェアを書式設定して再インストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-201">If you are unsure about the presence of other malware, you can format and re-install all the software on the device.</span></span> <span data-ttu-id="21cfd-202">モバイルデバイスでは、製造元の手順に従って、デバイスを出荷時イメージにリセットできます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-202">For mobile devices you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="21cfd-203">最新バージョンの Outlook をインストールします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-203">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="21cfd-204">Outlook の現在のバージョンでは、この両方の種類の攻撃が既定でブロックされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="21cfd-204">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="21cfd-205">メールボックスのすべてのオフラインコピーが削除されたら、ユーザーのパスワードをリセット (高品質のパスワードを使用) し、MFA がまだ有効になっていない場合は、 [Office 365 ユーザーのセットアップ多要素認証](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="21cfd-205">Once all offline copies of the mailbox have been removed, reset the user's password (use a high-quality one) and follow the steps in [Setup multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) if MFA has not already been enabled.</span></span> <span data-ttu-id="21cfd-206">これにより、ユーザーの資格情報が他の手段 (フィッシングやパスワードの再利用など) で公開されることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-206">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="21cfd-207">PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="21cfd-207">Using PowerShell</span></span>

<span data-ttu-id="21cfd-208">危険なルールを削除または無効にするために使用できるリモート PowerShell コマンドレットは2つあります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-208">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="21cfd-209">手順を実行するだけです。</span><span class="sxs-lookup"><span data-stu-id="21cfd-209">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="21cfd-210">Exchange サーバー上のメールボックスの手順</span><span class="sxs-lookup"><span data-stu-id="21cfd-210">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="21cfd-211">リモート PowerShell を使用して Exchange サーバーに接続します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-211">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="21cfd-212">[「リモート PowerShell を使用して Exchange サーバーに接続する](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-212">Follow the steps in [Connect to Exchange servers using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="21cfd-213">1つのルール、複数のルール、またはメールボックスからすべてのルールを完全に削除する場合は、コマンドレットの[削除](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)を使用します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-213">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="21cfd-214">詳細な調査のためにルールとその内容を保持する場合は[、コマンドレットを使用](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-214">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="21cfd-215">Exchange Online のメールボックスの手順</span><span class="sxs-lookup"><span data-stu-id="21cfd-215">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="21cfd-216">[「PowerShell を使用して Exchange Online に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-216">Follow the steps in [Connect to Exchange Online using PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="21cfd-217">1つのルール、複数のルール、またはメールボックスからすべてのルールを完全に削除するには、 [[受信トレイルールの削除](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)] コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-217">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="21cfd-218">詳細な調査のためにルールとその内容を保持する場合は[、コマンドレットを使用](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-218">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="21cfd-219">今後の攻撃を最小限に抑える方法</span><span class="sxs-lookup"><span data-stu-id="21cfd-219">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="21cfd-220">最初: アカウントを保護する</span><span class="sxs-lookup"><span data-stu-id="21cfd-220">First: protect your accounts</span></span>

<span data-ttu-id="21cfd-221">ルールとフォームのエクスプロイトは、攻撃者がユーザーのアカウントのいずれかを盗んだ後、または侵害した後にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-221">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="21cfd-222">そのため、これらの悪用を組織に対して使用できないようにするための最初の手順として、ユーザーアカウントを積極的に保護することが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-222">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="21cfd-223">アカウントが侵害される最も一般的な方法には、フィッシングまたは[パスワード spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)攻撃があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-223">Some of the most common ways that accounts are breached are through phishing or [password spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) attacks.</span></span>

<span data-ttu-id="21cfd-224">ユーザーアカウントや特に管理者アカウントを保護する最善の方法は、 [Office 365 ユーザーに多要素認証を設定](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)することです。</span><span class="sxs-lookup"><span data-stu-id="21cfd-224">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span> <span data-ttu-id="21cfd-225">次のことも実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-225">You should also:</span></span>

- <span data-ttu-id="21cfd-226">ユーザーアカウントがどのようにアクセスされ、[使用されるかを](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)監視します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-226">Monitor how your user accounts are [accessed and used](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="21cfd-227">最初の違反を防ぐことはできませんが、期間を短縮して、違反が早く検出された場合の影響を短縮することができます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-227">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="21cfd-228">これらの[Office 365 Cloud App Security ポリシー](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)を使用して、アカウントを監視し、異常なアクティビティに関する警告を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-228">You can use these [Office 365 Cloud App Security policies](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="21cfd-229">[**失敗したログイン試行回数**]: このポリシーは、環境をプロファイルし、ユーザーが1回のセッションで複数の失敗したログインアクティビティを実行したときに、違反が発生したことを示す通知をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-229">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="21cfd-230">**不可能な出張**: このポリシーでは、環境をプロファイルし、2つの場所間で予想される出張時間よりも短い期間に異なる場所にある同じユーザーからアクティビティが検出されたときにアラートをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-230">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="21cfd-231">これは、別のユーザーが同じ資格情報を使用していることを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-231">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="21cfd-232">このような異常動作を検出するには、新しいユーザーのアクティビティパターンを学習させる7日間の最初の学習期間が必要です。</span><span class="sxs-lookup"><span data-stu-id="21cfd-232">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="21cfd-233">通常は偽装されていない**アクティビティ (ユーザー別)**: このポリシーでは、環境をプロファイルし、ユーザーが1つのセッションで複数の偽装されたアクティビティを行ったときに、違反が発生したことを示すことができるように、通知をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-233">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="21cfd-234">[Office 365 のセキュリティスコア](https://securescore.office.com/)のようなツールを活用して、アカウントのセキュリティの構成と動作を管理します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-234">Leverage a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="21cfd-235">2番目: Outlook クライアントを最新の状態に保ちます</span><span class="sxs-lookup"><span data-stu-id="21cfd-235">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="21cfd-236">Outlook 2013 の完全に更新されたバージョンとパッチが適用されたバージョン、および2016は、既定で [アプリケーションを開始する] ルール/フォームアクションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-236">Fully-updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="21cfd-237">これにより、攻撃者がアカウントに違反したとしても、ルールおよびフォームのアクションはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-237">This will ensure that, even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="21cfd-238">最新の更新プログラムおよびセキュリティ更新プログラムは、「 [Office の更新プログラムをインストール](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5)する」の手順に従ってインストールできます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-238">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="21cfd-239">Outlook 2013 および2016クライアントのパッチバージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="21cfd-239">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="21cfd-240">**Outlook 2016**: 16.0.4534.1001 以上</span><span class="sxs-lookup"><span data-stu-id="21cfd-240">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="21cfd-241">**Outlook 2013**: 15.0.4937.1000 以上</span><span class="sxs-lookup"><span data-stu-id="21cfd-241">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="21cfd-242">個別のセキュリティ修正プログラムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21cfd-242">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="21cfd-243">Outlook 2016 セキュリティパッチ</span><span class="sxs-lookup"><span data-stu-id="21cfd-243">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="21cfd-244">Outlook 2013 セキュリティパッチ</span><span class="sxs-lookup"><span data-stu-id="21cfd-244">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="21cfd-245">3番目: Outlook クライアントを監視する</span><span class="sxs-lookup"><span data-stu-id="21cfd-245">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="21cfd-246">なお、パッチと更新プログラムがインストールされている場合でも、攻撃者がローカルコンピューターの構成を変更して "アプリケーションを起動する" 動作を再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-246">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="21cfd-247">[高度なグループポリシー管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/)を使用して、クライアントのローカルコンピューターポリシーを監視し、適用することができます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-247">You can use [Advanced Group Policy Management](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="21cfd-248">[64 ビットバージョンの Windows を使用してシステムレジストリを表示する方法](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows)についての情報を使用して、"Start Application" がレジストリ内の上書きによって再度有効になっているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-248">You can to see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows).</span></span> <span data-ttu-id="21cfd-249">次のサブキーをチェックします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-249">Check these subkeys:</span></span>

- <span data-ttu-id="21cfd-250">**Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="21cfd-250">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="21cfd-251">**Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="21cfd-251">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="21cfd-252">キー EnableUnsafeClientMailRules を探します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-252">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="21cfd-253">これが存在し、1に設定されている場合は、Outlook セキュリティパッチが上書きされ、コンピューターはフォーム/ルールの攻撃に対して脆弱になります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-253">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="21cfd-254">値が0の場合、"アプリケーションを起動します" アクションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-254">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="21cfd-255">更新され、パッチされたバージョンの Outlook がインストールされていて、このレジストリキーが存在しない場合、システムはこれらの攻撃に対して脆弱ではありません。</span><span class="sxs-lookup"><span data-stu-id="21cfd-255">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="21cfd-256">オンプレミスの Exchange インストールを使用しているお客様は、利用可能なパッチを持たない古いバージョンの Outlook をブロックすることを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-256">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="21cfd-257">このプロセスの詳細については、記事「 [Outlook クライアントのブロックを構成](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21cfd-257">Details on this process can be found in the article [Configure Outlook client blocking](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="21cfd-258">cybersecurity pro などの Office 365 の保護</span><span class="sxs-lookup"><span data-stu-id="21cfd-258">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="21cfd-259">Office 365 サブスクリプションには、データとユーザーを保護するために使用できる強力な一連のセキュリティ機能が付属しています。</span><span class="sxs-lookup"><span data-stu-id="21cfd-259">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="21cfd-260">[Office 365 セキュリティロードマップを使用して、最初の30日間、90日間、および](security-roadmap.md)office 365 テナントをセキュリティで保護するためのベストプラクティスを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="21cfd-260">Use the [Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="21cfd-261">最初の30日間に実行するタスク。</span><span class="sxs-lookup"><span data-stu-id="21cfd-261">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="21cfd-262">これらはすぐに影響を受け、ユーザーにとって影響が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="21cfd-262">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="21cfd-p135">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-p135">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="21cfd-p136">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="21cfd-p136">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="21cfd-267">関連項目:</span><span class="sxs-lookup"><span data-stu-id="21cfd-267">See also:</span></span>

- <span data-ttu-id="21cfd-268">保護された悪意のある[Outlook](https://silentbreaksecurity.com/malicious-outlook-rules/)ルールベクトルに関するセキュリティ投稿ルールベクトルについては、outlook ルールの詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="21cfd-268">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="21cfd-269">[MAPI OVER HTTP および Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on Blog For Mailrule Pwnage Outlook のルールによってメールボックスを活用するためのルーラーというツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="21cfd-269">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="21cfd-270">フォームの脅威ベクトルに関する、 [office の Outlook フォームおよびシェル](https://sensepost.com/blog/2017/outlook-forms-and-shells/)。</span><span class="sxs-lookup"><span data-stu-id="21cfd-270">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="21cfd-271">ルーラーコードベース</span><span class="sxs-lookup"><span data-stu-id="21cfd-271">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="21cfd-272">セキュリティ侵害のルーラーインジケーター</span><span class="sxs-lookup"><span data-stu-id="21cfd-272">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)
