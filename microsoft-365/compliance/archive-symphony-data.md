---
title: Microsoft 365 でアーカイブするコネクタを設定する
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
description: 管理者は、Globanet Gloy から Microsoft 365 にデータをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 94bd9bb8f2b7586e685769af389d6cd0a0ea18ac
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619833"
---
# <a name="set-up-a-connector-to-archive-symphony-data"></a><span data-ttu-id="91818-105">コネクタをセットアップして、アーカイブアーカイブデータを保存する</span><span class="sxs-lookup"><span data-stu-id="91818-105">Set up a connector to archive Symphony data</span></span>

<span data-ttu-id="91818-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Microsoft 365 組織内のユーザー メールボックスに対して、アーカイブされたデータをインポートしてアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="91818-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive Symphony data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="91818-107">金融サービス業界で使用されるメッセージングおよびコラボレーション プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="91818-107">Symphony is a messaging and collaboration platform used in the financial services industry.</span></span> <span data-ttu-id="91818-108">Globanet は、Microsoft 365 コンプライアンス センターで、サード パーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムをユーザーのメールボックスにインポートするために構成できる、 [多](https://globanet.com/symphony) くのデータ コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="91818-108">Globanet provides a [Symphony](https://globanet.com/symphony) data connector in the Microsoft 365 compliance center that you can configure to capture items from the third-party data source (on a regular basis) and then import those items to user mailboxes.</span></span> <span data-ttu-id="91818-109">コネクタは、アイテムのコンテンツを 1 つの電子メール メッセージ形式に変換し、そのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="91818-109">The connector converts the content of an item from the Symphony account to an email message format and then imports the item to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="91818-110">After Symphony communications are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span><span class="sxs-lookup"><span data-stu-id="91818-110">After Symphony communications are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="91818-111">Microsoft 365 のデータをインポートおよびアーカイブするために、多くのコネクタを使用すると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="91818-111">Using a Symphony connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-symphony-data"></a><span data-ttu-id="91818-112">アーカイブアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="91818-112">Overview of archiving Symphony data</span></span>

<span data-ttu-id="91818-113">次の概要では、データ コネクタを使用して Microsoft 365 の多くの通信をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="91818-113">The following overview explains the process of using a data connector to archive Symphony communications in Microsoft 365.</span></span>

![アーカイブ ワークフローのアーカイブ](../media/SymphonyConnectorWorkflow.png)

1. <span data-ttu-id="91818-115">組織は、立ち上がりサイトのセットアップと構成を行う場合に、立ち上げと構成を行います。</span><span class="sxs-lookup"><span data-stu-id="91818-115">Your organization works with Symphony to set up and configure a Symphony site.</span></span>

2. <span data-ttu-id="91818-116">24 時間に 1 回、Gloy からのチャット メッセージが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="91818-116">Once every 24 hours, chat messages from Symphony are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="91818-117">コネクタは、チャット メッセージの内容を電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="91818-117">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="91818-118">Microsoft 365 コンプライアンス センターで作成する多角形コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="91818-118">The Symphony connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="91818-119">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="91818-119">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="91818-120">ユーザーメールボックスに Inbox フォルダー内の **新しいサブフォルダーが作成** され、メッセージ アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="91818-120">A new subfolder in the Inbox folder named **Symphony** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="91818-121">コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="91818-121">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="91818-122">すべてのチャット メッセージには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="91818-122">Every chat message contains this property, which is populated with the email address for every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="91818-123">はじめに</span><span class="sxs-lookup"><span data-stu-id="91818-123">Before you begin</span></span>

- <span data-ttu-id="91818-124">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="91818-124">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="91818-125">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="91818-125">To create an account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="91818-126">このアカウントは、手順 1 でコネクタを作成するときにサインインします。</span><span class="sxs-lookup"><span data-stu-id="91818-126">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="91818-127">手順 1 で作成した (および手順 3 で完了する) ユーザーは、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="91818-127">The user who creates the Symphony connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="91818-128">この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="91818-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="91818-129">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="91818-129">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="91818-130">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="91818-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="91818-131">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="91818-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="91818-132">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="91818-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-symphony-connector"></a><span data-ttu-id="91818-133">手順 1: コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="91818-133">Step 1: Set up the Symphony connector</span></span>

<span data-ttu-id="91818-134">最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、多くのデータのコネクタを作成することです。 </span><span class="sxs-lookup"><span data-stu-id="91818-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Symphony data.</span></span>

1. <span data-ttu-id="91818-135">[データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタの数] に  >  **移動してクリックします**。</span><span class="sxs-lookup"><span data-stu-id="91818-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Symphony**.</span></span>

2. <span data-ttu-id="91818-136">[ **日本製品の説明** ] ページで、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="91818-136">On the **Symphony** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="91818-137">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="91818-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="91818-138">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="91818-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="91818-139">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="91818-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="91818-140">Globanet Merge1 サイトでコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="91818-140">Configure the Symphony connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="91818-141">2 番目の手順は、Merge1 サイト上の新しいコネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="91818-141">The second step is to configure the Symphony connector on the Merge1 site.</span></span> <span data-ttu-id="91818-142">Globanet Merge1 サイトでコネクタを構成する方法については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91818-142">For information about configuring  the Symphony connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="91818-143">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91818-143">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="91818-144">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="91818-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="91818-145">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="91818-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="91818-146">[外部ユーザー **を Microsoft 365 ユーザーに** マップする] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="91818-146">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="91818-147">多くのアイテムには、組織内のユーザーの電子メール アドレスを含む Email というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="91818-147">The Symphony items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="91818-148">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="91818-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="91818-149">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="91818-149">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-symphony-connector"></a><span data-ttu-id="91818-150">手順 4: コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="91818-150">Step 4: Monitor the Symphony connector</span></span>

<span data-ttu-id="91818-151">コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="91818-151">After you create the Symphony connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="91818-152">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="91818-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="91818-153">[ **コネクタ] タブを** クリックし、コネクタ **を** 選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="91818-153">Click the **Connectors** tab and then select the **Symphony** connector to display the flyout page.</span></span> <span data-ttu-id="91818-154">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="91818-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="91818-155">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="91818-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="91818-156">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="91818-156">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="91818-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="91818-157">Known issues</span></span>

- <span data-ttu-id="91818-158">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="91818-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="91818-159">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="91818-159">Support for larger items will be available at a later date.</span></span>
