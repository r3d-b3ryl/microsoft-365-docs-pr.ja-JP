---
title: リングセントラル データをアーカイブするコネクタを設定Microsoft 365
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
description: 管理者は、RingCentral データを Veritas からユーザーにインポートおよびアーカイブするコネクタをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、電子情報開示、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 4fc0b61d5bc47a573da3ef8dd12654316e77d073
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408938"
---
# <a name="set-up-a-connector-to-archive-ringcentral-data-preview"></a><span data-ttu-id="23410-105">RingCentral データをアーカイブするコネクタをセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="23410-105">Set up a connector to archive RingCentral data (preview)</span></span>

<span data-ttu-id="23410-106">サーバーの Veritas コネクタを使用Microsoft 365 コンプライアンス センター、RingCentral プラットフォームから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="23410-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the RingCentral platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="23410-107">Veritas には、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された RingCentral コネクタMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="23410-107">Veritas provides the RingCentral connector that is configured to capture items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="23410-108">コネクタは、チャット、添付ファイル、タスク、メモ、投稿などのコンテンツを RingCentral から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="23410-108">The connector converts content such as chats, attachments, tasks, notes, and posts from RingCentral to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="23410-109">RingCentral データをユーザー のメールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルMicrosoft 365コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="23410-109">After RingCentral data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels.</span></span> <span data-ttu-id="23410-110">RingCentral コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="23410-110">Using a RingCentral connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-ringcentral-data"></a><span data-ttu-id="23410-111">RingCentral データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="23410-111">Overview of archiving RingCentral data</span></span>

<span data-ttu-id="23410-112">次の概要では、コネクタを使用して、アプリケーション内の RingCentral データをアーカイブするMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="23410-112">The following overview explains the process of using a connector to archive the RingCentral data in Microsoft 365.</span></span>

![RingCentral データのアーカイブ ワークフロー](../media/RingCentralConnectorWorkflow.png)

1. <span data-ttu-id="23410-114">組織は RingCentral を使用して、RingCentral サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="23410-114">Your organization works with RingCentral to set up and configure a RingCentral site.</span></span>

2. <span data-ttu-id="23410-115">24 時間に 1 回、RingCentral アイテムは Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="23410-115">Once every 24 hours, RingCentral items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="23410-116">また、コネクタは RingCentral アイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="23410-116">The connector also converts RingCentral items to an email message format.</span></span>

3. <span data-ttu-id="23410-117">Microsoft 365 コンプライアンス センター で作成した RingCentral コネクタは、毎日 Veritas Merge1 サイトに接続し、RingCentral コンテンツを Microsoft クラウド内の安全な Azure Storage 場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="23410-117">The RingCentral connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day, and transfers the RingCentral content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="23410-118">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="23410-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="23410-119">**RingCentral** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="23410-119">A subfolder in the Inbox folder named **RingCentral** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="23410-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="23410-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="23410-121">すべての RingCentral アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="23410-121">Every RingCentral item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="23410-122">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="23410-122">Before you set up a connector</span></span>

- <span data-ttu-id="23410-123">Microsoft コネクタ用の Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="23410-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="23410-124">このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/form/requestacall/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="23410-124">To create this account, contact [Veritas Customer Support](https://www.veritas.com/form/requestacall/ms-connectors-contact).</span></span> <span data-ttu-id="23410-125">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="23410-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="23410-126">RingCentral アカウントからデータをフェッチする RingCentral アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="23410-126">Create a RingCentral application to fetch data from your RingCentral account.</span></span> <span data-ttu-id="23410-127">アプリケーションの作成の手順については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23410-127">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).</span></span>

- <span data-ttu-id="23410-128">手順 1 で RingCentral コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="23410-128">The user who creates the RingCentral connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="23410-129">この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="23410-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="23410-130">既定では、この役割は、グループ内の任意の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="23410-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="23410-131">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="23410-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="23410-132">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="23410-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="23410-133">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="23410-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-ringcentral-connector"></a><span data-ttu-id="23410-134">手順 1: RingCentral コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="23410-134">Step 1: Set up the RingCentral connector</span></span>

<span data-ttu-id="23410-135">最初の手順は、データ センターの [データ コネクタ] ページにアクセスし、RingCentral Microsoft 365 コンプライアンス センターコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="23410-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for RingCentral data.</span></span>

1. <span data-ttu-id="23410-136">に移動し <https://compliance.microsoft.com> 、[データ コネクタ **]**  >  **[RingCentral] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="23410-136">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **RingCentral**.</span></span>

2. <span data-ttu-id="23410-137">**[RingCentral 製品の説明]** ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="23410-137">On the **RingCentral** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="23410-138">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="23410-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="23410-139">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="23410-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="23410-140">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="23410-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-ringcentral-on-the-veritas-merge1-site"></a><span data-ttu-id="23410-141">手順 2: Veritas Merge1 サイトで RingCentral を構成する</span><span class="sxs-lookup"><span data-stu-id="23410-141">Step 2: Configure the RingCentral on the Veritas Merge1 site</span></span>

<span data-ttu-id="23410-142">2 番目の手順は、Veritas Merge1 サイトで RingCentral コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="23410-142">The second step is to configure the RingCentral connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="23410-143">RingCentral コネクタを構成する方法の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23410-143">For information about how to configure the RingCentral connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20RingCentral%20User%20Guide.pdf).</span></span>

<span data-ttu-id="23410-144">[ファイルの **保存と&完了]** をクリックすると、コネクタ ウィザードの [ユーザー マッピング] ページが表示Microsoft 365 コンプライアンス センターされます。</span><span class="sxs-lookup"><span data-stu-id="23410-144">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="23410-145">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="23410-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="23410-146">ユーザーをマップし、コネクタのセットアップを完了するには、次Microsoft 365 コンプライアンス センター手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="23410-146">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="23410-147">**[RingCentral ユーザーをユーザーにMicrosoft 365する]** ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="23410-147">On the **Map RingCentral users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="23410-148">RingCentral アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="23410-148">The RingCentral items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="23410-149">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="23410-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="23410-150">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="23410-150">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-ringcentral-connector"></a><span data-ttu-id="23410-151">手順 4: RingCentral コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="23410-151">Step 4: Monitor the RingCentral connector</span></span>

<span data-ttu-id="23410-152">RingCentral コネクタを作成した後は、コネクタの状態を [コネクタ] Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="23410-152">After you create the RingCentral connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="23410-153">左側の <https://compliance.microsoft.com/> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="23410-153">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="23410-154">[コネクタ **] タブをクリック** し **、RingCentral** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="23410-154">Click the **Connectors** tab and then select the **RingCentral** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="23410-155">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="23410-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="23410-156">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="23410-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="23410-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="23410-157">Known issues</span></span>

- <span data-ttu-id="23410-158">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="23410-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="23410-159">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="23410-159">Support for larger items will be available at a later date.</span></span>
