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
ms.openlocfilehash: d86c79f0f0ab74d1dfbb88e7803f4ee4d691ea73
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501178"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="173bc-103">ユーザー申請ポリシー</span><span class="sxs-lookup"><span data-stu-id="173bc-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="173bc-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="173bc-104">**Applies to**</span></span>
- [<span data-ttu-id="173bc-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="173bc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="173bc-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="173bc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="173bc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="173bc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="173bc-108">Exchange Online メールボックスを使用する Microsoft 365 組織では、悪意のあるメッセージまたは悪意ないメッセージを受信するメールボックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="173bc-108">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="173bc-109">ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージを傍受 (カスタム メールボックスにのみ送信) したり、メッセージのコピー (カスタム メールボックスと Microsoft に送信) を受信することができます。</span><span class="sxs-lookup"><span data-stu-id="173bc-109">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="173bc-110">この機能は、次のメッセージ レポート オプションで動作します。</span><span class="sxs-lookup"><span data-stu-id="173bc-110">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="173bc-111">レポート メッセージ アドイン</span><span class="sxs-lookup"><span data-stu-id="173bc-111">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="173bc-112">レポートフィッシング アドイン</span><span class="sxs-lookup"><span data-stu-id="173bc-112">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- <span data-ttu-id="173bc-113">[Outlook on the web の組み](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 込みレポート (以前は Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="173bc-113">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="173bc-114">Outlook for iOS および Android の組み込みレポート</span><span class="sxs-lookup"><span data-stu-id="173bc-114">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="173bc-115">Outlook on [the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)でレポートが無効になっている場合は、ここでユーザー申請を有効にすると、その設定が上書きされ、ユーザーは Outlook on the web でメッセージを再び報告できます。</span><span class="sxs-lookup"><span data-stu-id="173bc-115">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="173bc-116">指定したメールボックスにメッセージを転送するサード パーティ製のメッセージ レポート ツールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="173bc-116">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="173bc-117">Microsoft に直接ではなく、ユーザーが報告したメッセージをカスタム メールボックスに配信すると、管理者は管理者申請を使用してメッセージを選択的および手動で Microsoft に [報告できます](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="173bc-117">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="173bc-118">カスタム メールボックスの前提条件</span><span class="sxs-lookup"><span data-stu-id="173bc-118">Custom mailbox prerequisites</span></span>

<span data-ttu-id="173bc-119">ユーザーが報告したメッセージがカスタム メールボックスに移動するために必要な前提条件を構成するには、次の記事を使用します。</span><span class="sxs-lookup"><span data-stu-id="173bc-119">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="173bc-120">スパム信頼度を設定する Exchange メール フロー ルールを作成して、カスタム メールボックスのスパム フィルターをスキップします。</span><span class="sxs-lookup"><span data-stu-id="173bc-120">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="173bc-121">[「EAC を使用して、SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を **-1** に設定するメッセージの SCL を設定するメール フロー ルールを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="173bc-121">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="173bc-122">カスタム メールボックス内のマルウェアの添付ファイルのスキャンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="173bc-122">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="173bc-123">[Defender for Office [365](set-up-safe-attachments-policies.md)で安全な添付ファイル ポリシーを設定する] を使用して、[安全な添付ファイルの不明なマルウェアの応答をオフにする] を設定して安全な添付ファイル ポリシー **を作成します**。</span><span class="sxs-lookup"><span data-stu-id="173bc-123">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="173bc-124">カスタム メールボックス内のメッセージの URL スキャンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="173bc-124">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="173bc-125">[[Defender for Office 365]](set-up-safe-links-policies.md)で [安全なリンクポリシーを設定する] を使用して、[メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する] の [オフ] を設定して安全なリンク ポリシーを作成 **します**。</span><span class="sxs-lookup"><span data-stu-id="173bc-125">Use [Set up Safe Links policies in Defender for Office 365](set-up-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="173bc-126">マルウェアゼロ時間自動削除を無効にするマルウェア対策ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="173bc-126">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="173bc-127">「Use [the Security & コンプライアンス](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) センター」を参照してマルウェア対策ポリシーを作成し、[マルウェアゼロ時間 **自動削除** ] を [オフ] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="173bc-127">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="173bc-128">スパム フィルター ポリシーを作成して、カスタム メールボックス内のスパムとフィッシングのゼロ時間自動削除 (ZAP) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="173bc-128">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="173bc-129">「Use [the Security & コンプライアンス](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)センター」を参照してスパム対策ポリシーを作成し、[スパム ZAP とフィッシング **ZAP** のオン] チェック ボックス **をオフにします**。</span><span class="sxs-lookup"><span data-stu-id="173bc-129">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="173bc-130">カスタム メールボックスで迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="173bc-130">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="173bc-131">[[Exchange Online メールボックスの迷惑メール設定の構成] を使用して、](configure-junk-email-settings-on-exo-mailboxes.md)迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="173bc-131">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="173bc-132">無効にすると、EOP はスパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動できません **メッセージ** を迷惑メール フォルダーまたはメールボックスのセーフリスト コレクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="173bc-132">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="173bc-133">メールボックスが適用可能なすべての前提条件を満たしていることを確認した後、セキュリティ & コンプライアンス センターを使用してユーザー申請 [メールボックスを構成](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) します (この記事)。</span><span class="sxs-lookup"><span data-stu-id="173bc-133">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="173bc-134">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="173bc-134">What do you need to know before you begin?</span></span>

- <span data-ttu-id="173bc-135"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="173bc-135">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="173bc-136">[ユーザー申請] ページに **直接移動するには** 、 を使用します <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="173bc-136">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="173bc-137">ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="173bc-137">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="173bc-138">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="173bc-138">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="173bc-139">Exchange **Online の**[組織の管理](/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="173bc-139">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="173bc-140">Exchange Online PowerShell にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="173bc-140">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="173bc-141">使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合は、申請メールボックスを指定すると、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="173bc-141">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="173bc-142">ドメイン内の電子メール アドレスを指定する</span><span class="sxs-lookup"><span data-stu-id="173bc-142">Specify an email address in your domain</span></span>

  <span data-ttu-id="173bc-143">Exchange Online PowerShell へのアクセスを有効または無効にする方法の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="173bc-143">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="173bc-144">Exchange Online PowerShell へのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="173bc-144">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="173bc-145">Exchange Online のクライアント アクセス ルール</span><span class="sxs-lookup"><span data-stu-id="173bc-145">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="173bc-146">コンプライアンス センターのセキュリティ &を使用して、ユーザー申請メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="173bc-146">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="173bc-147">セキュリティ 管理コンプライアンス センター&、脅威管理ポリシー \> **の [ユーザー** の申請 \> **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="173bc-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="173bc-148">表示される **[ユーザーの申請]** ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="173bc-148">In the **User submissions** page that appears, select one of the following options:</span></span>

      1. <span data-ttu-id="173bc-149">**Outlook のレポート** メッセージ機能を有効にする (推奨) : レポート メッセージ アドイン、レポート フィッシング アドイン、または Outlook on the web の組み込みレポートを使用する場合は、このオプションを選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="173bc-149">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

    - <span data-ttu-id="173bc-150">**エンド ユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="173bc-150">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="173bc-151">表示される **[確認メッセージのカスタマイズ** ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="173bc-151">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

        - <span data-ttu-id="173bc-152">**提出前**: [**タイトル**] および [確認] メッセージ ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。 </span><span class="sxs-lookup"><span data-stu-id="173bc-152">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="173bc-153">変数 %type% を使用して、申請の種類 (迷惑メール、迷惑メール、フィッシングなど) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="173bc-153">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

            <span data-ttu-id="173bc-154">既に説明した通り、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。</span><span class="sxs-lookup"><span data-stu-id="173bc-154">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="173bc-155">電子メールは分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="173bc-155">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="173bc-156">一部の電子メールには、個人情報または機密情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="173bc-156">Some emails might contain personal or sensitive information.</span></span>

        - <span data-ttu-id="173bc-157">**申請後:**[展開] ![ アイコンをクリックします ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="173bc-157">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="173bc-158">[タイトル **] および** **[確認** ] メッセージ ボックスに、ユーザーがレポート メッセージ アドインまたはレポート フィッシング アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="173bc-158">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="173bc-159">変数 %type% を使用して、申請の種類を含めできます。</span><span class="sxs-lookup"><span data-stu-id="173bc-159">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="173bc-160">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="173bc-160">When you're finished, click **Save**.</span></span> <span data-ttu-id="173bc-161">これらの値をクリアするには、[ユーザー申請] **ページ** の [復元 **] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="173bc-161">To clear these values, click **Restore** back on the **User submissions** page.</span></span>
    
    - <span data-ttu-id="173bc-162">**エンド ユーザーレポートオプションをカスタマイズする**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="173bc-162">**Customize the end-user reporting options**: Click this link.</span></span> <span data-ttu-id="173bc-163">表示される **[エンドユーザーレポート オプションのカスタマイズ]** フライアウトで、[迷惑メールレポートオプション] の説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="173bc-163">In the **Customize end-user reporting options** flyout that appears, enter the descriptive text for Junk email reporting options.</span></span> 
<span data-ttu-id="173bc-164">[ **メッセージの報告時に表示するオプション] で、** 次のオプションの中から少なくとも 1 つを選択します。</span><span class="sxs-lookup"><span data-stu-id="173bc-164">Under **Options to show when messages are reported**, select at least one among the following options:</span></span>
        - <span data-ttu-id="173bc-165">**レポートを送信する前に確認する**</span><span class="sxs-lookup"><span data-stu-id="173bc-165">**Ask me before sending a report**</span></span>
        - <span data-ttu-id="173bc-166">**レポートを自動的に送信する**</span><span class="sxs-lookup"><span data-stu-id="173bc-166">**Automatically send reports**</span></span>
        -  <span data-ttu-id="173bc-167">**レポートを送信しない** </span><span class="sxs-lookup"><span data-stu-id="173bc-167">**Never send reports** </span></span>\
   <span data-ttu-id="173bc-168">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="173bc-168">When you're finished, click **Save**.</span></span>
              - <span data-ttu-id="173bc-169">**報告されたメッセージを送信する**: 次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="173bc-169">**Send the reported messages to**: Make one of the following selections:</span></span>
              - <span data-ttu-id="173bc-170">**Microsoft (推奨)**: ユーザー申請メールボックスが使用されていません (報告されたメッセージはすべて Microsoft に送信されます)。</span><span class="sxs-lookup"><span data-stu-id="173bc-170">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>
              - <span data-ttu-id="173bc-171">**Microsoft とカスタム メールボックスの** 両方 : 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="173bc-171">**Both Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="173bc-172">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="173bc-172">Distribution groups are not allowed.</span></span> <span data-ttu-id="173bc-173">ユーザー申請は、分析のために Microsoft と管理者またはセキュリティ操作チームが分析するカスタム メールボックスの両方に移動します。</span><span class="sxs-lookup"><span data-stu-id="173bc-173">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>
              - <span data-ttu-id="173bc-174">**カスタム メールボックスのみ**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="173bc-174">**Custom mailbox only**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="173bc-175">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="173bc-175">Distribution groups are not allowed.</span></span> <span data-ttu-id="173bc-176">このオプションは、最初に分析のために管理者またはセキュリティ運用チームにのみメッセージを移動する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="173bc-176">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="173bc-177">管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="173bc-177">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="173bc-178">米国政府機関 (GCC、GCC-H、DoD) は、カスタム メールボックスのみを **構成できます**。</span><span class="sxs-lookup"><span data-stu-id="173bc-178">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="173bc-179">他の 2 つのオプションは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="173bc-179">The other two options are disabled.</span></span>

        > [!NOTE]
        > <span data-ttu-id="173bc-180">組織がカスタム メールボックスにのみ送信するように構成されている場合、報告されたメッセージは再スキャンのために送信されません。ユーザーレポートメッセージ ポータルの結果は常に空になります。</span><span class="sxs-lookup"><span data-stu-id="173bc-180">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

      <span data-ttu-id="173bc-181">完了したら、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="173bc-181">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="173bc-182">[Outlook on the](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) Web メールボックス ポリシーを使用して Outlook on the web で迷惑メールレポートを無効にしたが、以前の設定のいずれかを構成して Microsoft にメッセージを報告した場合、ユーザーはレポート メッセージ アドインまたはレポートフィッシング アドインを使用して Outlook on the Web で Microsoft にメッセージを報告できます。</span><span class="sxs-lookup"><span data-stu-id="173bc-182">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>


    1. <span data-ttu-id="173bc-183">**Outlook** のレポート メッセージ機能を無効にする: レポート メッセージ アドイン、レポート フィッシング アドイン、または Outlook on the web の組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="173bc-183">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

          <span data-ttu-id="173bc-184">[この **カスタム メールボックスを使用して、ユーザーが報告した申請を受信する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="173bc-184">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="173bc-185">表示されるボックスに、365 に既に存在する既存のメールボックスの電子メール Officeします。</span><span class="sxs-lookup"><span data-stu-id="173bc-185">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="173bc-186">これは、電子メールを受信できる Exchange Online の既存のメールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="173bc-186">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

          <span data-ttu-id="173bc-187">完了したら、[確認] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="173bc-187">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="173bc-188">メッセージ送信形式</span><span class="sxs-lookup"><span data-stu-id="173bc-188">Message submission format</span></span>

<span data-ttu-id="173bc-189">カスタム メールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="173bc-189">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="173bc-190">申請の件名 (封筒のタイトル) は、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="173bc-190">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="173bc-191">SafetyAPIAction は次のいずれかの整数値です。</span><span class="sxs-lookup"><span data-stu-id="173bc-191">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="173bc-192">1: 迷惑メール</span><span class="sxs-lookup"><span data-stu-id="173bc-192">1: Junk</span></span>
- <span data-ttu-id="173bc-193">2: 迷惑メールではない</span><span class="sxs-lookup"><span data-stu-id="173bc-193">2: Not junk</span></span>
- <span data-ttu-id="173bc-194">3: フィッシング</span><span class="sxs-lookup"><span data-stu-id="173bc-194">3: Phishing</span></span>

<span data-ttu-id="173bc-195">次の例では、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="173bc-195">In the following example:</span></span>

- <span data-ttu-id="173bc-196">メッセージがフィッシングとして報告されています。</span><span class="sxs-lookup"><span data-stu-id="173bc-196">The message is being reported as phishing.</span></span>
- <span data-ttu-id="173bc-197">ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。</span><span class="sxs-lookup"><span data-stu-id="173bc-197">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="173bc-198">Sender IP は 167.220.232.101 です。</span><span class="sxs-lookup"><span data-stu-id="173bc-198">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="173bc-199">From アドレスが test@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="173bc-199">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="173bc-200">メッセージの件名は"フィッシング申請のテスト" です。</span><span class="sxs-lookup"><span data-stu-id="173bc-200">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="173bc-201">この形式に従ってないメッセージは、申請ポータルに正しく表示されません。</span><span class="sxs-lookup"><span data-stu-id="173bc-201">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
