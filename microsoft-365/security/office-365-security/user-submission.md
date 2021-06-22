---
title: ユーザー申請ポリシー
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、ユーザーによって報告されるスパムメールやフィッシングメールを収集するメールボックスを構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f565a71b44d27076ea6ff0b25be5d5b3932913c9
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53052989"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="fbe02-103">ユーザー申請ポリシー</span><span class="sxs-lookup"><span data-stu-id="fbe02-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fbe02-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="fbe02-104">**Applies to**</span></span>
- [<span data-ttu-id="fbe02-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fbe02-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fbe02-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="fbe02-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fbe02-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbe02-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="fbe02-108">メールボックスMicrosoft 365組織Exchange Online、悪意のあるメッセージまたは悪意ないメッセージを受信するメールボックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="fbe02-109">ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージを傍受 (カスタム メールボックスにのみ送信) したり、メッセージのコピー (カスタム メールボックスと Microsoft に送信) を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="fbe02-110">この機能は、次のメッセージ レポート オプションで動作します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="fbe02-111">レポート メッセージ アドイン</span><span class="sxs-lookup"><span data-stu-id="fbe02-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)
- [<span data-ttu-id="fbe02-112">レポートフィッシング アドイン</span><span class="sxs-lookup"><span data-stu-id="fbe02-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)
- [<span data-ttu-id="fbe02-113">サードパーティのレポート ツール</span><span class="sxs-lookup"><span data-stu-id="fbe02-113">Third-party reporting tools</span></span>](#third-party-reporting-tools)

<span data-ttu-id="fbe02-114">Microsoft に直接ではなく、ユーザーが報告したメッセージをカスタム メールボックスに配信すると、管理者は管理者申請を使用してメッセージを選択的および手動で Microsoft に [報告できます](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-114">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="fbe02-115">レポートが無効になっている[](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)場合は、Outlook on the web送信を有効にすると、この設定は上書きされ、ユーザーはメッセージを再びOutlook on the webできます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="fbe02-116">カスタム メールボックスの前提条件</span><span class="sxs-lookup"><span data-stu-id="fbe02-116">Custom mailbox prerequisites</span></span>

<span data-ttu-id="fbe02-117">ユーザーが報告したメッセージがカスタム メールボックスに移動するために必要な前提条件を構成するには、次の記事を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-117">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="fbe02-118">スパム信頼度を設定する Exchange メール フロー ルールを作成して、カスタム メールボックスのスパム フィルターをスキップします。</span><span class="sxs-lookup"><span data-stu-id="fbe02-118">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="fbe02-119">[「EAC を使用してメッセージの SCL を設定し、SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を [スパム フィルターのバイパス] に設定するメール フロー ルールを **作成する」を参照してください**。</span><span class="sxs-lookup"><span data-stu-id="fbe02-119">See [Use the EAC to create a mail flow rule that sets the SCL of a message](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **Bypass spam filtering**.</span></span>

- <span data-ttu-id="fbe02-120">[添付ファイルセーフスキャン](set-up-safe-attachments-policies.md)がオフになっているカスタム メールボックスを含む セーフ 添付ファイル ポリシーを作成します (セーフ **添付** ファイルの不明なマルウェア応答セクション \> **オフ**)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-120">[Create a Safe Attachments policy](set-up-safe-attachments-policies.md) that includes the custom mailbox where Safe Attachments scanning is turned off (**Safe Attachments unknown malware response** section \> **Off**).</span></span>

- <span data-ttu-id="fbe02-121">セーフ リンク [スキャン](set-up-safe-links-policies.md)がオフになっているカスタム メールボックスを含む セーフ リンク ポリシーを作成します ([メッセージ] セクションで不明な可能性のある悪意のある **URL** のアクションを選択 \> **します**)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-121">[Create a Safe Links policy](set-up-safe-links-policies.md) that includes the custom mailbox where Safe Links scanning is turned off (**Select the action for unknown potentially malicious URLs in messages** section \> **Off**).</span></span>

- <span data-ttu-id="fbe02-122">[マルウェアの](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)ゼロ時間自動削除 (ZAP) がオフになっているカスタム メールボックスを含むマルウェア対策ポリシーを作成します **([** 保護設定] セクション [マルウェアの 0 時間自動削除を有効にする] は \> 選択されません)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-122">[Create an anti-malware policy](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) that includes the custom mailbox where zero-hour auto purge (ZAP) for malware is turned off (**Protection settings** section \> **Enable zero-hour auto purge for malware** is not selected).</span></span>

- <span data-ttu-id="fbe02-123">[](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies)スパム用 ZAP とフィッシング用 ZAP がオフになっているカスタム メールボックスを含むスパム対策ポリシーを作成します (ゼロ時間自動削除セクション [有効な 0 時間自動削除 \> **(ZAP) は** 選択されません)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-123">[Create an anti-spam policy](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) that includes the custom mailbox where ZAP for spam and ZAP for phishing are turned off (**Zero-hour auto purge** section \> **Enabled zero-hour auto purge (ZAP)** is not selected).</span></span>

- <span data-ttu-id="fbe02-124">カスタム メールボックスで迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="fbe02-124">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="fbe02-125">迷惑[メール ルールを無効にするには、Exchange Onlineの](configure-junk-email-settings-on-exo-mailboxes.md)迷惑メール設定を構成するを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-125">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="fbe02-126">無効にした後、EOP はスパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動できませんメッセージを迷惑メール フォルダーまたはメールボックスのセーフリスト コレクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-126">After it's disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="fbe02-127">メールボックスが適用可能なすべての前提条件を満たしていることを確認した後、この記事の手順を使用してユーザー申請メールボックスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-127">After you've verified that your mailbox meets all applicable prerequisites, you can use the procedures in this article to configure the user submissions mailbox.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fbe02-128">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="fbe02-128">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fbe02-129"><https://security.microsoft.com/> で Microsoft 365 Defender ポータルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-129">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="fbe02-130">[申請] ページに直接 **移動するには** 、 を使用します <https://security.microsoft.com/reportsubmission> 。</span><span class="sxs-lookup"><span data-stu-id="fbe02-130">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="fbe02-131">ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbe02-131">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="fbe02-132">**[組織の管理\*\*\*\*] または [セキュリティ** 管理者][をMicrosoft 365 Defenderします](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-132">**Organization Management** or **Security Administrator** in the [Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="fbe02-133">**[組織の** 管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-133">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="fbe02-134">PowerShell へのアクセスExchange Online必要です。</span><span class="sxs-lookup"><span data-stu-id="fbe02-134">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="fbe02-135">使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、申請メールボックスを指定すると、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-135">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="fbe02-136">ドメイン内の電子メール アドレスを指定する</span><span class="sxs-lookup"><span data-stu-id="fbe02-136">Specify an email address in your domain</span></span>

  <span data-ttu-id="fbe02-137">PowerShell へのアクセスを有効または無効にする方法のExchange Online、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbe02-137">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="fbe02-138">Exchange Online PowerShell へのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="fbe02-138">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="fbe02-139">クライアント アクセス ルール (Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fbe02-139">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="fbe02-140">ユーザー申請メールボックスMicrosoft 365 Defenderポータルを使用して構成する</span><span class="sxs-lookup"><span data-stu-id="fbe02-140">Use the Microsoft 365 Defender portal to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="fbe02-141">このポータルMicrosoft 365 Defender、[ポリシー] &[脅威ポリシー] [その **他**] セクション [ユーザーが報告したメッセージの設定 \>  \> ] [ユーザーの申請] \>  \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="fbe02-141">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings** \> **User submissions**.</span></span>

2. <span data-ttu-id="fbe02-142">[ユーザーの **申請] ページ** で、表示される情報は **、[Microsoft** レポート メッセージ] Outlook設定が [オフ] または [オン] のOutlook **によって** 決 **まります**。</span><span class="sxs-lookup"><span data-stu-id="fbe02-142">On the **User submissions** page, what you see is determined by whether the **Microsoft Outlook Report Message button** setting is **Off** or **On**:</span></span>

   - <span data-ttu-id="fbe02-143">**[Microsoft Outlook レポート メッセージ] ボタン** \>**On** ![トグルオン: Outlook on the web でレポート メッセージ アドイン、レポート フィッシング アドイン、または組み込みのレポートを使用する場合は、このオプションを選択し、 ](../../media/scc-toggle-on.png) 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-143">**Microsoft Outlook Report Message button** \> **On** ![Toggle on](../../media/scc-toggle-on.png): Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>
     - <span data-ttu-id="fbe02-144">**報告されたメッセージを送信する**: 次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-144">**Send the reported messages to**: Select one of the following options:</span></span>
       - <span data-ttu-id="fbe02-145">**Microsoft**: ユーザー申請メールボックスは使用されません (報告されたメッセージはすべて Microsoft に送信されます)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-145">**Microsoft**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>
       - <span data-ttu-id="fbe02-146">**Microsoft と組織のメールボックス**: 表示されるボックスに、既存のメールボックスの電子メール Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="fbe02-146">**Microsoft and my organization's mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="fbe02-147">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="fbe02-147">Distribution groups are not allowed.</span></span> <span data-ttu-id="fbe02-148">ユーザー申請は、分析のために Microsoft と管理者またはセキュリティ操作チームが分析するカスタム メールボックスの両方に移動します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-148">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>
       - <span data-ttu-id="fbe02-149">**組織のメールボックス**: 表示されるボックスに、既存のメールボックスのメール アドレスをExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="fbe02-149">**My organization's mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="fbe02-150">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="fbe02-150">Distribution groups are not allowed.</span></span> <span data-ttu-id="fbe02-151">このオプションは、最初に分析のために管理者またはセキュリティ運用チームにのみメッセージを移動する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-151">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="fbe02-152">管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="fbe02-152">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

          > [!IMPORTANT]
          >
          > <span data-ttu-id="fbe02-153">米国政府機関 (GCC、GCC、DoD) は、自分の組織のメールボックス **のみを構成できます**。</span><span class="sxs-lookup"><span data-stu-id="fbe02-153">U.S. Government organizations (GCC, GCC High, and DoD) can only configure **My organization's mailbox**.</span></span> <span data-ttu-id="fbe02-154">他の 2 つのオプションは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="fbe02-154">The other two options are disabled.</span></span>
          >
          > <span data-ttu-id="fbe02-155">組織がカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージ ポータルの結果は常に空になります。</span><span class="sxs-lookup"><span data-stu-id="fbe02-155">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

       <span data-ttu-id="fbe02-156">[報告されたメッセージの送信先] で選択した値に関係 **なく、次** の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-156">Regardless of the value you selected for **Send the reported messages to**, the following settings are available:</span></span>

       - <span data-ttu-id="fbe02-157">**ユーザーが自分のメッセージを Microsoft に報告する場合の選択を許可する**</span><span class="sxs-lookup"><span data-stu-id="fbe02-157">**Let users choose if they want to report their message to Microsoft**</span></span>
       - <span data-ttu-id="fbe02-158">**[ユーザーが使用できるレポート オプションを選択** する] セクション: 次のオプションの中から少なくとも 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-158">**Select reporting options that are available to users** section: Select at least one among the following options:</span></span>
         - <span data-ttu-id="fbe02-159">**メッセージを送信する前に確認する**</span><span class="sxs-lookup"><span data-stu-id="fbe02-159">**Ask me before sending the message**</span></span>
         - <span data-ttu-id="fbe02-160">**常にメッセージを報告する**</span><span class="sxs-lookup"><span data-stu-id="fbe02-160">**Always report the message**</span></span>
         - <span data-ttu-id="fbe02-161">**メッセージを報告しない**</span><span class="sxs-lookup"><span data-stu-id="fbe02-161">**Never report the message**</span></span>

          > [!CAUTION]
          > <span data-ttu-id="fbe02-162">Outlook on the web メールボックス ポリシーを使用して[Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)で迷惑メール報告を無効にしたが、以前の設定を構成して Microsoft にメッセージを報告した場合、ユーザーはレポート メッセージ アドインまたはレポートフィッシング アドインを使用して Outlook on the web で Microsoft にメッセージを報告できます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-162">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configured any of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>

     - <span data-ttu-id="fbe02-163">**[ユーザー レポートエクスペリエンス] セクション**</span><span class="sxs-lookup"><span data-stu-id="fbe02-163">**User reporting experience section**</span></span>
       - <span data-ttu-id="fbe02-164">**[レポート** の前に]タブ: [タイトル] および [メッセージ] 本文ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-164">**Before reporting** tab: In the **Title** and **Message body** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="fbe02-165">変数 %type% を使用して、申請の種類 (迷惑メール、迷惑メール、フィッシングなど) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-165">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>
       - <span data-ttu-id="fbe02-166">**[レポート後**] タブ:  [タイトル] および [確認] メッセージ ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-166">**After reporting** tab: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="fbe02-167">変数 %type% を使用して、申請の種類を含めできます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-167">You can use the variable %type% to include the submission type.</span></span>

       <span data-ttu-id="fbe02-168">ページに示すように、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-168">As shown on the page, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

          > <span data-ttu-id="fbe02-169">電子メールは分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-169">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="fbe02-170">一部の電子メールには、個人情報または機密情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbe02-170">Some emails might contain personal or sensitive information.</span></span>

   - <span data-ttu-id="fbe02-171">**[Microsoft Outlook レポート メッセージ] ボタン** \>**Off** ![トグルオフ: レポート メッセージ アドイン、レポート フィッシング アドイン、または Outlook on the web の組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択し、次の設定を ](../../media/scc-toggle-off.png) 構成します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-171">**Microsoft Outlook Report Message button** \> **Off** ![Toggle off](../../media/scc-toggle-off.png): Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in, or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>
     - <span data-ttu-id="fbe02-172">[この **カスタム メールボックスを使用して、ユーザーが報告した申請を受信する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fbe02-172">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="fbe02-173">表示されるボックスに、メールを受信できる既存のメールボックスのExchange Onlineを入力します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-173">In the box that appears, enter the email address of an existing Exchange Online mailbox that can receive email.</span></span>

   <span data-ttu-id="fbe02-174">完了したら、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="fbe02-174">When you're finished, click **Confirm**.</span></span> <span data-ttu-id="fbe02-175">これらの値をクリアするには、[復元] を **クリックします。**</span><span class="sxs-lookup"><span data-stu-id="fbe02-175">To clear these values, click **Restore**</span></span>

## <a name="third-party-reporting-tools"></a><span data-ttu-id="fbe02-176">サードパーティのレポート ツール</span><span class="sxs-lookup"><span data-stu-id="fbe02-176">Third-party reporting tools</span></span>

<span data-ttu-id="fbe02-177">サード パーティ製のメッセージ レポート ツールを構成して、報告されたメッセージをカスタム メールボックスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-177">You can configure third-party message reporting tools to send reported messages to the custom mailbox.</span></span> <span data-ttu-id="fbe02-178">これを行うには、[Microsoft Outlook レポート メッセージ] ボタン **の設定** を[オフ]に設定し、自分の組織のメールボックスを選択Office 365メールボックスに設定します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-178">You would do this by setting the **Microsoft Outlook Report Message button** setting to **Off** and setting the **My organization's mailbox** to an Office 365 mailbox of your choice.</span></span>

<span data-ttu-id="fbe02-179">唯一の要件は、元のメッセージが .EML または .カスタム メールボックスに送信されるメッセージ内の MSG 添付ファイル (圧縮されていない) (元のメッセージをカスタム メールボックスに転送するだけではない)。</span><span class="sxs-lookup"><span data-stu-id="fbe02-179">The only requirement is that the original message is included as a .EML or .MSG attachment (not compressed) in the message that's sent to the custom mailbox (don't just forward the original message to the custom mailbox).</span></span>

<span data-ttu-id="fbe02-180">メッセージの書式設定の要件については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-180">The message formatting requirements are described in the next section.</span></span> <span data-ttu-id="fbe02-181">書式設定は省略可能ですが、指定された形式に従う場合、レポートは常にフィッシングとして送信されます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-181">The formatting is optional, but if it does not follow the prescribed format, the reports will always be submitted as phish.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="fbe02-182">メッセージ送信形式</span><span class="sxs-lookup"><span data-stu-id="fbe02-182">Message submission format</span></span>

<span data-ttu-id="fbe02-183">元の添付メッセージを正しく識別するには、カスタム メールボックスに送信されるメッセージには、特定の書式が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbe02-183">To correctly identify the original attached messages, messages that are sent to the custom mailbox require specific formatting.</span></span> <span data-ttu-id="fbe02-184">メッセージでこの形式を使用しない場合、添付された元のメッセージは常にフィッシング申請として識別されます。</span><span class="sxs-lookup"><span data-stu-id="fbe02-184">If the messages don't use this format, the original attached messages are always identified as phishing submissions.</span></span>

<span data-ttu-id="fbe02-185">元の添付メッセージを正しく識別するために、カスタム メールボックスに送信されるメッセージは、Subject (Envelope Title) に次の構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbe02-185">For correct identification of the original attached messages, messages that are sent to the custom mailbox need to use the following syntax for the Subject (Envelope Title):</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="fbe02-186">SafetyAPIAction は次のいずれかの整数値です。</span><span class="sxs-lookup"><span data-stu-id="fbe02-186">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="fbe02-187">1: 迷惑メール</span><span class="sxs-lookup"><span data-stu-id="fbe02-187">1: Junk</span></span>
- <span data-ttu-id="fbe02-188">2: 迷惑メールではない</span><span class="sxs-lookup"><span data-stu-id="fbe02-188">2: Not junk</span></span>
- <span data-ttu-id="fbe02-189">3: フィッシング</span><span class="sxs-lookup"><span data-stu-id="fbe02-189">3: Phishing</span></span>

<span data-ttu-id="fbe02-190">この例では、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbe02-190">This example uses the following values:</span></span>

- <span data-ttu-id="fbe02-191">メッセージがフィッシングとして報告されています。</span><span class="sxs-lookup"><span data-stu-id="fbe02-191">The message is being reported as phishing.</span></span>
- <span data-ttu-id="fbe02-192">ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。</span><span class="sxs-lookup"><span data-stu-id="fbe02-192">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="fbe02-193">Sender IP は 167.220.232.101 です。</span><span class="sxs-lookup"><span data-stu-id="fbe02-193">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="fbe02-194">From アドレスが test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="fbe02-194">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="fbe02-195">メッセージの件名は"フィッシング申請のテスト" です。</span><span class="sxs-lookup"><span data-stu-id="fbe02-195">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="fbe02-196">この形式に従らないメッセージは、申請ポータルに正しく表示されません。</span><span class="sxs-lookup"><span data-stu-id="fbe02-196">Messages that don't follow this format will not display properly in the Submissions portal.</span></span>
