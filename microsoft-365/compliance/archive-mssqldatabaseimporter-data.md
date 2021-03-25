---
title: MS データベースからデータをアーカイブするコネクタをSQLする
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
description: 管理者は、MS データベースからデータをインポートおよびアーカイブするコネクタをSQLできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 494e91085494ba027a80480faba3cfb189cbd928
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164218"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a><span data-ttu-id="1134a-105">MS データベースからデータをアーカイブするコネクタをSQLする</span><span class="sxs-lookup"><span data-stu-id="1134a-105">Set up a connector to archive data from MS SQL Database</span></span>

<span data-ttu-id="1134a-106">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、MS SQL Database から Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="1134a-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from MS SQL Database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="1134a-107">Veritas は、XML 構成ファイルを使用してデータベースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された MS SQL データベース インポート コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="1134a-107">Veritas provides you with an MS SQL Database Importer connector that's configured to capture items from a database using an XML configuration file and import those items to Microsoft 365.</span></span> <span data-ttu-id="1134a-108">コネクタは、MS SQL データベースから電子メール メッセージ形式にコンテンツを変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="1134a-108">The connector converts content from MS SQL Database to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="1134a-109">ユーザー メールボックスに格納されている MS SQL Database のコンテンツの後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="1134a-109">After content from MS SQL Database stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="1134a-110">Ms SQLデータベース コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1134a-110">Using an MS SQL Database connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-ms-sql-data"></a><span data-ttu-id="1134a-111">MS データのアーカイブSQL概要</span><span class="sxs-lookup"><span data-stu-id="1134a-111">Overview of archiving the MS SQL data</span></span>

<span data-ttu-id="1134a-112">次の概要では、コネクタを使用して Microsoft 365 の MS SQLをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="1134a-112">The following overview explains the process of using a connector to archive MS SQL data in Microsoft 365.</span></span>

![MS データのアーカイブ ワークフロー SQLする](../media/MSSQLDatabaseConnectorWorkflow.png)

1. <span data-ttu-id="1134a-114">組織は MS データベース プロバイダーとSQLして、MS データベース サイトをセットアップSQL構成します。</span><span class="sxs-lookup"><span data-stu-id="1134a-114">Your organization works with an MS SQL Database provider to set up and configure an MS SQL Database site.</span></span>

2. <span data-ttu-id="1134a-115">24 時間に 1 回、MS SQLデータベース アイテムが Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="1134a-115">Once every 24 hours, MS SQL Database items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="1134a-116">コネクタは、このコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="1134a-116">The connector also converts this content to an email message format.</span></span>

3. <span data-ttu-id="1134a-117">Microsoft 365 コンプライアンス センターで作成する MS SQL データベース インポート コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage の場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="1134a-117">The MS SQL Database Importer connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="1134a-118">コネクタは、ステップ [3](#step-3-map-users-and-complete-the-connector-setup)で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された MS SQL データベース アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="1134a-118">The connector imports the converted MS SQL Database items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="1134a-119">MS という名前の受信トレイ フォルダー **SQLデータベース** インポートツールがユーザー メールボックスに作成され、そのフォルダーにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1134a-119">A subfolder in the Inbox folder named **MS SQL Database Importer** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="1134a-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="1134a-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="1134a-121">MS データベースのすべてのアイテムSQLこのプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="1134a-121">Every item from the MS SQL Database contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1134a-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="1134a-122">Before you begin</span></span>

- <span data-ttu-id="1134a-123">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1134a-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="1134a-124">アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。</span><span class="sxs-lookup"><span data-stu-id="1134a-124">To create an account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="1134a-125">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1134a-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="1134a-126">手順 1 で MS SQL データベース インポート コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1134a-126">The user who creates the MS SQL Database Importer connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="1134a-127">Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="1134a-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1134a-128">既定では、この役割は Exchange Online の任意の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="1134a-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="1134a-129">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="1134a-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="1134a-130">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="1134a-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="1134a-131">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1134a-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a><span data-ttu-id="1134a-132">手順 1: データベース インポート コネクタの MS SQL設定する</span><span class="sxs-lookup"><span data-stu-id="1134a-132">Step 1: Set up the MS SQL Database Importer connector</span></span>

<span data-ttu-id="1134a-133">最初の手順は、Microsoft365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、MS SQL作成します。 </span><span class="sxs-lookup"><span data-stu-id="1134a-133">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the MS SQL Database.</span></span>

1. <span data-ttu-id="1134a-134">[データベース インポート] に移動し、[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com)   >  **] [MS SQL] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1134a-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** > **MS SQL Database Importer**.</span></span>

2. <span data-ttu-id="1134a-135">[MS データベース **インポートSQLの説明]** ページで、[新しいコネクタの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1134a-135">On the **MS SQL Database Importer** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="1134a-136">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1134a-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="1134a-137">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1134a-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="1134a-138">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="1134a-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="1134a-139">手順 2: Veritas Merge1 サイトSQL MS データベース インポート コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="1134a-139">Step 2: Configure the MS SQL Database Importer connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="1134a-140">2 番目の手順は、Merge1 サイトSQL MS データ インポート コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="1134a-140">The second step is to configure the MS SQL Database Importer connector on the Merge1 site.</span></span> <span data-ttu-id="1134a-141">データベース インバーの MS SQL構成方法については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1134a-141">For information about how to configure the MS SQL Database Importer, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="1134a-142">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1134a-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="1134a-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="1134a-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="1134a-144">ユーザーをマップし、コネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1134a-144">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="1134a-145">[ **データベース インポートユーザー SQL Microsoft 365** ユーザーにマップする] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1134a-145">On the **Map MS SQL Database Importer users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="1134a-146">[MS SQL データベース] アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1134a-146">The MS SQL Database items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="1134a-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1134a-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="1134a-148">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="1134a-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a><span data-ttu-id="1134a-149">手順 4: データベース インポート コネクタの MS SQL監視する</span><span class="sxs-lookup"><span data-stu-id="1134a-149">Step 4: Monitor the MS SQL Database Importer connector</span></span>

<span data-ttu-id="1134a-150">データベース インポート コネクタの MS SQL作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="1134a-150">After you create the MS SQL Database Importer connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="1134a-151">左側の <https://compliance.microsoft.com/> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="1134a-151">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="1134a-152">[コネクタ **] タブを** クリックし **、MS**  SQL データベース インポート コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="1134a-152">Click the **Connectors** tab and then select the **MS SQL Database** **Importer** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="1134a-153">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="1134a-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="1134a-154">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1134a-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="1134a-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="1134a-155">Known issues</span></span>

- <span data-ttu-id="1134a-156">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1134a-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="1134a-157">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="1134a-157">Support for larger items will be available at a later date.</span></span>