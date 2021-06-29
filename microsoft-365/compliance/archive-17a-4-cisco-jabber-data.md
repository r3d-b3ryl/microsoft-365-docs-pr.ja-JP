---
title: Cisco Jabber データをアーカイブするコネクタをセットアップMicrosoft 365
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
description: 17a-4 Cisco Jabber DataParser コネクタをセットアップして使用して、Cisco Jabber データをインポートおよびアーカイブする方法についてMicrosoft 365。
ms.openlocfilehash: b5bf70a00887a6ea802354f51ee5fd65f5351727
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096500"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data-preview"></a><span data-ttu-id="5bcd1-103">Cisco Jabber データをアーカイブするコネクタをセットアップする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="5bcd1-103">Set up a connector to archive Cisco Jabber data (preview)</span></span>

<span data-ttu-id="5bcd1-104">17a-4 LLC の[Cisco Jabber DataParser](https://www.17a-4.com/jabber-dataparser/)を使用して、Cisco Jabber から Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-104">Use the [Cisco Jabber DataParser](https://www.17a-4.com/jabber-dataparser/) from 17a-4 LLC to import and archive data from Cisco Jabber to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="5bcd1-105">DataParser には、サードパーティのデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートするように構成された Cisco Jabber コネクタがMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-105">The DataParser includes a Cisco Jabber connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="5bcd1-106">Cisco Jabber DataParser コネクタは、Cisco Jabber データを電子メール メッセージ形式に変換し、それらのアイテムをユーザー メールボックスにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-106">The Cisco Jabber DataParser connector converts Cisco Jabber data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="5bcd1-107">Cisco Jabber データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-107">After Cisco Jabber data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="5bcd1-108">Cisco Jabber コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-108">Using a Cisco Jabber connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-cisco-jabber-data"></a><span data-ttu-id="5bcd1-109">Cisco Jabber データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="5bcd1-109">Overview of archiving Cisco Jabber data</span></span>

<span data-ttu-id="5bcd1-110">次の概要では、データ コネクタを使用して Cisco Jabber データをアーカイブするプロセスについて説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-110">The following overview explains the process of using a data connector to archive Cisco Jabber data in Microsoft 365.</span></span>

![17a-4 の Cisco Jabber データのアーカイブ ワークフロー](../media/CiscoJabberDataParserConnectorWorkflow.png)

1. <span data-ttu-id="5bcd1-112">組織は 17a-4 を使用して、Cisco Jabber DataParser をセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-112">Your organization works with 17a-4 to set up and configure the Cisco Jabber DataParser.</span></span>

2. <span data-ttu-id="5bcd1-113">定期的に、Cisco Jabber アイテムは DataParser によって収集されます。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-113">On a regular basis, Cisco Jabber items are collected by the DataParser.</span></span> <span data-ttu-id="5bcd1-114">DataParser は、メッセージのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="5bcd1-115">Microsoft 365 コンプライアンス センター で作成した Cisco Jabber DataParser コネクタは、DataParser に接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-115">The Cisco Jabber DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="5bcd1-116">**Cisco Jabber DataParser** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、そのフォルダーに Cisco Jabber アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-116">A subfolder in the Inbox folder named **Cisco Jabber DataParser** is created in the user mailboxes, and the Cisco Jabber items are imported to that folder.</span></span> <span data-ttu-id="5bcd1-117">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="5bcd1-118">すべての Cisco Jabber アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-118">Every Cisco Jabber item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="5bcd1-119">コネクタをセットアップする前に</span><span class="sxs-lookup"><span data-stu-id="5bcd1-119">Before you set up a connector</span></span>

- <span data-ttu-id="5bcd1-120">Microsoft コネクタ用の DataParser アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="5bcd1-121">これを行うには [、17a-4 LLC にお問い合わせください](https://www.17a-4.com/contact/)。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="5bcd1-122">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="5bcd1-123">手順 1 で Cisco Jabber DataParser コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-123">The user who creates the Cisco Jabber DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="5bcd1-124">この役割は、データ コネクタ ページの[データ コネクタ] ページにコネクタを追加Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5bcd1-125">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="5bcd1-126">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="5bcd1-127">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="5bcd1-128">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-cisco-jabber-dataparser-connector"></a><span data-ttu-id="5bcd1-129">手順 1: Cisco Jabber DataParser コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="5bcd1-129">Step 1: Set up a Cisco Jabber DataParser connector</span></span>

<span data-ttu-id="5bcd1-130">最初の手順は、Microsoft 365 コンプライアンス センター の [データ コネクタ] ページにアクセスし、Cisco Jabber データ用の 17a-4 コネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Cisco Jabber data.</span></span>

1. <span data-ttu-id="5bcd1-131">に移動 <https://compliance.microsoft.com> し、[**データ** コネクタ  >  **] [Cisco Jabber DataParser] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Cisco Jabber DataParser**.</span></span>

2. <span data-ttu-id="5bcd1-132">**[Cisco Jabber DataParser** 製品の説明] ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-132">On the **Cisco Jabber DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="5bcd1-133">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="5bcd1-134">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="5bcd1-135">17a-4 アカウントにサインインし、Cisco Jabber DataParser 接続ウィザードの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-135">Sign in to your 17a-4 account and complete the steps in the Cisco Jabber DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-cisco-jabber-dataparser-connector"></a><span data-ttu-id="5bcd1-136">手順 2: Cisco Jabber DataParser コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="5bcd1-136">Step 2: Configure the Cisco Jabber DataParser connector</span></span>

<span data-ttu-id="5bcd1-137">17a-4 サポートを使用して、Cisco Jabber DataParser コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-137">Work with 17a-4 Support to configure the Cisco Jabber DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="5bcd1-138">手順 3: ユーザーをマップする</span><span class="sxs-lookup"><span data-stu-id="5bcd1-138">Step 3: Map users</span></span>

<span data-ttu-id="5bcd1-139">Cisco Jabber DataParser コネクタは、ユーザーにデータをインポートする前に、ユーザー Microsoft 365メール アドレスに自動的にマップMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-139">The Cisco Jabber DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-cisco-jabber-dataparser-connector"></a><span data-ttu-id="5bcd1-140">手順 4: Cisco Jabber DataParser コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="5bcd1-140">Step 4: Monitor the Cisco Jabber DataParser connector</span></span>

<span data-ttu-id="5bcd1-141">Cisco Jabber DataParser コネクタを作成した後、コネクタの状態を[ネットワーク] Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-141">After you create a Cisco Jabber DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="5bcd1-142">左側の <https://compliance.microsoft.com> ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="5bcd1-143">[コネクタ **] タブを** クリックし、作成した Cisco Jabber DataParser コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-143">Click the **Connectors** tab and then select the Cisco Jabber DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="5bcd1-144">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="5bcd1-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="5bcd1-145">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="5bcd1-146">既知の問題</span><span class="sxs-lookup"><span data-stu-id="5bcd1-146">Known issues</span></span>

<span data-ttu-id="5bcd1-147">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="5bcd1-148">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="5bcd1-148">Support for larger items will be available at a later date.</span></span>