---
title: MS SQL Database からデータをアーカイブするコネクタを設定する
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
description: 管理者は、MS SQL Database からデータをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 686575877f788a2c2662024d5fac3e425d08c500
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620384"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a><span data-ttu-id="ba2da-105">MS SQL Database からデータをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="ba2da-105">Set up a connector to archive data from MS SQL Database</span></span>

<span data-ttu-id="ba2da-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、MS SQL Database から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="ba2da-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from MS SQL Database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="ba2da-107">Globanet は、XML 構成ファイルを使用してデータベースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された MS SQL Database Importer コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-107">Globanet provides you with an MS SQL Database Importer connector that's configured to capture items from a database using an XML configuration file and import those items to Microsoft 365.</span></span> <span data-ttu-id="ba2da-108">コネクタは、MS SQL Database のコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ba2da-108">The connector converts content from MS SQL Database to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="ba2da-109">ユーザー メールボックスに保存されている MS SQL Database のコンテンツの後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-109">After content from MS SQL Database stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="ba2da-110">MS SQL データベース コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-110">Using an MS SQL Database connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-ms-sql-data"></a><span data-ttu-id="ba2da-111">MS サービス データのアーカイブSQL概要</span><span class="sxs-lookup"><span data-stu-id="ba2da-111">Overview of archiving the MS SQL data</span></span>

<span data-ttu-id="ba2da-112">次の概要では、コネクタを使用して MICROSOFT 365 の MS SQLアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-112">The following overview explains the process of using a connector to archive MS SQL data in Microsoft 365.</span></span>

![MS データのアーカイブ SQLワークフロー](../media/MSSQLDatabaseConnectorWorkflow.png)

1. <span data-ttu-id="ba2da-114">組織は MS SQL データベース プロバイダーと共同で MS データベース サイトをセットアップSQL構成します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-114">Your organization works with an MS SQL Database provider to set up and configure an MS SQL Database site.</span></span>

2. <span data-ttu-id="ba2da-115">24 時間ごとに MS SQLデータベース アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-115">Once every 24 hours, MS SQL Database items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="ba2da-116">コネクタは、このコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-116">The connector also converts this content to an email message format.</span></span>

3. <span data-ttu-id="ba2da-117">Microsoft 365 コンプライアンス センターで作成する MS SQL Database Importer コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-117">The MS SQL Database Importer connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="ba2da-118">コネクタは、ステップ 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された MS SQL Database アイテムを特定のユーザーのメールボックス [にインポート](#step-3-map-users-and-complete-the-connector-setup)します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-118">The connector imports the converted MS SQL Database items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="ba2da-119">MS SQL **Database Importer** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-119">A subfolder in the Inbox folder named **MS SQL Database Importer** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="ba2da-120">コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="ba2da-121">MS SQL Database のすべてのアイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-121">Every item from the MS SQL Database contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ba2da-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="ba2da-122">Before you begin</span></span>

- <span data-ttu-id="ba2da-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="ba2da-124">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="ba2da-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="ba2da-125">手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba2da-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="ba2da-126">手順 1 で MS SQL Database Importer コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba2da-126">The user who creates the MS SQL Database Importer connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ba2da-127">この役割は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="ba2da-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ba2da-128">既定では、この役割は Exchange Online の役割グループには割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="ba2da-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="ba2da-129">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ba2da-130">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ba2da-131">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba2da-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a><span data-ttu-id="ba2da-132">手順 1: MS データベース インSQLコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ba2da-132">Step 1: Set up the MS SQL Database Importer connector</span></span>

<span data-ttu-id="ba2da-133">最初の手順では、Microsoft365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、MS SQL Database のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-133">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the MS SQL Database.</span></span>

1. <span data-ttu-id="ba2da-134">[データ [https://compliance.microsoft.com](https://compliance.microsoft.com) コネクタMS SQL  >  **Database Importer] に移動してクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ba2da-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** > **MS SQL Database Importer**.</span></span>

2. <span data-ttu-id="ba2da-135">**[MS SQL Database Importer** 製品の説明] ページで、[新しいコネクタの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ba2da-135">On the **MS SQL Database Importer** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="ba2da-136">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ba2da-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="ba2da-137">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="ba2da-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="ba2da-138">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="ba2da-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="ba2da-139">手順 2: Globanet Merge1 サイトで MS SQL Database Importer コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="ba2da-139">Step 2: Configure the MS SQL Database Importer connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="ba2da-140">2 番目の手順は、Merge1 サイトで MS SQL Database Importer コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="ba2da-140">The second step is to configure the MS SQL Database Importer connector on the Merge1 site.</span></span> <span data-ttu-id="ba2da-141">データベース インデクサーで MS SQL構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="ba2da-141">For information about how to configure the MS SQL Database Importer, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="ba2da-142">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="ba2da-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="ba2da-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="ba2da-144">ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-144">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="ba2da-145">[Map **MS SQL Database Importer users to Microsoft 365 users]** ページで、自動ユーザー マッピングを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="ba2da-145">On the **Map MS SQL Database Importer users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="ba2da-146">MS SQL データベース アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-146">The MS SQL Database items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="ba2da-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="ba2da-148">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a><span data-ttu-id="ba2da-149">手順 4: MS データベース インSQLコネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="ba2da-149">Step 4: Monitor the MS SQL Database Importer connector</span></span>

<span data-ttu-id="ba2da-150">MS SQL Database Importer コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-150">After you create the MS SQL Database Importer connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="ba2da-151">左側の <https://compliance.microsoft.com/> ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba2da-151">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ba2da-152">[ **コネクタ]** タブをクリックし **、MS SQL Database** **Importer** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="ba2da-152">Click the **Connectors** tab and then select the **MS SQL Database** **Importer** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="ba2da-153">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba2da-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="ba2da-154">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba2da-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ba2da-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="ba2da-155">Known issues</span></span>

- <span data-ttu-id="ba2da-156">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ba2da-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="ba2da-157">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="ba2da-157">Support for larger items will be available at a later date.</span></span>
