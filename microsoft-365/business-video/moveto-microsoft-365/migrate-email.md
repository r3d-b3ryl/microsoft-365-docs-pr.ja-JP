---
title: Google ワークスペースからビジネス メールと予定表を移行する
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
description: メール、連絡先、予定表を Google ワークスペースから Microsoft 365 for business に移行する方法について説明します。
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913624"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="5f1dd-103">Google ワークスペースからビジネス メールと予定表を移行する</span><span class="sxs-lookup"><span data-stu-id="5f1dd-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="5f1dd-104">Google ワークスペースから Exchange Online への管理者が実行した移行を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="5f1dd-105">メールは、一度に、または段階で移行できます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="5f1dd-106">次の手順は、電子メール データを一度に移行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="5f1dd-107">詳細については [、「G Suite 移行の実行」を参照してください](/exchange/mailbox-migration/perform-g-suite-migration)。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-107">For more information, see [Perform a G Suite migration](/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="5f1dd-108">移行プロセスにはいくつかの手順が必要で、移行するデータの量に応じて数時間から数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="5f1dd-109">演習</span><span class="sxs-lookup"><span data-stu-id="5f1dd-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="5f1dd-110">Google サービス アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="5f1dd-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="5f1dd-111">Chrome ブラウザーを使用して、Google Workspace 管理コンソールにサインインします[(admin.google.com)。](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="5f1dd-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="5f1dd-112">新しいタブまたはウィンドウで、[サービス アカウント] [ページに移動](https://console.developers.google.com/iam-admin/serviceaccounts) します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="5f1dd-113">[プロジェクト **の作成] を** 選択し、プロジェクトに名前を付け、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="5f1dd-114">[サービス **アカウントの作成] を** 選択し、名前を入力し、[作成] **と [完了** ] の順に **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="5f1dd-115">[アクション] **メニューを** 開き、[編集] **を** 選択し、一意の ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="5f1dd-116">この ID は、プロセスの後半で必要になります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="5f1dd-117">[ドメイン全体 **の委任を表示する] セクションを開** きます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="5f1dd-118">[G **Suite ドメイン全体の委任を有効にする**] を選択し、同意画面の製品名を入力し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="5f1dd-119">製品名は移行プロセスでは使用されませんが、ダイアログに保存するために必要です。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="5f1dd-120">[操作] **メニューを再度** 開き、[キーの作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="5f1dd-121">**[JSON] を選択** し、[作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="5f1dd-122">プライベート キーは、デバイスのダウンロード フォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="5f1dd-123">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="5f1dd-124">プロジェクトの API 使用法を有効にする</span><span class="sxs-lookup"><span data-stu-id="5f1dd-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="5f1dd-125">[[API] ページに移動します](https://console.developers.google.com/apis/library)。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="5f1dd-126">検索バーに **「Gmail API」と入力します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="5f1dd-127">それを選択し、[有効にする] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="5f1dd-128">Google カレンダー API と連絡先 API でこのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="5f1dd-129">サービス アカウントへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="5f1dd-129">Grant access to the service account</span></span>

1. <span data-ttu-id="5f1dd-130">Google Workspace 管理コンソールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="5f1dd-131">[セキュリティ **] を選択** し、下にスクロールして API コントロール **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="5f1dd-132">下にスクロールして、[ **ドメイン全体の委任の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="5f1dd-133">[ **新規追加] を** 選択し、前にメモしたクライアント ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="5f1dd-134">次に、Google API の OAuth スコープを入力します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="5f1dd-135">これらは、手順 [5 の aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-135">These are available at [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="5f1dd-136">[ **承認] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="5f1dd-137">Microsoft 365 に送信されるメールのサブドメインを作成する</span><span class="sxs-lookup"><span data-stu-id="5f1dd-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="5f1dd-138">Google Workspace 管理 **コンソールに戻** ります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="5f1dd-139">[**ドメイン] 、[\*\*\*\*ドメインの管理]** の順に選択し、[**ドメイン エイリアスの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="5f1dd-140">のようなドメイン エイリアスを入力します `m365.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="5f1dd-141">次に、[ **続行] を選択し、ドメインの所有権を確認します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="5f1dd-142">通常、ドメイン検証には数分かかりますが、最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="5f1dd-143">
            [Microsoft 365 管理センター](https://admin.microsoft.com)に戻ります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="5f1dd-144">Microsoft **365 管理** センターの左側のナビゲーションで、[すべて表示] **、[\*\*\*\*設定**] 、[ドメイン] 、[ドメインの追加]**の順に選択します**。 </span><span class="sxs-lookup"><span data-stu-id="5f1dd-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="5f1dd-145">以前に作成したサブドメインを入力し、[このドメインを使用 **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="5f1dd-146">ドメインを接続するには、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="5f1dd-147">下にスクロールして、MX レコード、CNAME レコード、および TXT レコードをメモします。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="5f1dd-148">Google 管理コンソール **に戻る**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="5f1dd-149">[ **ドメイン] を選択し**、[ **ドメインの管理]**、[ **詳細の確認** ] の順に選択し、[ドメインの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="5f1dd-150">左側のナビゲーションで **、[DNS] を選択し** 、[カスタム リソース レコード **] まで下にスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="5f1dd-151">[レコードの種類] ドロップダウンを開き **、[MX]** を選択し、以前に記録した MX レコード情報を入力またはコピーして貼り付け、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="5f1dd-152">CNAME レコードと TXT レコードの処理を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="5f1dd-153">これらの変更を有効にするには、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="5f1dd-154">**Microsoft 365** 管理センターでオフにした場所に戻り、[続行] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="5f1dd-155">これで、ドメインがセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="5f1dd-156">Microsoft 365 でメール エイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="5f1dd-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="5f1dd-157">移行を開始する前に、新しいサブドメインを使用してユーザーのメール エイリアスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="5f1dd-158">次の手順を開始するには、Microsoft  365 管理センターの [ドメインの追加] ウィザードで、[アクティブ ユーザーに移動]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="5f1dd-159">ユーザーを選択し、[ユーザー名と **メールの管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="5f1dd-160">[ドメイン **] ドロップダウンから** 、以前に作成したサブドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="5f1dd-161">ユーザー名を入力し、[追加] **、[変更の\*\*\*\*保存]** を選択し、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="5f1dd-162">ユーザーごとにこのプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="5f1dd-163">移行プロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="5f1dd-163">Start the migration process</span></span>

<span data-ttu-id="5f1dd-164">完了したら、移行する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="5f1dd-165">**Microsoft 365** 管理センターの左側のナビゲーションで、下にスクロールして管理センターに移動し **、[Exchange] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="5f1dd-166">[ **受信者] で、[** 移行 **] を** 選択し、[ **新規**] **、[Exchange Online** への移行] の順に選択し **、[G Suite の** 移行] を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="5f1dd-167">移行するメールボックスの一覧を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="5f1dd-168">ファイルが次の形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="5f1dd-169">詳細については、「aka.ms/GoogleWorkspaceMigration」 [を参照してください](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-169">For details see [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="5f1dd-170">[ **ファイルの選択]** を選択し、CSV ファイルに移動して選択し、[開く] 、[ **次** へ] の順に **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="5f1dd-171">テストに使用する管理者メール アドレスを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="5f1dd-172">[**ファイルの選択]** を選択し、前に作成した JSON ファイル (通常はコンピューターの [ダウンロード] フォルダー) に移動し、それを選択し、[開く] 、[次へ] の **順に\*\*\*\*選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="5f1dd-173">[新しい移行バッチ名 **] フィールドに名前を入力します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="5f1dd-174">[ターゲット配信ドメイン] フィールドに作成したサブドメイン **を入力** し、[次へ] を選択し、[新規] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="5f1dd-175">情報を保存したら **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="5f1dd-176">これで、移行の状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="5f1dd-177">移行するユーザーの数に応じて、しばらく時間が経過した後、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="5f1dd-178">状態が [同期済み] に **変更したら**、[この移行 **バッチを完了する**] を選択し、[はい] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="5f1dd-179">プロセスが完了すると、状態は [完了] に **変わります**。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="5f1dd-180">必要な場合は、[詳細の表示] **を選択して** 、移行の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="5f1dd-181">**[閉じる]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-181">Select **Close**.</span></span> 
1. <span data-ttu-id="5f1dd-182">Outlook を開き、Google ワークスペースからのすべてのメールが正常に移行されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="5f1dd-183">予定表アイテムと連絡先にもこの操作を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5f1dd-183">You can repeat this for calendar items and contacts as well.</span></span>