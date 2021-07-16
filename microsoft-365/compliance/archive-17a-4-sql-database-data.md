---
title: コネクタをセットアップして、SQLデータをアーカイブMicrosoft 365
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
description: 17a-4 SQL DataParser コネクタを設定して使用して、SQL データをインポートおよびアーカイブするMicrosoft 365。
ms.openlocfilehash: 67ad3332a05356702df7b0624ee05519ff30bcac
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454031"
---
# <a name="set-up-a-connector-to-archive-sql-data"></a><span data-ttu-id="9c1ba-103">データをアーカイブするコネクタをSQLする</span><span class="sxs-lookup"><span data-stu-id="9c1ba-103">Set up a connector to archive SQL data</span></span>

<span data-ttu-id="9c1ba-104">17a-4 LLC SQL [DataParser](https://www.17a-4.com/sql-dataparser/)を使用して、SQL データベースから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-104">Use the [SQL DataParser](https://www.17a-4.com/sql-dataparser/) from 17a-4 LLC to import and archive data from a SQL database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="9c1ba-105">DataParser には、SQL データ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された、Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-105">The DataParser includes a SQL connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="9c1ba-106">DataParser SQLは、SQLデータを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-106">The SQL DataParser connector converts SQL data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="9c1ba-107">ユーザー SQLにデータを格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-107">After SQL data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="9c1ba-108">アプリケーション コネクタSQLを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-108">Using a SQL connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-sql-data"></a><span data-ttu-id="9c1ba-109">データのアーカイブSQL概要</span><span class="sxs-lookup"><span data-stu-id="9c1ba-109">Overview of archiving SQL data</span></span>

<span data-ttu-id="9c1ba-110">次の概要では、データ コネクタを使用してデータをアーカイブするプロセスSQL説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-110">The following overview explains the process of using a data connector to archive SQL data in Microsoft 365.</span></span>

![17a-4 SQLデータのアーカイブ ワークフロー](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. <span data-ttu-id="9c1ba-112">組織は 17a-4 を使用して、DataParser のSQL構成します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-112">Your organization works with 17a-4 to set up and configure the SQL DataParser.</span></span>

2. <span data-ttu-id="9c1ba-113">定期的に、データSQL DataParser によって収集されます。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-113">On a regular basis, SQL items are collected by the DataParser.</span></span> <span data-ttu-id="9c1ba-114">DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="9c1ba-115">Microsoft 365 コンプライアンス センターで作成する SQL DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-115">The SQL DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="9c1ba-116">**SQL DataParser という名前の受信** トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、SQLアイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-116">A subfolder in the Inbox folder named **SQL DataParser** is created in the user mailboxes, and the SQL items are imported to that folder.</span></span> <span data-ttu-id="9c1ba-117">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="9c1ba-118">すべてのSQLには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-118">Every SQL item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="9c1ba-119">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="9c1ba-119">Before you set up a connector</span></span>

- <span data-ttu-id="9c1ba-120">Microsoft コネクタ用の DataParser アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="9c1ba-121">これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="9c1ba-122">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="9c1ba-123">手順 1 で SQL DataParser コネクタを作成し 、手順 3 で完了するユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-123">The user who creates the SQL DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="9c1ba-124">この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9c1ba-125">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="9c1ba-126">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="9c1ba-127">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="9c1ba-128">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-sql-dataparser-connector"></a><span data-ttu-id="9c1ba-129">手順 1: DataParser コネクタSQLセットアップする</span><span class="sxs-lookup"><span data-stu-id="9c1ba-129">Step 1: Set up a SQL DataParser connector</span></span>

<span data-ttu-id="9c1ba-130">最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、SQL用の 17a-4 コネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for SQL data.</span></span>

1. <span data-ttu-id="9c1ba-131"><https://compliance.microsoft.com>[DataParser] に移動し、[**データ** コネクタ  >  **] SQLクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **SQL DataParser**.</span></span>

2. <span data-ttu-id="9c1ba-132">**[DataParser SQL説明] ページで、[** コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-132">On the **SQL DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="9c1ba-133">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="9c1ba-134">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="9c1ba-135">17a-4 アカウントにサインインし、DataParser 接続ウィザードの手順SQL完了します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-135">Sign in to your 17a-4 account and complete the steps in the SQL DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-sql-dataparser-connector"></a><span data-ttu-id="9c1ba-136">手順 2: DataParser コネクタSQL構成する</span><span class="sxs-lookup"><span data-stu-id="9c1ba-136">Step 2: Configure the SQL DataParser connector</span></span>

<span data-ttu-id="9c1ba-137">17a-4 サポートを使用して、DataParser コネクタSQL構成します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-137">Work with 17a-4 Support to configure the SQL DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="9c1ba-138">手順 3: ユーザーをマップする</span><span class="sxs-lookup"><span data-stu-id="9c1ba-138">Step 3: Map users</span></span>

<span data-ttu-id="9c1ba-139">データSQLデータをインポートする前に、DataParser コネクタは自動的にユーザーを自分Microsoft 365メール アドレスにマップMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-139">The SQL DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-sql-dataparser-connector"></a><span data-ttu-id="9c1ba-140">手順 4: DataParser コネクタSQL監視する</span><span class="sxs-lookup"><span data-stu-id="9c1ba-140">Step 4: Monitor the SQL DataParser connector</span></span>

<span data-ttu-id="9c1ba-141">DataParser SQLを作成した後、コネクタの状態を [データ] Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-141">After you create a SQL DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="9c1ba-142">左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9c1ba-143">[コネクタ **] タブを** クリックし、作成した SQL DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-143">Click the **Connectors** tab and then select the SQL DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="9c1ba-144">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="9c1ba-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="9c1ba-145">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9c1ba-146">既知の問題</span><span class="sxs-lookup"><span data-stu-id="9c1ba-146">Known issues</span></span>

<span data-ttu-id="9c1ba-147">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="9c1ba-148">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="9c1ba-148">Support for larger items will be available at a later date.</span></span>
