---
title: Microsoft 365 で ServiceNow データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet から Microsoft 365 に ServiceNow データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 99b1f64bdb1d977816d4881fa633d77acd60952c
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740334"
---
# <a name="set-up-a-connector-to-archive-servicenow-data"></a><span data-ttu-id="5032b-105">ServiceNow データをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="5032b-105">Set up a connector to archive ServiceNow data</span></span>

<span data-ttu-id="5032b-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、ServiceNow プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="5032b-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the ServiceNow platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="5032b-107">Globanet は、サード パーティのデータ ソースからアイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートする [ServiceNow](https://globanet.com/servicenow/) コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="5032b-107">Globanet provides a [ServiceNow](https://globanet.com/servicenow/) connector that captures items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="5032b-108">コネクタは、ServiceNow からのライブ メッセージ、添付ファイル、投稿などのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="5032b-108">The connector converts the content such as live messages, attachments, and posts from ServiceNow to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="5032b-109">ServiceNow データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5032b-109">After ServiceNow data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="5032b-110">ServiceNow コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5032b-110">Using a ServiceNow connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-servicenow-data"></a><span data-ttu-id="5032b-111">ServiceNow データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="5032b-111">Overview of archiving ServiceNow data</span></span>

<span data-ttu-id="5032b-112">次の概要では、コネクタを使用して Microsoft 365 の ServiceNow データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5032b-112">The following overview explains the process of using a connector to archive the ServiceNow data in Microsoft 365.</span></span>

![ServiceNow データのアーカイブ ワークフロー](../media/ServiceNowConnectorWorkflow.png)

1. <span data-ttu-id="5032b-114">組織は ServiceNow と共同で ServiceNow サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="5032b-114">Your organization works with ServiceNow to set up and configure a ServiceNow site.</span></span>

2. <span data-ttu-id="5032b-115">24 時間ごとに、ServiceNow アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="5032b-115">Once every 24 hours, ServiceNow items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="5032b-116">コネクタは、ServiceNow アイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="5032b-116">The connector also converts ServiceNow items to an email message format.</span></span>

3. <span data-ttu-id="5032b-117">Microsoft 365 コンプライアンス センターで作成する ServiceNow コネクタは、毎日 Globanet Merge1 サイトに接続し、ServiceNow コンテンツを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="5032b-117">The ServiceNow connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the ServiceNow content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="5032b-118">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたアイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="5032b-118">The connector imports the converted items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="5032b-119">ServiceNow という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5032b-119">A subfolder in the Inbox folder named **ServiceNow** is created in the user mailboxes, and items are imported to that folder.</span></span> <span data-ttu-id="5032b-120">コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="5032b-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="5032b-121">すべての ServiceNow アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="5032b-121">Every ServiceNow item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5032b-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="5032b-122">Before you begin</span></span>

- <span data-ttu-id="5032b-123">Microsoft コネクタの Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5032b-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="5032b-124">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="5032b-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="5032b-125">手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5032b-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="5032b-126">ServiceNow アカウントからデータを取得する ServiceNow アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="5032b-126">Create a ServiceNow application to fetch data from your ServiceNow account.</span></span> <span data-ttu-id="5032b-127">アプリケーションの作成に関する詳しい手順については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="5032b-127">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="5032b-128">手順 1 で ServiceNow コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5032b-128">The user who creates the ServiceNow connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="5032b-129">この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="5032b-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5032b-130">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="5032b-130">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="5032b-131">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5032b-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="5032b-132">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="5032b-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="5032b-133">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5032b-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-servicenow-connector"></a><span data-ttu-id="5032b-134">手順 1: ServiceNow コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="5032b-134">Step 1: Set up the ServiceNow connector</span></span>

<span data-ttu-id="5032b-135">最初の手順は、Microsoft 365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、ServiceNow データのコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="5032b-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for ServiceNow data.</span></span>

1. <span data-ttu-id="5032b-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **ServiceNow**.</span><span class="sxs-lookup"><span data-stu-id="5032b-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **ServiceNow**.</span></span>

2. <span data-ttu-id="5032b-137">**ServiceNow 製品の説明** ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5032b-137">On the **ServiceNow** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="5032b-138">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5032b-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="5032b-139">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="5032b-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="5032b-140">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="5032b-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-servicenow-on-the-globanet-merge1-site"></a><span data-ttu-id="5032b-141">手順 2: Globanet Merge1 サイトで ServiceNow を構成する</span><span class="sxs-lookup"><span data-stu-id="5032b-141">Step 2: Configure the ServiceNow on the Globanet Merge1 site</span></span>

<span data-ttu-id="5032b-142">2 番目の手順は、Globanet Merge1 サイトで ServiceNow コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="5032b-142">The second step is to configure the ServiceNow connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="5032b-143">ServiceNow コネクタを構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="5032b-143">For information about how to configure the ServiceNow connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20ServiceNow%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="5032b-144">[Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5032b-144">After you click **Save & Finish,** the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="5032b-145">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="5032b-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="5032b-146">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5032b-146">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="5032b-147">**[ServiceNow ユーザーを Microsoft 365** ユーザーにマップする] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="5032b-147">On the **Map ServiceNow users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="5032b-148">ServiceNow アイテムには、組織内のユーザーの電子メール アドレスを含む Email というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5032b-148">The ServiceNow items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="5032b-149">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5032b-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="5032b-150">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="5032b-150">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-servicenow-connector"></a><span data-ttu-id="5032b-151">手順 4: ServiceNow コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="5032b-151">Step 4: Monitor the ServiceNow connector</span></span>

<span data-ttu-id="5032b-152">ServiceNow コネクタを作成すると、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5032b-152">After you create the ServiceNow connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="5032b-153">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="5032b-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="5032b-154">[ **コネクタ] タブ** をクリックし **、ServiceNow** コネクタを選択して、コネクタに関するプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="5032b-154">Click the **Connectors** tab and then select the **ServiceNow** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="5032b-155">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="5032b-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="5032b-156">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5032b-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="5032b-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5032b-157">Known issues</span></span>

- <span data-ttu-id="5032b-158">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5032b-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="5032b-159">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="5032b-159">Support for larger items will be available at a later date.</span></span>
