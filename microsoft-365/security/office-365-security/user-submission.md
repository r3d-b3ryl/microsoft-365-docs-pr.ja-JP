---
title: スパムおよびフィッシング メッセージのユーザー送信用のメールボックスを指定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、ユーザーによって報告されるスパム メールやフィッシング メールを収集するように、メールボックスを構成する方法について学習できます。
ms.openlocfilehash: 76264801820b6a41ee744a8adcc3b3b48a8e9479
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826743"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="f43bd-103">Exchange Online でスパムやフィッシング メッセージのユーザーを送信するためのメールボックスを指定する</span><span class="sxs-lookup"><span data-stu-id="f43bd-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="f43bd-104">Exchange Online メールボックスを使用している Microsoft 365 組織では、ユーザーが悪意のあるとして報告を受けたり、悪意のあるものでないと報告するメッセージを受信するメールボックスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="f43bd-105">ユーザーがさまざまなレポート オプションを使用してメッセージを送信する場合、このメールボックスを使用してメッセージをインターセプト (カスタム メールボックスのみに送信する) か、またはメッセージのコピーを受信 (カスタム メールボックスおよび Microsoft に送信する) ことができます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="f43bd-106">この機能は次のメッセージ報告オプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="f43bd-107">レポート メッセージ アドイン</span><span class="sxs-lookup"><span data-stu-id="f43bd-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="f43bd-108">[Outlook on the web (前の名)](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) の組み込みのレポートOutlook Web App)</span><span class="sxs-lookup"><span data-stu-id="f43bd-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="f43bd-109">iOS および Android 用の Outlook の組み込みレポート</span><span class="sxs-lookup"><span data-stu-id="f43bd-109">Built-in reporting in Outlook for iOS and Android</span></span>

  > [!NOTE]
  > <span data-ttu-id="f43bd-110">Outlook on the web でレポート [機能が無効になっている場合](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)、ユーザーの送信を有効にすると、その設定が無効になり、ユーザーは Web 上の Outlook でメッセージを再びレポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="f43bd-111">指定したメールボックスにメッセージを転送する、サード パーティのメッセージ レポート ツールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="f43bd-112">ユーザーから報告されたメッセージを直接 Microsoft に送信するのではなく、カスタムのメールボックスに送信すると、管理者は管理者の申請を使用して、管理者が選択的に Microsoft にメッセージを [報告することができます](admin-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="f43bd-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f43bd-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="f43bd-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f43bd-114"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f43bd-115">ユーザーの申請ページに **直接進むには、** 次のコマンドを使用します <https://protection.office.com/userSubmissionsReportMessage> 。</span><span class="sxs-lookup"><span data-stu-id="f43bd-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="f43bd-116">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-116">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f43bd-117">ユーザーの送信の構成を変更するには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f43bd-118">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f43bd-119">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f43bd-120">ユーザーの送信に対する読み取り専用アクセスを行う場合は、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-120">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f43bd-121">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-121">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f43bd-122">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-122">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="f43bd-123">セキュリティ コンプライアンス センター &を使用してユーザー送信メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="f43bd-123">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="f43bd-124">セキュリティ コンプライアンス センター&で、[脅威管理 **ポリシー ユーザー** \> **による** \> **送信] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="f43bd-125">表示される **[ユーザーの提出** ] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-125">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="f43bd-126">a.</span><span class="sxs-lookup"><span data-stu-id="f43bd-126">a.</span></span> <span data-ttu-id="f43bd-127">**Outlook でメッセージ報告機能を有効にする (推奨)**: 迷惑メール報告アドインまたは Outlook on the web の組み込みのレポートを使用する場合は、このオプションを選択してから、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-127">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="f43bd-128">**エンド ユーザー確認メッセージをカスタマイズします**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f43bd-128">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="f43bd-129">表示される **確認メッセージのポ** ップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-129">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="f43bd-130">**送信前**: タイトルと **確認** メッセージ **ボックスに** 、ユーザーがレポート メッセージ アドインを使用してメッセージを報告する前に表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-130">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="f43bd-131">変数 %type% を使用して、提出の種類 (迷惑メール、迷惑メール以外、フィッシングなど) を含めることが可能です。</span><span class="sxs-lookup"><span data-stu-id="f43bd-131">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="f43bd-132">既に説明したとおり、報告されたメッセージを Microsoft に送信するオプションを選択した場合、次のテキストも通知に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-132">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="f43bd-133">メールは、分析のためにその情報をそのものとして Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-133">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="f43bd-134">個人または機密情報が含まれているメールの中には、一部のメールが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-134">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="f43bd-135">**提出後**: 展開 ![ アイコンをクリックします ](../../media/scc-expand-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="f43bd-135">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="f43bd-136">[タイトル **]** および **[確認] メッセージ ボックスに** 、ユーザーが報告メッセージ アドインを使用してメッセージを報告した後に表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-136">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="f43bd-137">変数 %type% を使用して、提出の種類を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-137">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="f43bd-138">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f43bd-138">When you're finished, click **Save**.</span></span> <span data-ttu-id="f43bd-139">これらの値をクリアするには、[ **ユーザーの申請** を戻 **す] ページの [戻る] をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-139">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="f43bd-140">**報告されたメッセージの送信**: 次のいずれかを選択します:</span><span class="sxs-lookup"><span data-stu-id="f43bd-140">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="f43bd-141">**Microsoft (推奨)**: ユーザー送信メールボックスは使用されません (報告されたすべてのメッセージは Microsoft に送信されます)。</span><span class="sxs-lookup"><span data-stu-id="f43bd-141">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="f43bd-142">**Microsoft とカスタム メールボックス**: 表示されるボックスに既存の Exchange Online メールボックスのメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-142">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="f43bd-143">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="f43bd-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="f43bd-144">ユーザーの送信は、分析のため Microsoft と、管理者またはセキュリティ運用チームのカスタム メールボックスの両方に移動して分析します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-144">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="f43bd-145">**カスタム メールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-145">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="f43bd-146">配布グループは許可されません。</span><span class="sxs-lookup"><span data-stu-id="f43bd-146">Distribution groups are not allowed.</span></span> <span data-ttu-id="f43bd-147">このオプションは、最初に分析を目的として、メッセージを管理者またはセキュリティ運用チームにのみ送信する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-147">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="f43bd-148">管理者がユーザーを転送しない限り、メッセージは Microsoft には送信されません。</span><span class="sxs-lookup"><span data-stu-id="f43bd-148">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f43bd-149">米国政府機関 (GCC、GCC-H、DoD) は、カスタム メールボックスのみを **構成できます**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-149">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="f43bd-150">その他の 2 つのオプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-150">The other two options are disabled.</span></span> 

      <span data-ttu-id="f43bd-151">完了したら、[確認] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-151">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="f43bd-152">Web 上の [Outlook のメールボックス ポリシーを使用して Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) 上の Outlook で迷惑メール レポート機能を無効にしているが、メッセージを Microsoft に報告するために以前のいずれかの設定を構成した場合、ユーザーはメッセージ報告アドインを使用して、Outlook on the web でメッセージを Microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="f43bd-152">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="f43bd-153">**Outlook のメッセージ報告機能を無効にします。レポート**メッセージ アドインまたは Outlook on the web の組み込みレポートの代わりにサード パーティ製のレポート ツールを使用する場合は、このオプションを選択してから、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-153">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="f43bd-154">[ **このカスタム メールボックスを使用して、ユーザーの報告された送信を受信する] を選きます**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-154">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="f43bd-155">表示されるボックスに、既に存在するメール アドレスのメール アドレスを Officeします。</span><span class="sxs-lookup"><span data-stu-id="f43bd-155">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="f43bd-156">これは、電子メールを受信できる、Exchange Online の既存のメールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-156">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="f43bd-157">完了したら、[確認] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="f43bd-157">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="f43bd-158">メッセージ送信の形式</span><span class="sxs-lookup"><span data-stu-id="f43bd-158">Message submission format</span></span>

<span data-ttu-id="f43bd-159">カスタム メールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-159">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="f43bd-160">申請のサブジェクト (エンベロープ タイトル) は次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f43bd-160">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="f43bd-161">SafetyAPIAction は、次のいずれかの整数値です。</span><span class="sxs-lookup"><span data-stu-id="f43bd-161">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="f43bd-162">1: 迷惑メール</span><span class="sxs-lookup"><span data-stu-id="f43bd-162">1: Junk</span></span>
- <span data-ttu-id="f43bd-163">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="f43bd-163">2: NotJunk</span></span>
- <span data-ttu-id="f43bd-164">3: フィッシング</span><span class="sxs-lookup"><span data-stu-id="f43bd-164">3: Phish</span></span>

<span data-ttu-id="f43bd-165">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f43bd-165">In the following example:</span></span>

- <span data-ttu-id="f43bd-166">メッセージはフィッシングとして報告されています。</span><span class="sxs-lookup"><span data-stu-id="f43bd-166">The message is being reported as Phish.</span></span>
- <span data-ttu-id="f43bd-167">ネットワーク メッセージ ID は 49871234-6dc6-43e8-abcd-08d797f20abe です。</span><span class="sxs-lookup"><span data-stu-id="f43bd-167">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="f43bd-168">送信者の IP は、167.220.232.101 です。</span><span class="sxs-lookup"><span data-stu-id="f43bd-168">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="f43bd-169">送信元アドレスはtest@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="f43bd-169">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="f43bd-170">メッセージの件名が「フィッシングのテスト」である</span><span class="sxs-lookup"><span data-stu-id="f43bd-170">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="f43bd-171">この形式に従っていないメッセージは、申請ポータルに正しく表示されません。</span><span class="sxs-lookup"><span data-stu-id="f43bd-171">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
