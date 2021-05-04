---
title: MS 上の Cisco Jabber をアーカイブするコネクタをセットアップし、SQLデータをMicrosoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理者は、Ms 上の Cisco Jabber をインポートおよびアーカイブするコネクタをセットアップし、SQL で Veritas からデータをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 01899e4142d6e60fb10a101f7af8e9b4143a38c8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764305"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a><span data-ttu-id="e94a9-105">MS データで Cisco Jabber をアーカイブするコネクタをSQLする</span><span class="sxs-lookup"><span data-stu-id="e94a9-105">Set up a connector to archive Cisco Jabber on MS SQL data</span></span>

<span data-ttu-id="e94a9-106">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、Cisco Jabber プラットフォームから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Cisco Jabber platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="e94a9-107">Veritas は、1:1 チャット メッセージやグループ チャットなど、Jabber の MS SQL Database からアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された[Cisco Jabber](https://globanet.com/jabber/)コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-107">Veritas provides you with a [Cisco Jabber](https://globanet.com/jabber/) connector that is configured to capture items from the Jabber's MS SQL Database, such as 1:1 chat messages and group chats and then import those items to Microsoft 365.</span></span> <span data-ttu-id="e94a9-108">コネクタは、Cisco Jabber の MS SQL Database からデータを取得し、処理し、コンテンツをユーザーの Cisco Jabber アカウントから電子メール メッセージ形式に変換し、Microsoft 365 のユーザーのメールボックスにそれらのアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e94a9-108">The connector retrieves data from the Cisco Jabber's MS SQL Database, processes it, and the converts the content from a user's Cisco Jabber account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="e94a9-109">Cisco Jabber データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-109">After Cisco Jabber data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="e94a9-110">Cisco Jabber コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-110">Using a Cisco Jabber connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-data"></a><span data-ttu-id="e94a9-111">Cisco Jabber データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="e94a9-111">Overview of archiving Cisco Jabber data</span></span>

<span data-ttu-id="e94a9-112">次の概要では、コネクタを使用して、Ms 上の Cisco Jabber をアーカイブし、SQLデータをアーカイブMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="e94a9-112">The following overview explains the process of using a connector to archive Cisco Jabber on MS SQL data in Microsoft 365.</span></span>

![Cisco Jabber データのアーカイブ ワークフロー](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. <span data-ttu-id="e94a9-114">組織は、Cisco と一緒に MS サーバーで Cisco Jabber をセットアップおよび構成SQL Database。</span><span class="sxs-lookup"><span data-stu-id="e94a9-114">Your organization works with Cisco to set up and configure a Cisco Jabber on MS SQL Database.</span></span>

2. <span data-ttu-id="e94a9-115">24 時間に 1 回、Cisco Jabber アイテムは MS SQL Database Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-115">Once every 24 hours, Cisco Jabber items are copied from the MS SQL Database to the Veritas Merge1 site.</span></span> <span data-ttu-id="e94a9-116">コネクタは、チャット メッセージのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-116">The connector also converts the content of chat messages to an email message format.</span></span>

3. <span data-ttu-id="e94a9-117">Microsoft 365 コンプライアンス センターで作成する Cisco Jabber コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage 場所にアイテムを転送します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-117">The Cisco Jabber connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="e94a9-118">コネクタとしての自動ユーザー マッピングは、手順 3 で説明されている *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="e94a9-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="e94a9-119">MS SQL の **Cisco Jabber という** 名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにメッセージ アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-119">A subfolder in the Inbox folder named **Cisco Jabber on MS SQL** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="e94a9-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="e94a9-121">すべての Cisco Jabber アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-121">Every Cisco Jabber item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e94a9-122">開始する前に</span><span class="sxs-lookup"><span data-stu-id="e94a9-122">Before you begin</span></span>

- <span data-ttu-id="e94a9-123">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="e94a9-124">このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。</span><span class="sxs-lookup"><span data-stu-id="e94a9-124">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="e94a9-125">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e94a9-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="e94a9-126">手順 1 でコネクタSQL Databaseする前に、Jabber アイテムを取得する MS ファイルをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="e94a9-126">Set up an MS SQL Database to retrieve Jabber items from before creating the connector in Step 1.</span></span> <span data-ttu-id="e94a9-127">手順 2 で Cisco Jabber コネクタを構成するSQL Database MS インターフェイスの接続設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-127">You will specify the connection settings for the MS SQL Database when configuring the Cisco Jabber connector in Step 2.</span></span> <span data-ttu-id="e94a9-128">詳細については [、「Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e94a9-128">For more information, see the [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="e94a9-129">手順 1 で Cisco Jabber コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e94a9-129">The user who creates the Cisco Jabber connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e94a9-130">この役割は、コンプライアンス センターの [**データ** コネクタ] ページにコネクタを追加Microsoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="e94a9-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e94a9-131">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="e94a9-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="e94a9-132">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e94a9-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e94a9-133">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e94a9-134">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e94a9-134">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a><span data-ttu-id="e94a9-135">手順 1: MS インターフェイス コネクタで Cisco Jabber をSQLする</span><span class="sxs-lookup"><span data-stu-id="e94a9-135">Step 1: Set up the Cisco Jabber on MS SQL connector</span></span>

<span data-ttu-id="e94a9-136">最初の手順は、コンプライアンス センターのデータ コネクタにアクセスし、ms Microsoft 365データ上に Cisco Jabber 用のコネクタSQLすることです。</span><span class="sxs-lookup"><span data-stu-id="e94a9-136">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for Cisco Jabber on MS SQL data.</span></span>

1. <span data-ttu-id="e94a9-137">MS の [https://compliance.microsoft.com](https://compliance.microsoft.com/) [データ コネクタ  >  **] の [Cisco Jabber] に移動してSQL。**</span><span class="sxs-lookup"><span data-stu-id="e94a9-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/)and then click **Data connectors** > **Cisco Jabber on MS SQL**.</span></span>

2. <span data-ttu-id="e94a9-138">[MS の **Cisco Jabber SQL** 説明] ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e94a9-138">On the **Cisco Jabber on MS SQL** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="e94a9-139">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e94a9-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="e94a9-140">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e94a9-140">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="e94a9-141">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="e94a9-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="e94a9-142">手順 2: Veritas Merge1 サイトの MS SQLコネクタで Cisco Jabber を構成する</span><span class="sxs-lookup"><span data-stu-id="e94a9-142">Step 2: Configure the Cisco Jabber on MS SQL connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="e94a9-143">2 番目の手順は、Veritas Merge1 サイトの MS SQLコネクタで Cisco Jabber を構成することです。</span><span class="sxs-lookup"><span data-stu-id="e94a9-143">The second step is to configure the Cisco Jabber on MS SQL connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="e94a9-144">MS SQL コネクタで Cisco Jabber を構成する方法については[、「Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)サード パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e94a9-144">For information about how to configure the Cisco Jabber on MS SQL connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="e94a9-145">[ファイルの **保存と&完了**] をクリックすると、コンプライアンス センターのコネクタ ウィザードの [ユーザー Microsoft 365] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="e94a9-146">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="e94a9-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="e94a9-147">ユーザーをマップし、コンプライアンス センターでセットアップされたコネクタをMicrosoft 365するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-147">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="e94a9-148">[MS 上 **の Cisco Jabber をマップSQLユーザー** Microsoft 365に移動するには、自動ユーザー マッピングを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="e94a9-148">On the **Map Cisco Jabber on MS SQL users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="e94a9-149">MS の Cisco Jabber SQLには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-149">The Cisco Jabber on MS SQL items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="e94a9-150">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="e94a9-151">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-151">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-connector"></a><span data-ttu-id="e94a9-152">手順 4: Cisco Jabber コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="e94a9-152">Step 4: Monitor the Cisco Jabber connector</span></span>

<span data-ttu-id="e94a9-153">Ms SQL コネクタに Cisco Jabber を作成した後、コンプライアンス センターでコネクタのMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-153">After you create the Cisco Jabber on MS SQL connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="e94a9-154">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="e94a9-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="e94a9-155">[コネクタ **] タブをクリック** し、MS コネクタの **Cisco Jabber** SQLして、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="e94a9-155">Click the **Connectors** tab and then select the **Cisco Jabber on MS SQL** connector to display the flyout page.</span></span> <span data-ttu-id="e94a9-156">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="e94a9-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="e94a9-157">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="e94a9-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="e94a9-158">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-158">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e94a9-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e94a9-159">Known issues</span></span>

- <span data-ttu-id="e94a9-160">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e94a9-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="e94a9-161">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="e94a9-161">Support for larger items will be available at a later date.</span></span>
