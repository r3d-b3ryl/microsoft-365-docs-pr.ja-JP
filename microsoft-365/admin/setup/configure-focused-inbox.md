---
title: 組織内のすべてのユーザー用に優先受信トレイを構成する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: '組織のすべてのユーザーまたは特定のユーザー用に優先受信トレイを構成する方法について説明します。 '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779931"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>組織内のすべてのユーザー用に優先受信トレイを構成する

  職場のすべてのユーザー用にメールの動作を構成する必要がある場合は、この記事が役立ちます。 ここでは、業務向けにカスタマイズする方法や無効にする方法について説明しており、[よく寄せられる質問](#faq-for-focused-inbox)に回答しています。  <br/> 自分に対してだけ優先受信トレイを無効にする場合は、「[優先受信トレイを無効にする](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2)」を参照してください。  
   
If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>組織で優先受信トレイの有効/無効を切り替える

組織のすべてのユーザーに対して優先受信トレイの有効/無効を切り替えるには、PowerShell を使用します。 この操作を Microsoft 365 管理センターで行う場合は、 エンジニアリング チームにお知らせください。 **[ここで投票してください。](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **優先受信トレイを無効にする**
  
The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients. 
  
1. [リモート PowerShell で Exchange Online に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
3. 
            **Get-OrganizationConfig** コマンドレットを実行します。 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. **FocusedInboxOn** を探して、現在の設定を表示します。 
    
    ![優先受信トレイの状態に関する PowerShell からの応答。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. 次のコマンドレットを実行して、優先受信トレイを無効にします。
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. **Get-OrganizationConfig** コマンドレットをもう一度実行し、FocusedInboxOn が $false に設定されていることを確認します。これは、FocusedInbox がオフになったことを意味します。 
    
 **優先受信トレイを有効にする**
  
- 上の手順 5 で、次のコマンドレットを実行して、優先受信トレイを有効にします。
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>優先受信トレイを有効にすると、ユーザーに何が表示されますか。 

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![ユーザーが最初に Outlook on the web を開いたときの優先受信トレイの画像。](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![優先受信トレイがユーザーにロールアウトされてから、Outlook が再度開かれたときの優先受信トレイの画像。](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>特定のユーザーについて優先受信トレイの有効/無効を切り替える

This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients. 
  
1. [リモート PowerShell で Exchange Online に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.
    
3. **Get-FocusedInbox** コマンドレットを実行します。例を示します。 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. FocusedInboxOn を探して、現在の設定を表示します。
    
    ![優先受信トレイの状態に関する PowerShell からの応答。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. 次のコマンドレットを実行して、優先受信トレイを無効にします。
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. または、次のコマンドレットを実行して、優先受信トレイを有効にします。
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>トランスポート ルールを作成する UI を使用して、すべてのユーザーの優先ビューにメール メッセージを直接表示する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。
    
2. [**メール フロー**] \> [**ルール**] に移動します。 ![EAC 追加アイコン](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)を選択し、[**新しいルールを作成する...**] を選択します。 
    
3. 新しいルールの作成後、[**保存**] を選択してルールを開始します。 
    
    次の図は、"Payroll Department"(給与課) からのすべてのメッセージを優先受信トレイに配信する例を示しています。
    
    ![優先受信トレイ、給与](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>トランスポート ルールを作成する PowerShell を使用して、すべてのユーザーの優先ビューにメール メッセージを直接表示する

1. [リモート PowerShell で Exchange Online に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).

3. たとえば、次のコマンドを実行すると、"Payroll Department"(給与課) からのすべてのメッセージを優先受信トレイに配信できます。
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> この例の "X-MS-Exchange-Organization-BypassFocusedInbox" と "true" では、大文字と小文字が区別されます。
> また、優先受信トレイは低優先メールをバイパスする X ヘッダーを優先します。したがって、この設定を低優先メールで使用すると、優先受信トレイで使用されます。 詳細な構文とパラメーターについては、「[New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194)」を参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メール メッセージのヘッダーをチェックして、そのメール メッセージが、優先受信トレイのトランスポート ルールをバイパスして受信トレイに届いているかどうかを確認できます。 優先受信トレイのトランスポート ルールが適用されている組織のメールボックスからメール メッセージを選択します。 メッセージにスタンプされたヘッダーを調べると、**X-MS-Exchange-Organization-BypassFocusedInbox: true** ヘッダーが表示されます。 これは、迂回が機能していることを意味します。 ヘッダー情報を調べる方法については、「[電子メール メッセージのインターネット ヘッダー情報を表示する](https://go.microsoft.com/fwlink/p/?LinkId=822530)」を参照してください。 
 
## <a name="turn-onoff-clutter"></a>低優先メールをオン/オフにする
 
We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>優先受信トレイに関する FAQ

ここでは、優先受信トレイについてよく寄せられる質問にお答えします。 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>組織で優先受信トレイをロール アウトする方法を制御できますか。

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>優先受信トレイ機能を使用できるのは Office 2016 クライアントのみですか。

はい、Office 2016 のユーザーのみが利用できます。 Outlook 2013 以前にこの機能を移植する予定はありません。
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>優先受信トレイの変更が Outlook で反映されるまでどれくらいかかりますか。

優先受信トレイを有効または無効にした場合、設定は、ユーザーが Outlook​​ を終了して再起動した後に有効になります。
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>優先受信トレイを有効にした場合、低優先メールはどうなりますか。

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
[Tony Redmond](https://www.petri.com/author/tony-redmond) (Microsoft MVP) による投稿「 [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365)」 (Office 365 内の低優先メールを優先受信トレイに置き換える方法) を参照してください。
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>低優先メールのユーザーを保持できますか。 低優先メールと優先受信トレイの使用に関する Microsoft の推奨事項は何ですか。

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>優先受信トレイにすべてのユーザーを移動する場合、エンド ユーザーに対して低優先メールを無効にすべきですか。

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>優先受信トレイを管理するために 2 つの異なるコマンドレットがあるのはなぜですか。

優先受信トレイには、次の 2 つの状態が関連付けられます。
  
- **組織レベル**: 優先受信トレイの状態で、関連付けられた最終更新タイムスタンプ。 
    
- **メールボックス レベル**: 優先受信トレイの状態で、関連付けられた最終更新タイムスタンプ 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Outlook はどのようにして、これらの 2 つの状態で表示する優先受信トレイの操作環境を決定するのですか。

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>組織で優先受信トレイを無効にしているときに、Get-FocusedInbox コマンドレットが "true" を返すのはなぜですか。

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>スクリプトを実行して優先受信トレイを有効にしているユーザーを確認することはできますか。

No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.
