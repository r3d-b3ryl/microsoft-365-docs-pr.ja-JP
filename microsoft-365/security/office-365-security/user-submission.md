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
ms.openlocfilehash: 0f3c7f160e26b8befcbbe8096c07e9eb6fecb533
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613434"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="1fdf8-103">Exchange Online でスパムおよびフィッシングメッセージをユーザーが送信するためのメールボックスを指定する</span><span class="sxs-lookup"><span data-stu-id="1fdf8-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="1fdf8-104">Exchange Online メールボックスを使用している Microsoft 365 組織では、ユーザーが悪意のあるメールや悪意のないメッセージを受信するメールボックスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="1fdf8-105">ユーザーがさまざまなレポートオプションを使用してメッセージを送信する場合、このメールボックスを使用して、メッセージを傍受する (カスタムメールボックスにのみ送信する) か、メッセージのコピーを受信する (カスタムメールボックスおよび Microsoft に送信) ことができます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="1fdf8-106">この機能は、次のメッセージレポートオプションで機能します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="1fdf8-107">レポートメッセージアドイン</span><span class="sxs-lookup"><span data-stu-id="1fdf8-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="1fdf8-108">[Web 上の outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (旧称 Outlook web App) での組み込みレポート</span><span class="sxs-lookup"><span data-stu-id="1fdf8-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="1fdf8-109">[Web 上の outlook で](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)レポートが無効になっている場合、ここでユーザーによる送信を有効にすると、その設定が無効になり、ユーザーは web 上の outlook でメッセージを再度レポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="1fdf8-110">また、指定したメールボックスにメッセージを転送するように、サードパーティ製のメッセージレポートツールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="1fdf8-111">ユーザーが報告したメッセージを Microsoft に直接送信する代わりにカスタムメールボックスに配信することにより、管理者は、[管理者送信](admin-submission.md)を使用してメッセージを選択的に、手動で microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1fdf8-112">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="1fdf8-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1fdf8-113"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1fdf8-114">[**ユーザーの送信**] ページに直接移動するには、を使用 <https://protection.office.com/userSubmissionsReportMessage> します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="1fdf8-115">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1fdf8-116">スタンドアロンの EOP PowerShell に接続するには、「 [Exchange Online Protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1fdf8-117">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="1fdf8-118">ユーザーが送信するメールボックスを構成するには、**組織の管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1fdf8-119">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="1fdf8-120">セキュリティ & コンプライアンスセンターを使用してユーザー送信メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="1fdf8-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="1fdf8-121">[セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのユーザーの送信] に移動 \> **Policy** \> **User submissions**します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="1fdf8-122">表示される [**ユーザーの送信**] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="1fdf8-123">a.</span><span class="sxs-lookup"><span data-stu-id="1fdf8-123">a.</span></span> <span data-ttu-id="1fdf8-124">**Outlook のレポートメッセージ機能を有効にする (推奨)**: レポートメッセージアドインまたは outlook on the web の組み込みのレポートを使用して、次の設定を構成する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-124">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="1fdf8-125">**エンドユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-125">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="1fdf8-126">[**確認メッセージのカスタマイズ**] ポップアップが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-126">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="1fdf8-127">**提出前**:**タイトル**と確認の**メッセージ**ボックスに、レポートメッセージアドインを使用してメッセージを報告する前にユーザーに表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-127">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="1fdf8-128">変数% 型% を使用して、送信の種類 (迷惑メール、迷惑メールではない、フィッシングなど) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-128">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="1fdf8-129">前述したように、報告されたメッセージを Microsoft に送信するオプションを選択すると、通知に次のテキストも追加されます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-129">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="1fdf8-130">電子メールは、のように、分析のために Microsoft に提出されます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-130">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="1fdf8-131">メールによっては個人情報や機密情報が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-131">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="1fdf8-132">**送信後**: [ ![ 展開] アイコンをクリックし ](../../media/scc-expand-icon.png) ます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-132">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="1fdf8-133">[**タイトル**] および [**確認メッセージ**] ボックスに、レポートメッセージアドインを使用してメッセージを報告した後にユーザーに表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-133">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="1fdf8-134">変数% 型% を使用して、提出の種類を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-134">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="1fdf8-135">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-135">When you're finished, click **Save**.</span></span> <span data-ttu-id="1fdf8-136">これらの値をクリアするには、[**ユーザーの送信**] ページの [元に**戻す**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-136">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="1fdf8-137">**報告されたメッセージの送信先**: 次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-137">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="1fdf8-138">**Microsoft (推奨)**: ユーザーの送信メールボックスが使用されていません (報告されたすべてのメッセージが Microsoft に送られます)。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-138">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="1fdf8-139">**Microsoft およびカスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-139">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="1fdf8-140">配布グループは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-140">Distribution groups are not allowed.</span></span> <span data-ttu-id="1fdf8-141">ユーザーによる送信は、分析のために Microsoft と Microsoft の両方に、管理者またはセキュリティ運用チームのためのカスタムメールボックスに移動します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-141">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="1fdf8-142">**カスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-142">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="1fdf8-143">配布グループは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="1fdf8-144">このオプションを使用するのは、最初に分析のために管理者またはセキュリティ操作チームのみにメッセージを移動する場合です。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-144">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="1fdf8-145">管理者が自分を転送しない限り、メッセージは Microsoft には送られません。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-145">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="1fdf8-146">米国政府機関 (GCC、GCC、.H、DoD) は、**カスタムメールボックス**のみを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-146">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="1fdf8-147">他の2つのオプションは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-147">The other two options are disabled.</span></span> 

      <span data-ttu-id="1fdf8-148">完了したら、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-148">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="1fdf8-149">Web 上の outlook on the web メールボックスポリシーを使用して outlook の[迷惑メール報告を無効](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)にしたが、microsoft にメッセージを報告するために以前の設定のいずれかを構成した場合、ユーザーはレポートメッセージアドインを使用して、web 上の outlook でメッセージを microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-149">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="1fdf8-150">**Outlook のレポートメッセージ機能を無効に**する: レポートメッセージアドインまたは web 上の Outlook の組み込みレポートではなくサードパーティのレポートツールを使用し、次の設定を構成する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-150">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="1fdf8-151">[**このカスタムメールボックスを使用して、ユーザーが報告した送信を受信する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-151">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="1fdf8-152">表示されるボックスに、Office 365 に既に存在する既存のメールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-152">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="1fdf8-153">これは、電子メールを受信できる Exchange Online の既存のメールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-153">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="1fdf8-154">完了したら、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-154">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="1fdf8-155">メッセージ送信形式</span><span class="sxs-lookup"><span data-stu-id="1fdf8-155">Message submission format</span></span>

