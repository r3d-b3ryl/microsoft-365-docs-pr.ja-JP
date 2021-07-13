---
title: 組織内のすべてのユーザー用に優先受信トレイを構成する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: すべてのユーザー用のメール設定の構築を担当している場合は、この記事でユーザー用の優先受信トレイの設定方法が確認できます。
ms.openlocfilehash: 74663342adc3dd29f35d462b2dee7bbbc771f8f0
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393597"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="2a041-103">組織内のすべてのユーザー用に優先受信トレイを構成する</span><span class="sxs-lookup"><span data-stu-id="2a041-103">Configure Focused Inbox for everyone in your organization</span></span>

<span data-ttu-id="2a041-104">職場のすべてのユーザー用にメールの動作を構成する必要がある場合は、この記事が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2a041-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="2a041-105">ここでは、業務向けにカスタマイズする方法や無効にする方法について説明しており、[よく寄せられる質問](#faq-for-focused-inbox)に回答しています。</span><span class="sxs-lookup"><span data-stu-id="2a041-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>

<span data-ttu-id="2a041-106">自分に対してだけ優先受信トレイを無効にする場合は、「[優先受信トレイを無効にする](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  

<span data-ttu-id="2a041-p102">ユーザーが業務上の特定のメール メッセージ (たとえば、HR や給与に関するもの) を受信したことを確認する必要がある場合、優先受信トレイを構成して、これらのメッセージを優先ビューに表示することができます。また、組織のユーザーにメールボックスの優先受信トレイを表示するかどうかを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a041-p102">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="2a041-109">組織で優先受信トレイの有効/無効を切り替える</span><span class="sxs-lookup"><span data-stu-id="2a041-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="2a041-110">組織のすべてのユーザーに対して優先受信トレイの有効/無効を切り替えるには、PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="2a041-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="2a041-111">この操作を Microsoft 365 管理センターで行う場合は、</span><span class="sxs-lookup"><span data-stu-id="2a041-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="2a041-112">エンジニアリング チームにお知らせください。</span><span class="sxs-lookup"><span data-stu-id="2a041-112">Let our Engineering team know.</span></span> <span data-ttu-id="2a041-113">**[ここで投票してください。](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="2a041-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
<span data-ttu-id="2a041-114">**優先受信トレイを無効にする**</span><span class="sxs-lookup"><span data-stu-id="2a041-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="2a041-p104">以下の PowerShell の例では、組織で優先受信トレイを **無効** にします。ただし、ユーザーが機能を使えなくなることはありません。必要な場合は、引き続き、各クライアントでもう一度優先受信トレイを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2a041-p104">The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="2a041-118">[リモート PowerShell で Exchange Online に接続する](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2a041-118">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2a041-p105">この手順を実行する前にアクセス許可が割り当てられている必要があります。必要なアクセス許可を確認するには、「[メッセージング ポリシーとコンプライアンスのアクセス許可](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help)」の項目「トランスポート ルール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).</span></span>

3. <span data-ttu-id="2a041-121">
            \*\*Get-OrganizationConfig\*\* コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a041-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 

    ```powershell
    Get-OrganizationConfig
    ```

4. <span data-ttu-id="2a041-122">**FocusedInboxOn** を探して、現在の設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="2a041-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 

    ![優先受信トレイの状態に関する PowerShell からの応答。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="2a041-124">次のコマンドレットを実行して、優先受信トレイを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a041-124">Run the following cmdlet to turn Focused Inbox off.</span></span>

    ```powershell
    Set-OrganizationConfig -FocusedInboxOn $false
    ```

6. <span data-ttu-id="2a041-125">**Get-OrganizationConfig** コマンドレットをもう一度実行し、FocusedInboxOn が $false に設定されていることを確認します。これは、FocusedInbox がオフになったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="2a041-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 

<span data-ttu-id="2a041-126">**優先受信トレイを有効にする**</span><span class="sxs-lookup"><span data-stu-id="2a041-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="2a041-127">上の手順 5 で、次のコマンドレットを実行して、優先受信トレイを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a041-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>

  ```powershell
  Set-OrganizationConfig -FocusedInboxOn $true
  ```
    
## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="2a041-128">優先受信トレイを有効にすると、ユーザーに何が表示されますか。 </span><span class="sxs-lookup"><span data-stu-id="2a041-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="2a041-p106">ユーザーが Outlook を終了して再起動した後でのみ、優先ビューが表示されます。Outlook を再起動すると、Outlook ユーザー インターフェイスにヒントが表示され、新しい優先受信トレイを使用する選択肢がユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="2a041-p106">Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![ユーザーが最初に Outlook on the web を開いたときの優先受信トレイの画像。](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="2a041-p107&quot;>低優先メールから優先受信トレイに切り替える場合は、その機能を有効にするか (&quot;試してみる")、解除するかを決めることができます。複数の (サポートされている) クライアントを持つユーザーの場合は、各クライアント上で個別に優先受信トレイを有効/無効にすることができます。次のようなヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a041-p107">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:</span></span>
  
![優先受信トレイがユーザーにロールアウトされてから、Outlook が再度開かれたときの優先受信トレイの画像。](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="2a041-p108">ユーザーが優先受信トレイの使用開始を決定すると、低優先メールは自動的に無効になります。低優先メール フォルダーが標準的なフォルダーに変換されると、ユーザーはそのフォルダーの名前の変更または削除を行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="2a041-p108">When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="2a041-138">特定のユーザーについて優先受信トレイの有効/無効を切り替える</span><span class="sxs-lookup"><span data-stu-id="2a041-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="2a041-139">この例では、Contoso 組織内の Tim Matthews に対して優先受信トレイを **無効** にします。</span><span class="sxs-lookup"><span data-stu-id="2a041-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span></span> <span data-ttu-id="2a041-140">ただし、Tim が機能を使えなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="2a041-140">However, it doesn't block the availability of the feature to him.</span></span> <span data-ttu-id="2a041-141">必要な場合は、引き続き、各クライアントでもう一度優先受信トレイを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2a041-141">If he wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="2a041-142">[リモート PowerShell で Exchange Online に接続する](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2a041-142">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2a041-p110">この手順を実行する前にアクセス許可が割り当てられている必要があります。必要なアクセス許可を確認するには、トピック「メッセージング ポリシーとコンプライアンスのアクセス許可」の項目「トランスポート ルール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-p110">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>

3. <span data-ttu-id="2a041-145">**Get-FocusedInbox** コマンドレットを実行します。例を示します。</span><span class="sxs-lookup"><span data-stu-id="2a041-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 

    ```powershell
    Get-FocusedInbox -Identity <tim@contoso.com>
    ```

4. <span data-ttu-id="2a041-146">FocusedInboxOn を探して、現在の設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="2a041-146">Look for FocusedInboxOn to view its current setting:</span></span>

    ![優先受信トレイの状態に関する PowerShell からの応答。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="2a041-148">次のコマンドレットを実行して、優先受信トレイを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2a041-148">Run the following cmdlet to turn off Focused Inbox:</span></span>

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
    ```

    <span data-ttu-id="2a041-149">または、次のコマンドレットを実行して、優先受信トレイを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a041-149">OR, run the following cmdlet to turn it on:</span></span>

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
    ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="2a041-150">トランスポート ルールを作成する UI を使用して、すべてのユーザーの優先ビューにメール メッセージを直接表示する</span><span class="sxs-lookup"><span data-stu-id="2a041-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="2a041-151"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a041-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="2a041-152">[**メール フロー**] \> [**ルール**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a041-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="2a041-153">![EAC 追加アイコン](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)を選択し、[**新しいルールを作成する...**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a041-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 

3. <span data-ttu-id="2a041-154">新しいルールの作成後、[**保存**] を選択してルールを開始します。</span><span class="sxs-lookup"><span data-stu-id="2a041-154">After you're done creating the new rule, select **Save** to start the rule.</span></span>

    <span data-ttu-id="2a041-155">次の図は、"Payroll Department"(給与課) からのすべてのメッセージを優先受信トレイに配信する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="2a041-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>

    ![優先受信トレイ、給与](../../media/focusedinbox-transport-rule.PNG)

    > [!NOTE]
    > <span data-ttu-id="2a041-157">この例のメッセージ ヘッダー値のテキストは、**X-MS-Exchange-Organization-BypassFocusedInbox** です。</span><span class="sxs-lookup"><span data-stu-id="2a041-157">The message header value text in this example is, **X-MS-Exchange-Organization-BypassFocusedInbox**.</span></span>
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="2a041-158">トランスポート ルールを作成する PowerShell を使用して、すべてのユーザーの優先ビューにメール メッセージを直接表示する</span><span class="sxs-lookup"><span data-stu-id="2a041-158">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="2a041-159">[リモート PowerShell で Exchange Online に接続する](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2a041-159">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2a041-p112">この手順を実行する前にアクセス許可が割り当てられている必要があります。必要なアクセス許可を確認するには、「[メッセージング ポリシーとコンプライアンスのアクセス許可](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help)」の項目「トランスポート ルール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-p112">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).</span></span>

3. <span data-ttu-id="2a041-162">たとえば、次のコマンドを実行すると、"Payroll Department"(給与課) からのすべてのメッセージを優先受信トレイに配信できます。</span><span class="sxs-lookup"><span data-stu-id="2a041-162">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>

    ```powershell
    New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
    ```

> [!IMPORTANT]
> <span data-ttu-id="2a041-163">この例の "X-MS-Exchange-Organization-BypassFocusedInbox" と "true" では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2a041-163">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="2a041-164">また、優先受信トレイは低優先メールをバイパスする X ヘッダーを優先します。したがって、この設定を低優先メールで使用すると、優先受信トレイで使用されます。</span><span class="sxs-lookup"><span data-stu-id="2a041-164">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="2a041-165">詳細な構文とパラメーターについては、「[New-TransportRule](/powershell/module/exchange/new-transportrule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-165">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2a041-166">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="2a041-166">How do you know this worked?</span></span>

<span data-ttu-id="2a041-167">メール メッセージのヘッダーをチェックして、そのメール メッセージが、優先受信トレイのトランスポート ルールをバイパスして受信トレイに届いているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2a041-167">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="2a041-168">優先受信トレイのトランスポート ルールが適用されている組織のメールボックスからメール メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a041-168">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="2a041-169">メッセージにスタンプされたヘッダーを調べると、**X-MS-Exchange-Organization-BypassFocusedInbox: true** ヘッダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a041-169">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="2a041-170">これは、迂回が機能していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2a041-170">This means the bypass is working.</span></span> <span data-ttu-id="2a041-171">ヘッダー情報を調べる方法については、「[電子メール メッセージのインターネット ヘッダー情報を表示する](https://go.microsoft.com/fwlink/p/?LinkId=822530)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-171">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span>

### <a name="what-will-the-user-see"></a><span data-ttu-id="2a041-172">ユーザーには何が表示されますか?</span><span class="sxs-lookup"><span data-stu-id="2a041-172">What will the user see?</span></span>

<span data-ttu-id="2a041-173">トランスポート ルールが設定されている場合、オーバーライドの通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a041-173">If a transport rule is in place, a notification will be shown for the override.</span></span> <span data-ttu-id="2a041-174">Outlook on the web は、 [常に他に移動] を無効にし、ツールチップを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a041-174">Outlook on the web will disable the "Always move to Other" and show a tooltip.</span></span> <span data-ttu-id="2a041-175">デスクトップ上の Outlook クライアントでは、[常に他に移動] を選択でき、ダイアログがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a041-175">Outlook clients on desktop will allow selection for "Always move to Other" and will pop up a dialog.</span></span>

## <a name="turn-onoff-clutter"></a><span data-ttu-id="2a041-176">低優先メールをオン/オフにする</span><span class="sxs-lookup"><span data-stu-id="2a041-176">Turn on/off Clutter</span></span>

<span data-ttu-id="2a041-p116">Microsoft では、一部のユーザーの低優先メールの動作が突然停止したという報告を受信しています。この問題が発生した場合、特定のユーザーの低優先メールを再び有効にすることができます。[組織での低優先メールの構成](../email/configure-clutter.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-p116">We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>

## <a name="faq-for-focused-inbox"></a><span data-ttu-id="2a041-180">優先受信トレイに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="2a041-180">FAQ for Focused Inbox</span></span>

<span data-ttu-id="2a041-181">ここでは、優先受信トレイについてよく寄せられる質問にお答えします。</span><span class="sxs-lookup"><span data-stu-id="2a041-181">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span>

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="2a041-182">組織で優先受信トレイをロール アウトする方法を制御できますか。</span><span class="sxs-lookup"><span data-stu-id="2a041-182">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="2a041-p117">はい。組織全体に対して優先受信トレイの有効/無効を切り替えることができます。また、指定したユーザーに対して有効/無効を切り替えることもできます。上記を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-p117">Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="2a041-186">優先受信トレイ機能を使用できるのは Office 2016 クライアントのみですか。</span><span class="sxs-lookup"><span data-stu-id="2a041-186">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="2a041-p118">はい、Office 2016 のユーザーのみが利用できます。Outlook 2013 以前にこの機能を移植する予定はありません。</span><span class="sxs-lookup"><span data-stu-id="2a041-p118">Yes, only users with Office 2016 are affected. The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="2a041-189">優先受信トレイの変更が Outlook で反映されるまでどれくらいかかりますか。</span><span class="sxs-lookup"><span data-stu-id="2a041-189">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="2a041-190">優先受信トレイを有効または無効にした場合、設定は、ユーザーが Outlook​​ を終了して再起動した後に有効になります。</span><span class="sxs-lookup"><span data-stu-id="2a041-190">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="2a041-191">優先受信トレイを有効にした場合、低優先メールはどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="2a041-191">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="2a041-p119">切り替えると、利用可能性の低いメールは [低優先メール] フォルダーに表示されなくなります。切り替え後は、受信トレイの [優先] タブと [その他] タブにメールが振り分けられます。アイテムを [低優先メール] フォルダーに移動するためのアルゴリズムが優先受信トレイに利用されています。つまり、[低優先メール] に移動されていたメールが、[その他] に移動するようになりました。既に [低優先メール] フォルダーにあるメッセージは、削除または移動するまで、[低優先メール] フォルダーに残ります。</span><span class="sxs-lookup"><span data-stu-id="2a041-p119">After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="2a041-196">[Tony Redmond](https://www.petri.com/author/tony-redmond) (Microsoft MVP) による投稿「 [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365)」 (Office 365 内の低優先メールを優先受信トレイに置き換える方法) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2a041-196">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="2a041-p120">低優先メールのユーザーを保持できますか。低優先メールと優先受信トレイの使用に関する Microsoft の推奨事項は何ですか。</span><span class="sxs-lookup"><span data-stu-id="2a041-p120">Can I keep users on Clutter? What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="2a041-p121">はい、低優先メールのユーザーを保持し、優先受信トレイを無効にすることはできます。ただし、最終的に低優先メールは優先受信トレイに完全に置き換えられるため、Microsoft ではすぐに優先受信トレイに移動することをお勧めします。Exchange Online で低優先メールを使用する場合の詳細については、次のブログの投稿を参照してください。[優先受信トレイに対する更新プログラムと低優先メールに関する Microsoft のプラン](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="2a041-p121">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="2a041-201">優先受信トレイにすべてのユーザーを移動する場合、エンド ユーザーに対して低優先メールを無効にすべきですか。</span><span class="sxs-lookup"><span data-stu-id="2a041-201">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="2a041-p122">いいえ。Set-Clutter コマンドレットを実行することで、明示的にメールボックスに対して低優先メールを無効にできます。ただし、これを行う場合、メールボックスの所有者に、受信トレイに残っている、[低優先メール] フォルダーに以前リダイレクトされたメッセージが表示されます。クライアントが優先受信トレイをサポートするバージョンにアップグレードされるまでに、これらのメッセージを処理する必要があります。したがって、アップグレードされたクライアントが使用できるようになるまでは、低優先メールを無効にしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2a041-p122">No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="2a041-206">優先受信トレイを管理するために 2 つの異なるコマンドレットがあるのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="2a041-206">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="2a041-207">優先受信トレイには、次の 2 つの状態が関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="2a041-207">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="2a041-208">**組織レベル**: 優先受信トレイの状態で、関連付けられた最終更新タイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="2a041-208">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span>

- <span data-ttu-id="2a041-209">**メールボックス レベル**: 優先受信トレイの状態で、関連付けられた最終更新タイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="2a041-209">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="2a041-210">Outlook はどのようにして、これらの 2 つの状態で表示する優先受信トレイの操作環境を決定するのですか。</span><span class="sxs-lookup"><span data-stu-id="2a041-210">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="2a041-p123">Outlook は、最終タイムスタンプを持つコマンドレットを選択して、表示する操作環境を決定します。既定では、どちらのタイム スタンプも "null" で、この場合、機能は有効です。</span><span class="sxs-lookup"><span data-stu-id="2a041-p123">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="2a041-213">組織で優先受信トレイを無効にしているときに、Get-FocusedInbox コマンドレットが "true" を返すのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="2a041-213">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="2a041-p124">優先受信トレイを制御するコマンドレットは 2 つあります。メールボックスに対して Get-FocusedInbox を実行すると、機能のメールボックス レベルの状態が返されます。Outlook の操作環境は、どちらのコマンドレットが最後に変更されたかに基づいて選択されます。</span><span class="sxs-lookup"><span data-stu-id="2a041-p124">There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="2a041-217">スクリプトを実行して優先受信トレイを有効にしているユーザーを確認することはできますか。</span><span class="sxs-lookup"><span data-stu-id="2a041-217">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="2a041-p125">いいえ。これは仕様です。優先受信トレイを有効にするのはクライアント側の設定なので、コマンドレットが実行できるのは、ユーザーのメールボックスがクライアントの操作環境に適しているかどうかを伝えることのみです。一部のクライアントで有効にして、それと同時に、その他のクライアントで無効にすることができます。たとえば、Outlook アプリと Outlook Mobile で有効にして、Outlook on the web で無効にすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="2a041-p125">No, and this is by design. Focused Inbox enablement is a client-side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>

## <a name="related-content"></a><span data-ttu-id="2a041-221">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="2a041-221">Related content</span></span>

<span data-ttu-id="2a041-222">[組織での低優先メールを構成](../email/configure-clutter.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="2a041-222">[Configure Clutter for your organization](../email/configure-clutter.md) (article)</span></span>\
<span data-ttu-id="2a041-223">[共有メールボックスの設定を構成](../email/configure-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="2a041-223">[Configure shared mailbox settings](../email/configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="2a041-224">[署名と免責事項を作成](create-signatures-and-disclaimers.md) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="2a041-224">[Create signatures and disclaimers](create-signatures-and-disclaimers.md) (video)</span></span>
