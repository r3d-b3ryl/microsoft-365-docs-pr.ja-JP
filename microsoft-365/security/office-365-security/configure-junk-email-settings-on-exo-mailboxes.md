---
title: Exchange Online のメールボックスで迷惑メール設定を構成する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスの迷惑メール設定を構成する方法について説明します。 これらの設定の多くは、Outlook または web 上の Outlook でユーザーが使用できます。
ms.openlocfilehash: ea3727bcfa90229da64db96b531885383d2bf7ed
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206630"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a><span data-ttu-id="7b084-104">Exchange Online のメールボックスで迷惑メール設定を構成する</span><span class="sxs-lookup"><span data-stu-id="7b084-104">Configure junk email settings on Exchange Online mailboxes</span></span>

<span data-ttu-id="7b084-105">Exchange Online にメールボックスを持つ Microsoft 365 組織では、組織のスパム対策の設定は Exchange Online Protection (EOP) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="7b084-105">In Microsoft 365 organizations with mailboxes in Exchange Online, organizational anti-spam settings are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="7b084-106">詳細については、「 [EOP のスパム対策保護](anti-spam-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-106">For more information, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

<span data-ttu-id="7b084-107">ただし、管理者が Exchange Online の個々のメールボックスで構成できる特定のスパム対策設定もあります。</span><span class="sxs-lookup"><span data-stu-id="7b084-107">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="7b084-108">**迷惑メールルールを有効または無効**にする: 迷惑メールルールは、すべてのメールボックスで既定で有効になっている迷惑メールルールという名前の非表示の受信トレイルールです。</span><span class="sxs-lookup"><span data-stu-id="7b084-108">**Enable or disable the junk email rule**: The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="7b084-109">迷惑メールルールは、次の機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="7b084-109">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="7b084-110">スパム**対策ポリシーに基づいて、メッセージを [迷惑メール] フォルダーに移動する**: スパムフィルター verdict の [**メッセージを迷惑メールフォルダーに移動する**] アクションを使用してスパム対策ポリシーを構成した場合、迷惑メールフィルタールールは、メッセージがメールボックスに配信された後に、そのメッセージを迷惑メールフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="7b084-110">**Move messages to the Junk Email folder based on anti-spam policies**: When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="7b084-111">スパムフィルター処理の詳細については、「verdicts」の「スパム[対策ポリシーの構成 EOP](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-111">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="7b084-112">同様に、0時間の自動削除 (ZAP) によって配信されたメッセージがスパムまたはフィッシングであると判断された場合、迷惑メールフィルタールールはメッセージを迷惑メールフォルダースパムフィルター verdict アクション**に移動**するための迷惑メールフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="7b084-112">Similarly, if zero-hour auto purge (ZAP) determines a delivered message is spam or phish, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="7b084-113">ZAP の詳細については、「 [Exchange Online のゼロ時間自動削除 (ZAP)](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-113">For more information about ZAP, see [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).</span></span>
  
  - <span data-ttu-id="7b084-114">**ユーザーが outlook または web 上の outlook で自分自身に対して構成する迷惑メール設定**: セーフリスト_コレクション_は、各メールボックスの差出人セーフリスト、宛先セーフリスト、および受信拒否リストです。</span><span class="sxs-lookup"><span data-stu-id="7b084-114">**Junk email settings that users configure for themselves in Outlook or Outlook on the web**: The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Block senders list on each mailbox.</span></span> <span data-ttu-id="7b084-115">これらのリストのエントリは、迷惑メールルールがメッセージを受信トレイまたは迷惑メールフォルダーに移動するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7b084-115">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="7b084-116">ユーザーは、Outlook または web 上の Outlook (旧称 Outlook Web App) で自分のメールボックスのセーフリストコレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-116">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="7b084-117">管理者は、任意のユーザーのメールボックスでセーフリストコレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-117">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="7b084-118">メールボックスで迷惑メールルールが有効になっている場合、EOP は迷惑メールフォルダーにメッセージを移動することができます。これにより、スパムフィルター処理 verdict アクションに基づいて、メールボックスの迷惑メールフォルダーにメッセージを**移動**したり、受信拒否リストに含まれるメッセージを迷惑メールフォルダーに配信することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="7b084-118">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="7b084-119">迷惑メールルールがメールボックスで無効になっている場合、EOP は、迷惑メールフォルダーにメッセージを移動することはできません verdict アクションは、迷惑メールフォルダーまたはメールボックス上のセーフリストコレクションに**メッセージを移動**します。</span><span class="sxs-lookup"><span data-stu-id="7b084-119">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="7b084-120">管理者は、Exchange Online PowerShell を使用して、メールボックスの迷惑メールルールの状態を無効、有効にし、表示することができます。</span><span class="sxs-lookup"><span data-stu-id="7b084-120">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="7b084-121">管理者は、Exchange Online PowerShell を使用して、メールボックス (差出人セーフリスト、宛先セーフリスト、および受信拒否リスト) のセーフリストコレクションのエントリを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b084-121">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Block senders list).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7b084-122">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="7b084-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7b084-123">これらの手順を実行するには、Exchange Online PowerShell のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-123">You can only use Exchange Online PowerShell to perform these procedures.</span></span> <span data-ttu-id="7b084-124">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7b084-125">これらの手順を実行する前に、アクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b084-125">You need to be assigned permissions before you can do these procedures.</span></span> <span data-ttu-id="7b084-126">具体的には、**メール受信者**の役割 (既定では、**組織の管理**、**受信者の管理**、およびカスタムの**メール受信者**の役割グループに割り当てられます) または**ユーザーオプション**の役割 (既定では、**組織の管理**と**ヘルプデスク**の役割グループに割り当てられます) が必要です。</span><span class="sxs-lookup"><span data-stu-id="7b084-126">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management**, **Recipient Management**, and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="7b084-127">Exchange Online の役割グループにユーザーを追加するには、「 [Exchange online で役割グループを変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-127">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="7b084-128">既定のアクセス許可を持つユーザーは、 [Exchange Online PowerShell へのアクセス](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)権を持っている限り、自分のメールボックスでこれらの手順を実行できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-128">Note that a user with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7b084-129">EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b084-129">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="7b084-130">詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-130">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

- <span data-ttu-id="7b084-131">共有メールボックスの信頼できる差出人は、Azure AD に同期されず、設計に EOP れます。</span><span class="sxs-lookup"><span data-stu-id="7b084-131">Safe Senders for shared mailboxes are not synchronized to Azure AD and EOP by design.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="7b084-132">Exchange Online の PowerShell を使用してメールボックス内の迷惑メールルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="7b084-132">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="7b084-133">Outlook (Exchange キャッシュ モードで) または Web 上の Outlook で開かれているメールボックスで迷惑メール ルールを無効にするには、 **Set-MailboxJunkEmailConfiguration** コマンドレットのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-133">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="7b084-134">メールボックスが開かれていない場合は、次のエラーが表示されます。 `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` このエラーを一括操作で抑制する場合は、 `-ErrorAction SlientlyContinue` **set-mailboxjunkemailconfiguration**コマンドに追加できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-134">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

<span data-ttu-id="7b084-135">メールボックスで迷惑メール ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b084-135">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="7b084-136">次の例では、Ori Epstein のメールボックスで迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7b084-136">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="7b084-137">次の例では、組織内のすべてのユーザーのメールボックスの迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="7b084-137">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="7b084-138">構文およびパラメーターの詳細については、「 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-138">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="7b084-139">ユーザーが自分のメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7b084-139">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="7b084-140">このエラーを一括操作で抑制するには、 `-ErrorAction SlientlyContinue` **set-mailboxjunkemailconfiguration**コマンドにを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b084-140">To suppress this error for bulk operations, add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
> 
> - <span data-ttu-id="7b084-141">迷惑メールルールを無効にしても、Outlook の迷惑メールフィルター (構成方法によって異なります) では、メッセージがスパムであるかどうかを判断し、メッセージを自分のスパム verdict およびメールボックスのセーフリストコレクションに基づいて受信トレイまたは迷惑メールフォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-141">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="7b084-142">詳細については、このトピックの「[Outlook での迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-142">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7b084-143">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="7b084-143">How do you know this worked?</span></span>

<span data-ttu-id="7b084-144">メールボックスで迷惑メール ルールを正常に有効または無効にしたことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b084-144">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="7b084-145">_ \< MailboxIdentity \> _をメールボックスの名前、エイリアス、または電子メールアドレスに置き換え、次のコマンドを実行して**Enabled**プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="7b084-145">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="7b084-146">Exchange Online の PowerShell を使用してメールボックスのセーフリストコレクションを構成する</span><span class="sxs-lookup"><span data-stu-id="7b084-146">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="7b084-147">メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b084-147">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="7b084-148">既定では、ユーザーは Outlook または web 上の Outlook の自分のメールボックスでセーフリストコレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-148">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="7b084-149">管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-149">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="7b084-150">次の表に、これらのパラメーターの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="7b084-150">These parameters are described in the following table.</span></span>

|||
|---|---|
|<span data-ttu-id="7b084-151">**Set-mailboxjunkemailconfiguration のパラメーター**</span><span class="sxs-lookup"><span data-stu-id="7b084-151">**Parameter on Set-MailboxJunkEmailConfiguration**</span></span>|<span data-ttu-id="7b084-152">**Outlook on the web の設定**</span><span class="sxs-lookup"><span data-stu-id="7b084-152">**Outlook on the web setting**</span></span>|
|<span data-ttu-id="7b084-153">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="7b084-153">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="7b084-154">**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**</span><span class="sxs-lookup"><span data-stu-id="7b084-154">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="7b084-155">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="7b084-155">_ContactsTrusted_</span></span>|<span data-ttu-id="7b084-156">**自分の連絡先からのメールを信頼する**</span><span class="sxs-lookup"><span data-stu-id="7b084-156">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="7b084-157">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="7b084-157">_TrustedListsOnly_</span></span>|<span data-ttu-id="7b084-158">**[差出人セーフリスト] と [セーフリスト] のアドレスからの電子メールのみを信頼する**</span><span class="sxs-lookup"><span data-stu-id="7b084-158">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="7b084-159">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7b084-159">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="7b084-160">**これらの送信者からのメールを [迷惑メール] フォルダーに移動しない**</span><span class="sxs-lookup"><span data-stu-id="7b084-160">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="7b084-161"><sup>\*</sup>**メモ**:</span><span class="sxs-lookup"><span data-stu-id="7b084-161"><sup>\*</sup> **Notes**:</span></span>

- <span data-ttu-id="7b084-162">Exchange Online では、差出人セーフリストまたは_TrustedSendersAndDomains_パラメーターの**ドメインエントリ**は認識されないため、電子メールアドレスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b084-162">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="7b084-163">スタンドアロン EOP でディレクトリ同期を使用すると、ドメインエントリは既定で同期されませんが、ドメインの同期を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7b084-163">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="7b084-164">詳細については、「 [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-164">For more information, see [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange).</span></span>

- <span data-ttu-id="7b084-165">**Set-mailboxjunkemailconfiguration**コマンドレットを使用して、宛先セーフリストを直接変更することはできません ( _TrustedRecipientsAndDomains_パラメーターは機能しません)。</span><span class="sxs-lookup"><span data-stu-id="7b084-165">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="7b084-166">信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。</span><span class="sxs-lookup"><span data-stu-id="7b084-166">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="7b084-167">メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b084-167">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="7b084-168">複数の値を入力して、 _BlockedSendersAndDomains_パラメーターと_TrustedSendersAndDomains_パラメーターの既存のエントリを上書きするには、次の構文を使用し `"<Value1>","<Value2>"...` ます。</span><span class="sxs-lookup"><span data-stu-id="7b084-168">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="7b084-169">他の既存のエントリに影響を与えずに、1つまたは複数の値を追加または削除するには、次の構文を使用します。`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="7b084-169">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="7b084-170">以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7b084-170">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="7b084-171">Shopping@fabrikam.com の値を受信拒否リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="7b084-171">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="7b084-172">[差出人セーフリスト] および [宛先セーフリスト] から値 chris@fourthcoffee.com を削除します。</span><span class="sxs-lookup"><span data-stu-id="7b084-172">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="7b084-173">信頼できる差出人として扱われるように [連絡先] フォルダー内の連絡先を構成する。</span><span class="sxs-lookup"><span data-stu-id="7b084-173">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="7b084-174">次の例では、組織内の全ユーザーのメールボックスの受信拒否リストから contoso.com ドメインを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b084-174">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="7b084-175">構文およびパラメーターの詳細については、「 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-175">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
> 
> - <span data-ttu-id="7b084-176">ユーザーが自分のメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="7b084-176">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="7b084-177">このエラーを一括操作で抑制するには、 `-ErrorAction SlientlyContinue` **set-mailboxjunkemailconfiguration**コマンドにを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b084-177">To suppress this error for bulk operations, add `-ErrorAction SlientlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
> 
> - <span data-ttu-id="7b084-178">迷惑メールルールがメールボックスで無効になっている場合でも、セーフリストコレクションを構成することができます。また、Outlook の迷惑メールフィルターは、受信トレイまたは迷惑メールフォルダーにメッセージを移動できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-178">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="7b084-179">詳細については、このトピックの「[Outlook での迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-179">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>
> 
> - <span data-ttu-id="7b084-180">Outlook の迷惑メールフィルターには、追加のセーフリストのコレクション設定があります (たとえば、**電子メールが [差出人セーフリスト] に自動的に追加**されます)。</span><span class="sxs-lookup"><span data-stu-id="7b084-180">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list**).</span></span> <span data-ttu-id="7b084-181">詳細については、「[迷惑メールフィルターを使用して表示するメッセージを制御する](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-181">For more information, see [Use Junk Email Filters to control which messages you see](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7b084-182">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="7b084-182">How do you know this worked?</span></span>

<span data-ttu-id="7b084-183">メールボックスにセーフリスト コレクションを正常に構成したことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b084-183">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="7b084-184">_ \< MailboxIdentity \> _をメールボックスの名前、エイリアス、または電子メールアドレスに置き換え、次のコマンドを実行してプロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="7b084-184">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="7b084-185">値のリストが長すぎる場合は、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b084-185">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="7b084-186">Outlook での迷惑メール設定について</span><span class="sxs-lookup"><span data-stu-id="7b084-186">About junk email settings in Outlook</span></span>

<span data-ttu-id="7b084-187">Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b084-187">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="7b084-188">詳細については、「 [Microsoft 365 Apps for enterprise、office 2019、および office 2016 用の管理用テンプレートファイル (ADMX/ADML) と Office カスタマイズツール](https://www.microsoft.com/download/details.aspx?id=49030)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-188">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).</span></span>

<span data-ttu-id="7b084-189">Outlook の迷惑メールフィルターで、[**ホーム**迷惑メール] オプションの [オート**フィルターなし**] オプションが既定値に設定されている場合 \> **Junk** \> **Junk E-Mail Options** \> **Options**、outlook は massages をスパムとして分類しませんが、セーフリストコレクション (差出人セーフリスト、宛先セーフリスト、受信拒否リスト) を使用して、メッセージを配信後に迷惑メールフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="7b084-189">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="7b084-190">これらの設定の詳細については、「[迷惑メールフィルターの概要](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-190">For more information about these settings, see [Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="7b084-191">Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="7b084-191">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="7b084-192">このスパム分類は、EOP によって決定されるスパム信頼レベル (SCL) とは別のものです。</span><span class="sxs-lookup"><span data-stu-id="7b084-192">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="7b084-193">実際には、Outlook は EOP の SCL を無視します (スパムフィルターをスキップするようにメッセージにマークされている場合を除きます)。また、そのメッセージがスパムであるかどうかを判断するために、独自の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b084-193">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="7b084-194">当然のことですが、スパム verdict から EOP と Outlook を同じにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b084-194">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="7b084-195">これらの設定の詳細については、「[迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-195">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="7b084-196">11月2016に、Microsoft は、Exchange と Outlook の SmartScreen フィルターのスパム定義の更新を中止しました。</span><span class="sxs-lookup"><span data-stu-id="7b084-196">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="7b084-197">既存の SmartScreen スパム定義は残されていましたが、その有効性は時間とともに低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b084-197">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="7b084-198">詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7b084-198">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="7b084-199">そのため、Outlook の迷惑メールフィルターは、メールボックスで迷惑メールルールが無効になっている場合でも、メールボックスのセーフリストコレクションと独自のスパム分類を使用して、メッセージを迷惑メールフォルダーに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="7b084-199">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="7b084-200">Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="7b084-200">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="7b084-201">セーフリストコレクションは Exchange Online メールボックスに保存されるので、Outlook のセーフリストコレクションに対する変更は web 上の Outlook に表示され、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="7b084-201">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

## <a name="limits-for-junk-email-settings"></a><span data-ttu-id="7b084-202">迷惑メールの設定の制限</span><span class="sxs-lookup"><span data-stu-id="7b084-202">Limits for junk email settings</span></span>

<span data-ttu-id="7b084-203">ユーザーのメールボックスに格納されているセーフリストコレクション (差出人セーフリスト、宛先セーフリスト、および受信拒否リスト) は、EOP にも同期されます。</span><span class="sxs-lookup"><span data-stu-id="7b084-203">The safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) that's stored in the user's mailbox is also synchronized to EOP.</span></span> <span data-ttu-id="7b084-204">ディレクトリ同期の場合、セーフリストコレクションは Azure AD に同期されます。</span><span class="sxs-lookup"><span data-stu-id="7b084-204">With directory synchronization, the safelist collection is synchronized to Azure AD.</span></span>

- <span data-ttu-id="7b084-205">ユーザーのメールボックスのセーフリストコレクションには、すべてのリストと、追加の迷惑メールフィルター設定を含む 510 KB の制限があります。</span><span class="sxs-lookup"><span data-stu-id="7b084-205">The safelist collection in the user's mailbox has a limit of 510 KB, which includes all lists, plus additional junk email filter settings.</span></span> <span data-ttu-id="7b084-206">ユーザーがこの制限を超えると、次のような Outlook エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b084-206">If a user exceeds this limit, they will receive an Outlook error that looks like this:</span></span>

  > <span data-ttu-id="7b084-207">サーバーの迷惑メールリストに追加できません。</span><span class="sxs-lookup"><span data-stu-id="7b084-207">Cannot/Unable add to the server Junk E-mail lists.</span></span> <span data-ttu-id="7b084-208">サーバーで許可されているサイズを超えています。</span><span class="sxs-lookup"><span data-stu-id="7b084-208">You are over the size allowed on the server.</span></span> <span data-ttu-id="7b084-209">迷惑メールの一覧がサーバーで許可されているサイズまで縮小されるまで、サーバー上の迷惑メールフィルターは無効になります。</span><span class="sxs-lookup"><span data-stu-id="7b084-209">The Junk E-mail filter on the server will be disabled until your Junk E-mail lists have been reduced to the size allowed by the server.</span></span>

  <span data-ttu-id="7b084-210">この制限の詳細と変更方法については、「 [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b084-210">For more information about this limit and how to change it, see [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit).</span></span>

- <span data-ttu-id="7b084-211">EOP の同期されたセーフリストコレクションの同期の制限は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7b084-211">The synchronized safelist collection in EOP has the following synchronization limits:</span></span>

  - <span data-ttu-id="7b084-212">[差出人セーフリスト]、[宛先セーフリスト]、および [外部連絡先からの**電子メールが信頼**されている場合、連絡先からのすべてのエントリが有効になります。1024</span><span class="sxs-lookup"><span data-stu-id="7b084-212">1024 total entries in the Safe Senders list, the Safe Recipients list, and external contacts if **Trust email from my contacts** is enabled.</span></span>
  - <span data-ttu-id="7b084-213">受信拒否リストと禁止ドメインリストに含まれるエントリの合計は500です。</span><span class="sxs-lookup"><span data-stu-id="7b084-213">500 total entries in the Blocked Senders list and Blocked Domains list.</span></span>

  <span data-ttu-id="7b084-214">1024エントリの制限に達すると、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="7b084-214">When the 1024 entry limit is reached, the following things happen:</span></span>
  
  - <span data-ttu-id="7b084-215">このリストは、PowerShell および Outlook on the web のエントリを受け付けなくなりますが、エラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7b084-215">The list stops accepting entries in PowerShell and Outlook on the web, but no error is displayed.</span></span>

    <span data-ttu-id="7b084-216">Outlook ユーザーは、1024個を超えるエントリを引き続き追加することができます。これは、Outlook の制限の 510 KB に達するまでです。</span><span class="sxs-lookup"><span data-stu-id="7b084-216">Outlook users can continue to add more than 1024 entries until they reach the Outlook limit of 510 KB.</span></span> <span data-ttu-id="7b084-217">EOP フィルターがメールボックスに配信される前にメッセージをブロックしない限り (メールフロールール、スプーフィング防止など)、Outlook はこれらの追加エントリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b084-217">Outlook can use these additional entries, as long as an EOP filter doesn't block the message before delivery to the mailbox (mail flow rules, anti-spoofing, etc.).</span></span>

- <span data-ttu-id="7b084-218">ディレクトリ同期を使用すると、エントリは次の順序で Azure AD に同期されます。</span><span class="sxs-lookup"><span data-stu-id="7b084-218">With directory synchronization, the entries are synchronized to Azure AD in the following order:</span></span>

  1. <span data-ttu-id="7b084-219">連絡先**からの信頼電子メール**が有効になっている場合のメール連絡先。</span><span class="sxs-lookup"><span data-stu-id="7b084-219">Mail contacts if **Trust email from my contacts** is enabled.</span></span>
  2. <span data-ttu-id="7b084-220">差出人セーフリストと宛先セーフリストは、最初の1024エントリに対して変更が行われるたびに、組み合わせ、重複除外、およびアルファベット順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="7b084-220">The Safe Sender list and Safe Recipient list are combined, de-duplicated, and sorted alphabetically whenever a change is made for the first 1024 entries.</span></span>

  <span data-ttu-id="7b084-221">最初の1024エントリが使用され、関連情報がメッセージヘッダーにスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="7b084-221">The first 1024 entries are used, and relevant information is stamped in the message headers.</span></span>
  
  <span data-ttu-id="7b084-222">Azure AD に同期されていない1024のエントリは、Outlook (web 上の Outlook ではない) によって処理され、メッセージヘッダーに情報はスタンプされません。</span><span class="sxs-lookup"><span data-stu-id="7b084-222">Entries over 1024 that weren't synchronized to Azure AD are processed by Outlook (not Outlook on the web), and no information is stamped in the message headers.</span></span>

<span data-ttu-id="7b084-223">ご覧のとおり、 **[連絡先からの電子メールを信頼**する] 設定を有効にすると、同期可能な差出人と安全な受信者の数が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="7b084-223">As you can see, enabling the **Trust email from my contacts** setting reduces the number of Safe Senders and Safe Recipients that can be synchronized.</span></span> <span data-ttu-id="7b084-224">このことが問題になる場合は、グループポリシーを使用してこの機能をオフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7b084-224">If this is a concern, then we recommend using Group Policy to turn this feature off:</span></span>

- <span data-ttu-id="7b084-225">ファイル名: outlk16 ax</span><span class="sxs-lookup"><span data-stu-id="7b084-225">File name: outlk16.opax</span></span>
- <span data-ttu-id="7b084-226">ポリシー設定:**連絡先からの電子メールを信頼**する</span><span class="sxs-lookup"><span data-stu-id="7b084-226">Policy setting: **Trust e-mail from contacts**</span></span>
