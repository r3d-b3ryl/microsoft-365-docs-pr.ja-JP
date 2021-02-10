---
title: Exchange Online メールボックスで迷惑メール設定を構成する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスで迷惑メール設定を構成する方法について説明します。 これらの設定の多くは、Outlook または Outlook on the web のユーザーが使用できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2aa75376a431ded5abf44ad17ddad4f0ac731fa8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165693"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a><span data-ttu-id="c644b-104">Exchange Online メールボックスで迷惑メール設定を構成する</span><span class="sxs-lookup"><span data-stu-id="c644b-104">Configure junk email settings on Exchange Online mailboxes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c644b-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c644b-105">**Applies to**</span></span>
- [<span data-ttu-id="c644b-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c644b-106">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="c644b-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c644b-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="c644b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c644b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c644b-109">Exchange Online にメールボックスがある Microsoft 365 組織では、組織のスパム対策設定は Exchange Online Protection (EOP) によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="c644b-109">In Microsoft 365 organizations with mailboxes in Exchange Online, organizational anti-spam settings are controlled by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="c644b-110">詳細については [、「EOP でのスパム対策保護」を参照してください](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="c644b-110">For more information, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

<span data-ttu-id="c644b-111">ただし、管理者が Exchange Online の個々のメールボックスに対して構成できる特定のスパム対策設定も用意されています。</span><span class="sxs-lookup"><span data-stu-id="c644b-111">But, there are also specific anti-spam settings that admins can configure on individual mailboxes in Exchange Online:</span></span>

- <span data-ttu-id="c644b-112">**迷惑メール ルールを** 有効または無効にする : 迷惑メール ルールは、すべてのメールボックスで既定で有効になっている迷惑メール ルールという名前の非表示の受信トレイ ルールです。</span><span class="sxs-lookup"><span data-stu-id="c644b-112">**Enable or disable the junk email rule**: The junk email rule is a hidden Inbox rule named Junk E-mail Rule that's enabled by default in every mailbox.</span></span> <span data-ttu-id="c644b-113">迷惑メール ルールは、次の機能を制御します。</span><span class="sxs-lookup"><span data-stu-id="c644b-113">The junk email rule controls the following features:</span></span>

  - <span data-ttu-id="c644b-114">スパム対策ポリシーに基づいてメッセージを [迷惑メール] フォルダーに移動 **する:** スパム対策ポリシーがスパムフィルターの条件として [迷惑メール] フォルダーに移動するアクションを使用して構成されている場合、迷惑メール フィルター ルールは、メッセージがメールボックスに配信された後、そのメッセージを [迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c644b-114">**Move messages to the Junk Email folder based on anti-spam policies**: When an anti-spam policy is configured with the action **Move message to Junk Email folder** for a spam filtering verdict, the junk email filter rule moves the message to the Junk Email folder after the message is delivered to the mailbox.</span></span> <span data-ttu-id="c644b-115">スパム対策ポリシーでのスパム フィルターの条件の詳細については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c644b-115">For more information about spam filtering verdicts in anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="c644b-116">同様に、ゼロアワー自動消去 (ZAP) によって配信されたメッセージがスパムまたはフィッシングと判断された場合、迷惑メール フィルター ルールは、メッセージを [迷惑メール] フォルダーのスパム フィルターの判断アクションに移動するために [迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c644b-116">Similarly, if zero-hour auto purge (ZAP) determines a delivered message is spam or phish, the junk email filter rule moves the message to the Junk Email folder for **Move message to Junk Email folder** spam filtering verdict actions.</span></span> <span data-ttu-id="c644b-117">ZAP の詳細については、Exchange Online のゼロアワー自動消去 [(ZAP) を参照してください](zero-hour-auto-purge.md)。</span><span class="sxs-lookup"><span data-stu-id="c644b-117">For more information about ZAP, see [Zero-hour auto purge (ZAP) in Exchange Online](zero-hour-auto-purge.md).</span></span>

  - <span data-ttu-id="c644b-118">**ユーザー** が Outlook または Outlook on the web で自分自身のために構成する迷惑メール設定: セーフリスト コレクションは、各メールボックスの差出人セーフ リスト、宛先セーフ リスト、および受信拒否リストです。</span><span class="sxs-lookup"><span data-stu-id="c644b-118">**Junk email settings that users configure for themselves in Outlook or Outlook on the web**: The _safelist collection_ is the Safe Senders list, the Safe Recipients list, and the Blocked Senders list on each mailbox.</span></span> <span data-ttu-id="c644b-119">これらの一覧のエントリは、迷惑メール ルールがメッセージを受信トレイまたは迷惑メール フォルダーに移動するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="c644b-119">The entries in these lists determine whether the junk email rule moves the message to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="c644b-120">ユーザーは、Outlook または Outlook on the web (旧称: outlook on the web) で、自分のメールボックスのセーフリスト コレクションをOutlook Web App。</span><span class="sxs-lookup"><span data-stu-id="c644b-120">Users can configure the safelist collection for their own mailbox in Outlook or Outlook on the web (formerly known as Outlook Web App).</span></span> <span data-ttu-id="c644b-121">管理者は、任意のユーザーのメールボックスにセーフリスト コレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-121">Admins can configure the safelist collection on any user's mailbox.</span></span>

<span data-ttu-id="c644b-122">メールボックスで迷惑メール ルールが有効になっている場合、EOP はスパム フィルターの条件アクションに基づいてメッセージを [迷惑メール] フォルダーに移動するか、メールボックスの受信拒否リストにメッセージを移動し、(メールボックスの差出人セーフ リストに基づいて) 迷惑メール フォルダーにメッセージが配信されるのを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="c644b-122">When the junk email rule is enabled on the mailbox, EOP is able to move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the Blocked Senders list on the mailbox, and prevent messages from being delivered to the Junk Email folder (based on the Safe Senders list on the mailbox).</span></span>

 <span data-ttu-id="c644b-123">メールボックスで迷惑メール ルールが無効になっている場合、EOP はスパム フィルターの確認アクションに基づいてメッセージを [迷惑メール] フォルダーに移動できません。メッセージを [迷惑メール] フォルダーまたはメールボックスのセーフリスト コレクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="c644b-123">When the junk email rule is disabled on the mailbox, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="c644b-124">管理者は、Exchange Online PowerShell を使用して、メールボックスの迷惑メール ルールの無効化、有効化、および状態の表示を行えます。</span><span class="sxs-lookup"><span data-stu-id="c644b-124">Admins can use Exchange Online PowerShell to disable, enable, and view the status of the junk email rule on mailboxes.</span></span> <span data-ttu-id="c644b-125">管理者は、Exchange Online PowerShell を使用して、メールボックスのセーフリスト コレクション (差出人セーフ リスト、宛先セーフ リスト、受信拒否リスト) のエントリを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-125">Admins can also use Exchange Online PowerShell to configure entries in the safelist collection on mailboxes (the Safe Senders list, the Safe Recipients list, and the Blocked Senders list).</span></span>

> [!NOTE]
> <span data-ttu-id="c644b-126">ユーザーが自分の差出人セーフ リストに追加した送信者からのメッセージは、EOP の一部として接続フィルターをスキップします (SCL は -1)。</span><span class="sxs-lookup"><span data-stu-id="c644b-126">Messages from senders that users have added to their own Safe Senders lists will skip connection filtering as part of EOP (the SCL is -1).</span></span> <span data-ttu-id="c644b-127">ユーザーが Outlook の差出人セーフ リストにエントリを追加するのを防ぐには、この記事の後半の  [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」に記載されているグループ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c644b-127">To prevent users from adding entries to their Safe Senders list in Outlook, use Group Policy as mentioned in the  [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section later in this article.</span></span> <span data-ttu-id="c644b-128">ポリシー フィルター、コンテンツ フィルター、および 365 Officeの Defender は、引き続きメッセージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="c644b-128">Policy filtering, Content filtering and Defender for Office 365 checks will still be applied to the messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c644b-129">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="c644b-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c644b-130">この記事の手順を実行するには、Exchange Online PowerShell のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-130">You can only use Exchange Online PowerShell to do the procedures in this article.</span></span> <span data-ttu-id="c644b-131">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c644b-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c644b-132">この記事の手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c644b-132">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="c644b-133">具体的には、"Mail **Recipients/** メール受信者" 役割 (既定では "Organization **Management/** 組織の管理"、"Recipient **Management/** 受信者の管理"、および **"Custom Mail Recipients/** カスタム メール受信者" 役割グループに割り当てられる) または **"User Options/** ユーザー オプション" 役割 (既定では **"Organization Management/** 組織の管理" 役割グループと **"Help Desk/** ヘルプ デスク" 役割グループに割り当てられている) が必要です。</span><span class="sxs-lookup"><span data-stu-id="c644b-133">Specifically, you need the **Mail Recipients** role (which is assigned to the **Organization Management**, **Recipient Management**, and **Custom Mail Recipients** role groups by default) or the **User Options** role (which is assigned to the **Organization Management** and **Help Desk** role groups by default).</span></span> <span data-ttu-id="c644b-134">Exchange Online の役割グループにユーザーを追加するには、「Exchange Online で役割グループを変更 [する」を参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。</span><span class="sxs-lookup"><span data-stu-id="c644b-134">To add users to role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span> <span data-ttu-id="c644b-135">既定のアクセス許可を持つユーザーは、Exchange Online PowerShell にアクセスできる限り、自分のメールボックスで同じ [手順を実行できます](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="c644b-135">Note that users with default permissions can do these same procedures on their own mailbox, as long as they have [access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c644b-136">EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c644b-136">In standalone EOP environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="c644b-137">詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c644b-137">For details, see [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>

- <span data-ttu-id="c644b-138">共有メールボックスの差出人セーフ リストは、設計上 Azure AD EOP に同期されません。</span><span class="sxs-lookup"><span data-stu-id="c644b-138">Safe Senders for shared mailboxes are not synchronized to Azure AD and EOP by design.</span></span>

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a><span data-ttu-id="c644b-139">Exchange Online PowerShell を使用してメールボックスの迷惑メール ルールを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="c644b-139">Use Exchange Online PowerShell to enable or disable the junk email rule in a mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="c644b-140">Outlook (Exchange キャッシュ モードで) または Web 上の Outlook で開かれているメールボックスで迷惑メール ルールを無効にするには、 **Set-MailboxJunkEmailConfiguration** コマンドレットのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-140">You can only use the **Set-MailboxJunkEmailConfiguration** cmdlet to disable the junk email rule on a mailbox that's been opened in Outlook (in Cached Exchange mode) or Outlook on the web.</span></span> <span data-ttu-id="c644b-141">メールボックスが開いていない場合は、次のエラーが表示されます。一括操作でこのエラーを抑制する場合は `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration** コマンドに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-141">If the mailbox hasn't been opened, you'll receive the error: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` If you want to suppress this error for bulk operations, you can add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>

<span data-ttu-id="c644b-142">メールボックスで迷惑メール ルールを有効または無効にするには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c644b-142">To enable or disable the junk email rule on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

<span data-ttu-id="c644b-143">次の例では、Ori Epstein のメールボックスで迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c644b-143">This example disables the junk email rule on Ori Epstein's mailbox.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

<span data-ttu-id="c644b-144">次の例では、組織内のすべてのユーザーのメールボックスの迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c644b-144">This example disables the junk email rule on all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

<span data-ttu-id="c644b-145">構文およびパラメーターの詳細については [、「Set-MailboxJunkEmailConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="c644b-145">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c644b-146">ユーザーがメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c644b-146">If the user has never opened their mailbox, you might receive an error when you run the previous command.</span></span> <span data-ttu-id="c644b-147">一括操作でこのエラーを抑制するには `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。</span><span class="sxs-lookup"><span data-stu-id="c644b-147">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="c644b-148">迷惑メール ルールを無効にした場合でも、Outlook 迷惑メール フィルター (構成方法に応じて) は、メッセージがスパムであるかどうかを判断し、メッセージ自身のスパムの判断とメールボックスのセーフリスト コレクションに基づいて、メッセージを [受信トレイ] フォルダーまたは [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-148">Even if you disable the junk email rule, the Outlook Junk Email Filter (depending on how it's configured) can also determine whether a message is spam, and can move messages to the Inbox or Junk Email folder based on it's own spam verdict and the the safelist collection on the mailbox.</span></span> <span data-ttu-id="c644b-149">詳細については、この記事の [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c644b-149">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this article.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c644b-150">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="c644b-150">How do you know this worked?</span></span>

<span data-ttu-id="c644b-151">メールボックスで迷惑メール ルールを正常に有効または無効にしたことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c644b-151">To verify that you have successfully enabled or disabled the junk email rule on a mailbox, use any of the following procedures:</span></span>

- <span data-ttu-id="c644b-152">メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行して Enabled プロパティの値 _\<MailboxIdentity\>_ **を** 確認します。</span><span class="sxs-lookup"><span data-stu-id="c644b-152">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the **Enabled** property value:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a><span data-ttu-id="c644b-153">Exchange Online PowerShell を使用してメールボックスのセーフリスト コレクションを構成する</span><span class="sxs-lookup"><span data-stu-id="c644b-153">Use Exchange Online PowerShell to configure the safelist collection on a mailbox</span></span>

<span data-ttu-id="c644b-154">メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c644b-154">The safelist collection on a mailbox includes the Safe Senders list, the Safe Recipients list, and the Blocked Senders list.</span></span> <span data-ttu-id="c644b-155">既定では、ユーザーは Outlook または Outlook on the web の自分のメールボックスでセーフリスト コレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-155">By default, users can configure the safelist collection on their own mailbox in Outlook or Outlook on the web.</span></span> <span data-ttu-id="c644b-156">管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-156">Administrators can use the corresponding parameters on the **Set-MailboxJunkEmailConfiguration** cmdlet to configure the safelist collection on a user's mailbox.</span></span> <span data-ttu-id="c644b-157">次の表に、これらのパラメーターの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="c644b-157">These parameters are described in the following table.</span></span>

****

|<span data-ttu-id="c644b-158">パラメーターのSet-MailboxJunkEmailConfiguration</span><span class="sxs-lookup"><span data-stu-id="c644b-158">Parameter on Set-MailboxJunkEmailConfiguration</span></span>|<span data-ttu-id="c644b-159">Outlook on the web の設定</span><span class="sxs-lookup"><span data-stu-id="c644b-159">Outlook on the web setting</span></span>|
|---|---|
|<span data-ttu-id="c644b-160">_BlockedSendersAndDomains_</span><span class="sxs-lookup"><span data-stu-id="c644b-160">_BlockedSendersAndDomains_</span></span>|<span data-ttu-id="c644b-161">**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**</span><span class="sxs-lookup"><span data-stu-id="c644b-161">**Move email from these senders or domains to my Junk Email folder**</span></span>|
|<span data-ttu-id="c644b-162">_ContactsTrusted_</span><span class="sxs-lookup"><span data-stu-id="c644b-162">_ContactsTrusted_</span></span>|<span data-ttu-id="c644b-163">**自分の連絡先からのメールを信頼する**</span><span class="sxs-lookup"><span data-stu-id="c644b-163">**Trust email from my contacts**</span></span>|
|<span data-ttu-id="c644b-164">_TrustedListsOnly_</span><span class="sxs-lookup"><span data-stu-id="c644b-164">_TrustedListsOnly_</span></span>|<span data-ttu-id="c644b-165">**信頼できる差出人とドメインのリストと安全なメール リストのアドレスからのメールのみを信頼する**</span><span class="sxs-lookup"><span data-stu-id="c644b-165">**Only trust email from addresses in my Safe senders and domains list and Safe mailing lists**</span></span>|
|<span data-ttu-id="c644b-166">_TrustedSendersAndDomains_<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c644b-166">_TrustedSendersAndDomains_<sup>\*</sup></span></span>|<span data-ttu-id="c644b-167">**これらの送信者から [迷惑メール] フォルダーにメールを移動しない**</span><span class="sxs-lookup"><span data-stu-id="c644b-167">**Don't move email from these senders to my Junk Email folder**</span></span>|
|

<span data-ttu-id="c644b-168"><sup>\*</sup>**メモ**:</span><span class="sxs-lookup"><span data-stu-id="c644b-168"><sup>\*</sup> **Notes**:</span></span>

- <span data-ttu-id="c644b-169">Exchange Online **では、信頼** できる差出人のリストまたは _TrustedSendersAndDomains_ パラメーターのドメイン エントリは認識されないので、電子メール アドレスのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="c644b-169">In Exchange Online, **domain entries** in the Safe Senders list or _TrustedSendersAndDomains_ parameter aren't recognized, so only use email addresses.</span></span> <span data-ttu-id="c644b-170">ディレクトリ同期を使用するスタンドアロン EOP では、ドメイン エントリは既定では同期されませんが、ドメインの同期を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c644b-170">In standalone EOP with directory synchronization, domain entries aren't synchronized by default, but you can enable synchronization for domains.</span></span> <span data-ttu-id="c644b-171">詳細については [、KB3019657 を参照](https://support.microsoft.com/help/3019657)してください。</span><span class="sxs-lookup"><span data-stu-id="c644b-171">For more information, see [KB3019657](https://support.microsoft.com/help/3019657).</span></span>

- <span data-ttu-id="c644b-172">**Set-MailboxJunkEmailConfiguration** コマンドレットを使用して宛先セーフ リストを直接変更することはできません _(TrustedRecipientsAndDomains_ パラメーターは機能しません)。</span><span class="sxs-lookup"><span data-stu-id="c644b-172">You can't directly modify the Safe Recipients list by using the **Set-MailboxJunkEmailConfiguration** cmdlet (the _TrustedRecipientsAndDomains_ parameter doesn't work).</span></span> <span data-ttu-id="c644b-173">信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。</span><span class="sxs-lookup"><span data-stu-id="c644b-173">You modify the Safe Senders list, and those changes are synchronized to the Safe Recipients list.</span></span>

<span data-ttu-id="c644b-174">メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c644b-174">To configure the safelist collection on a mailbox, use the following syntax:</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

<span data-ttu-id="c644b-175">複数の値を入力し _、BlockedSendersAndDomains_ および _TrustedSendersAndDomains_ パラメーターの既存のエントリを上書きするには、次の構文を使用します `"<Value1>","<Value2>"...` 。</span><span class="sxs-lookup"><span data-stu-id="c644b-175">To enter multiple values and overwrite any existing entries for the _BlockedSendersAndDomains_ and _TrustedSendersAndDomains_ parameters, use the following syntax: `"<Value1>","<Value2>"...`.</span></span> <span data-ttu-id="c644b-176">他の既存のエントリに影響を及ぼさずに 1 つ以上の値を追加または削除するには、次の構文を使用します。 `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span><span class="sxs-lookup"><span data-stu-id="c644b-176">To add or remove one or more values without affecting other existing entries, use the following syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`</span></span>

<span data-ttu-id="c644b-177">以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c644b-177">This example configures the following settings for the safelist collection on Ori Epstein's mailbox:</span></span>

- <span data-ttu-id="c644b-178">受信拒否リストshopping@fabrikam.com値を追加します。</span><span class="sxs-lookup"><span data-stu-id="c644b-178">Add the value shopping@fabrikam.com to the Blocked Senders list.</span></span>

- <span data-ttu-id="c644b-179">差出人セーフ リストchris@fourthcoffee.com宛先セーフ リストから値を削除します。</span><span class="sxs-lookup"><span data-stu-id="c644b-179">Remove the value chris@fourthcoffee.com from the Safe Senders list and the Safe Recipients list.</span></span>

- <span data-ttu-id="c644b-180">信頼できる差出人として扱われるように [連絡先] フォルダー内の連絡先を構成する。</span><span class="sxs-lookup"><span data-stu-id="c644b-180">Configures contacts in the Contacts folder to be treated as trusted senders.</span></span>

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

<span data-ttu-id="c644b-181">次の例では、組織内の全ユーザーのメールボックスの受信拒否リストから contoso.com ドメインを削除します。</span><span class="sxs-lookup"><span data-stu-id="c644b-181">This example removes the domain contoso.com from the Blocked Senders list in all user mailboxes in the organization.</span></span>

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

<span data-ttu-id="c644b-182">構文およびパラメーターの詳細については [、「Set-MailboxJunkEmailConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="c644b-182">For detailed syntax and parameter information, see [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c644b-183">ユーザーがメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c644b-183">If the user has never opened their mailbox, you might receive an error when you run the previous commands.</span></span> <span data-ttu-id="c644b-184">一括操作でこのエラーを抑制するには `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。</span><span class="sxs-lookup"><span data-stu-id="c644b-184">To suppress this error for bulk operations, add `-ErrorAction SilentlyContinue` to the **Set-MailboxJunkEmailConfiguration** command.</span></span>
>
> - <span data-ttu-id="c644b-185">メールボックスで迷惑メール ルールが無効になっている場合でも、セーフリスト コレクションを構成できます。Outlook 迷惑メール フィルターは、受信トレイまたは迷惑メール フォルダーにメッセージを移動できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-185">Even if the junk email rule is disabled on the mailbox, you can still configure the safelist collection, and the Outlook Junk Email Filter is able to move messages to the Inbox or the Junk Email folder.</span></span> <span data-ttu-id="c644b-186">詳細については、この記事の [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c644b-186">For more information, see the [About junk email settings in Outlook](#about-junk-email-settings-in-outlook) section in this article.</span></span>
>
> - <span data-ttu-id="c644b-187">Outlook 迷惑メール フィルターには、追加のセーフリスト コレクション設定があります (たとえば、メールを受信したユーザーを [差出人セーフ リスト **に自動的に追加する] など**)。</span><span class="sxs-lookup"><span data-stu-id="c644b-187">The Outlook Junk Email Filter has additional safelist collection settings (for example, **Automatically add people I email to the Safe Senders list**).</span></span> <span data-ttu-id="c644b-188">詳細については、「迷惑メール フィルター [を使用して表示されるメッセージを制御する」を参照してください](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)。</span><span class="sxs-lookup"><span data-stu-id="c644b-188">For more information, see [Use Junk Email Filters to control which messages you see](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c644b-189">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="c644b-189">How do you know this worked?</span></span>

<span data-ttu-id="c644b-190">メールボックスにセーフリスト コレクションを正常に構成したことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c644b-190">To verify that you have successfully configured the safelist collection on a mailbox, use any of following procedures:</span></span>

- <span data-ttu-id="c644b-191">メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行してプロパティ _\<MailboxIdentity\>_ の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="c644b-191">Replace _\<MailboxIdentity\>_ with the name, alias, or email address of the mailbox, and run the following command to verify the property values:</span></span>

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  <span data-ttu-id="c644b-192">値の一覧が長すぎる場合は、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c644b-192">If the list of values is too long, use this syntax:</span></span>

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a><span data-ttu-id="c644b-193">Outlook での迷惑メール設定について</span><span class="sxs-lookup"><span data-stu-id="c644b-193">About junk email settings in Outlook</span></span>

<span data-ttu-id="c644b-194">Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c644b-194">To enable, disable, and configure the client-side Junk Email Filter settings that are available in Outlook, use Group Policy.</span></span> <span data-ttu-id="c644b-195">詳細については[、「Microsoft 365 Apps for enterprise、Office 2019、Office 2016](https://www.microsoft.com/download/details.aspx?id=49030)用の管理用テンプレート ファイル (ADMX/ADML) および Office[](https://support.microsoft.com/help/2252421)カスタマイズ ツール」および「グループ ポリシーを使用して差出人セーフ リストなどの迷惑メール設定を展開する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c644b-195">For more information, see [Administrative Template files (ADMX/ADML) and Office Customization Tool for Microsoft 365 Apps for enterprise, Office 2019, and Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) and [How to deploy junk email settings, such as the Safe Senders list, by using Group Policy](https://support.microsoft.com/help/2252421).</span></span>

<span data-ttu-id="c644b-196">Outlook 迷惑メール フィルターが既定値に設定されている場合、[自宅の迷惑メール電子メール オプション] オプションで自動フィルターを実行しない場合 \>  \>  \> 、Outlook はスパムとして分類しようとはしませんが、配信後にセーフリスト コレクション (差出人セーフ リスト、宛先セーフ リスト、受信拒否リスト) を使用してメッセージを迷惑メール フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c644b-196">When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options** \> **Options**, Outlook doesn't attempt to classify massages as spam, but still uses the safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery.</span></span> <span data-ttu-id="c644b-197">これらの設定の詳細については、「迷惑メール フィルターの概要 [」を参照してください](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。</span><span class="sxs-lookup"><span data-stu-id="c644b-197">For more information about these settings, see [Overview of the Junk Email Filter](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

<span data-ttu-id="c644b-198">Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="c644b-198">When the Outlook Junk Email Filter is set to **Low** or **High**, the Outlook Junk Email Filter uses its own SmartScreen filter technology to identify and move spam to the Junk Email folder.</span></span> <span data-ttu-id="c644b-199">このスパム分類は、EOP によって決定される SCL (Spam Confidence Level) とは別の分類です。</span><span class="sxs-lookup"><span data-stu-id="c644b-199">This spam classification is separate from the spam confidence level (SCL) that's determined by EOP.</span></span> <span data-ttu-id="c644b-200">実際、Outlook は EOP からの SCL を無視し (EOP がスパム フィルタリングをスキップするようにメッセージをマークしない限り)、独自の条件を使用してメッセージがスパムであるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c644b-200">In fact, Outlook ignores the SCL from EOP (unless EOP marked the message to skip spam filtering) and uses its own criteria to determine whether the message is spam.</span></span> <span data-ttu-id="c644b-201">もちろん、EOP と Outlook からのスパムの検出は同じ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c644b-201">Of course, it's possible that the spam verdict from EOP and Outlook might be the same.</span></span> <span data-ttu-id="c644b-202">これらの設定の詳細については、「迷惑メール フィルター」の「保護レベルを変更 [する」を参照してください](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。</span><span class="sxs-lookup"><span data-stu-id="c644b-202">For more information about these settings, see [Change the level of protection in the Junk Email Filter](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).</span></span>

> [!NOTE]
> <span data-ttu-id="c644b-203">2016 年 11 月に、Microsoft は Exchange と Outlook の SmartScreen フィルターのスパム定義の更新の生成を停止しました。</span><span class="sxs-lookup"><span data-stu-id="c644b-203">In November 2016, Microsoft stopped producing spam definition updates for the SmartScreen filters in Exchange and Outlook.</span></span> <span data-ttu-id="c644b-204">既存の SmartScreen スパム定義は残っていますが、その有効性は時間の流れる中で低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c644b-204">The existing SmartScreen spam definitions were left in place, but their effectiveness will likely degrade over time.</span></span> <span data-ttu-id="c644b-205">詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c644b-205">For more information, see [Deprecating support for SmartScreen in Outlook and Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).</span></span>

<span data-ttu-id="c644b-206">そのため、Outlook 迷惑メール フィルターは、メールボックスのセーフリスト コレクションと独自のスパム分類を使用して、迷惑メール ルールがメールボックスで無効になっている場合でも、メッセージを [迷惑メール] フォルダーに移動できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-206">So, the Outlook Junk Email Filter is able to use the mailbox's safelist collection and its own spam classification to move messages to the Junk Email folder, even if the junk email rule is disabled in the mailbox.</span></span>

<span data-ttu-id="c644b-207">Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c644b-207">Outlook and Outlook on the web both support the safelist collection.</span></span> <span data-ttu-id="c644b-208">セーフリスト コレクションは Exchange Online メールボックスに保存されます。そのため、Outlook のセーフリスト コレクションに対する変更は Outlook on the web に表示され、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="c644b-208">The safelist collection is saved in the Exchange Online mailbox, so changes to the safelist collection in Outlook appear in Outlook on the web, and vice-versa.</span></span>

## <a name="limits-for-junk-email-settings"></a><span data-ttu-id="c644b-209">迷惑メール設定の制限</span><span class="sxs-lookup"><span data-stu-id="c644b-209">Limits for junk email settings</span></span>

<span data-ttu-id="c644b-210">ユーザーのメールボックスに格納されているセーフリスト コレクション (差出人セーフ リスト、宛先セーフ リスト、受信拒否リスト) も EOP と同期されます。</span><span class="sxs-lookup"><span data-stu-id="c644b-210">The safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) that's stored in the user's mailbox is also synchronized to EOP.</span></span> <span data-ttu-id="c644b-211">ディレクトリ同期を使用すると、セーフリスト コレクションは Azure AD。</span><span class="sxs-lookup"><span data-stu-id="c644b-211">With directory synchronization, the safelist collection is synchronized to Azure AD.</span></span>

- <span data-ttu-id="c644b-212">ユーザーのメールボックス内のセーフリスト コレクションの上限は 510 KB で、これにはすべてのリストに加えて、追加の迷惑メール フィルター設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c644b-212">The safelist collection in the user's mailbox has a limit of 510 KB, which includes all lists, plus additional junk email filter settings.</span></span> <span data-ttu-id="c644b-213">ユーザーがこの制限を超えると、次のような Outlook エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c644b-213">If a user exceeds this limit, they will receive an Outlook error that looks like this:</span></span>

  > <span data-ttu-id="c644b-214">Cannot/Unable add to the server Junk E-mail lists.</span><span class="sxs-lookup"><span data-stu-id="c644b-214">Cannot/Unable add to the server Junk E-mail lists.</span></span> <span data-ttu-id="c644b-215">サーバーで許可されているサイズを超えました。</span><span class="sxs-lookup"><span data-stu-id="c644b-215">You are over the size allowed on the server.</span></span> <span data-ttu-id="c644b-216">迷惑メール リストがサーバーで許可されているサイズに縮小されるまで、サーバーの迷惑メール フィルターは無効になります。</span><span class="sxs-lookup"><span data-stu-id="c644b-216">The Junk E-mail filter on the server will be disabled until your Junk E-mail lists have been reduced to the size allowed by the server.</span></span>

  <span data-ttu-id="c644b-217">この制限と変更方法の詳細については [、KB2669081 を参照](https://support.microsoft.com/help/2669081)してください。</span><span class="sxs-lookup"><span data-stu-id="c644b-217">For more information about this limit and how to change it, see [KB2669081](https://support.microsoft.com/help/2669081).</span></span>

- <span data-ttu-id="c644b-218">EOP の同期されたセーフリスト コレクションには、次の同期制限があります。</span><span class="sxs-lookup"><span data-stu-id="c644b-218">The synchronized safelist collection in EOP has the following synchronization limits:</span></span>

  - <span data-ttu-id="c644b-219">連絡先からの信頼メールが有効な場合、差出人セーフ リスト、宛先セーフ リスト、および外部連絡先の合計エントリ数は 1024 です。</span><span class="sxs-lookup"><span data-stu-id="c644b-219">1024 total entries in the Safe Senders list, the Safe Recipients list, and external contacts if **Trust email from my contacts** is enabled.</span></span>
  - <span data-ttu-id="c644b-220">[受信拒否リスト] および [受信拒否ドメイン] リストの合計エントリ数は 500 です。</span><span class="sxs-lookup"><span data-stu-id="c644b-220">500 total entries in the Blocked Senders list and Blocked Domains list.</span></span>

  <span data-ttu-id="c644b-221">1024 エントリの制限に達すると、次のことが発生します。</span><span class="sxs-lookup"><span data-stu-id="c644b-221">When the 1024 entry limit is reached, the following things happen:</span></span>

  - <span data-ttu-id="c644b-222">この一覧は PowerShell と Outlook on the web のエントリの受け入れを停止しますが、エラーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c644b-222">The list stops accepting entries in PowerShell and Outlook on the web, but no error is displayed.</span></span>

    <span data-ttu-id="c644b-223">Outlook ユーザーは、Outlook の制限である 510 KB に達するまで、1024 を超えるエントリを引き続き追加できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-223">Outlook users can continue to add more than 1024 entries until they reach the Outlook limit of 510 KB.</span></span> <span data-ttu-id="c644b-224">EOP フィルターがメールボックスに配信する前にメッセージをブロックしない限り (メール フロー ルール、スプーフィング対策など)、Outlook ではこれらの追加のエントリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c644b-224">Outlook can use these additional entries, as long as an EOP filter doesn't block the message before delivery to the mailbox (mail flow rules, anti-spoofing, etc.).</span></span>

- <span data-ttu-id="c644b-225">ディレクトリ同期では、エントリは Azure AD次の順序で同期されます。</span><span class="sxs-lookup"><span data-stu-id="c644b-225">With directory synchronization, the entries are synchronized to Azure AD in the following order:</span></span>

  1. <span data-ttu-id="c644b-226">連絡先からのメール **が信頼できる場合は、連絡先に** メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="c644b-226">Mail contacts if **Trust email from my contacts** is enabled.</span></span>
  2. <span data-ttu-id="c644b-227">差出人セーフ リストと宛先セーフ リストは、最初の 1024 エントリに変更が行われたときに、アルファベット順に結合、重複、並べ替えを行います。</span><span class="sxs-lookup"><span data-stu-id="c644b-227">The Safe Sender list and Safe Recipient list are combined, de-duplicated, and sorted alphabetically whenever a change is made for the first 1024 entries.</span></span>

  <span data-ttu-id="c644b-228">最初の 1024 エントリが使用され、関連する情報がメッセージ ヘッダーにスタンプされます。</span><span class="sxs-lookup"><span data-stu-id="c644b-228">The first 1024 entries are used, and relevant information is stamped in the message headers.</span></span>

  <span data-ttu-id="c644b-229">Azure AD に同期されていない 1024 を超えるエントリは、Outlook (Web 上の Outlook ではなく) によって処理され、メッセージ ヘッダーに情報がスタンプされません。</span><span class="sxs-lookup"><span data-stu-id="c644b-229">Entries over 1024 that weren't synchronized to Azure AD are processed by Outlook (not Outlook on the web), and no information is stamped in the message headers.</span></span>

<span data-ttu-id="c644b-230">ご覧のように、[連絡先からの信頼メール] 設定を有効にすると、同期できる信頼できる差出人と信頼できる受信者の数が減少します。</span><span class="sxs-lookup"><span data-stu-id="c644b-230">As you can see, enabling the **Trust email from my contacts** setting reduces the number of Safe Senders and Safe Recipients that can be synchronized.</span></span> <span data-ttu-id="c644b-231">これが問題である場合は、グループ ポリシーを使用してこの機能をオフにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c644b-231">If this is a concern, then we recommend using Group Policy to turn this feature off:</span></span>

- <span data-ttu-id="c644b-232">ファイル名: outlk16.opax</span><span class="sxs-lookup"><span data-stu-id="c644b-232">File name: outlk16.opax</span></span>
- <span data-ttu-id="c644b-233">ポリシー設定: **連絡先からの電子メールを信頼する**</span><span class="sxs-lookup"><span data-stu-id="c644b-233">Policy setting: **Trust e-mail from contacts**</span></span>
