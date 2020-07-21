---
title: カスタムドメインから Microsoft 365 をパイロットする
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: 2つのテストアカウントのみを使用して、カスタムドメインから Microsoft 365 メールボックスに電子メール機能をパイロットする方法について説明します。
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186049"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="88712-103">カスタムドメインから Microsoft 365 をパイロットする</span><span class="sxs-lookup"><span data-stu-id="88712-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="88712-104">次の要件と制限を使用して Microsoft 365 をパイロットできます。</span><span class="sxs-lookup"><span data-stu-id="88712-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="88712-105">現在の電子メール プロバイダーで、電子メール転送のサービスが提供されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="88712-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="88712-106">Microsoft 365 にこれらのレコードを管理させるのではなく、DNS ホスティングプロバイダーでMicrosoft 365 DNS レコードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88712-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="88712-107">詳細については、「[DNSレコードを追加してドメインに接続する](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88712-107">To learn more, see [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

- <span data-ttu-id="88712-108">他の電子メールサーバーのユーザーの空き時間情報は利用できません。</span><span class="sxs-lookup"><span data-stu-id="88712-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="88712-109">管理者が 1 つの場所からすべてのユーザーアカウントを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="88712-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="88712-110">ユーザーが Microsoft 365 スパムフィルターを使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="88712-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="88712-111">Microsoft 365 パイロットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="88712-111">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="88712-112">次の手順に従って、Microsoft 365 パイロットをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="88712-112">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="88712-113">手順 1: Microsoft 365 管理センターにサインインする</span><span class="sxs-lookup"><span data-stu-id="88712-113">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="88712-114">職場または学校のアカウントで 「[Microsoft 365 管理センター](https://admin.microsoft.com)」にサインインします。</span><span class="sxs-lookup"><span data-stu-id="88712-114">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="88712-115">左側のナビゲーションウィンドウで[**設定** > **ドメイン**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-115">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="88712-116">手順 2: 使おうとしているドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="88712-116">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="88712-117">[**ドメイン**] ページで、[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-117">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="88712-118">ボックスにドメイン名を入力し、[**このドメインを使用**]を選択して、[**続行**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-118">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="88712-119">電子メールやインスタントメッセージなど、ドメインでテストするサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-119">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="88712-120">[**ドメインの確認**]ページで、手順バイ手順の指示に従い、次に[**確認**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-120">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="88712-121">DNS の変更が有効になるまで数分から 72 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="88712-121">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="88712-122">確認が成功すると、DNS レコードを変更するように求められます。</span><span class="sxs-lookup"><span data-stu-id="88712-122">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="88712-123">手順 3: Exchange Online でドメインを共有としてマークする</span><span class="sxs-lookup"><span data-stu-id="88712-123">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="88712-124">Exchange 管理センターの[**メールフロー**]セクションで、[**承認済みドメイン**]を選択してから、変更するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-124">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="88712-125">ダブルクリックしてウィンドウを開き、[**内部リレー**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-125">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="88712-126">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-126">Select **Save**.</span></span>

    <span data-ttu-id="88712-127">この設定が有効になるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="88712-127">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="88712-128">手順 4: 既存の電子メールサーバーのブロックを解除します（オプション）</span><span class="sxs-lookup"><span data-stu-id="88712-128">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="88712-129">Microsoft 365 では、スパム保護に Exchange Online Protection（EOP） を使用しています。</span><span class="sxs-lookup"><span data-stu-id="88712-129">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="88712-130">EOP は、現在のメールサーバーが転送する大量のスパムを検出すると、既存のメールサーバーをブロックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="88712-130">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="88712-131">他の電子メールプロバイダーのスパム保護を信頼している場合は、Microsoft 365でサーバーのブロックを解除できます。</span><span class="sxs-lookup"><span data-stu-id="88712-131">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="88712-132">既存の電子メールサーバーのブロックを解除すると、元のサーバーを介して届くすべてのスパムが Microsoft 365 メールボックスに届くようになるため、Microsoft 365 がスパムをどの程度防止できるかを評価することはできません。</span><span class="sxs-lookup"><span data-stu-id="88712-132">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="88712-133">Exchange 管理センターのナビゲーションウィンドウで、[**保護**]を選択し、[**接続フィルタ**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-133">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="88712-134">[**IP許可リスト**]で**+** を選択し、現在の電子メールプロバイダのメールサーバー IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="88712-134">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="88712-135">手順 5: ユーザー アカウントを作成して主要な (返信先) アドレスを設定する</span><span class="sxs-lookup"><span data-stu-id="88712-135">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="88712-136">Microsoft 365 管理センターの左側のナビゲーションで、[**ユーザー** > **アクティブユーザー**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-136">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="88712-137">2 つの既存のユーザーを追加して、2 つのテストアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="88712-137">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="88712-138">アカウントごとに、[\*\* +ユーザーを追加\*\*]を選択し、テストするパスワードの方法など、必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="88712-138">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="88712-139">ユーザーの電子メールアドレスが同じであることを確認するには、[**ユーザー名**]フィールドがユーザーの現在の電子メールアドレスと一致していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="88712-139">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="88712-140">適切なライセンスを選択し、[**次へ**]をクリックして、[**追加の終了**]をクリックします。</span><span class="sxs-lookup"><span data-stu-id="88712-140">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="88712-141">[**ユーザー名**] の隣の、ドロップダウン リストからカスタム ドメイン名を選択します。</span><span class="sxs-lookup"><span data-stu-id="88712-141">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="88712-142">**を選択し、** > **を作成し、** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="88712-142">Select **Create** > **Close**.</span></span>

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="88712-143">手順 6: DNS ホスティング プロバイダーで DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="88712-143">Step 6: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="88712-144">DNS ホスティングプロバイダーの Web サイトにサインインし、「[DNS レコードを追加してドメインに接続する](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="88712-144">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="88712-145">**次の2つの例外を設けてください。**</span><span class="sxs-lookup"><span data-stu-id="88712-145">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="88712-146">新しい MX レコードは作成せず、既存の MX レコードの変更も行いません。</span><span class="sxs-lookup"><span data-stu-id="88712-146">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="88712-147">Exchange Online の新しい SPF （TXT）レコードを作成する代わりに、以前の電子メールプロバイダーの Sender Policy Framework （SPF）レコードが既にある場合は、現在のTXTレコードに「include:spf.protection.outlook.com」を追加します。</span><span class="sxs-lookup"><span data-stu-id="88712-147">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="88712-148">例えば、「v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all」です。</span><span class="sxs-lookup"><span data-stu-id="88712-148">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="88712-149">SPFレコードがない場合は、Microsoft 365 で推奨されているレコードを変更して、現在の電子メールプロバイダーのドメインを含め、spf.protection.outlook.com を追加します。</span><span class="sxs-lookup"><span data-stu-id="88712-149">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="88712-150">これにより、両方の電子メールシステムからの送信メッセージが承認されます。</span><span class="sxs-lookup"><span data-stu-id="88712-150">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="88712-151">手順 7: 現在のプロバイダーで電子メールの転送をセットアップする</span><span class="sxs-lookup"><span data-stu-id="88712-151">Step 7: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="88712-152">現在の電子メール プロバイダーで、onmicrosoft.com domain ドメインへの転送を管理するユーザーの電子メール アカウントで設定します。</span><span class="sxs-lookup"><span data-stu-id="88712-152">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="88712-153">ユーザー A メールボックスを usera@yourcompany.onmicrosoft.com に転送する</span><span class="sxs-lookup"><span data-stu-id="88712-153">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="88712-154">ユーザー B のメールボックスをuserb@yourcompany.onmicrosoft.comに転送する</span><span class="sxs-lookup"><span data-stu-id="88712-154">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="88712-155">この手順を完了すると、usera@yourcompany.com および userb@yourcompany.com に送信されたすべての電子メールが Microsoft 365 で利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="88712-155">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="88712-156">電子メール転送を設定する正確な手順については、現在の電子メールプロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="88712-156">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="88712-157">現在の電子メール プロバイダーでメッセージのコピーを保持する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="88712-157">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="88712-158">大半のプロバイダーは、返信が元の送信者に送信されるように、送信者の返信先アドレスをそのままにして電子メールを転送します。</span><span class="sxs-lookup"><span data-stu-id="88712-158">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-8-test-mail-flow"></a><span data-ttu-id="88712-159">手順 8: メール フローをテストする</span><span class="sxs-lookup"><span data-stu-id="88712-159">Step 8: Test mail flow</span></span>

1. <span data-ttu-id="88712-160">ユーザー A の資格情報を使用して Outlook Web App にサインインします。</span><span class="sxs-lookup"><span data-stu-id="88712-160">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="88712-161">次のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="88712-161">Perform these tests:</span></span>

    - <span data-ttu-id="88712-162">例えば、ユーザー B に電子メールを送信して、ローカルのMicrosoft 電子メールをテストします。電子メールはすぐに配信されます。</span><span class="sxs-lookup"><span data-stu-id="88712-162">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="88712-163">このシナリオでは、Microsoft 365 メールボックスがローカルであるため、メッセージは元のサーバーのユーザー B のメールボックスにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="88712-163">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="88712-164">例えば、ユーザー C に電子メールを送信して、既存の電子メールシステムのユーザーへの電子メールをテストします。電子メールは、元のメールサーバーのユーザー C のメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="88712-164">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="88712-165">外部アカウントまたは既存の電子メールシステムの従業員の電子メールアカウントから転送が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="88712-165">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="88712-166">例えば、ユーザー C の元のサーバーアカウントまたは Hotmail アカウントから、ユーザー A に電子メールを送信し、それがユーザー A の Microsoft 365 メールボックスに届くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="88712-166">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-9-move-mailbox-contents"></a><span data-ttu-id="88712-167">手順 9: メールボックスのコンテンツを移動する</span><span class="sxs-lookup"><span data-stu-id="88712-167">Step 9: Move mailbox contents</span></span>

<span data-ttu-id="88712-168">2 名のテストユーザーのみを移動し、ユーザー A とユーザー B の両方が Outlook を使用しているため、新しいOutlookプロファイルで古い .PST ファイルを開き、メッセージ、カレンダーアイテム、連絡先などをコピーすることで、電子メールを移動できます。 </span><span class="sxs-lookup"><span data-stu-id="88712-168">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="88712-169">詳細については、「[Outlook の .pst ファイルからメール、連絡先、カレンダーをインポートする](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88712-169">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="88712-170">それらが Microsoft 365 メールボックスの適切な場所にインポートされると、アイテムはどこのどのデバイスからでもアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="88712-170">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>

<span data-ttu-id="88712-171">より多くのメールボックスが関係する場合、または従業員が Outlook を使用していない場合は、Exchange 管理センターで利用可能な移行ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="88712-171">When more mailboxes are involved, or if employees are not using Outlook, you can use the migration tools available in the Exchange admin center.</span></span> <span data-ttu-id="88712-172">開始するには、Exchange 管理センターに移動し、[IMAP サーバーから Exchange Online メールボックスへのメールの移行-新しい記事のリソースが必要です]の指示に従います。</span><span class="sxs-lookup"><span data-stu-id="88712-172">To get started, go to Exchange admin center, and follow the directions in [Migrate Email from an IMAP Server to Exchange Online Mailboxes – we need a new article resource].</span></span>