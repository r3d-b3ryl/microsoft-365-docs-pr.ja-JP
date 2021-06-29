---
title: コネクタをセットアップして、ズーム データをアーカイブMicrosoft 365
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
description: 17a-4 Zoom DataParser コネクタをセットアップして使用して、ズーム データをインポートおよびアーカイブする方法についてMicrosoft 365。
ms.openlocfilehash: dffececb0719999abf19ea58eab1a52afdb3daea
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097217"
---
# <a name="set-up-a-connector-to-archive-zoom-data-preview"></a><span data-ttu-id="e9653-103">ズーム データをアーカイブするコネクタをセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e9653-103">Set up a connector to archive Zoom data (preview)</span></span>

<span data-ttu-id="e9653-104">17a-4 LLC の[Zoom DataParser](https://www.17a-4.com/dataparser/)を使用して、Zoom プラットフォームから組織内のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="e9653-104">Use the [Zoom DataParser](https://www.17a-4.com/dataparser/) from 17a-4 LLC to import and archive data from the Zoom platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="e9653-105">DataParser には、サード パーティ製のデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された Zoom コネクタMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="e9653-105">The DataParser includes a Zoom connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="e9653-106">Zoom DataParser コネクタは、Zoom データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="e9653-106">The Zoom DataParser connector converts Zoom data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="e9653-107">ユーザー メールボックスにズーム データを格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどのコンプライアンス機能Microsoft 365を適用できます。</span><span class="sxs-lookup"><span data-stu-id="e9653-107">After Zoom data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="e9653-108">ズーム コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e9653-108">Using a Zoom connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-data"></a><span data-ttu-id="e9653-109">ズーム データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="e9653-109">Overview of archiving Zoom data</span></span>

<span data-ttu-id="e9653-110">次の概要では、データ コネクタを使用してズーム データをアーカイブするプロセスについて説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e9653-110">The following overview explains the process of using a data connector to archive Zoom data in Microsoft 365.</span></span>

![17a-4 のズーム データのアーカイブ ワークフロー](../media/ZoomDataParserConnectorWorkflow.png)

1. <span data-ttu-id="e9653-112">組織は 17a-4 を使用して Zoom DataParser を設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="e9653-112">Your organization works with 17a-4 to set up and configure the Zoom DataParser.</span></span>

2. <span data-ttu-id="e9653-113">定期的に、Zoom アイテムは DataParser によって収集されます。</span><span class="sxs-lookup"><span data-stu-id="e9653-113">On a regular basis, Zoom items are collected by the DataParser.</span></span> <span data-ttu-id="e9653-114">DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="e9653-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="e9653-115">Microsoft 365 コンプライアンス センター で作成した Zoom DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="e9653-115">The Zoom DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="e9653-116">**Zoom DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにズーム アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="e9653-116">A subfolder in the Inbox folder named **Zoom DataParser** is created in the user mailboxes, and the Zoom items are imported to that folder.</span></span> <span data-ttu-id="e9653-117">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="e9653-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="e9653-118">すべての Zoom アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="e9653-118">Every Zoom item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="e9653-119">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="e9653-119">Before you set up a connector</span></span>

- <span data-ttu-id="e9653-120">Microsoft コネクタ用の DataParser アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9653-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="e9653-121">これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="e9653-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="e9653-122">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9653-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="e9653-123">手順 1 で Zoom DataParser コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9653-123">The user who creates the Zoom DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="e9653-124">この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="e9653-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e9653-125">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="e9653-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="e9653-126">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e9653-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="e9653-127">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="e9653-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="e9653-128">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e9653-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-zoom-dataparser-connector"></a><span data-ttu-id="e9653-129">手順 1: Zoom DataParser コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e9653-129">Step 1: Set up a Zoom DataParser connector</span></span>

<span data-ttu-id="e9653-130">最初の手順は、データ ウィンドウの [データ コネクタ] ページにアクセスしMicrosoft 365 コンプライアンス センターズーム データ用の 17a-4 コネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="e9653-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Zoom data.</span></span>

1. <span data-ttu-id="e9653-131">[データ コネクタ <https://compliance.microsoft.com> ] **[Zoom**  >  **DataParser] に移動し、[データ コネクタ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e9653-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Zoom DataParser**.</span></span>

2. <span data-ttu-id="e9653-132">[Zoom **DataParser 製品の説明] ページ** で、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e9653-132">On the **Zoom DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="e9653-133">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e9653-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="e9653-134">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e9653-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="e9653-135">17a-4 アカウントにサインインし、Zoom DataParser 接続ウィザードの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="e9653-135">Sign in to your 17a-4 account and complete the steps in the Zoom DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-zoom-dataparser-connector"></a><span data-ttu-id="e9653-136">手順 2: Zoom DataParser コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="e9653-136">Step 2: Configure the Zoom DataParser connector</span></span>

<span data-ttu-id="e9653-137">17a-4 サポートを使用して Zoom DataParser コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="e9653-137">Work with 17a-4 Support to configure the Zoom DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="e9653-138">手順 3: ユーザーをマップする</span><span class="sxs-lookup"><span data-stu-id="e9653-138">Step 3: Map users</span></span>

<span data-ttu-id="e9653-139">Zoom DataParser コネクタは、ユーザーにデータをインポートする前に、ユーザー Microsoft 365メール アドレスに自動的にマップMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="e9653-139">The Zoom DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-zoom-dataparser-connector"></a><span data-ttu-id="e9653-140">手順 4: Zoom DataParser コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="e9653-140">Step 4: Monitor the Zoom DataParser connector</span></span>

<span data-ttu-id="e9653-141">Zoom DataParser コネクタを作成した後は、コネクタの状態を [データ の表示] Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="e9653-141">After you create a Zoom DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="e9653-142">左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9653-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="e9653-143">[コネクタ **] タブをクリック** し、作成した Zoom DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="e9653-143">Click the **Connectors** tab and then select the Zoom DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="e9653-144">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="e9653-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="e9653-145">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e9653-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e9653-146">既知の問題</span><span class="sxs-lookup"><span data-stu-id="e9653-146">Known issues</span></span>

<span data-ttu-id="e9653-147">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e9653-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="e9653-148">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="e9653-148">Support for larger items will be available at a later date.</span></span>