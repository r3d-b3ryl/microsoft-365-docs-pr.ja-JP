---
title: Microsoft 365 でピボット データをアーカイブするコネクタを設定する
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
description: 管理者は、Microsoft 365 の Globanet からピボット データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 23badcb2a8d2873f03b86499ccfd4c9a96b81090
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620374"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a><span data-ttu-id="3ae1a-104">ピボット データをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="3ae1a-104">Set up a connector to archive Pivot data</span></span>

<span data-ttu-id="3ae1a-105">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、ピボット プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートしてアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Pivot platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="3ae1a-106">Globanet は、サードパーティ[](https://globanet.com/pivot/)のデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたピボット コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-106">Globanet provides you with a [Pivot](https://globanet.com/pivot/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="3ae1a-107">Pivot は、市場参加者との共同作業を可能にするインスタント メッセージング プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-107">Pivot is an instant messaging platform that allows collaboration with financial market participants.</span></span> <span data-ttu-id="3ae1a-108">コネクタは、チャット メッセージなどのアイテムをユーザーの Pivot アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-108">The connector converts items such as chat messages, from a users' Pivot accounts to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="3ae1a-109">ピボット データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-109">After Pivot data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="3ae1a-110">ピボット コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-110">Using a Pivot connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-pivot-data"></a><span data-ttu-id="3ae1a-111">ピボット データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="3ae1a-111">Overview of archiving Pivot data</span></span>

<span data-ttu-id="3ae1a-112">次の概要では、コネクタを使用して Microsoft 365 のピボット データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-112">The following overview explains the process of using a connector to archive the Pivot data in Microsoft 365.</span></span>

![ピボット データのアーカイブ ワークフロー](../media/PivotConnectorWorkflow.png)

1. <span data-ttu-id="3ae1a-114">組織は Pivot と共同でピボット ソース サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-114">Your organization works with Pivot to set up and configure a Pivot source site.</span></span>

2. <span data-ttu-id="3ae1a-115">24 時間ごとに、Pivot アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-115">Once every 24 hours, Pivot items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="3ae1a-116">コネクタは、ピボット アイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-116">The connector also converts the Pivot items to an email message format.</span></span>

3. <span data-ttu-id="3ae1a-117">Microsoft 365 コンプライアンス センターで作成するピボット コネクタは、毎日 Globanet Merge1 サイトに接続し、ピボット アイテムを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-117">The Pivot connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the Pivot items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="3ae1a-118">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、ピボット アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-118">The connector imports the Pivot items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="3ae1a-119">ユーザーのメールボックスに **Pivot** という名前の受信トレイ フォルダー内のサブフォルダーが作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-119">A subfolder in the Inbox folder named **Pivot** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="3ae1a-120">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="3ae1a-121">すべてのピボット アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-121">Every Pivot item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3ae1a-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="3ae1a-122">Before you begin</span></span>

- <span data-ttu-id="3ae1a-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="3ae1a-124">このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact/)。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-124">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="3ae1a-125">このアカウントは、手順 1 でコネクタを作成するときにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="3ae1a-126">手順 1 でピボット コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-126">The user who creates the Pivot connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="3ae1a-127">この役割は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3ae1a-128">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="3ae1a-129">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3ae1a-130">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="3ae1a-131">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-pivot-connector"></a><span data-ttu-id="3ae1a-132">手順 1: ピボット コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="3ae1a-132">Step 1: Set up the Pivot connector</span></span>

<span data-ttu-id="3ae1a-133">最初の手順は、Microsoft コンプライアンス センターの **[データ** コネクタ] ページにアクセスし、ピボット データ用のコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-133">The first step is to access to the **Data Connectors** page in the Microsoft compliance center and create a connector for Pivot data.</span></span>

1. <span data-ttu-id="3ae1a-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **Pivot**.</span><span class="sxs-lookup"><span data-stu-id="3ae1a-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Pivot**.</span></span>

2. <span data-ttu-id="3ae1a-135">ピボット製品の **説明ページ** で、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-135">On the **Pivot** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="3ae1a-136">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="3ae1a-137">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="3ae1a-138">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-pivot-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="3ae1a-139">手順 2: Globanet Merge1 サイトでピボット コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="3ae1a-139">Step 2: Configure the Pivot connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="3ae1a-140">2 番目の手順は、Merge1 サイトでピボット コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-140">The second step is to configure the Pivot connector on the Merge1 site.</span></span> <span data-ttu-id="3ae1a-141">Globanet Merge1 サイトでピボット コネクタを構成する方法については [、「Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-141">For information about how to configure the Pivot connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="3ae1a-142">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="3ae1a-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="3ae1a-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="3ae1a-144">ユーザーをマップし、Microsoft 356 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-144">To map users and complete the connector setup in the Microsoft 356 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="3ae1a-145">[ピボット ユーザー **を Microsoft 365 ユーザーに** マップする] ページで、ユーザーの自動マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-145">On the **Map Pivot users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="3ae1a-146">ピボット アイテムには、組織内のユーザー *の電子* メール アドレスを含む Email というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-146">The Pivot items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="3ae1a-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="3ae1a-148">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-pivot-connector"></a><span data-ttu-id="3ae1a-149">手順 4: ピボット コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="3ae1a-149">Step 4: Monitor the Pivot connector</span></span>

<span data-ttu-id="3ae1a-150">ピボット コネクタを作成すると、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-150">After you create the Pivot connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3ae1a-151">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3ae1a-152">[ **コネクタ] タブを** クリックし、ピボット **コネクタを選択** して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-152">Click the **Connectors** tab and then select the **Pivot** connector to display the flyout page.</span></span> <span data-ttu-id="3ae1a-153">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="3ae1a-154">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="3ae1a-155">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-155">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3ae1a-156">既知の問題</span><span class="sxs-lookup"><span data-stu-id="3ae1a-156">Known issues</span></span>

- <span data-ttu-id="3ae1a-157">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="3ae1a-158">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3ae1a-158">Support for larger items will be available at a later date.</span></span>
