---
title: ユーザー申請ポリシー
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
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
description: 管理者は、ユーザーによって報告されるスパムおよびフィッシングメールを収集するメールボックスを構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9759bbae1dc49b80859198e11e6f85383cdf2f66
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988130"
---
# <a name="user-submissions-policy"></a><span data-ttu-id="807a7-103">ユーザー申請ポリシー</span><span class="sxs-lookup"><span data-stu-id="807a7-103">User submissions policy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="807a7-104">Exchange Online メールボックスを持つ Microsoft 365 組織では、ユーザーが悪意のあるまたは悪意はないと報告するメッセージを受信するメールボックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="807a7-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="807a7-105">ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージを傍受 (カスタム メールボックスにのみ送信) したり、メッセージのコピーを受信 (カスタム メールボックスと Microsoft に送信) することができます。</span><span class="sxs-lookup"><span data-stu-id="807a7-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="807a7-106">この機能は、次のメッセージ報告オプションで動作します。</span><span class="sxs-lookup"><span data-stu-id="807a7-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="807a7-107">レポート メッセージ アドイン</span><span class="sxs-lookup"><span data-stu-id="807a7-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- [<span data-ttu-id="807a7-108">フィッシング報告アドイン</span><span class="sxs-lookup"><span data-stu-id="807a7-108">The Report Phishing add-in</span></span>](enable-the-report-phish-add-in.md)

