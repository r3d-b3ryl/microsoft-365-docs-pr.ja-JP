---
title: Microsoft 365 で EML データをアーカイブするコネクタをセットアップする
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
description: 管理者は、Globanet から Microsoft 365 に EML データをインポートおよびアーカイブするコネクタをセットアップできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: a7495ea4accd2a40b188f92a75336f81a8f527f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924435"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a><span data-ttu-id="efafc-105">EML データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="efafc-105">Set up a connector to archive EML data</span></span>

<span data-ttu-id="efafc-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Microsoft 365 組織のユーザー メールボックスに EML データをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="efafc-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive EML data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="efafc-107">EML は、ファイルに保存された電子メール メッセージのファイル拡張子です。</span><span class="sxs-lookup"><span data-stu-id="efafc-107">EML is the file extension for an email message saved to a file.</span></span> <span data-ttu-id="efafc-108">コネクタは、アイテムのコンテンツをソース形式から電子メール メッセージ形式に変換し、そのアイテムをユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="efafc-108">The connector converts the content of an item from the source format to an email message format and then imports the item to a user mailbox.</span></span>

<span data-ttu-id="efafc-109">EML メッセージをユーザー メールボックスに保存した後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="efafc-109">After EML messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="efafc-110">EML コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="efafc-110">Using an EML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-eml-data"></a><span data-ttu-id="efafc-111">EML データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="efafc-111">Overview of archiving EML data</span></span>

<span data-ttu-id="efafc-112">次の概要では、コネクタを使用して Microsoft 365 の EML データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="efafc-112">The following overview explains the process of using a connector to archive EML data in Microsoft 365.</span></span>

![EML データのアーカイブ ワークフロー](../media/EMLConnectorWorkflow.png)

1. <span data-ttu-id="efafc-114">組織は EML ソースと一緒に EML サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="efafc-114">Your organization works with the EML source to set up and configure an EML site.</span></span>

2. <span data-ttu-id="efafc-115">24 時間に 1 回、EML ソースのコンテンツ アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="efafc-115">Once every 24 hours, content items from the EML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="efafc-116">このプロセスの間、EML ファイルのコンテンツは電子メール メッセージ形式に変換されます。</span><span class="sxs-lookup"><span data-stu-id="efafc-116">During this process, the content of an EML file is converted to an email message format.</span></span>

3. <span data-ttu-id="efafc-117">Microsoft 365 コンプライアンス センターで作成した EML コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage の場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="efafc-117">The EML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="efafc-118">コネクタは、手順 3 で説明されている自動ユーザー マッピング プロセスの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="efafc-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping process that's described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="efafc-119">このプロセスでは **、EML** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、EML アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="efafc-119">During this process, a subfolder in the Inbox folder named **EML** is created in the user mailboxes, and the EML items are imported to that folder.</span></span> <span data-ttu-id="efafc-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="efafc-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="efafc-121">すべてのメッセージには、このプロパティが含まれるので、コンテンツ アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="efafc-121">Every message contains this property, which is populated with the email address of every participant of the content item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="efafc-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="efafc-122">Before you begin</span></span>

- <span data-ttu-id="efafc-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="efafc-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="efafc-124">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="efafc-124">To create an account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="efafc-125">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="efafc-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="efafc-126">手順 1 で EML コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="efafc-126">The user who creates the EML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="efafc-127">Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="efafc-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="efafc-128">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="efafc-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="efafc-129">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="efafc-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="efafc-130">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="efafc-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="efafc-131">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efafc-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-eml-connector"></a><span data-ttu-id="efafc-132">手順 1: EML コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="efafc-132">Step 1: Set up an EML Connector</span></span>

<span data-ttu-id="efafc-133">最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、EML データ用のコネクタを作成することです。 </span><span class="sxs-lookup"><span data-stu-id="efafc-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for EML data.</span></span>

1. <span data-ttu-id="efafc-134">[データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ EML] に移動し、[データ **コネクタ**  >  **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="efafc-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **EML**.</span></span>

2. <span data-ttu-id="efafc-135">**[EML 製品の説明]** ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="efafc-135">On the **EML** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="efafc-136">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="efafc-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="efafc-137">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="efafc-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="efafc-138">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="efafc-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="efafc-139">手順 2: Globanet Merge1 サイトで EML コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="efafc-139">Step 2: Configure the EML connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="efafc-140">2 番目の手順は、Globanet Merge1 サイトで EML コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="efafc-140">The second step is to configure the EML connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="efafc-141">EML コネクタの構成の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efafc-141">For information about configuring  the EML connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="efafc-142">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efafc-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="efafc-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="efafc-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="efafc-144">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="efafc-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="efafc-145">[外部ユーザー **を Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="efafc-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="efafc-146">EML ソース アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="efafc-146">The EML source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="efafc-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、EML アイテムは、そのユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="efafc-147">If the connector can associate this address with a Microsoft 365 user, the EML items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="efafc-148">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="efafc-148">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-eml-connector"></a><span data-ttu-id="efafc-149">手順 4: EML コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="efafc-149">Step 4: Monitor the EML connector</span></span>

<span data-ttu-id="efafc-150">EML コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="efafc-150">After you create the EML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="efafc-151">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="efafc-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="efafc-152">[コネクタ **] タブをクリック** し **、EML** コネクタを選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="efafc-152">Click the **Connectors** tab and then select the **EML** connector to display the flyout page.</span></span> <span data-ttu-id="efafc-153">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="efafc-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="efafc-154">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="efafc-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="efafc-155">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="efafc-155">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="efafc-156">既知の問題</span><span class="sxs-lookup"><span data-stu-id="efafc-156">Known issues</span></span>

- <span data-ttu-id="efafc-157">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="efafc-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="efafc-158">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="efafc-158">Support for larger items will be available at a later date.</span></span>