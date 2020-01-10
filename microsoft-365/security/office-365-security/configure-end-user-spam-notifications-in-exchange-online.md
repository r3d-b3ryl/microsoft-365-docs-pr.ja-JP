---
title: Exchange Online エンドユーザースパム通知の構成
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 既定の企業全体のスパムフィルターポリシーまたはドメインに適用されるカスタムスパムフィルターポリシーに対して、エンドユーザーのスパム通知を構成できます。
ms.openlocfilehash: 8e77fbb619db776d7231f6e1f944f1237c1d601c
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021993"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="2bebe-103">Exchange Online エンドユーザースパム通知の構成</span><span class="sxs-lookup"><span data-stu-id="2bebe-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bebe-104">このトピックはクラウドでホストされたメールボックスを保護している Exchange Online のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="2bebe-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="2bebe-105">オンプレミスのメールボックスを保護している Exchange Online Protection (EOP) スタンドアロンのお客様は、代わりに次のトピックを参照してください。 [EOP でエンドユーザーのスパム通知を構成](configure-end-user-spam-notifications-in-eop.md)します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="2bebe-106">既定の企業全体のスパムフィルターポリシーまたはカスタムスパムフィルターポリシーのエンドユーザースパム通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="2bebe-107">エンドユーザーのスパム通知メッセージを有効にすると、ユーザーは自分のスパム検疫済みメッセージを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-107">Enabling end-user spam notification messages lets your users manage their own spam-quarantined messages.</span></span> 
  
