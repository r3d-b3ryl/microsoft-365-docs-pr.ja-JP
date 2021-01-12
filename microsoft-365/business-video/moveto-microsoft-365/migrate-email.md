---
title: Google Workspace からビジネス メールとカレンダーを移行する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Google Workspace からビジネス向け Microsoft 365 にメール、連絡先、予定表を移行する方法について説明します。
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794645"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="72ec6-103">Google Workspace からビジネス メールとカレンダーを移行する</span><span class="sxs-lookup"><span data-stu-id="72ec6-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="72ec6-104">Google Workspace から Exchange Online への管理者が実行した移行を使用できます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="72ec6-105">メールは、一度に移行するか、または段階で移行できます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="72ec6-106">次の手順は、メール データを一度に移行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="72ec6-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="72ec6-107">詳細については [、「G Suite の移行を実行する」を参照してください](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)。</span><span class="sxs-lookup"><span data-stu-id="72ec6-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="72ec6-108">移行プロセスはいくつかの手順を実行し、移行するデータの量に応じて数時間から数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="72ec6-109">演習</span><span class="sxs-lookup"><span data-stu-id="72ec6-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="72ec6-110">Google サービス アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="72ec6-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="72ec6-111">Chrome ブラウザーを使用して、Google Workspace 管理コンソールにサインイン[admin.google.com。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="72ec6-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="72ec6-112">新しいタブまたはウィンドウで、[サービス アカウント] [ページに移動](https://console.developers.google.com/iam-admin/serviceaccounts) します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="72ec6-113">[プロジェクト **の作成] を選択し**、プロジェクトに名前を付け、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="72ec6-114">Select **Create service account,** enter a name, choose **Create** and then **Done**.</span><span class="sxs-lookup"><span data-stu-id="72ec6-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="72ec6-115">[操作] **メニューを** 開き、[編集] **を選択して**、一意の ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="72ec6-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="72ec6-116">この ID は、プロセスの後半で必要になります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="72ec6-117">[ドメイン全体 **の委任の表示] セクションを開** きます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="72ec6-118">[G **Suite ドメイン全体の委任を有効** にする] を選択し、同意画面の製品名を入力して、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="72ec6-119">製品名は移行プロセスでは使用されませんが、ダイアログに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="72ec6-120">もう一度 **[操作] メニュー** を開き、[キーの **作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="72ec6-121">**[JSON] を選択** し、[作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="72ec6-122">このプライベート キーは、デバイスのダウンロード フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="72ec6-123">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="72ec6-124">プロジェクトの API の使用を有効にする</span><span class="sxs-lookup"><span data-stu-id="72ec6-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="72ec6-125">API ページ [に移動します](https://console.developers.google.com/apis/library)。</span><span class="sxs-lookup"><span data-stu-id="72ec6-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="72ec6-126">検索バーに **「Gmail API」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="72ec6-127">それを選択し、[有効にする] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="72ec6-128">Google カレンダー API と連絡先 API に対してこのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="72ec6-129">サービス アカウントへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="72ec6-129">Grant access to the service account</span></span>

1. <span data-ttu-id="72ec6-130">Google Workspace 管理コンソールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="72ec6-131">[ **セキュリティ] を選択** し、下にスクロールして API コントロール **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="72ec6-132">下にスクロールして、[ **ドメイン全体の委任の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="72ec6-133">[新規 **追加] を** 選択し、前にメモしたクライアント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="72ec6-134">次に、Google API の OAuth スコープを入力します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="72ec6-135">これらは手順 5 の [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) で利用できます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="72ec6-136">Choose **Authorize**.</span><span class="sxs-lookup"><span data-stu-id="72ec6-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="72ec6-137">Microsoft 365 に送信されるメールのサブドメインを作成する</span><span class="sxs-lookup"><span data-stu-id="72ec6-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="72ec6-138">Google Workspace 管理 **コンソールに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="72ec6-139">Select **Domains,** **Manage domains,** then, **Add a domain alias**.</span><span class="sxs-lookup"><span data-stu-id="72ec6-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="72ec6-140">次のようなドメイン エイリアスを入力します `m365.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="72ec6-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="72ec6-141">次に、[ **続行] を選択し、ドメインの所有権を確認します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="72ec6-142">通常、ドメインの検証には数分かかりますが、最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="72ec6-143">
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="72ec6-144">Microsoft **365** 管理センターの左側のナビゲーションで、[すべて表示] 、[**設定**] 、[ドメイン] の順に選択し、[ドメインの追加]**を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="72ec6-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="72ec6-145">以前に作成したサブドメインを入力し、[このドメインを使用 **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="72ec6-146">ドメインに接続するには、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="72ec6-147">下にスクロールして、MX レコード、CNAME レコード、および TXT レコードをメモします。</span><span class="sxs-lookup"><span data-stu-id="72ec6-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="72ec6-148">Google 管理コンソール **に戻る**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="72ec6-149">Select **Domains,** select **Manage domains,** **Verify Details** and then, Manage **domain**.</span><span class="sxs-lookup"><span data-stu-id="72ec6-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="72ec6-150">左側のナビゲーションで **、[DNS]** を選択し、[カスタム リソース レコード] **まで下にスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="72ec6-151">Open the record type dropdown and select **MX,** enter or copy and paste the MX record information you previously noted, then choose **Add**.</span><span class="sxs-lookup"><span data-stu-id="72ec6-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="72ec6-152">CNAME レコードと TXT レコードに対してこのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="72ec6-153">これらの変更が有効にな時期が近付く場合があります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="72ec6-154">**Microsoft 365** 管理センターでオフにした場所に戻り、[続行] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="72ec6-155">これで、ドメインがセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="72ec6-156">Microsoft 365 でメール エイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="72ec6-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="72ec6-157">移行を開始する前に、新しいサブドメインを使用してユーザーの電子メール エイリアスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="72ec6-158">次の手順を開始するには、Microsoft  365 管理センターのドメインの追加ウィザードで、[アクティブなユーザーに移動]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="72ec6-159">ユーザーを選択し、ユーザー名と **メールを管理します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="72ec6-160">**[Domains] ドロップダウン** から、前に作成したサブドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="72ec6-161">ユーザー名を入力し、[追加] **を選択し**、[ **変更の保存] を** 選択して、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="72ec6-162">ユーザーごとにこのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="72ec6-163">移行プロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="72ec6-163">Start the migration process</span></span>

<span data-ttu-id="72ec6-164">完了したら、移行の準備が整います。</span><span class="sxs-lookup"><span data-stu-id="72ec6-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="72ec6-165">**Microsoft 365** 管理センターの左側のナビゲーションで、[管理センター ] まで下にスクロールし **、[Exchange]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="72ec6-166">[**受信者] で、[** 移行] **を** 選択し、[新規]、[Exchange Online に移行 **]、G** **Suite** の移行、[次へ] の順に **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="72ec6-167">移行するメールボックスの一覧を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="72ec6-168">ファイルが次の形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="72ec6-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="72ec6-169">詳細については、以下を[参照aka.ms/GoogleWorkspaceMigration。](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)</span><span class="sxs-lookup"><span data-stu-id="72ec6-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="72ec6-170">Select **Choose File,** navigate to the CSV file, choose it, select **Open,** then **Next**.</span><span class="sxs-lookup"><span data-stu-id="72ec6-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="72ec6-171">テストに使用する管理者のメール アドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="72ec6-172">Select **Choose File,** navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open,** then **Next**.</span><span class="sxs-lookup"><span data-stu-id="72ec6-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="72ec6-173">[新しい移行バッチ名 **] フィールドに名前を入力します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="72ec6-174">[ターゲット配信ドメイン] フィールドに作成したサブドメイン **を** 入力し、[次へ] を選択し、[新規] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="72ec6-175">情報を保存したら **、[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="72ec6-176">これで、移行の状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="72ec6-177">移行するユーザーの数に応じて、しばらく時間が経過した後、[最新の情報に更新] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="72ec6-178">状態が [同期済み] に **変** わったら、[この移行バッチを完了する] を選択し **、[** はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="72ec6-179">プロセスが完了すると、状態が [完了] に **変わります**。</span><span class="sxs-lookup"><span data-stu-id="72ec6-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="72ec6-180">必要に合う場合は、[詳細の表示 **] を** 選択して、移行の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="72ec6-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="72ec6-181">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-181">Select **Close**.</span></span> 
1. <span data-ttu-id="72ec6-182">Outlook を開き、Google Workspace からのすべてのメールが正常に移行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="72ec6-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="72ec6-183">予定表アイテムと連絡先に対して、この操作を繰り返し行います。</span><span class="sxs-lookup"><span data-stu-id="72ec6-183">You can repeat this for calendar items and contacts as well.</span></span>