<span data-ttu-id="1fdf8-156">カスタムメールボックスに送信されるメッセージは、特定の送信メール形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-156">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="1fdf8-157">提出物の件名 (封筒のタイトル) は、次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-157">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="1fdf8-158">"Saf Etyapiaction" は、次のいずれかの整数型 (integer) の値です。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-158">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="1fdf8-159">1: 迷惑メール</span><span class="sxs-lookup"><span data-stu-id="1fdf8-159">1: Junk</span></span>
- <span data-ttu-id="1fdf8-160">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="1fdf8-160">2: NotJunk</span></span>
- <span data-ttu-id="1fdf8-161">3: フィッシング</span><span class="sxs-lookup"><span data-stu-id="1fdf8-161">3: Phish</span></span>

<span data-ttu-id="1fdf8-162">次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-162">In the following example:</span></span>

- <span data-ttu-id="1fdf8-163">メッセージはフィッシングとして報告されています。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-163">The message is being reported as Phish.</span></span>
- <span data-ttu-id="1fdf8-164">ネットワークメッセージ ID は49871234-6dc6-43e8-abcd-08d797f20abe です。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-164">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="1fdf8-165">送信者の IP は167.220.232.101 です。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-165">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="1fdf8-166">From アドレスは test@contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-166">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="1fdf8-167">メッセージの件名行は "test フィッシング提出" です。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-167">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="1fdf8-168">この形式に従っていないメッセージは、送信ポータルで適切に表示されません。</span><span class="sxs-lookup"><span data-stu-id="1fdf8-168">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
