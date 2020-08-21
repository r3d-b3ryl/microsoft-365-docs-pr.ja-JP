---
title: Exchange Online のメールボックスで迷惑メール設定を構成する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online のメールボックスで迷惑メール設定を構成する方法を学習できます。 これらの設定の多くは、Outlook または Web 上の Outlook のユーザーが利用できます。
ms.openlocfilehash: 171eca8535958f01a7f749ad678e6ea9dd83d80c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825715"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a><span data-ttu-id="84d4b-104">Exchange Online のメールボックスで迷惑メール設定を構成する</span><span class="sxs-lookup"><span data-stu-id="84d4b-104">Configure junk email settings on Exchange Online mailboxes</span></span>

<span data-ttu-id="84d4b-105">Exchange Online にメールボックスを持つ Microsoft 365 組織では、組織のスパム対策設定が Exchange Online Protection (EOP) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-105">In Microsoft 365 organizations with mailboxes in Exchange Online, organizational anti-spam settings are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="84d4b-106">詳細については [、EOP のスパム対策保護を参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-106">For more information, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

<span data-ttu-id="84d4b-107">ただし、管理者が Exchange Online の個々のメールボックスに構成できる特定のスパム対策設定があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-107">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="84d4b-108">**迷惑メールのルールを有効または無効にする**: 迷惑メールのルールは、すべてのメールボックスで既定で有効になる「迷惑メール ルール」という名前の非表示の受信トレイ ルールです。</span><span class="sxs-lookup"><span data-stu-id="84d4b-108">**Enable or disable the junk email rule**: The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="84d4b-109">迷惑メールのルールでは、以下の機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-109">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="84d4b-110">**スパム対策ポリシーに基づいて、メッセージを [迷惑メール] フォルダーに移動します**。スパム対策ポリシーが、スパム対策フィルター確認用の [迷惑メール] フォルダーに **アクション** を設定して構成されている場合、迷惑メール フィルター ルールは、メッセージがメールボックスに配信された後に、そのメッセージを [迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-110">**Move messages to the Junk Email folder based on anti-spam policies**: When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="84d4b-111">スパム対策ポリシーのスパム対策フィルターの詳細については、「EOP でスパム [対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-111">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="84d4b-112">同様に、ゼロア自動消去 (ZAP) が、配信されたメッセージがスパムまたはフィッシングであると判断した場合、迷惑メール フィルター ルールは、そのメッセージを [移動メッセージの迷惑メール] フォルダーに移動し **、迷惑** メール フォルダー スパム対策フィルター判定アクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-112">Similarly, if zero-hour auto purge (ZAP) determines a delivered message is spam or phish, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="84d4b-113">ZAP の詳細については [、Exchange Online のゼロアハージ (ZAP) を参照してください](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-113">For more information about ZAP, see [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).</span></span>

  - <span data-ttu-id="84d4b-114">**ユーザーが Outlook または Web 上**の Outlook でユーザーに構成する迷惑メール設定: セーフリスト _コレクション_ は、信頼できる差出人のリスト、信頼できる宛先のリスト、および各メールボックスの差出人セーフ リストです。</span><span class="sxs-lookup"><span data-stu-id="84d4b-114">**Junk email settings that users configure for themselves in Outlook or Outlook on the web**: The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Block senders list on each mailbox.</span></span> <span data-ttu-id="84d4b-115">これらのリストのエントリによって、迷惑メール ルールがメッセージを [受信トレイ] フォルダーまたは [迷惑メール] フォルダーに移動するかどうかが決定されます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-115">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="84d4b-116">ユーザーは、Outlook または Web 上の Outlook (前の名前と呼ばられていました) に、ユーザーが独自のメールボックスのセーフリスト コレクションOutlook Web App。</span><span class="sxs-lookup"><span data-stu-id="84d4b-116">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="84d4b-117">管理者は、任意のユーザーのメールボックスのセーフリスト コレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-117">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="84d4b-118">メールボックスで迷惑メール ルールが有効になっている場合、EOP では、スパム フィルタリング確認の操作に基づいて、メッセージを [ **迷惑** メール] フォルダーまたはメールボックスの受信拒否リストに移動し、(メールボックスの差出人セーフ リストに基づいて) メッセージが [迷惑メール] フォルダーに配信されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-118">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="84d4b-119">メールボックスで迷惑メール ルールが無効になっている場合、EOP では、スパム フィルタリング確認のアクションに基づいて、メッセージを [ **迷惑** メール] フォルダーまたはメールボックスのセーフリスト コレクションに移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="84d4b-119">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="84d4b-120">管理者は、Exchange Online PowerShell を使用して、メールボックスでの迷惑メール ルールの無効化、有効化、状態の表示を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-120">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="84d4b-121">管理者は、Exchange Online PowerShell を使用して、メールボックスのセーフリスト コレクション ([信頼できる差出人のリスト]、[信頼できる宛先のリスト]、および [差出人を受信拒否] のリスト) にエントリを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-121">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Block senders list).</span></span>

> [!NOTE]
> <span data-ttu-id="84d4b-122">ユーザーが独自の信頼できる差出人のリストに追加した送信者からのメッセージは、EOP の一部として接続フィルター処理をスキップします (SCL が -1 です)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-122">Messages from senders that users have added to their own Safe Senders lists will skip connection filtering as part of EOP (the SCL is -1).</span></span> <span data-ttu-id="84d4b-123">Outlook の信頼できる差出人のリストにユーザーがエントリを追加できないようにするには、このトピックで後述する  [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」で説明するようにグループ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-123">To prevent users from adding entries to their Safe Senders list in Outlook, use Group Policy as mentioned in the  [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section later in this topic.</span></span> <span data-ttu-id="84d4b-124">ポリシー フィルター処理では、コンテンツ フィルターと Advanced Threat Protection (ATP) のチェックが引き続きメッセージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-124">Policy filtering, Content filtering and Advanced Threat Protection (ATP) checks will still be applied to the messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="84d4b-125">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="84d4b-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="84d4b-126">これらの手順を実行するには、Exchange Online PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-126">You can only use Exchange Online PowerShell to perform these procedures.</span></span> <span data-ttu-id="84d4b-127">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84d4b-127">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="84d4b-128">これらの手順を実行する場合は、ああたかじ必要なアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-128">You need to be assigned permissions before you can do these procedures.</span></span> <span data-ttu-id="84d4b-129">具体的には、 **メール** 受信者の役割 (既定で **組織**管理、 **受信者**管理、 **およびカスタム メール受信者** の役割グループに割り当てられる) またはユーザー オプション ( **既定** で **組織管理]、"Help** **Desk/ヘルプ デスク" 役割グループに割** り当てられる) が必要です。</span><span class="sxs-lookup"><span data-stu-id="84d4b-129">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management**, **Recipient Management**, and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="84d4b-130">Exchange Online で役割グループにユーザーを追加するには、「Exchange Online [で役割グループを変更する」を参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-130">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="84d4b-131">既定のアクセス許可を持つユーザーは、Exchange Online PowerShell にアクセスできる場合、同じ [手順を各自分のメールボックスに対して実行できます](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-131">Note that a user with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="84d4b-132">EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-132">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="84d4b-133">詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84d4b-133">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

- <span data-ttu-id="84d4b-134">共有メールボックスの差出人セーフ リストは、Azure および ADからは、設計により同期されません。</span><span class="sxs-lookup"><span data-stu-id="84d4b-134">Safe Senders for shared mailboxes are not synchronized to Azure AD and EOP by design.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="84d4b-135">Exchange Online PowerShell を使用して、メールボックスで迷惑メール ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="84d4b-135">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="84d4b-136">Outlook (Exchange キャッシュ モードで) または Web 上の Outlook で開かれているメールボックスで迷惑メール ルールを無効にするには、 **Set-MailboxJunkEmailConfiguration** コマンドレットのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-136">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="84d4b-137">メールボックスが開かれていない場合、次のエラーが表示されます。一括操作に対して `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` このエラーを表示しない場合は `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** することができます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-137">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

<span data-ttu-id="84d4b-138">メールボックスで迷惑メール ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-138">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="84d4b-139">次の例では、Ori Epstein のメールボックスで迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="84d4b-139">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="84d4b-140">次の例では、組織内のすべてのユーザーのメールボックスの迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="84d4b-140">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="84d4b-141">構文およびパラメーターの詳細については [、「Set-MailboxJunkEmailConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-141">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="84d4b-142">ユーザーがメールボックスをまだ開きなかった場合、前のコマンドを実行する際にエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-142">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="84d4b-143">一括操作でこのエラーを表示しないために `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-143">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="84d4b-144">迷惑メール ルールを無効にした場合でも、Outlook の迷惑メール フィルターは (構成方法に応じて) スパムであるかどうかを判断し、メッセージを独自のスパム判別や、メールボックスのセーフリスト コレクションに基づいて、[受信トレイ] フォルダーまたは [迷惑メール] フォルダーに移動できるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-144">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="84d4b-145">詳細については、このトピックの「[Outlook での迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84d4b-145">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="84d4b-146">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="84d4b-146">How do you know this worked?</span></span>

<span data-ttu-id="84d4b-147">メールボックスで迷惑メール ルールを正常に有効または無効にしたことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-147">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="84d4b-148">Enabled _\<MailboxIdentity\>_ プロパティの値を名前、エイリアス、または電子メール アドレスと置き換え、次の **コマンドを実行して Enabled プロパティの値を** 確認します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-148">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="84d4b-149">Exchange Online PowerShell を使用してメールボックスにセーフリスト コレクションを構成する</span><span class="sxs-lookup"><span data-stu-id="84d4b-149">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="84d4b-150">メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="84d4b-150">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="84d4b-151">ユーザーは、既定では Outlook または Web 上の Outlook のユーザー独自のメールボックスのセーフリスト コレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-151">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="84d4b-152">管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-152">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="84d4b-153">次の表に、これらのパラメーターの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-153">These parameters are described in the following table.</span></span>

****

|<span data-ttu-id="84d4b-154">Set-MailboxJunkEmailConfiguration のパラメーター</span><span class="sxs-lookup"><span data-stu-id="84d4b-154">Parameter on Set-MailboxJunkEmailConfiguration</span></span>|<span data-ttu-id="84d4b-155">Outlook on the web の設定</span><span class="sxs-lookup"><span data-stu-id="84d4b-155">Outlook on the web setting</span></span>|
|---|---|
|<span data-ttu-id="84d4b-156">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="84d4b-156">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="84d4b-157">**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**</span><span class="sxs-lookup"><span data-stu-id="84d4b-157">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="84d4b-158">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="84d4b-158">_ContactsTrusted_</span></span>|<span data-ttu-id="84d4b-159">**自分の連絡先からのメールを信頼する**</span><span class="sxs-lookup"><span data-stu-id="84d4b-159">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="84d4b-160">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="84d4b-160">_TrustedListsOnly_</span></span>|<span data-ttu-id="84d4b-161">**自分の信頼できる差出人とドメインのリストおよび信頼できるメールだけを信頼できるメールのリスト**</span><span class="sxs-lookup"><span data-stu-id="84d4b-161">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="84d4b-162">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="84d4b-162">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="84d4b-163">**次の送信者からのメールは [迷惑メール] フォルダーに移動しない**</span><span class="sxs-lookup"><span data-stu-id="84d4b-163">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="84d4b-164"><sup>\*</sup>**注**:</span><span class="sxs-lookup"><span data-stu-id="84d4b-164"><sup>\*</sup> **Notes**:</span></span>

- <span data-ttu-id="84d4b-165">Exchange Online では、 **信頼できる差出** 人のリストまたは _TrustedSendersAndDomains パラメーターのドメイン_ エントリが認識されないため、電子メール アドレスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-165">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="84d4b-166">ディレクトリ同期を行うスタンドアロン EOP では、ドメイン エントリは既定では同期されませんが、ドメインの同期を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-166">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="84d4b-167">詳細については [、KB3019657 を参照してください](https://support.microsoft.com/help/3019657)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-167">For more information, see [KB3019657](https://support.microsoft.com/help/3019657).</span></span>

- <span data-ttu-id="84d4b-168">**Set-MailboxJunkEmailConfiguration**コマンドレットを使用して、信頼できる宛先のリストを直接変更することはできません _(TrustedRecipientsAndDomains_パラメーターが機能しません)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-168">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="84d4b-169">信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-169">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="84d4b-170">メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-170">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="84d4b-171">複数の値を入力し _、BlockedSendersAndDomains、および TrustedSendersAndDomains_ パラメーターの既存の _エントリをすべて上書きするには_ 、次の構文を使用します `"<Value1>","<Value2>"...` 。</span><span class="sxs-lookup"><span data-stu-id="84d4b-171">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="84d4b-172">他の既存のエントリに影響を及ぼせずに、1 つまたは複数の値を追加または削除するには、次の構文を使用します。 `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="84d4b-172">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="84d4b-173">以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-173">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="84d4b-174">値のリストにshopping@fabrikam.comを追加する</span><span class="sxs-lookup"><span data-stu-id="84d4b-174">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="84d4b-175">信頼できる差出chris@fourthcoffee.com信頼できるリストと信頼できる宛先のリストから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-175">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="84d4b-176">信頼できる差出人として扱われるように [連絡先] フォルダー内の連絡先を構成する。</span><span class="sxs-lookup"><span data-stu-id="84d4b-176">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="84d4b-177">次の例では、組織内の全ユーザーのメールボックスの受信拒否リストから contoso.com ドメインを削除します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-177">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="84d4b-178">構文およびパラメーターの詳細については [、「Set-MailboxJunkEmailConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-178">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="84d4b-179">ユーザーがメールボックスをまだ開きなかった場合、前のコマンドを実行する際にエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-179">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="84d4b-180">一括操作でこのエラーを表示しないために `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-180">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="84d4b-181">メールボックスで迷惑メールのルールが無効になっている場合でも、セーフリスト コレクションを構成できます。Outlook の迷惑メール フィルターでメッセージを [受信トレイ] または [迷惑メール] フォルダーに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-181">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="84d4b-182">詳細については、このトピックの「[Outlook での迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84d4b-182">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this topic.</span></span>
>
> - <span data-ttu-id="84d4b-183">Outlook 迷惑メール フィルターには、追加のセーフリスト コレクションの設定があります (たとえば、 **差出人セーフリストにメールを自動的に追加します**)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-183">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list**).</span></span> <span data-ttu-id="84d4b-184">詳細については、「迷惑メール フィルター [を使用して、表示するメッセージを制御する」を参照してください](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-184">For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="84d4b-185">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="84d4b-185">How do you know this worked?</span></span>

<span data-ttu-id="84d4b-186">メールボックスにセーフリスト コレクションを正常に構成したことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-186">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="84d4b-187">メールボックス _\<MailboxIdentity\>_ の名前、エイリアス、または電子メール アドレスを使用して置き換え、次のコマンドを実行してプロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-187">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="84d4b-188">値のリストが長すぎる場合は、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-188">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="84d4b-189">Outlook での迷惑メール設定について</span><span class="sxs-lookup"><span data-stu-id="84d4b-189">About junk email settings in Outlook</span></span>

<span data-ttu-id="84d4b-190">Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-190">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="84d4b-191">詳細については [、「Microsoft 365 Apps for enterprise、Office 2019、Office 2016 用の管理用テンプレート ファイル (ADMX/ADML)」および「Office 2016 用の管理用テンプレート ファイル」および「Office 2016」](https://www.microsoft.com/download/details.aspx?id=49030) などの電子メール設定をグループ [ポリシーを使用して展開する方法を参照してください](https://support.microsoft.com/help/2252421)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-191">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) and [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy](https://support.microsoft.com/help/2252421).</span></span>

<span data-ttu-id="84d4b-192">Outlook の迷惑メール フィルターが既定値 [迷惑メールの迷惑メール**Home**オプション] に [**自動**フィルターなし] に設定されている場合、Outlook では大文字と迷惑メールを分類するのを試みず、引き続きセーフリスト コレクション (信頼できる差出人のリスト、信頼できる宛先のリスト、受信拒否リスト) を使用して、配信後にメッセージを \> **Junk** \> **Junk E-Mail Options** \> **Options**[迷惑メール] フォルダーに移動しています。</span><span class="sxs-lookup"><span data-stu-id="84d4b-192">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="84d4b-193">これらの設定の詳細については、「迷惑メール [フィルターの概要」を参照してください](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-193">For more information about these settings, see [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="84d4b-194">Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-194">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="84d4b-195">この迷惑メールの分類は、EOP で決定される Spam Confidence Level (SCL) とは別のものです。</span><span class="sxs-lookup"><span data-stu-id="84d4b-195">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="84d4b-196">Outlook は、EOP から SCL を無視し (EOP がスパム フィルターをスキップするメッセージを除外した場合を除きます)、その独自の条件を使用してメッセージがスパムかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-196">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="84d4b-197">もちろん、EOP からのスパム常に詳細なディクテートが同じである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-197">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="84d4b-198">これらの設定の詳細については、「迷惑メール [フィルターの保護レベルを変更する」を参照してください](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-198">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="84d4b-199">2016 年 11 月、Microsoft は Exchange と Outlook の SmartScreen フィルターのスパム定義の更新を停止しました。</span><span class="sxs-lookup"><span data-stu-id="84d4b-199">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="84d4b-200">既存の SmartScreen スパム定義はそのままでしたが、その効果は時間とや切り替わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-200">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="84d4b-201">詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="84d4b-201">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="84d4b-202">したがって、メールボックスで迷惑メール ルールが無効になっている場合でも、Outlook の迷惑メール フィルターでは、メールボックスのセーフリスト コレクションと独自の迷惑メールの分類を使用して、メッセージを [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-202">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="84d4b-203">Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-203">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="84d4b-204">セーフリスト コレクションは Exchange Online メールボックスに保存されるため、Outlook のセーフリスト コレクションに対する変更は Web 上の Outlook に表示され、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="84d4b-204">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

## <a name="limits-for-junk-email-settings"></a><span data-ttu-id="84d4b-205">迷惑メール設定の制限</span><span class="sxs-lookup"><span data-stu-id="84d4b-205">Limits for junk email settings</span></span>

<span data-ttu-id="84d4b-206">ユーザーのメールボックスに格納されているセーフリスト コレクション (信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リスト) も EOP と同期されます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-206">The safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) that's stored in the user's mailbox is also synchronized to EOP.</span></span> <span data-ttu-id="84d4b-207">ディレクトリ同期を使用すると、セーフリスト コレクションは Azure ユーザーの Azure AD。</span><span class="sxs-lookup"><span data-stu-id="84d4b-207">With directory synchronization, the safelist collection is synchronized to Azure AD.</span></span>

- <span data-ttu-id="84d4b-208">ユーザーのメールボックス内のセーフリスト コレクションのサイズは 510 KB に制限されます。すべてのリストと、他の迷惑メール フィルター設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-208">The safelist collection in the user's mailbox has a limit of 510 KB, which includes all lists, plus additional junk email filter settings.</span></span> <span data-ttu-id="84d4b-209">ユーザーがこの制限を超えると、次のような Outlook エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-209">If a user exceeds this limit, they will receive an Outlook error that looks like this:</span></span>

  > <span data-ttu-id="84d4b-210">サーバーの迷惑メール リストに追加/アクセスできません。</span><span class="sxs-lookup"><span data-stu-id="84d4b-210">Cannot/Unable add to the server Junk E-mail lists.</span></span> <span data-ttu-id="84d4b-211">サーバーで許可されているサイズを超えています。</span><span class="sxs-lookup"><span data-stu-id="84d4b-211">You are over the size allowed on the server.</span></span> <span data-ttu-id="84d4b-212">サーバー上の迷惑メール フィルターは、迷惑メール リストがサーバーで許容されるサイズまで減らされるまで無効になります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-212">The Junk E-mail filter on the server will be disabled until your Junk E-mail lists have been reduced to the size allowed by the server.</span></span>

  <span data-ttu-id="84d4b-213">この制限と変更方法の詳細については [、KB2669081 を参照してください](https://support.microsoft.com/help/2669081)。</span><span class="sxs-lookup"><span data-stu-id="84d4b-213">For more information about this limit and how to change it, see [KB2669081](https://support.microsoft.com/help/2669081).</span></span>

- <span data-ttu-id="84d4b-214">EOP の同期済みセーフリスト コレクションの同期に次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="84d4b-214">The synchronized safelist collection in EOP has the following synchronization limits:</span></span>

  - <span data-ttu-id="84d4b-215">信頼できる差出人のリスト、信頼できる宛先のリスト、および連絡先からのメールを信頼できる場合は、1024 エントリが合計で、信頼 **できる差出人のリスト、および外部連絡先** のエントリが合計で 1024 個。</span><span class="sxs-lookup"><span data-stu-id="84d4b-215">1024 total entries in the Safe Senders list, the Safe Recipients list, and external contacts if **Trust email from my contacts** is enabled.</span></span>
  - <span data-ttu-id="84d4b-216">受信拒否リストおよび受信拒否ドメイン リストに登録されたエントリの合計 500</span><span class="sxs-lookup"><span data-stu-id="84d4b-216">500 total entries in the Blocked Senders list and Blocked Domains list.</span></span>

  <span data-ttu-id="84d4b-217">1024 エントリの制限数に達すると、次のことが行われます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-217">When the 1024 entry limit is reached, the following things happen:</span></span>

  - <span data-ttu-id="84d4b-218">リストは PowerShell および Web 上の Outlook のエントリの受け入れを停止しますが、エラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="84d4b-218">The list stops accepting entries in PowerShell and Outlook on the web, but no error is displayed.</span></span>

    <span data-ttu-id="84d4b-219">Outlook ユーザーは、Outlook の制限である 510 KB に達するまで、引き続き 1024 を超えるエントリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-219">Outlook users can continue to add more than 1024 entries until they reach the Outlook limit of 510 KB.</span></span> <span data-ttu-id="84d4b-220">これらの追加エントリを使用できます (メール フロー ルール、スプーフィング対策など) をメールボックスに配信する前に EOP フィルターでメッセージをブロックしない場合に。</span><span class="sxs-lookup"><span data-stu-id="84d4b-220">Outlook can use these additional entries, as long as an EOP filter doesn't block the message before delivery to the mailbox (mail flow rules, anti-spoofing, etc.).</span></span>

- <span data-ttu-id="84d4b-221">ディレクトリ同期では、エントリが Azure サーバーに対して次AD同期されます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-221">With directory synchronization, the entries are synchronized to Azure AD in the following order:</span></span>

  1. <span data-ttu-id="84d4b-222">[連絡先からのメール **を信頼する] が有効になっている場合の** メール連絡先。</span><span class="sxs-lookup"><span data-stu-id="84d4b-222">Mail contacts if **Trust email from my contacts** is enabled.</span></span>
  2. <span data-ttu-id="84d4b-223">最初の 1024 エントリに対して変更が行われた場合は常に、差出人セーフ リストと信頼できる差出人のリストは、アルフォベット順に並べ替え、区切り順かれて表示されます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-223">The Safe Sender list and Safe Recipient list are combined, de-duplicated, and sorted alphabetically whenever a change is made for the first 1024 entries.</span></span>

  <span data-ttu-id="84d4b-224">最初の 1024 エントリが使用され、関連情報はメッセージ ヘッダーにスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="84d4b-224">The first 1024 entries are used, and relevant information is stamped in the message headers.</span></span>

  <span data-ttu-id="84d4b-225">同期されていない 1024 を超えるエントリ ADは Outlook on the web によって処理され (Outlook on the web には同期されません)、メッセージ ヘッダー内に情報はスタンプされません。</span><span class="sxs-lookup"><span data-stu-id="84d4b-225">Entries over 1024 that weren't synchronized to Azure AD are processed by Outlook (not Outlook on the web), and no information is stamped in the message headers.</span></span>

<span data-ttu-id="84d4b-226">お書きのとおり、連絡先から **メールを信頼** する設定で、同期できる信頼できる差出人と信頼できる宛先の数が減少します。</span><span class="sxs-lookup"><span data-stu-id="84d4b-226">As you can see, enabling the **Trust email from my contacts** setting reduces the number of Safe Senders and Safe Recipients that can be synchronized.</span></span> <span data-ttu-id="84d4b-227">これに問題が発生した場合は、グループ ポリシーを使用してこの機能を無効にしてください。</span><span class="sxs-lookup"><span data-stu-id="84d4b-227">If this is a concern, then we recommend using Group Policy to turn this feature off:</span></span>

- <span data-ttu-id="84d4b-228">ファイル名: outlk16.opax</span><span class="sxs-lookup"><span data-stu-id="84d4b-228">File name: outlk16.opax</span></span>
- <span data-ttu-id="84d4b-229">ポリシー設定: **連絡先からの電子メールを信頼する**</span><span class="sxs-lookup"><span data-stu-id="84d4b-229">Policy setting: **Trust e-mail from contacts**</span></span>
