---
title: 17a-4 DataParser コネクタをセットアップして、17a-4 DataParser ConnectデータをアーカイブMicrosoft 365
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
description: 17a-4 FX Connect DataParser コネクタをセットアップして使用して、データをインポートおよびアーカイブする方法ConnectをMicrosoft 365。
ms.openlocfilehash: 667f36d111a877a7e2e04aa54653f61556d337d9
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454495"
---
# <a name="set-up-a-connector-to-archive-data-from-fx-connect"></a><span data-ttu-id="6677b-103">FX サーバーからデータをアーカイブするコネクタをConnect</span><span class="sxs-lookup"><span data-stu-id="6677b-103">Set up a connector to archive data from FX Connect</span></span>

<span data-ttu-id="6677b-104">17a-4 LLC の FX Connect [DataParser](https://www.17a-4.com/dataparser-roadmap/)を使用して、FX Connect から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="6677b-104">Use the [FX Connect DataParser](https://www.17a-4.com/dataparser-roadmap/) from 17a-4 LLC to import and archive data from FX Connect to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="6677b-105">DataParser には、サードパーティConnectからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された FX Microsoft 365 が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6677b-105">The DataParser includes a FX Connect connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="6677b-106">FX Connect DataParser コネクタは、FX Connect データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="6677b-106">The FX Connect DataParser connector converts FX Connect data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="6677b-107">FX Connectデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="6677b-107">After FX Connect data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="6677b-108">FX Connectコネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6677b-108">Using a FX Connect connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fx-connect-data"></a><span data-ttu-id="6677b-109">データのアーカイブ FX Connect概要</span><span class="sxs-lookup"><span data-stu-id="6677b-109">Overview of archiving FX Connect data</span></span>

<span data-ttu-id="6677b-110">次の概要では、データ コネクタを使用してデータをアーカイブするプロセスについてConnectをMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="6677b-110">The following overview explains the process of using a data connector to archive FX Connect data in Microsoft 365.</span></span>

![17a-4 の FX Connectアーカイブ ワークフロー](../media/FXConnectDataParserConnectorWorkflow.png)

1. <span data-ttu-id="6677b-112">組織は 17a-4 を使用して、DataParser の FX Connect構成します。</span><span class="sxs-lookup"><span data-stu-id="6677b-112">Your organization works with 17a-4 to set up and configure the FX Connect DataParser.</span></span>

2. <span data-ttu-id="6677b-113">定期的に、FX Connectアイテムは DataParser によって収集されます。</span><span class="sxs-lookup"><span data-stu-id="6677b-113">On a regular basis, FX Connect items are collected by the DataParser.</span></span> <span data-ttu-id="6677b-114">DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="6677b-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="6677b-115">Microsoft 365 コンプライアンス センター でConnectする FX コネクタは DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="6677b-115">The FX Connect DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="6677b-116">FX Connect **DataParser という** 名前の受信トレイ フォルダー内のサブフォルダーがユーザー のメールボックスに作成され、そのフォルダーに FX Connect アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="6677b-116">A subfolder in the Inbox folder named **FX Connect DataParser** is created in the user mailboxes, and the FX Connect items are imported to that folder.</span></span> <span data-ttu-id="6677b-117">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="6677b-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="6677b-118">すべての FX Connectには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="6677b-118">Every FX Connect item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="6677b-119">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="6677b-119">Before you set up a connector</span></span>

- <span data-ttu-id="6677b-120">Microsoft コネクタ用の DataParser アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6677b-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="6677b-121">これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="6677b-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="6677b-122">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6677b-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="6677b-123">手順 1 で FX Connect DataParser コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6677b-123">The user who creates the FX Connect DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6677b-124">この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="6677b-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6677b-125">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="6677b-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="6677b-126">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6677b-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6677b-127">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="6677b-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6677b-128">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6677b-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-fx-connect-dataparser-connector"></a><span data-ttu-id="6677b-129">手順 1: DATAParser コネクタConnect設定する</span><span class="sxs-lookup"><span data-stu-id="6677b-129">Step 1: Set up a FX Connect DataParser connector</span></span>

<span data-ttu-id="6677b-130">最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、FX データ用の 17a-4 コネクタConnectすることです。</span><span class="sxs-lookup"><span data-stu-id="6677b-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for FX Connect data.</span></span>

1. <span data-ttu-id="6677b-131">に移動 <https://compliance.microsoft.com> し **、[Data Connectors** FX Connect  >  **DataParser] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6677b-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **FX Connect DataParser**.</span></span>

2. <span data-ttu-id="6677b-132">**[FX ファイル] Connect DataParser** 製品の説明ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="6677b-132">On the **FX Connect DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="6677b-133">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6677b-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="6677b-134">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="6677b-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="6677b-135">17a-4 アカウントにサインインし、FX サーバーの DataParser 接続ウィザードConnect完了します。</span><span class="sxs-lookup"><span data-stu-id="6677b-135">Sign in to your 17a-4 account and complete the steps in the FX Connect DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-fx-connect-dataparser-connector"></a><span data-ttu-id="6677b-136">手順 2: DATAParser コネクタConnect FX を構成する</span><span class="sxs-lookup"><span data-stu-id="6677b-136">Step 2: Configure the FX Connect DataParser connector</span></span>

<span data-ttu-id="6677b-137">17a-4 サポートを使用して、DATAParser コネクタの FX Connect構成します。</span><span class="sxs-lookup"><span data-stu-id="6677b-137">Work with 17a-4 Support to configure the FX Connect DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="6677b-138">手順 3: ユーザーをマップする</span><span class="sxs-lookup"><span data-stu-id="6677b-138">Step 3: Map users</span></span>

<span data-ttu-id="6677b-139">FX Connect DataParser コネクタは、データをインポートする前に、ユーザー Microsoft 365メール アドレスに自動的にマップMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="6677b-139">The FX Connect DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-fx-connect-dataparser-connector"></a><span data-ttu-id="6677b-140">手順 4: DATAParser コネクタConnect FX を監視する</span><span class="sxs-lookup"><span data-stu-id="6677b-140">Step 4: Monitor the FX Connect DataParser connector</span></span>

<span data-ttu-id="6677b-141">DataParser コネクタに FX Connectを作成した後、コネクタの状態を表示できます。Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="6677b-141">After you create a FX Connect DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="6677b-142">左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="6677b-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="6677b-143">[コネクタ **] タブを** クリックし、作成した FX Connect DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="6677b-143">Click the **Connectors** tab and then select the FX Connect DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="6677b-144">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="6677b-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="6677b-145">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6677b-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6677b-146">既知の問題</span><span class="sxs-lookup"><span data-stu-id="6677b-146">Known issues</span></span>

<span data-ttu-id="6677b-147">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6677b-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="6677b-148">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="6677b-148">Support for larger items will be available at a later date.</span></span>
