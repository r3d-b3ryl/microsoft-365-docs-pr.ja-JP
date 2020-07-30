---
title: ユーザーがスパムおよびフィッシングメッセージを送信するためのメールボックスを指定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、ユーザーによって報告されたスパムやフィッシング電子メールを収集するようにメールボックスを構成する方法について説明します。
ms.openlocfilehash: 0be1a4efa04d3e7a7968880b2a1cca108fdd34f9
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503093"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="871c5-103">Exchange Online でスパムおよびフィッシングメッセージをユーザーが送信するためのメールボックスを指定する</span><span class="sxs-lookup"><span data-stu-id="871c5-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="871c5-104">Exchange Online メールボックスを使用している Microsoft 365 組織では、ユーザーが悪意のあるメールや悪意のないメッセージを受信するメールボックスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="871c5-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="871c5-105">ユーザーがさまざまなレポートオプションを使用してメッセージを送信する場合、このメールボックスを使用して、メッセージを傍受する (カスタムメールボックスにのみ送信する) か、メッセージのコピーを受信する (カスタムメールボックスおよび Microsoft に送信) ことができます。</span><span class="sxs-lookup"><span data-stu-id="871c5-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="871c5-106">この機能は、次のメッセージレポートオプションで機能します。</span><span class="sxs-lookup"><span data-stu-id="871c5-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="871c5-107">レポートメッセージアドイン</span><span class="sxs-lookup"><span data-stu-id="871c5-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="871c5-108">[Web 上の outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (旧称 Outlook web App) での組み込みレポート</span><span class="sxs-lookup"><span data-stu-id="871c5-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="871c5-109">IOS および Android 用の Outlook の組み込みレポート</span><span class="sxs-lookup"><span data-stu-id="871c5-109">Built-in reporting in Outlook for iOS and Android</span></span>

  > [!NOTE]
  > <span data-ttu-id="871c5-110">[Web 上の outlook で](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)レポートが無効になっている場合、ここでユーザーによる送信を有効にすると、その設定が無効になり、ユーザーは web 上の outlook でメッセージを再度レポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="871c5-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="871c5-111">また、指定したメールボックスにメッセージを転送するように、サードパーティ製のメッセージレポートツールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="871c5-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="871c5-112">ユーザーが報告したメッセージを Microsoft に直接送信する代わりにカスタムメールボックスに配信することにより、管理者は、[管理者送信](admin-submission.md)を使用してメッセージを選択的に、手動で microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="871c5-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="871c5-113">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="871c5-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="871c5-114"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="871c5-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="871c5-115">[**ユーザーの送信**] ページに直接移動するには、を使用 <https://protection.office.com/userSubmissionsReportMessage> します。</span><span class="sxs-lookup"><span data-stu-id="871c5-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="871c5-116">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="871c5-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="871c5-117">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="871c5-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="871c5-118">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="871c5-118">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="871c5-119">ユーザー送信の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="871c5-119">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="871c5-120">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="871c5-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="871c5-121">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="871c5-121">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="871c5-122">ユーザーの送信に対して読み取り専用アクセスを行うには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="871c5-122">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="871c5-123">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="871c5-123">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="871c5-124">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="871c5-124">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="871c5-125">セキュリティ & コンプライアンスセンターを使用してユーザー送信メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="871c5-125">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="871c5-126">[セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのユーザーの送信] に移動 \> **Policy** \> **User submissions**します。</span><span class="sxs-lookup"><span data-stu-id="871c5-126">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="871c5-127">表示される [**ユーザーの送信**] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="871c5-127">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="871c5-128">a.</span><span class="sxs-lookup"><span data-stu-id="871c5-128">a.</span></span> <span data-ttu-id="871c5-129">**Outlook のレポートメッセージ機能を有効にする (推奨)**: レポートメッセージアドインまたは outlook on the web の組み込みのレポートを使用して、次の設定を構成する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="871c5-129">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="871c5-130">**エンドユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="871c5-130">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="871c5-131">[**確認メッセージのカスタマイズ**] ポップアップが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="871c5-131">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="871c5-132">**提出前**:**タイトル**と確認の**メッセージ**ボックスに、レポートメッセージアドインを使用してメッセージを報告する前にユーザーに表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="871c5-132">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="871c5-133">変数% 型% を使用して、送信の種類 (迷惑メール、迷惑メールではない、フィッシングなど) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="871c5-133">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="871c5-134">前述したように、報告されたメッセージを Microsoft に送信するオプションを選択すると、通知に次のテキストも追加されます。</span><span class="sxs-lookup"><span data-stu-id="871c5-134">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="871c5-135">電子メールは、のように、分析のために Microsoft に提出されます。</span><span class="sxs-lookup"><span data-stu-id="871c5-135">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="871c5-136">メールによっては個人情報や機密情報が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="871c5-136">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="871c5-137">**送信後**: [ ![ 展開] アイコンをクリックし ](../../media/scc-expand-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="871c5-137">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="871c5-138">[**タイトル**] および [**確認メッセージ**] ボックスに、レポートメッセージアドインを使用してメッセージを報告した後にユーザーに表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="871c5-138">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="871c5-139">変数% 型% を使用して、提出の種類を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="871c5-139">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="871c5-140">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="871c5-140">When you're finished, click **Save**.</span></span> <span data-ttu-id="871c5-141">これらの値をクリアするには、[**ユーザーの送信**] ページの [元に**戻す**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="871c5-141">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="871c5-142">**報告されたメッセージの送信先**: 次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="871c5-142">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="871c5-143">**Microsoft (推奨)**: ユーザーの送信メールボックスが使用されていません (報告されたすべてのメッセージが Microsoft に送られます)。</span><span class="sxs-lookup"><span data-stu-id="871c5-143">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="871c5-144">**Microsoft およびカスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="871c5-144">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="871c5-145">配布グループは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="871c5-145">Distribution groups are not allowed.</span></span> <span data-ttu-id="871c5-146">ユーザーによる送信は、分析のために Microsoft と Microsoft の両方に、管理者またはセキュリティ運用チームのためのカスタムメールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="871c5-146">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="871c5-147">**カスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="871c5-147">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="871c5-148">配布グループは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="871c5-148">Distribution groups are not allowed.</span></span> <span data-ttu-id="871c5-149">このオプションを使用するのは、最初に分析のために管理者またはセキュリティ操作チームのみにメッセージを移動する場合です。</span><span class="sxs-lookup"><span data-stu-id="871c5-149">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="871c5-150">管理者が自分を転送しない限り、メッセージは Microsoft には送られません。</span><span class="sxs-lookup"><span data-stu-id="871c5-150">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="871c5-151">米国政府機関 (GCC、GCC、.H、DoD) は、**カスタムメールボックス**のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="871c5-151">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="871c5-152">他の2つのオプションは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="871c5-152">The other two options are disabled.</span></span> 

      <span data-ttu-id="871c5-153">完了したら、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="871c5-153">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="871c5-154">Web 上の outlook on the web メールボックスポリシーを使用して outlook の[迷惑メール報告を無効](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)にしたが、microsoft にメッセージを報告するために以前の設定のいずれかを構成した場合、ユーザーはレポートメッセージアドインを使用して、web 上の outlook でメッセージを microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="871c5-154">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="871c5-155">**Outlook のレポートメッセージ機能を無効に**する: レポートメッセージアドインまたは web 上の Outlook の組み込みレポートではなくサードパーティのレポートツールを使用し、次の設定を構成する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="871c5-155">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="871c5-156">[**このカスタムメールボックスを使用して、ユーザーが報告した送信を受信する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="871c5-156">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="871c5-157">表示されるボックスに、Office 365 に既に存在する既存のメールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="871c5-157">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="871c5-158">これは、電子メールを受信できる Exchange Online の既存のメールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="871c5-158">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="871c5-159">完了したら、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="871c5-159">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="871c5-160">メッセージ送信形式</span><span class="sxs-lookup"><span data-stu-id="871c5-160">Message submission format</span></span>

<span data-ttu-id="871c5-161">カスタムメールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="871c5-161">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="871c5-162">提出物の件名 (封筒のタイトル) は、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="871c5-162">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="871c5-163">"Saf Etyapiaction" は、次のいずれかの整数型 (integer) の値です。</span><span class="sxs-lookup"><span data-stu-id="871c5-163">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="871c5-164">1: 迷惑メール</span><span class="sxs-lookup"><span data-stu-id="871c5-164">1: Junk</span></span>
- <span data-ttu-id="871c5-165">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="871c5-165">2: NotJunk</span></span>
- <span data-ttu-id="871c5-166">3: フィッシング</span><span class="sxs-lookup"><span data-stu-id="871c5-166">3: Phish</span></span>

<span data-ttu-id="871c5-167">次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="871c5-167">In the following example:</span></span>

- <span data-ttu-id="871c5-168">メッセージはフィッシングとして報告されています。</span><span class="sxs-lookup"><span data-stu-id="871c5-168">The message is being reported as Phish.</span></span>
- <span data-ttu-id="871c5-169">ネットワークメッセージ ID は49871234-6dc6-43e8-abcd-08d797f20abe です。</span><span class="sxs-lookup"><span data-stu-id="871c5-169">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="871c5-170">送信者の IP は167.220.232.101 です。</span><span class="sxs-lookup"><span data-stu-id="871c5-170">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="871c5-171">From アドレスは test@contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="871c5-171">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="871c5-172">メッセージの件名行は "test フィッシング提出" です。</span><span class="sxs-lookup"><span data-stu-id="871c5-172">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="871c5-173">この形式に従っていないメッセージは、送信ポータルで適切に表示されません。</span><span class="sxs-lookup"><span data-stu-id="871c5-173">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
