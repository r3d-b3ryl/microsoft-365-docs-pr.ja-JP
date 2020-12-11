---
title: Microsoft 365 で Reuters FX データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet から Microsoft 365 に Reuters FX データをインポートしてアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 40988b103f0130c78d9450e0ce4ea2d848c891a0
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619803"
---
# <a name="set-up-a-connector-to-archive-reuters-fx-data"></a><span data-ttu-id="48910-105">Reuters FX データをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="48910-105">Set up a connector to archive Reuters FX data</span></span>

<span data-ttu-id="48910-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Reuters FX プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="48910-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters FX platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="48910-107">Globanet は、サード パーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Reuters FX](https://globanet.com/reuters-fx/) コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="48910-107">Globanet provides you with a [Reuters FX](https://globanet.com/reuters-fx/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="48910-108">コネクタは、通貨と FX レートを Reuters FX アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="48910-108">The connector converts the currencies and FX rates from the Reuters FX account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="48910-109">Reuters FX データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="48910-109">After Reuters FX data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="48910-110">Reuters FX コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="48910-110">Using a Reuters FX connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-fx-data"></a><span data-ttu-id="48910-111">アーカイブ Reuters FX データの概要</span><span class="sxs-lookup"><span data-stu-id="48910-111">Overview of archiving Reuters FX data</span></span>

<span data-ttu-id="48910-112">次の概要では、コネクタを使用して Microsoft 365 で Reuters FX データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="48910-112">The following overview explains the process of using a connector to archive Reuters FX data in Microsoft 365.</span></span>

![Reuters FX データのアーカイブ ワークフロー](../media/ReutersFXConnectorWorkflow.png)

1. <span data-ttu-id="48910-114">組織は Reuters FX と共同で、Reuters FX サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="48910-114">Your organization works with Reuters FX to set up and configure a Reuters FX site.</span></span>

2. <span data-ttu-id="48910-115">24 時間ごとに、Reuters FX アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="48910-115">Once every 24 hours, Reuters FX items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="48910-116">コネクタは、アイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="48910-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="48910-117">Microsoft 365 コンプライアンス センターで作成する Reuters FX コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にコンテンツを転送します。</span><span class="sxs-lookup"><span data-stu-id="48910-117">The Reuters FX connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="48910-118">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="48910-118">The connector imports the items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="48910-119">**Reuters FX** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="48910-119">A subfolder in the Inbox folder named **Reuters FX** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="48910-120">コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="48910-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="48910-121">すべての Reuters FX アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="48910-121">Every Reuters FX item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="48910-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="48910-122">Before you begin</span></span>

- <span data-ttu-id="48910-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="48910-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="48910-124">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us)。</span><span class="sxs-lookup"><span data-stu-id="48910-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="48910-125">手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48910-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="48910-126">手順 1 で Reuters FX コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="48910-126">The user who creates the Reuters FX connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="48910-127">この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="48910-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="48910-128">既定では、この役割は Exchange Online の役割グループには割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="48910-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="48910-129">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="48910-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="48910-130">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="48910-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="48910-131">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48910-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-fx-connector"></a><span data-ttu-id="48910-132">手順 1: Reuters FX コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="48910-132">Step 1: Set up the Reuters FX connector</span></span>

<span data-ttu-id="48910-133">最初の手順は、Microsoft 365 の **[Data Connectors]** ページにアクセスし、Reuters FX データ用のコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="48910-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters FX data.</span></span>

1. <span data-ttu-id="48910-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **Reuters FX**.</span><span class="sxs-lookup"><span data-stu-id="48910-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters FX**.</span></span>

2. <span data-ttu-id="48910-135">**[Reuters FX 製品の** 説明] ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="48910-135">On the **Reuters FX** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="48910-136">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="48910-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="48910-137">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="48910-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="48910-138">コネクタを構成するには、Merge1 アカウントに署名します。</span><span class="sxs-lookup"><span data-stu-id="48910-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-fx-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="48910-139">手順 2: Globanet Merge1 サイトで Reuters FX コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="48910-139">Step 2: Configure the Reuters FX connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="48910-140">2 番目の手順は、Globanet Merge1 サイトで Reuters FX コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="48910-140">The second step is to configure the Reuters FX connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="48910-141">Reuters FX コネクタの構成については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="48910-141">For information about configuring the Reuters FX connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="48910-142">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48910-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="48910-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="48910-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="48910-144">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="48910-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="48910-145">[Map **Reuters FX users to Microsoft 365 users] (Microsoft 365** ユーザーへのマップ) ページで、自動ユーザー マッピングを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="48910-145">On the **Map Reuters FX users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="48910-146">Reuters FX アイテムには、組織内のユーザーの電子メール アドレスを含む Email というプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="48910-146">Reuters FX items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="48910-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="48910-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="48910-148">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="48910-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-fx-connector"></a><span data-ttu-id="48910-149">手順 4: Reuters FX コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="48910-149">Step 4: Monitor the Reuters FX connector</span></span>

<span data-ttu-id="48910-150">Reuters FX コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="48910-150">After you create the Reuters FX connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="48910-151">左側の <https://compliance.microsoft.com/> ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="48910-151">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="48910-152">[ **コネクタ] タブ** をクリックし **、Reuters FX** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="48910-152">Click the **Connectors** tab and then select the **Reuters FX** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="48910-153">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="48910-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="48910-154">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="48910-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="48910-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="48910-155">Known issues</span></span>

- <span data-ttu-id="48910-156">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="48910-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="48910-157">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="48910-157">Support for larger items will be available at a later date.</span></span>
