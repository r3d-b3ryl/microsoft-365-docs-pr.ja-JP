---
title: Microsoft 365 で Yieldbroker データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet から Microsoft 365 に Yieldbroker データをインポートしてアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 1591198dae3a7a5082c4f8f7ba925eb9e6dd680b
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722980"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data-preview"></a><span data-ttu-id="2cec9-105">Yieldbroker データをアーカイブするコネクタを設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2cec9-105">Set up a connector to archive Yieldbroker data (preview)</span></span>

<span data-ttu-id="2cec9-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Yieldbroker から Microsoft 365 組織内のユーザー メールボックスにデータをインポートしてアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="2cec9-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Yieldbroker to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="2cec9-107">Globanet は、サード パーティのデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Yieldbroker](https://globanet.com/yieldbroker/) コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-107">Globanet provides you with a [Yieldbroker](https://globanet.com/yieldbroker/) connector that's configured to capture items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="2cec9-108">コネクタは、コンテンツを Yieldbroker から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="2cec9-108">The connector converts the content from Yieldbroker to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="2cec9-109">Yieldbroker がユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-109">After Yieldbroker is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="2cec9-110">Yieldbroker コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-110">Using a Yieldbroker connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-yieldbroker-data"></a><span data-ttu-id="2cec9-111">Yieldbroker データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="2cec9-111">Overview of archiving Yieldbroker data</span></span>

<span data-ttu-id="2cec9-112">次の概要では、コネクタを使用して Microsoft 365 の Yieldbroker データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-112">The following overview explains the process of using a connector to archive the Yieldbroker data in Microsoft 365.</span></span>

![Yieldbroker データのアーカイブ ワークフロー](../media/YieldbrokerConnectorWorkflow.png)

1. <span data-ttu-id="2cec9-114">組織は Yieldbroker と共同で Yieldbroker サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-114">Your organization works with the Yieldbroker to set up and configure a Yieldbroker site.</span></span>

2. <span data-ttu-id="2cec9-115">24 時間ごとに、Yieldbroker アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-115">Once every 24 hours, Yieldbroker items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="2cec9-116">コネクタは、コンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-116">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="2cec9-117">Microsoft 365 コンプライアンス センターで作成する Yieldbroker コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-117">The Yieldbroker connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="2cec9-118">コネクタは、ステップ 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Yieldbroker アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="2cec9-118">The connector imports the converted Yieldbroker items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="2cec9-119">ユーザー メールボックスに **Yieldbroker** という名前の受信トレイ フォルダー内のサブフォルダーが作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-119">A subfolder in the Inbox folder named **Yieldbroker** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="2cec9-120">コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="2cec9-121">すべての Yieldbroker にはこのプロパティが含まれているので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-121">Every Yieldbroker contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2cec9-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="2cec9-122">Before you begin</span></span>

- <span data-ttu-id="2cec9-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="2cec9-124">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="2cec9-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="2cec9-125">手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cec9-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="2cec9-126">手順 1 で Yieldbroker コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cec9-126">The user who creates the Yieldbroker connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="2cec9-127">この役割は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="2cec9-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2cec9-128">既定では、この役割は Exchange Online の役割グループには割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="2cec9-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="2cec9-129">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="2cec9-130">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="2cec9-131">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cec9-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-yieldbroker-connector"></a><span data-ttu-id="2cec9-132">手順 1: Yieldbroker コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="2cec9-132">Step 1: Set up the Yieldbroker connector</span></span>

<span data-ttu-id="2cec9-133">最初の手順は、Microsoft 365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、Yieldbroker のコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="2cec9-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for the Yieldbroker.</span></span>

1. <span data-ttu-id="2cec9-134">[データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ &gt; **Yieldbroker] に移動してクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2cec9-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** &gt; **Yieldbroker**.</span></span>

2. <span data-ttu-id="2cec9-135">**Yieldbroker 製品の説明ページ** で、[新しいコネクタの追加 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2cec9-135">On the **Yieldbroker** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="2cec9-136">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2cec9-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="2cec9-137">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="2cec9-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="2cec9-138">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2cec9-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-yieldbroker-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="2cec9-139">手順 2: Globanet Merge1 サイトで Yieldbroker コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="2cec9-139">Step 2: Configure the Yieldbroker connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="2cec9-140">2 番目の手順は、Merge1 サイトで Yieldbroker コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="2cec9-140">The second step is to configure the Yieldbroker connector on the Merge1 site.</span></span> <span data-ttu-id="2cec9-141">Yieldbroker を構成する方法については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cec9-141">For information about how to configure the Yieldbroker, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="2cec9-142">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="2cec9-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="2cec9-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="2cec9-144">ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-144">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="2cec9-145">**[Yieldbroker ユーザーを Microsoft 365 ユーザーに** マップする] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2cec9-145">On the **Map Yieldbroker users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="2cec9-146">Yieldbroker アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-146">The Yieldbroker items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="2cec9-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="2cec9-148">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-yieldbroker-connector"></a><span data-ttu-id="2cec9-149">手順 4: Yieldbroker コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="2cec9-149">Step 4: Monitor the Yieldbroker connector</span></span>

<span data-ttu-id="2cec9-150">Yieldbroker コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-150">After you create the Yieldbroker connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="2cec9-151">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cec9-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="2cec9-152">[ **コネクタ] タブ** をクリックし **、Yieldbroker** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="2cec9-152">Click the **Connectors** tab and then select the **Yieldbroker** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="2cec9-153">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cec9-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="2cec9-154">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2cec9-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2cec9-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="2cec9-155">Known issues</span></span>

- <span data-ttu-id="2cec9-156">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2cec9-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="2cec9-157">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="2cec9-157">Support for larger items will be available at a later date.</span></span>
