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
ms.openlocfilehash: bdcf86474a7f2edb458075e884c20e56d231df6d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197841"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="1192f-103">カスタムドメインから Microsoft 365 をパイロットする</span><span class="sxs-lookup"><span data-stu-id="1192f-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="1192f-104">次の要件と制限を使用して Microsoft 365 をパイロットできます。</span><span class="sxs-lookup"><span data-stu-id="1192f-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="1192f-105">現在の電子メール プロバイダーで、電子メール転送のサービスが提供されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1192f-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="1192f-106">Microsoft 365 にこれらのレコードを管理させるのではなく、DNS ホスティングプロバイダーでMicrosoft 365 DNS レコードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1192f-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="1192f-107">詳細については、「[DNSレコードを追加してドメインに接続する](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1192f-107">To learn more, see [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="1192f-108">他の電子メールサーバーのユーザーの空き時間情報は利用できません。</span><span class="sxs-lookup"><span data-stu-id="1192f-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="1192f-109">管理者が 1 つの場所からすべてのユーザーアカウントを管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="1192f-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="1192f-110">ユーザーが Microsoft 365 スパムフィルターを使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1192f-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="1192f-111">これは、ユーザー数が非常に少ない場合にお勧めです。パイロット用にメールを使用する場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="1192f-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="1192f-112">Microsoft 365 パイロットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="1192f-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="1192f-113">次の手順に従って、Microsoft 365 パイロットをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="1192f-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="1192f-114">手順 1: Microsoft 365 管理センターにサインインする</span><span class="sxs-lookup"><span data-stu-id="1192f-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="1192f-115">職場または学校のアカウントで 「[Microsoft 365 管理センター](https://admin.microsoft.com)」にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1192f-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="1192f-116">左側のナビゲーションウィンドウで[**設定** > **ドメイン**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="1192f-117">手順 2: 使おうとしているドメインを所有していることを確認する</span><span class="sxs-lookup"><span data-stu-id="1192f-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="1192f-118">[**ドメイン**] ページで、[**ドメインの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="1192f-119">ボックスにドメイン名を入力し、[**このドメインを使用**]を選択して、[**続行**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="1192f-120">電子メールやインスタントメッセージなど、ドメインでテストするサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="1192f-121">[**ドメインの確認**]ページで、手順バイ手順の指示に従い、次に[**確認**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="1192f-122">DNS の変更が有効になるまで数分から 72 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="1192f-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="1192f-123">確認が成功すると、DNS レコードを変更するように求められます。</span><span class="sxs-lookup"><span data-stu-id="1192f-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="1192f-124">手順 3: Exchange Online でドメインを共有としてマークする</span><span class="sxs-lookup"><span data-stu-id="1192f-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="1192f-125">Exchange 管理センターの[**メールフロー**]セクションで、[**承認済みドメイン**]を選択してから、変更するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="1192f-126">ダブルクリックしてウィンドウを開き、[**内部リレー**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-126">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="1192f-127">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-127">Select **Save**.</span></span>

    <span data-ttu-id="1192f-128">この設定が有効になるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1192f-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="1192f-129">手順 4: 既存の電子メールサーバーのブロックを解除します（オプション）</span><span class="sxs-lookup"><span data-stu-id="1192f-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="1192f-130">Microsoft 365 では、スパム保護に Exchange Online Protection（EOP） を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1192f-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="1192f-131">EOP は、現在のメールサーバーが転送する大量のスパムを検出すると、既存のメールサーバーをブロックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1192f-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="1192f-132">他の電子メールプロバイダーのスパム保護を信頼している場合は、Microsoft 365でサーバーのブロックを解除できます。</span><span class="sxs-lookup"><span data-stu-id="1192f-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="1192f-133">既存の電子メールサーバーのブロックを解除すると、元のサーバーを介して届くすべてのスパムが Microsoft 365 メールボックスに届くようになるため、Microsoft 365 がスパムをどの程度防止できるかを評価することはできません。</span><span class="sxs-lookup"><span data-stu-id="1192f-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="1192f-134">Exchange 管理センターのナビゲーションウィンドウで、[**保護**]を選択し、[**接続フィルタ**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="1192f-135">[**IP許可リスト**]で **+** を選択し、現在の電子メールプロバイダのメールサーバー IP アドレスを追加します。</span><span class="sxs-lookup"><span data-stu-id="1192f-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="1192f-136">手順 5: ユーザー アカウントを作成して主要な (返信先) アドレスを設定する</span><span class="sxs-lookup"><span data-stu-id="1192f-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="1192f-137">Microsoft 365 管理センターの左側のナビゲーションで、[**ユーザー** > **アクティブユーザー**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="1192f-138">2 つの既存のユーザーを追加して、2 つのテストアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1192f-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="1192f-139">アカウントごとに、[**+ユーザーを追加**]を選択し、テストするパスワードの方法など、必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1192f-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="1192f-140">ユーザーの電子メールアドレスが同じであることを確認するには、[**ユーザー名**]フィールドがユーザーの現在の電子メールアドレスと一致していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1192f-140">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="1192f-141">適切なライセンスを選択し、[**次へ**]をクリックして、[**追加の終了**]をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1192f-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="1192f-142">[**ユーザー名**] の隣の、ドロップダウン リストからカスタム ドメイン名を選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="1192f-143">**を選択し、** > **を作成し、** を閉じます。</span><span class="sxs-lookup"><span data-stu-id="1192f-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="1192f-144">手順 6: \*\*Microsoft 365 または Office 365 からメール サーバーに流れるようにメールを構成する</span><span class="sxs-lookup"><span data-stu-id="1192f-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="1192f-145">次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1192f-145">There are two steps for this:</span></span>

1. <span data-ttu-id="1192f-146">Microsoft 365 または Office 365 環境を構成します。</span><span class="sxs-lookup"><span data-stu-id="1192f-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="1192f-147">Microsoft 365 または Office 365 からメール サーバーへのコネクタを設定します。</span><span class="sxs-lookup"><span data-stu-id="1192f-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="1192f-148">1. Microsoft 365 または Office 365 環境を構成する</span><span class="sxs-lookup"><span data-stu-id="1192f-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="1192f-149">Microsoft 365 または Office365 で次の手順が完了したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1192f-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="1192f-150">コネクタを設定するには、開始する前にアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1192f-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="1192f-151">必要なアクセス許可を確認するには、「[EOP の機能のアクセス許可](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop)」トピックの「Microsoft 365 および Office 365 コネクタ」の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1192f-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/feature-permissions-in-eop) topic.</span></span>

2. <span data-ttu-id="1192f-152">EOP か ExchangeOnline でメール サーバーからインターネットにメールを中継する場合は、次のいずれかの方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="1192f-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="1192f-153">Microsoft 365 または Office 365 の承認済みドメインと一致するサブジェクト名で構成されている証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="1192f-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="1192f-154">証明書の共通名、またはサブジェクトの別名を組織のプライマリ SMTP ドメインと一致させることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1192f-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="1192f-155">詳細については、「[オンプレミスのメール環境の前提条件](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1192f-155">For details, see [Prerequisites for your on-premises email environment](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="1192f-156">または</span><span class="sxs-lookup"><span data-stu-id="1192f-156">-OR-</span></span>

   - <span data-ttu-id="1192f-157">組織の送信者のドメインとサブドメインがすべて Microsoft 365 または Office 365 の承認済みドメインとして構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1192f-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="1192f-158">承認済みドメインの定義に関する詳細は、「[Exchange Online で承認済みドメインを管理する](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」および「[Exchange Online でサブドメインのメール フローを有効にする](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1192f-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="1192f-159">Microsoft 365 または Office 365 からメール サーバーへとメールを配信するのに、メール フロー ルール (トランスポート ルールとも呼ばれます) を使用するか、ドメイン名を使用するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1192f-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="1192f-160">ほとんどの企業は、すべての承認済みドメインにメールを配信することを選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="1192f-161">詳細については、「[シナリオ: Exchange Online での条件付きメール ルーティング](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1192f-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="1192f-162">「[Exchange Online でのメール フロー ルールの処理](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」の説明に従って、メール フロー ルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="1192f-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="1192f-163">たとえば、現在メールが配布リストを介して複数のサイトに送信されている場合は、コネクタ付きのメール フロー ルールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1192f-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="1192f-164">2. Microsoft 365 または Office 365 からメール サーバーへのコネクタを設定します。</span><span class="sxs-lookup"><span data-stu-id="1192f-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="1192f-165">Microsoft 365 または Office 365 にコネクタを作成するには、**[管理者]** をクリックし、そして **[Exchange]** をクリックして Exchange 管理センターへ移動します。</span><span class="sxs-lookup"><span data-stu-id="1192f-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="1192f-166">次に、**[メール フロー]** をクリックし、**[コネクタ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1192f-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="1192f-167">ウィザードを使用してコネクタを設定します。</span><span class="sxs-lookup"><span data-stu-id="1192f-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="1192f-168">ウィザードを起動するには、プラス記号 **+** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1192f-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="1192f-169">最初の画面で、**From** Office 365 および **To** 組織のメール サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1192f-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="1192f-170">**[次へ]** をクリックして、ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="1192f-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="1192f-171">詳細情報については、**[ヘルプ]** または **[詳細情報]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1192f-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="1192f-172">ウィザードに従って設定を行います。</span><span class="sxs-lookup"><span data-stu-id="1192f-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="1192f-173">最後に、コネクタが検証されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1192f-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="1192f-174">コネクタが検証されない場合は、表示されているメッセージをダブルクリックして詳細を表示させ、問題の解決のために「[コネクタを検証する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)」を参照します。</span><span class="sxs-lookup"><span data-stu-id="1192f-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="1192f-175">手順 7: DNS ホスティング プロバイダーで DNS レコードを更新する</span><span class="sxs-lookup"><span data-stu-id="1192f-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="1192f-176">DNS ホスティングプロバイダーの Web サイトにサインインし、「[DNS レコードを追加してドメインに接続する](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="1192f-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="1192f-177">**次の2つの例外を設けてください。**</span><span class="sxs-lookup"><span data-stu-id="1192f-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="1192f-178">新しい MX レコードは作成せず、既存の MX レコードの変更も行いません。</span><span class="sxs-lookup"><span data-stu-id="1192f-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="1192f-179">Exchange Online の新しい SPF （TXT）レコードを作成する代わりに、以前の電子メールプロバイダーの Sender Policy Framework （SPF）レコードが既にある場合は、現在のTXTレコードに「include:spf.protection.outlook.com」を追加します。</span><span class="sxs-lookup"><span data-stu-id="1192f-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="1192f-180">例えば、「v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all」です。</span><span class="sxs-lookup"><span data-stu-id="1192f-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="1192f-181">SPFレコードがない場合は、Microsoft 365 で推奨されているレコードを変更して、現在の電子メールプロバイダーのドメインを含め、spf.protection.outlook.com を追加します。</span><span class="sxs-lookup"><span data-stu-id="1192f-181">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="1192f-182">これにより、両方の電子メールシステムからの送信メッセージが承認されます。</span><span class="sxs-lookup"><span data-stu-id="1192f-182">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="1192f-183">手順 8: 現在のプロバイダーで電子メールの転送をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1192f-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="1192f-184">現在の電子メール プロバイダーで、onmicrosoft.com domain ドメインへの転送を管理するユーザーの電子メール アカウントで設定します。</span><span class="sxs-lookup"><span data-stu-id="1192f-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="1192f-185">ユーザー A メールボックスを usera@yourcompany.onmicrosoft.com に転送する</span><span class="sxs-lookup"><span data-stu-id="1192f-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="1192f-186">ユーザー B のメールボックスをuserb@yourcompany.onmicrosoft.comに転送する</span><span class="sxs-lookup"><span data-stu-id="1192f-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="1192f-187">この手順を完了すると、usera@yourcompany.com および userb@yourcompany.com に送信されたすべての電子メールが Microsoft 365 で利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1192f-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="1192f-188">電子メール転送を設定する正確な手順については、現在の電子メールプロバイダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="1192f-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="1192f-189">現在の電子メール プロバイダーでメッセージのコピーを保持する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1192f-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="1192f-190">大半のプロバイダーは、返信が元の送信者に送信されるように、送信者の返信先アドレスをそのままにして電子メールを転送します。</span><span class="sxs-lookup"><span data-stu-id="1192f-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="1192f-191">手順 9: メール フローをテストする</span><span class="sxs-lookup"><span data-stu-id="1192f-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="1192f-192">ユーザー A の資格情報を使用して Outlook Web App にサインインします。</span><span class="sxs-lookup"><span data-stu-id="1192f-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="1192f-193">次のテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="1192f-193">Perform these tests:</span></span>

    - <span data-ttu-id="1192f-194">例えば、ユーザー B に電子メールを送信して、ローカルのMicrosoft 電子メールをテストします。電子メールはすぐに配信されます。</span><span class="sxs-lookup"><span data-stu-id="1192f-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="1192f-195">このシナリオでは、Microsoft 365 メールボックスがローカルであるため、メッセージは元のサーバーのユーザー B のメールボックスにルーティングされません。</span><span class="sxs-lookup"><span data-stu-id="1192f-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="1192f-196">例えば、ユーザー C に電子メールを送信して、既存の電子メールシステムのユーザーへの電子メールをテストします。電子メールは、元のメールサーバーのユーザー C のメールボックスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="1192f-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="1192f-197">外部アカウントまたは既存の電子メールシステムの従業員の電子メールアカウントから転送が正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1192f-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="1192f-198">例えば、ユーザー C の元のサーバーアカウントまたは Hotmail アカウントから、ユーザー A に電子メールを送信し、それがユーザー A の Microsoft 365 メールボックスに届くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1192f-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="1192f-199">手順 10: メールボックスのコンテンツを移動する</span><span class="sxs-lookup"><span data-stu-id="1192f-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="1192f-200">2 名のテストユーザーのみを移動し、ユーザー A とユーザー B の両方が Outlook を使用しているため、新しいOutlookプロファイルで古い .PST ファイルを開き、メッセージ、カレンダーアイテム、連絡先などをコピーすることで、電子メールを移動できます。 </span><span class="sxs-lookup"><span data-stu-id="1192f-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="1192f-201">詳細については、「[Outlook の .pst ファイルからメール、連絡先、カレンダーをインポートする](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1192f-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="1192f-202">それらが Microsoft 365 メールボックスの適切な場所にインポートされると、アイテムはどこのどのデバイスからでもアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="1192f-202">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>