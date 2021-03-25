---
title: Microsoft 365 でシンフォニー データをアーカイブするコネクタをセットアップする
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
description: 管理者は、Veritas Symphony から Microsoft 365 にデータをインポートおよびアーカイブするコネクタをセットアップできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: b3ddb6826f7ef68808a819ee1d860b020efea98a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163981"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a><span data-ttu-id="12c64-105">シンフォニー データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="12c64-105">Set up a connector to archive Symphony data</span></span>

<span data-ttu-id="12c64-106">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、Microsoft 365 組織のユーザー メールボックスにシンフォニー データをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="12c64-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive Symphony data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="12c64-107">シンフォニーは、金融サービス業界で使用されるメッセージングとコラボレーション プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="12c64-107">Symphony is a messaging and collaboration platform used in the financial services industry.</span></span> <span data-ttu-id="12c64-108">Veritas は[](https://globanet.com/symphony)、Microsoft 365 コンプライアンス センターにシンフォニー データ コネクタを提供し、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムをユーザー メールボックスにインポートするために構成できます。</span><span class="sxs-lookup"><span data-stu-id="12c64-108">Veritas provides a [Symphony](https://globanet.com/symphony) data connector in the Microsoft 365 compliance center that you can configure to capture items from the third-party data source (on a regular basis) and then import those items to user mailboxes.</span></span> <span data-ttu-id="12c64-109">コネクタは、アイテムのコンテンツをシンフォニー アカウントから電子メール メッセージ形式に変換し、そのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="12c64-109">The connector converts the content of an item from the Symphony account to an email message format and then imports the item to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="12c64-110">ユーザー メールボックスにシンフォニー通信が格納された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="12c64-110">After Symphony communications are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="12c64-111">Microsoft 365 でシンフォニー コネクタを使用してデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="12c64-111">Using a Symphony connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-symphony-data"></a><span data-ttu-id="12c64-112">シンフォニー データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="12c64-112">Overview of archiving Symphony data</span></span>

<span data-ttu-id="12c64-113">次の概要では、データ コネクタを使用して Microsoft 365 のシンフォニー通信をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="12c64-113">The following overview explains the process of using a data connector to archive Symphony communications in Microsoft 365.</span></span>

![シンフォニー のアーカイブ ワークフロー](../media/SymphonyConnectorWorkflow.png)

1. <span data-ttu-id="12c64-115">組織は、シンフォニーと一緒にシンフォニー サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="12c64-115">Your organization works with Symphony to set up and configure a Symphony site.</span></span>

2. <span data-ttu-id="12c64-116">24 時間に 1 回、シンフォニーからのチャット メッセージが Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="12c64-116">Once every 24 hours, chat messages from Symphony are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="12c64-117">また、コネクタはチャット メッセージのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="12c64-117">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="12c64-118">Microsoft 365 コンプライアンス センターで作成するシンフォニー コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage の場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="12c64-118">The Symphony connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="12c64-119">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="12c64-119">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="12c64-120">**シン** フォニーという名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー メールボックスに作成され、メッセージ アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="12c64-120">A new subfolder in the Inbox folder named **Symphony** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="12c64-121">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="12c64-121">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="12c64-122">すべてのチャット メッセージには、このプロパティが含まれるので、参加者ごとに電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="12c64-122">Every chat message contains this property, which is populated with the email address for every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="12c64-123">はじめに</span><span class="sxs-lookup"><span data-stu-id="12c64-123">Before you begin</span></span>

- <span data-ttu-id="12c64-124">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="12c64-124">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="12c64-125">アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="12c64-125">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="12c64-126">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="12c64-126">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="12c64-127">手順 1 でシンフォニー コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="12c64-127">The user who creates the Symphony connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="12c64-128">Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="12c64-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="12c64-129">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="12c64-129">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="12c64-130">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="12c64-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="12c64-131">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="12c64-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="12c64-132">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="12c64-132">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-symphony-connector"></a><span data-ttu-id="12c64-133">手順 1: シンフォニー コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="12c64-133">Step 1: Set up the Symphony connector</span></span>

<span data-ttu-id="12c64-134">最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、シンフォニー データ用のコネクタを作成することです。 </span><span class="sxs-lookup"><span data-stu-id="12c64-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Symphony data.</span></span>

1. <span data-ttu-id="12c64-135">[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) シンフォニー]**に移動し、[データ コネクタ**  >  **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="12c64-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Symphony**.</span></span>

2. <span data-ttu-id="12c64-136">[シンフォ **ニー製品の説明** ] ページで、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="12c64-136">On the **Symphony** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="12c64-137">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="12c64-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="12c64-138">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="12c64-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="12c64-139">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="12c64-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="configure-the-symphony-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="12c64-140">Veritas Merge1 サイトでシンフォニー コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="12c64-140">Configure the Symphony connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="12c64-141">2 番目の手順は、Merge1 サイトでシンフォニー コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="12c64-141">The second step is to configure the Symphony connector on the Merge1 site.</span></span> <span data-ttu-id="12c64-142">Veritas Merge1 サイトでのシンフォニー コネクタの構成の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12c64-142">For information about configuring  the Symphony connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="12c64-143">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12c64-143">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="12c64-144">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="12c64-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="12c64-145">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="12c64-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="12c64-146">[外部ユーザー **を Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="12c64-146">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="12c64-147">シンフォニー アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="12c64-147">The Symphony items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="12c64-148">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="12c64-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="12c64-149">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="12c64-149">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-symphony-connector"></a><span data-ttu-id="12c64-150">手順 4: シンフォニー コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="12c64-150">Step 4: Monitor the Symphony connector</span></span>

<span data-ttu-id="12c64-151">シンフォニー コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="12c64-151">After you create the Symphony connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="12c64-152">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="12c64-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="12c64-153">[コネクタ **] タブをクリック** し、シンフォニー コネクタ **を選択** して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="12c64-153">Click the **Connectors** tab and then select the **Symphony** connector to display the flyout page.</span></span> <span data-ttu-id="12c64-154">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="12c64-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="12c64-155">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="12c64-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="12c64-156">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="12c64-156">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="12c64-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="12c64-157">Known issues</span></span>

- <span data-ttu-id="12c64-158">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="12c64-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="12c64-159">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="12c64-159">Support for larger items will be available at a later date.</span></span>