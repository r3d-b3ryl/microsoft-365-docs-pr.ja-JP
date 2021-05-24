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
ms.openlocfilehash: 852e87ee76d9692b789ca217720ac3efb08f31a8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624611"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="968ee-103">ユーザー申請ポリシー</span><span class="sxs-lookup"><span data-stu-id="968ee-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="968ee-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="968ee-104">**Applies to**</span></span>
- [<span data-ttu-id="968ee-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="968ee-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="968ee-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="968ee-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="968ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="968ee-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="968ee-108">メールボックスMicrosoft 365組織Exchange Online、悪意のあるメッセージまたは悪意ないメッセージを受信するメールボックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="968ee-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="968ee-109">ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージを傍受 (カスタム メールボックスにのみ送信) したり、メッセージのコピー (カスタム メールボックスと Microsoft に送信) を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="968ee-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="968ee-110">この機能は、次のメッセージ レポート オプションで動作します。</span><span class="sxs-lookup"><span data-stu-id="968ee-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="968ee-111">レポート メッセージ アドイン</span><span class="sxs-lookup"><span data-stu-id="968ee-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="968ee-112">レポートフィッシング アドイン</span><span class="sxs-lookup"><span data-stu-id="968ee-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- [<span data-ttu-id="968ee-113">サードパーティのレポート ツール</span><span class="sxs-lookup"><span data-stu-id="968ee-113">Third-party reporting tools</span></span>](#third-party-reporting-tools)

<span data-ttu-id="968ee-114">Microsoft に直接ではなく、ユーザーが報告したメッセージをカスタム メールボックスに配信すると、管理者は管理者申請を使用してメッセージを選択的および手動で Microsoft に [報告できます](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="968ee-114">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="968ee-115">web 上の[](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)Outlook でレポートが無効になっている場合、ここでユーザーの申請を有効にすると、その設定が上書きされ、ユーザーは web 上の Outlookでメッセージを報告できます。</span><span class="sxs-lookup"><span data-stu-id="968ee-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="968ee-116">カスタム メールボックスの前提条件</span><span class="sxs-lookup"><span data-stu-id="968ee-116">Custom mailbox prerequisites</span></span>

<span data-ttu-id="968ee-117">ユーザーが報告したメッセージがカスタム メールボックスに移動するために必要な前提条件を構成するには、次の記事を使用します。</span><span class="sxs-lookup"><span data-stu-id="968ee-117">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="968ee-118">スパム信頼度を設定する Exchange メール フロー ルールを作成して、カスタム メールボックスのスパム フィルターをスキップします。</span><span class="sxs-lookup"><span data-stu-id="968ee-118">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="968ee-119">[「EAC を使用してメッセージの SCL を設定し、SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を [スパム フィルターのバイパス] に設定するメール フロー ルールを **作成する」を参照してください**。</span><span class="sxs-lookup"><span data-stu-id="968ee-119">See [Use the EAC to create a mail flow rule that sets the SCL of a message](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **Bypass spam filtering**.</span></span>

- <span data-ttu-id="968ee-120">カスタム メールボックス内のマルウェアの添付ファイルのスキャンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="968ee-120">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="968ee-121">[Defender [for セーフ](set-up-safe-attachments-policies.md)の添付ファイル ポリシーの設定Office 365を使用して、セーフ 添付ファイルポリシーを作成し、[添付ファイルの不明なマルウェアの応答] の [セーフ]**を設定します**。</span><span class="sxs-lookup"><span data-stu-id="968ee-121">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="968ee-122">カスタム メールボックス内のメッセージの URL スキャンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="968ee-122">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="968ee-123">[[Defender for Office 365](set-up-safe-links-policies.md)で セーフ リンク ポリシーを設定する] を使用して、[メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する] の設定を [オフ] に設定して セーフ リンク ポリシーを作成 **します**。</span><span class="sxs-lookup"><span data-stu-id="968ee-123">Use [Set up Safe Links policies in Defender for Office 365](set-up-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="968ee-124">マルウェアゼロ時間自動削除を無効にするマルウェア対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="968ee-124">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="968ee-125">「Use [the Security & コンプライアンス](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) センター」を参照してマルウェア対策ポリシーを作成し、[マルウェアゼロ時間 **自動削除** ] を [オフ] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="968ee-125">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="968ee-126">スパム フィルター ポリシーを作成して、カスタム メールボックス内のスパムとフィッシングのゼロ時間自動削除 (ZAP) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="968ee-126">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="968ee-127">「Use [the Security & コンプライアンス](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)センター」を参照してスパム対策ポリシーを作成し、[スパム ZAP とフィッシング **ZAP** のオン] チェック ボックス **をオフにします**。</span><span class="sxs-lookup"><span data-stu-id="968ee-127">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="968ee-128">カスタム メールボックスで迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="968ee-128">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="968ee-129">迷惑[メール ルールを無効にするには、Exchange Onlineの](configure-junk-email-settings-on-exo-mailboxes.md)迷惑メール設定を構成するを使用します。</span><span class="sxs-lookup"><span data-stu-id="968ee-129">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="968ee-130">無効にすると、EOP はスパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動できません **メッセージ** を迷惑メール フォルダーまたはメールボックスのセーフリスト コレクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="968ee-130">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="968ee-131">メールボックスが適用可能なすべての前提条件を満たしていることを確認した後、セキュリティ & コンプライアンス センターを使用してユーザー申請 [メールボックスを構成](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) します (この記事)。</span><span class="sxs-lookup"><span data-stu-id="968ee-131">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="968ee-132">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="968ee-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="968ee-133"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="968ee-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="968ee-134">[ユーザー申請] ページに **直接移動するには** 、 を使用します <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="968ee-134">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="968ee-135">ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="968ee-135">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="968ee-136">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="968ee-136">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="968ee-137">**[組織の** 管理] [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="968ee-137">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="968ee-138">PowerShell へのアクセスExchange Online必要です。</span><span class="sxs-lookup"><span data-stu-id="968ee-138">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="968ee-139">使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、申請メールボックスを指定すると、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="968ee-139">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="968ee-140">ドメイン内の電子メール アドレスを指定する</span><span class="sxs-lookup"><span data-stu-id="968ee-140">Specify an email address in your domain</span></span>

  <span data-ttu-id="968ee-141">PowerShell へのアクセスを有効または無効にする方法のExchange Online、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="968ee-141">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="968ee-142">Exchange Online PowerShell へのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="968ee-142">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="968ee-143">クライアント アクセス ルール (Exchange Online</span><span class="sxs-lookup"><span data-stu-id="968ee-143">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="968ee-144">コンプライアンス センターのセキュリティ &を使用して、ユーザー申請メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="968ee-144">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="968ee-145">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー \> **の [ユーザー** の申請 \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="968ee-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="968ee-146">表示される **[ユーザーの申請]** ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="968ee-146">In the **User submissions** page that appears, select one of the following options:</span></span>

      1. <span data-ttu-id="968ee-147">**Outlook (推奨)** のレポート メッセージ機能を有効にする: レポート メッセージ アドイン、レポート フィッシング アドイン、または web 上の Outlook の組み込みレポートを使用する場合は、このオプションを選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="968ee-147">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

    - <span data-ttu-id="968ee-148">**エンド ユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="968ee-148">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="968ee-149">表示される **[確認メッセージのカスタマイズ** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="968ee-149">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

        - <span data-ttu-id="968ee-150">**提出前**: [**タイトル**] および [確認] メッセージ ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。 </span><span class="sxs-lookup"><span data-stu-id="968ee-150">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="968ee-151">変数 %type% を使用して、申請の種類 (迷惑メール、迷惑メール、フィッシングなど) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="968ee-151">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

          <span data-ttu-id="968ee-152">既に説明した通り、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。</span><span class="sxs-lookup"><span data-stu-id="968ee-152">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

          > <span data-ttu-id="968ee-153">電子メールは分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="968ee-153">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="968ee-154">一部の電子メールには、個人情報または機密情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="968ee-154">Some emails might contain personal or sensitive information.</span></span>

        - <span data-ttu-id="968ee-155">**申請後:**[展開] ![ アイコンをクリックします ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="968ee-155">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="968ee-156">[タイトル **] および** **[確認** ] メッセージ ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="968ee-156">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="968ee-157">変数 %type% を使用して、申請の種類を含めできます。</span><span class="sxs-lookup"><span data-stu-id="968ee-157">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="968ee-158">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="968ee-158">When you're finished, click **Save**.</span></span> <span data-ttu-id="968ee-159">これらの値をクリアするには、[ユーザー申請] **ページ** の [復元 **] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="968ee-159">To clear these values, click **Restore** back on the **User submissions** page.</span></span>
    
    - <span data-ttu-id="968ee-160">**エンド ユーザーレポートオプションをカスタマイズする**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="968ee-160">**Customize the end-user reporting options**: Click this link.</span></span> <span data-ttu-id="968ee-161">表示される **[エンドユーザーレポート オプションのカスタマイズ]** フライアウトで、[迷惑メールレポートオプション] の説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="968ee-161">In the **Customize end-user reporting options** flyout that appears, enter the descriptive text for Junk email reporting options.</span></span> 
    
      <span data-ttu-id="968ee-162">[ **メッセージの報告時に表示するオプション] で、** 次のオプションの中から少なくとも 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="968ee-162">Under **Options to show when messages are reported**, select at least one among the following options:</span></span>
        - <span data-ttu-id="968ee-163">**レポートを送信する前に確認する**</span><span class="sxs-lookup"><span data-stu-id="968ee-163">**Ask me before sending a report**</span></span>
        - <span data-ttu-id="968ee-164">**レポートを自動的に送信する**</span><span class="sxs-lookup"><span data-stu-id="968ee-164">**Automatically send reports**</span></span>
        - <span data-ttu-id="968ee-165">**レポートを送信しない**</span><span class="sxs-lookup"><span data-stu-id="968ee-165">**Never send reports**</span></span>
       
      <span data-ttu-id="968ee-166">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="968ee-166">When you're finished, click **Save**.</span></span>

        - <span data-ttu-id="968ee-167">**報告されたメッセージを送信する**: 次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="968ee-167">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="968ee-168">**Microsoft (推奨)**: ユーザー申請メールボックスが使用されていません (報告されたメッセージはすべて Microsoft に送信されます)。</span><span class="sxs-lookup"><span data-stu-id="968ee-168">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="968ee-169">**Microsoft とカスタム メールボックスの** 両方 : 表示されるボックスに、既存のメールボックスの電子メール Exchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="968ee-169">**Both Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="968ee-170">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="968ee-170">Distribution groups are not allowed.</span></span> <span data-ttu-id="968ee-171">ユーザー申請は、分析のために Microsoft と管理者またはセキュリティ操作チームが分析するカスタム メールボックスの両方に移動します。</span><span class="sxs-lookup"><span data-stu-id="968ee-171">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="968ee-172">**カスタム メールボックスのみ**: 表示されるボックスに、既存のメールボックスの電子メール アドレスをExchange Onlineします。</span><span class="sxs-lookup"><span data-stu-id="968ee-172">**Custom mailbox only**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="968ee-173">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="968ee-173">Distribution groups are not allowed.</span></span> <span data-ttu-id="968ee-174">このオプションは、最初に分析のために管理者またはセキュリティ運用チームにのみメッセージを移動する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="968ee-174">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="968ee-175">管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="968ee-175">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

          > [!NOTE]
          > <span data-ttu-id="968ee-176">米国政府機関 (GCC、GCC-H、DoD) は、カスタム メールボックスのみを **構成できます**。</span><span class="sxs-lookup"><span data-stu-id="968ee-176">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="968ee-177">他の 2 つのオプションは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="968ee-177">The other two options are disabled.</span></span>

          > [!NOTE]
          > <span data-ttu-id="968ee-178">組織がカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージ ポータルの結果は常に空になります。</span><span class="sxs-lookup"><span data-stu-id="968ee-178">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

      <span data-ttu-id="968ee-179">完了したら、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="968ee-179">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="968ee-180">web メールボックス ポリシーで Outlook を使用して web 上の[Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)で迷惑メール報告を無効にしたが、Microsoft にメッセージを報告する前の設定のいずれかを構成した場合、ユーザーはレポート メッセージ アドインまたはレポート フィッシング アドインを使用して、Web 上の Outlook で Microsoft にメッセージを報告できます。</span><span class="sxs-lookup"><span data-stu-id="968ee-180">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>


    2. <span data-ttu-id="968ee-181">**Outlook** のレポート メッセージ機能を無効にする: レポート メッセージ アドイン、レポート フィッシング アドイン、または web 上の Outlook の組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="968ee-181">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in, or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

       <span data-ttu-id="968ee-182">[この **カスタム メールボックスを使用して、ユーザーが報告した申請を受信する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="968ee-182">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="968ee-183">表示されるボックスに、既存のメールボックスの電子メール アドレスを入力します。Office 365。</span><span class="sxs-lookup"><span data-stu-id="968ee-183">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="968ee-184">これは、電子メールを受信できる既存Exchange Onlineメールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="968ee-184">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

       <span data-ttu-id="968ee-185">完了したら、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="968ee-185">When you're finished, click **Confirm**.</span></span>

## <a name="third-party-reporting-tools"></a><span data-ttu-id="968ee-186">サードパーティのレポート ツール</span><span class="sxs-lookup"><span data-stu-id="968ee-186">Third-party reporting tools</span></span>

<span data-ttu-id="968ee-187">サード パーティ製のメッセージ レポート ツールを構成して、報告されたメッセージをカスタム メールボックスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="968ee-187">You can configure third-party message reporting tools to send reported messages to the custom mailbox.</span></span> <span data-ttu-id="968ee-188">唯一の要件は、元のメッセージがカスタム メールボックスに送信されるメッセージの添付ファイルとして含まれる場合です (元のメッセージをカスタム メールボックスに転送するだけではない)。</span><span class="sxs-lookup"><span data-stu-id="968ee-188">The only requirement is that the original message is included as an attachment in the message that's sent to the custom mailbox (don't just forward the original message to the custom mailbox).</span></span>

<span data-ttu-id="968ee-189">メッセージの書式設定の要件については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="968ee-189">The message formatting requirements are described in the next section.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="968ee-190">メッセージ送信形式</span><span class="sxs-lookup"><span data-stu-id="968ee-190">Message submission format</span></span>

<span data-ttu-id="968ee-191">元の添付メッセージを正しく識別するには、カスタム メールボックスに送信されるメッセージには、特定の書式が必要です。</span><span class="sxs-lookup"><span data-stu-id="968ee-191">To correctly identify the original attached messages, messages that are sent to the custom mailbox require specific formatting.</span></span> <span data-ttu-id="968ee-192">メッセージでこの形式を使用しない場合、添付された元のメッセージは常にフィッシング申請として識別されます。</span><span class="sxs-lookup"><span data-stu-id="968ee-192">If the messages don't use this format, the original attached messages are always identified as phishing submissions.</span></span>

<span data-ttu-id="968ee-193">元の添付メッセージを正しく識別するために、カスタム メールボックスに送信されるメッセージは、Subject (Envelope Title) に次の構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="968ee-193">For correct identification of the original attached messages, messages that are sent to the custom mailbox need to use the following syntax for the Subject (Envelope Title):</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="968ee-194">SafetyAPIAction は次のいずれかの整数値です。</span><span class="sxs-lookup"><span data-stu-id="968ee-194">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="968ee-195">1: 迷惑メール</span><span class="sxs-lookup"><span data-stu-id="968ee-195">1: Junk</span></span>
- <span data-ttu-id="968ee-196">2: 迷惑メールではない</span><span class="sxs-lookup"><span data-stu-id="968ee-196">2: Not junk</span></span>
- <span data-ttu-id="968ee-197">3: フィッシング</span><span class="sxs-lookup"><span data-stu-id="968ee-197">3: Phishing</span></span>

<span data-ttu-id="968ee-198">この例では、次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="968ee-198">This example uses the following values:</span></span>

- <span data-ttu-id="968ee-199">メッセージがフィッシングとして報告されています。</span><span class="sxs-lookup"><span data-stu-id="968ee-199">The message is being reported as phishing.</span></span>
- <span data-ttu-id="968ee-200">ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。</span><span class="sxs-lookup"><span data-stu-id="968ee-200">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="968ee-201">Sender IP は 167.220.232.101 です。</span><span class="sxs-lookup"><span data-stu-id="968ee-201">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="968ee-202">From アドレスが test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="968ee-202">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="968ee-203">メッセージの件名は"フィッシング申請のテスト" です。</span><span class="sxs-lookup"><span data-stu-id="968ee-203">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="968ee-204">この形式に従らないメッセージは、申請ポータルに正しく表示されません。</span><span class="sxs-lookup"><span data-stu-id="968ee-204">Messages that don't follow this format will not display properly in the Submissions portal.</span></span>