- <span data-ttu-id="807a7-109">[Outlook on the web の](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) 組み込みレポート (旧称: Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="807a7-109">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="807a7-110">iOS および Android 用の Outlook の組み込みレポート</span><span class="sxs-lookup"><span data-stu-id="807a7-110">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="807a7-111">Outlook on [the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)でレポートが無効になっている場合、ここでユーザーの送信を有効にすると、その設定が上書きされ、ユーザーは Outlook on the web でメッセージを再び報告できます。</span><span class="sxs-lookup"><span data-stu-id="807a7-111">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="807a7-112">指定したメールボックスにメッセージを転送するサード パーティ製のメッセージ報告ツールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="807a7-112">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="807a7-113">ユーザーが報告したメッセージを Microsoft に直接ではなくカスタム メールボックスに配信すると、管理者は管理者の送信を使用してメッセージを選択的および手動で Microsoft に [報告できます](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="807a7-113">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="custom-mailbox-prerequisites"></a><span data-ttu-id="807a7-114">カスタム メールボックスの前提条件</span><span class="sxs-lookup"><span data-stu-id="807a7-114">Custom mailbox prerequisites</span></span>

<span data-ttu-id="807a7-115">次の記事を使用して、ユーザーが報告したメッセージがカスタム メールボックスに移動するために必要な前提条件を構成します。</span><span class="sxs-lookup"><span data-stu-id="807a7-115">Use the following articles to configure the prerequisites required so user reported messages go to your custom mailbox:</span></span>

- <span data-ttu-id="807a7-116">スパム信頼度を設定する Exchange メール フロー ルールを作成して、カスタム メールボックスのスパム フィルター処理をスキップします。</span><span class="sxs-lookup"><span data-stu-id="807a7-116">Skip spam filtering on the custom mailbox by creating an exchange mail flow rule to set the spam confidence level.</span></span> <span data-ttu-id="807a7-117">[「EAC を使用して、SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)を **-1** に設定するメッセージの SCL を設定するメール フロー ルールを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="807a7-117">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) to set the SCL to **-1**.</span></span>

- <span data-ttu-id="807a7-118">カスタム メールボックス内のマルウェアの添付ファイルのスキャンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="807a7-118">Turn off scanning attachments for malware in the custom mailbox.</span></span> <span data-ttu-id="807a7-119">[Office 365](set-up-atp-safe-attachments-policies.md)の Defender で安全な添付ファイルの設定ポリシーを使って、安全な添付ファイルのポリシーを作成し、[安全な添付ファイル] を [安全な添付ファイル] の不明なマルウェア応答に対してオフに **設定します**。</span><span class="sxs-lookup"><span data-stu-id="807a7-119">Use [Set up Safe Attachments policies in Defender for Office 365](set-up-atp-safe-attachments-policies.md) to create a Safe Attachments policy with the setting **Off** for **Safe Attachments unknown malware response**.</span></span>

- <span data-ttu-id="807a7-120">カスタム メールボックス内のメッセージの URL スキャンを無効にします。</span><span class="sxs-lookup"><span data-stu-id="807a7-120">Turn off URL scanning on messages in the custom mailbox.</span></span> <span data-ttu-id="807a7-121">[Office 365](set-up-atp-safe-links-policies.md)の Defender で安全なリンクポリシーの設定を使用して、メッセージ内の悪意のある可能性のある不明な URL に対するアクションをオフに設定して安全なリンク ポリシーを作成 **します**。</span><span class="sxs-lookup"><span data-stu-id="807a7-121">Use [Set up Safe Links policies in Defender for Office 365](set-up-atp-safe-links-policies.md) to create a Safe Links policy with the setting **Off** for **Select the action for unknown potentially malicious URLs in messages**.</span></span>

- <span data-ttu-id="807a7-122">マルウェア対策ポリシーを作成して、マルウェアゼロアワー自動消去を無効にします。</span><span class="sxs-lookup"><span data-stu-id="807a7-122">Create an anti-malware policy to turn off Malware Zero-hour Auto Purge.</span></span> <span data-ttu-id="807a7-123">「 [セキュリティ/コンプライアンス センター&](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) 使用してマルウェア対策ポリシーを作成し、マルウェアゼロアワー **自動** 消去をオフに設定する」を **参照してください**。</span><span class="sxs-lookup"><span data-stu-id="807a7-123">See [Use the Security & Compliance Center to create anti-malware policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) to set **Malware Zero-hour Auto Purge** to **Off**.</span></span>

- <span data-ttu-id="807a7-124">スパム フィルター ポリシーを作成して、カスタム メールボックスでスパムとフィッシングのゼロアワー自動消去 (ZAP) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="807a7-124">Create a spam filter policy to disable zero-hour auto purge (ZAP) for spam and phishing in the custom mailbox.</span></span> <span data-ttu-id="807a7-125">「Security [& Compliance Center](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies)を使用してスパム対策ポリシーを作成し、スパム ZAP とフィッシング **ZAP** の **オン** チェック ボックスをオフにする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="807a7-125">See [Use the Security & Compliance Center to create anti-spam policies](configure-your-spam-filter-policies.md#use-the-security--compliance-center-to-create-anti-spam-policies) and clear the **On** checkboxes for **Spam ZAP** and **Phish ZAP**.</span></span>

- <span data-ttu-id="807a7-126">カスタム メールボックスの迷惑メール ルールを無効にします。</span><span class="sxs-lookup"><span data-stu-id="807a7-126">Disable the junk email rule in the custom mailbox.</span></span> <span data-ttu-id="807a7-127">[迷惑メール ルールを無効にするには、Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md)メールボックスで迷惑メール設定を構成するを使用します。</span><span class="sxs-lookup"><span data-stu-id="807a7-127">Use [Configure junk email settings on Exchange Online mailboxes](configure-junk-email-settings-on-exo-mailboxes.md) to disable the junk email rule.</span></span> <span data-ttu-id="807a7-128">無効にすると、EOP はスパム フィルターの条件アクションに基づいてメッセージを [迷惑メール] フォルダーに移動できません。メッセージを [迷惑メール] フォルダーまたはメールボックスのセーフリスト コレクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="807a7-128">Once disabled, EOP can't move messages to the Junk Email folder based on the spam filtering verdict action **Move message to Junk Email folder** or the safelist collection on the mailbox.</span></span>

<span data-ttu-id="807a7-129">メールボックスが該当する前提条件を満たしていることを確認した後、セキュリティ [&](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) コンプライアンス センターを使用してユーザー送信メールボックスを構成します (この記事内)。</span><span class="sxs-lookup"><span data-stu-id="807a7-129">After you've verified that your mailbox meets all applicable prerequisites, [Use the Security & Compliance Center to configure the user submissions mailbox](#use-the-security--compliance-center-to-configure-the-user-submissions-mailbox) (in this article).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="807a7-130">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="807a7-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="807a7-131"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="807a7-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="807a7-132">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="807a7-132">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="807a7-133">ユーザーの提出の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="807a7-133">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="807a7-134">**組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="807a7-134">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="807a7-135">Exchange Online **での**[組織の管理](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)。</span><span class="sxs-lookup"><span data-stu-id="807a7-135">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="807a7-136">Exchange Online PowerShell にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="807a7-136">You need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="807a7-137">使用しようとしているアカウントが Exchange Online PowerShell にアクセスできない場合、送信メールボックスを指定すると、次のようなエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="807a7-137">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that looks like this when specify the submissions mailbox:</span></span>

  > <span data-ttu-id="807a7-138">ドメイン内のメール アドレスを指定する</span><span class="sxs-lookup"><span data-stu-id="807a7-138">Specify an email address in your domain</span></span>

  <span data-ttu-id="807a7-139">Exchange Online PowerShell へのアクセスを有効または無効にする方法の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="807a7-139">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>

  - [<span data-ttu-id="807a7-140">Exchange Online PowerShell へのアクセスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="807a7-140">Enable or disable access to Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [<span data-ttu-id="807a7-141">Exchange Online のクライアント アクセス規則</span><span class="sxs-lookup"><span data-stu-id="807a7-141">Client Access Rules in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="807a7-142">セキュリティ/コンプライアンス センター&使用して、ユーザーの送信メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="807a7-142">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="807a7-143">セキュリティ/コンプライアンス センター&、脅威 **管理ポリシーのユーザー提出に** \>  \> **移動します**。</span><span class="sxs-lookup"><span data-stu-id="807a7-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="807a7-144">表示される **[ユーザーの提出** ] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="807a7-144">In the **User submissions** page that appears, select one of the following options:</span></span>

   1. <span data-ttu-id="807a7-145">**Outlook** のレポート メッセージ機能を有効にする (推奨) : Outlook on the web でレポート メッセージ アドイン、Report Phishing アドイン、または組み込みのレポートを使用する場合は、このオプションを選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="807a7-145">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="807a7-146">**エンド ユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="807a7-146">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="807a7-147">表示される **[確認メッセージの** カスタマイズ] フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="807a7-147">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="807a7-148">**Before submission**: In the **Title** and Confirmation message boxes, enter the **descriptive** text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span><span class="sxs-lookup"><span data-stu-id="807a7-148">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="807a7-149">変数 %type% を使用して、提出の種類 (迷惑メール、迷惑メール、フィッシングなど) を含めできます。</span><span class="sxs-lookup"><span data-stu-id="807a7-149">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="807a7-150">既に説明した通り、報告されたメッセージを Microsoft に送信するオプションを選択すると、次のテキストも通知に追加されます。</span><span class="sxs-lookup"><span data-stu-id="807a7-150">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="807a7-151">電子メールは分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="807a7-151">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="807a7-152">一部のメールには、個人情報や機密情報が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="807a7-152">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="807a7-153">**After submission**: Click ![ Expand icon ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="807a7-153">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="807a7-154">[タイトル **]** **および** [確認] メッセージ ボックスに、レポート メッセージ アドインまたは Report Phishing アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="807a7-154">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in or the Report Phishing add-in.</span></span> <span data-ttu-id="807a7-155">提出の種類を含めるには、変数 %type% を使用できます。</span><span class="sxs-lookup"><span data-stu-id="807a7-155">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="807a7-156">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="807a7-156">When you're finished, click **Save**.</span></span> <span data-ttu-id="807a7-157">これらの値をクリアするには、[ **ユーザー** の提出] ページで [元 **に戻す] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="807a7-157">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="807a7-158">**報告されたメッセージの送信先**: 次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="807a7-158">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="807a7-159">**Microsoft (推奨)**: ユーザー送信メールボックスは使用されません (報告されたメッセージはすべて Microsoft に送信されます)。</span><span class="sxs-lookup"><span data-stu-id="807a7-159">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="807a7-160">**Microsoft とカスタム メールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="807a7-160">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="807a7-161">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="807a7-161">Distribution groups are not allowed.</span></span> <span data-ttu-id="807a7-162">ユーザーの送信は、分析のために Microsoft に送信され、管理者またはセキュリティ運用チームが分析するカスタム メールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="807a7-162">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="807a7-163">**カスタム メールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="807a7-163">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="807a7-164">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="807a7-164">Distribution groups are not allowed.</span></span> <span data-ttu-id="807a7-165">このオプションは、最初に分析のために管理者またはセキュリティ運用チームにのみメッセージを送信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="807a7-165">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="807a7-166">管理者が自分で転送しない限り、メッセージは Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="807a7-166">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="807a7-167">米国政府機関 (GCC、GCC-H、DoD) は、カスタム メールボックスのみを **構成できます**。</span><span class="sxs-lookup"><span data-stu-id="807a7-167">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="807a7-168">他の 2 つのオプションは無効です。</span><span class="sxs-lookup"><span data-stu-id="807a7-168">The other two options are disabled.</span></span>

      <span data-ttu-id="807a7-169">完了したら、[確認] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="807a7-169">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="807a7-170">Outlook on the web メールボックス ポリシーを使用して [Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) で迷惑メール報告を無効にしているが、Microsoft にメッセージを報告する前の設定のいずれかを構成した場合、ユーザーはレポート メッセージ アドインまたは Report Phishing アドインを使用して Outlook on the web の Microsoft にメッセージを報告できます。</span><span class="sxs-lookup"><span data-stu-id="807a7-170">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in or the Report Phishing add-in.</span></span>

   - <span data-ttu-id="807a7-171">**Outlook** の [メッセージの報告] 機能を無効にする: このオプションは、Outlook on the web のレポート メッセージ アドイン、フィッシング報告アドイン、または組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合に選択し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="807a7-171">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in, the Report Phishing add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="807a7-172">[この **カスタム メールボックスを使用して、報告されたユーザーの提出を受信する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="807a7-172">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="807a7-173">表示されるボックスに、既存のメールボックスの電子メール アドレスを入力します。このメール アドレスは、既に Office 365 に存在します。</span><span class="sxs-lookup"><span data-stu-id="807a7-173">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="807a7-174">これは、電子メールを受信できる Exchange Online の既存のメールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="807a7-174">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="807a7-175">完了したら、[確認] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="807a7-175">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="807a7-176">メッセージ送信形式</span><span class="sxs-lookup"><span data-stu-id="807a7-176">Message submission format</span></span>

<span data-ttu-id="807a7-177">カスタム メールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="807a7-177">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="807a7-178">提出の件名 (封筒のタイトル) は、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="807a7-178">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="807a7-179">SafetyAPIAction は、次のいずれかの整数値です。</span><span class="sxs-lookup"><span data-stu-id="807a7-179">where SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="807a7-180">1: 迷惑メール</span><span class="sxs-lookup"><span data-stu-id="807a7-180">1: Junk</span></span>
- <span data-ttu-id="807a7-181">2: 迷惑メールではない</span><span class="sxs-lookup"><span data-stu-id="807a7-181">2: Not junk</span></span>
- <span data-ttu-id="807a7-182">3: フィッシング</span><span class="sxs-lookup"><span data-stu-id="807a7-182">3: Phishing</span></span>

<span data-ttu-id="807a7-183">次の例では、</span><span class="sxs-lookup"><span data-stu-id="807a7-183">In the following example:</span></span>

- <span data-ttu-id="807a7-184">メッセージがフィッシングとして報告されています。</span><span class="sxs-lookup"><span data-stu-id="807a7-184">The message is being reported as phishing.</span></span>
- <span data-ttu-id="807a7-185">ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。</span><span class="sxs-lookup"><span data-stu-id="807a7-185">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="807a7-186">Sender IP は 167.220.232.101 です。</span><span class="sxs-lookup"><span data-stu-id="807a7-186">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="807a7-187">From アドレスがtest@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="807a7-187">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="807a7-188">メッセージの件名は「フィッシングの送信のテスト」です。</span><span class="sxs-lookup"><span data-stu-id="807a7-188">The message's subject line is "test phishing submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phishing submission)`

<span data-ttu-id="807a7-189">この形式に従ってないメッセージは、提出ポータルに正しく表示されません。</span><span class="sxs-lookup"><span data-stu-id="807a7-189">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
