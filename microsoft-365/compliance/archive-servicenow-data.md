---
title: Microsoft 365 で ServiceNow データをアーカイブするコネクタをセットアップする
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
description: 管理者は、ServiceNow データを Globanet から Microsoft 365 にインポートおよびアーカイブするコネクタをセットアップできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: d9cc40e8d7660be96cefb8ec0d13e2b95bb8f31a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925109"
---
# <a name="set-up-a-connector-to-archive-servicenow-data"></a><span data-ttu-id="80804-105">ServiceNow データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="80804-105">Set up a connector to archive ServiceNow data</span></span>

<span data-ttu-id="80804-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、ServiceNow プラットフォームから Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="80804-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the ServiceNow platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="80804-107">Globanet は [、サードパーティのデータ](https://globanet.com/servicenow/) ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートする ServiceNow コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="80804-107">Globanet provides a [ServiceNow](https://globanet.com/servicenow/) connector that captures items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="80804-108">コネクタは、ServiceNow からのライブ メッセージ、添付ファイル、投稿などのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="80804-108">The connector converts the content such as live messages, attachments, and posts from ServiceNow to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="80804-109">ServiceNow データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="80804-109">After ServiceNow data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="80804-110">ServiceNow コネクタを使用して Microsoft 365 でデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="80804-110">Using a ServiceNow connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-servicenow-data"></a><span data-ttu-id="80804-111">ServiceNow データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="80804-111">Overview of archiving ServiceNow data</span></span>

<span data-ttu-id="80804-112">次の概要では、コネクタを使用して Microsoft 365 の ServiceNow データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="80804-112">The following overview explains the process of using a connector to archive the ServiceNow data in Microsoft 365.</span></span>

![ServiceNow データのアーカイブ ワークフロー](../media/ServiceNowConnectorWorkflow.png)

1. <span data-ttu-id="80804-114">組織は ServiceNow と一緒に ServiceNow サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="80804-114">Your organization works with ServiceNow to set up and configure a ServiceNow site.</span></span>

2. <span data-ttu-id="80804-115">24 時間に 1 回、ServiceNow アイテムは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="80804-115">Once every 24 hours, ServiceNow items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="80804-116">また、コネクタは ServiceNow アイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="80804-116">The connector also converts ServiceNow items to an email message format.</span></span>

3. <span data-ttu-id="80804-117">Microsoft 365 コンプライアンス センターで作成する ServiceNow コネクタは、毎日 Globanet Merge1 サイトに接続し、ServiceNow コンテンツを Microsoft クラウド内の安全な Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="80804-117">The ServiceNow connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the ServiceNow content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="80804-118">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="80804-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="80804-119">**ServiceNow** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="80804-119">A subfolder in the Inbox folder named **ServiceNow** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="80804-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="80804-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="80804-121">すべての ServiceNow アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="80804-121">Every ServiceNow item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="80804-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="80804-122">Before you begin</span></span>

- <span data-ttu-id="80804-123">Microsoft コネクタ用の Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="80804-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="80804-124">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="80804-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="80804-125">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="80804-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="80804-126">ServiceNow アカウントからデータをフェッチする ServiceNow アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="80804-126">Create a ServiceNow application to fetch data from your ServiceNow account.</span></span> <span data-ttu-id="80804-127">アプリケーションの作成の手順については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80804-127">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="80804-128">手順 1 で ServiceNow コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="80804-128">The user who creates the ServiceNow connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="80804-129">Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="80804-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="80804-130">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="80804-130">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="80804-131">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="80804-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="80804-132">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="80804-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="80804-133">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="80804-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-servicenow-connector"></a><span data-ttu-id="80804-134">手順 1: ServiceNow コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="80804-134">Step 1: Set up the ServiceNow connector</span></span>

<span data-ttu-id="80804-135">最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、ServiceNow データ用のコネクタを作成することです。 </span><span class="sxs-lookup"><span data-stu-id="80804-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for ServiceNow data.</span></span>

1. <span data-ttu-id="80804-136">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) 、[データ コネクタ]   >  **[ServiceNow] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="80804-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **ServiceNow**.</span></span>

2. <span data-ttu-id="80804-137">**[ServiceNow 製品の説明]** ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="80804-137">On the **ServiceNow** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="80804-138">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="80804-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="80804-139">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="80804-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="80804-140">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="80804-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-servicenow-on-the-globanet-merge1-site"></a><span data-ttu-id="80804-141">手順 2: Globanet Merge1 サイトで ServiceNow を構成する</span><span class="sxs-lookup"><span data-stu-id="80804-141">Step 2: Configure the ServiceNow on the Globanet Merge1 site</span></span>

<span data-ttu-id="80804-142">2 番目の手順は、Globanet Merge1 サイトで ServiceNow コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="80804-142">The second step is to configure the ServiceNow connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="80804-143">ServiceNow コネクタを構成する方法の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="80804-143">For information about how to configure the ServiceNow connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="80804-144">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="80804-144">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="80804-145">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="80804-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="80804-146">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="80804-146">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="80804-147">**[ServiceNow ユーザーを Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="80804-147">On the **Map ServiceNow users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="80804-148">ServiceNow アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="80804-148">The ServiceNow items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="80804-149">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="80804-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="80804-150">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="80804-150">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-servicenow-connector"></a><span data-ttu-id="80804-151">手順 4: ServiceNow コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="80804-151">Step 4: Monitor the ServiceNow connector</span></span>

<span data-ttu-id="80804-152">ServiceNow コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="80804-152">After you create the ServiceNow connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="80804-153">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="80804-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="80804-154">[コネクタ **] タブをクリック** し **、ServiceNow** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="80804-154">Click the **Connectors** tab and then select the **ServiceNow** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="80804-155">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="80804-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="80804-156">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="80804-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="80804-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="80804-157">Known issues</span></span>

- <span data-ttu-id="80804-158">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="80804-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="80804-159">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="80804-159">Support for larger items will be available at a later date.</span></span>