<span data-ttu-id="2bebe-p103">エンド ユーザー向けスパム通知は、構成した期間 (1 ～ 15 日の間で指定可能) に、エンド ユーザーが受信したすべてのスパム検疫済みメッセージのリストを含みます。通知メッセージを記述する言語を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="2bebe-110">通知メッセージを受信すると、エンドユーザーは次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="2bebe-111">[**送信者をブロック**する] Office 365 で、受信拒否リストに送信者を追加する場合。</span><span class="sxs-lookup"><span data-stu-id="2bebe-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="2bebe-112">メッセージがスパムではなく、Office 365 がメールボックスにメッセージを送信する場合は、**リリースを解放**します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-112">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="2bebe-113">プレビューやリリースなどの他のアクションを実行する場合は、セキュリティ & コンプライアンスセンター内の検疫ポータルに移動するように**確認**します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2bebe-114">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="2bebe-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="2bebe-115">予想所要時間:2 分</span><span class="sxs-lookup"><span data-stu-id="2bebe-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="2bebe-116">「この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bebe-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="2bebe-117">必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)」トピックの「スパム対策」のエントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bebe-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="2bebe-118">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bebe-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="2bebe-119">EAC を使って、エンド ユーザー向けスパム通知を構成する</span><span class="sxs-lookup"><span data-stu-id="2bebe-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="2bebe-120">Exchange 管理センター (EAC) で、 **[保護]** \> **[スパム フィルター]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="2bebe-121">エンドユーザーのスパム通知を有効にするスパムフィルターポリシーを選択します (既定では無効になっています)。</span><span class="sxs-lookup"><span data-stu-id="2bebe-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="2bebe-122">右側のウィンドウにポリシーに関する概要情報が表示されるので、**[エンド ユーザーのスパム通知の構成]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bebe-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="2bebe-123">以降のダイアログ ボックスで、次のオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="2bebe-p105">**[エンド ユーザーのスパム通知を有効にする]** このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。(反対にこのポリシーを有効にすると、このチェック ボックスをオフにすることで、ポリシー用のエンド ユーザーのスパム通知を無効にすることができます。)</span><span class="sxs-lookup"><span data-stu-id="2bebe-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="2bebe-p106">**エンド ユーザーのスパム通知を～日ごとに送信** エンド ユーザーのスパム通知を送信する頻度を指定します。既定値は 3 日です。1 ～ 15 日の間で指定できます。たとえば 7 日間を指定した場合の通知には、直前の 7 日間のユーザー宛のメッセージのうち、スパム検疫に転送されたすべてのメッセージのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="2bebe-130">**通知の言語** ドロップダウン リストを使用して、このポリシーにエンドユーザーのスパム通知の作成に使用する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="2bebe-131">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bebe-131">Click **Save**.</span></span> <span data-ttu-id="2bebe-132">エンドユーザーのスパム通知の設定を含む、スパムフィルターポリシー設定の概要が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="2bebe-133">エンドユーザーのスパム通知は、有効になっているスパムフィルターポリシーに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="2bebe-134">>  エンド ユーザーの迷惑メールの通知は、1 日 1 回だけ送信されます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="2bebe-135">特定のカスタマーについて通知の配信時間を保証することは不可能であり、設定もできません。</span><span class="sxs-lookup"><span data-stu-id="2bebe-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="2bebe-136">**ヒント:** エンドユーザーのスパム通知を完全に実装する前に限定された一連のユーザーに送信してテストする場合は、ユーザーが存在するドメインに対してエンドユーザーのスパム通知を有効にするカスタムスパムフィルターポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="2bebe-137">次に、EAC の [**メールフロー \>ルール**] で、メールフロールール (トランスポートルールとも呼ばれます) を作成して、通知を受信するユーザーの例外を除き、quarantine@messaging.microsoft.com (通知を送信する電子メールアドレス) からのメッセージをブロックします。</span><span class="sxs-lookup"><span data-stu-id="2bebe-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="2bebe-138">下の図は、Contoso.com ドメインからの 2 人のユーザー (SaraD と AlexD) に対する例外を作成する例です。</span><span class="sxs-lookup"><span data-stu-id="2bebe-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![エンド ユーザー向けスパム通知をテストするためのトランスポート ルール](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="2bebe-140">SCC を使用してエンドユーザーのスパム通知を構成する</span><span class="sxs-lookup"><span data-stu-id="2bebe-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="2bebe-141">セキュリティ/コンプライアンスセンター (SCC) を使用して、エンドユーザーのスパム通知を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="2bebe-142">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-142">Follow these steps:</span></span>

1. <span data-ttu-id="2bebe-143">セキュリティ/コンプライアンスセンターを開き、[**脅威管理** \> **ポリシー** \>のスパム**対策**] に移動するか、 https://protection.office.com/antispam直接リンクを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="2bebe-144">エンドユーザーのスパム通知を有効にするスパムフィルターポリシーの横にある下矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bebe-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="2bebe-145">[**エンドユーザーのスパム通知の構成**] リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bebe-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="2bebe-146">以降のダイアログ ボックスで、次のオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="2bebe-p111">**[エンド ユーザーのスパム通知を有効にする]** このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。(反対にこのポリシーを有効にすると、このチェック ボックスをオフにすることで、ポリシー用のエンド ユーザーのスパム通知を無効にすることができます。)</span><span class="sxs-lookup"><span data-stu-id="2bebe-p111">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="2bebe-p112">**エンド ユーザーのスパム通知を～日ごとに送信** エンド ユーザーのスパム通知を送信する頻度を指定します。既定値は 3 日です。1 ～ 15 日の間で指定できます。たとえば 7 日間を指定した場合の通知には、直前の 7 日間のユーザー宛のメッセージのうち、スパム検疫に転送されたすべてのメッセージのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-p112">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="2bebe-153">**通知の言語** ドロップダウン リストを使用して、このポリシーにエンドユーザーのスパム通知の作成に使用する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bebe-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="2bebe-154">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bebe-154">Click **Save**.</span></span> <span data-ttu-id="2bebe-155">エンドユーザーのスパム通知の設定を含む、スパムフィルターポリシー設定の概要がウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bebe-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="2bebe-156">関連情報</span><span class="sxs-lookup"><span data-stu-id="2bebe-156">For more information</span></span>

[<span data-ttu-id="2bebe-157">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="2bebe-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
