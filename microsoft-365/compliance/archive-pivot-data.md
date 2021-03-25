---
title: Microsoft 365 でピボット データをアーカイブするコネクタをセットアップする
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
description: 管理者は、Microsoft 365 の Veritas からピボット データをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 8e88f5166ebcc4d1285a81e041b6d97be46786e3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164198"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a><span data-ttu-id="4d765-104">ピボット データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="4d765-104">Set up a connector to archive Pivot data</span></span>

<span data-ttu-id="4d765-105">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、ピボット プラットフォームから Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="4d765-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Pivot platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="4d765-106">Veritas は、サードパーティ[](https://globanet.com/pivot/)のデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたピボット コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="4d765-106">Veritas provides you with a [Pivot](https://globanet.com/pivot/) connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="4d765-107">Pivot は、金融市場参加者とのコラボレーションを可能にするインスタント メッセージング プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="4d765-107">Pivot is an instant messaging platform that allows collaboration with financial market participants.</span></span> <span data-ttu-id="4d765-108">コネクタは、チャット メッセージなどのアイテムをユーザーのピボット アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="4d765-108">The connector converts items such as chat messages, from a users' Pivot accounts to an email message format and then imports those items to the user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="4d765-109">ピボット データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="4d765-109">After Pivot data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="4d765-110">ピボット コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4d765-110">Using a Pivot connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-pivot-data"></a><span data-ttu-id="4d765-111">ピボット データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="4d765-111">Overview of archiving Pivot data</span></span>

<span data-ttu-id="4d765-112">次の概要では、コネクタを使用して Microsoft 365 のピボット データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4d765-112">The following overview explains the process of using a connector to archive the Pivot data in Microsoft 365.</span></span>

![ピボット データのアーカイブ ワークフロー](../media/PivotConnectorWorkflow.png)

1. <span data-ttu-id="4d765-114">組織はピボットを使用してピボット ソース サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="4d765-114">Your organization works with Pivot to set up and configure a Pivot source site.</span></span>

2. <span data-ttu-id="4d765-115">24 時間に 1 回、ピボット アイテムは Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4d765-115">Once every 24 hours, Pivot items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="4d765-116">コネクタは、ピボットアイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="4d765-116">The connector also converts the Pivot items to an email message format.</span></span>

3. <span data-ttu-id="4d765-117">Microsoft 365 コンプライアンス センターで作成したピボット コネクタは、毎日 Veritas Merge1 サイトに接続し、ピボット アイテムを Microsoft クラウドの安全な Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="4d765-117">The Pivot connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the Pivot items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="4d765-118">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、ピボット アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="4d765-118">The connector imports the Pivot items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="4d765-119">Pivot という名前の受信トレイフォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="4d765-119">A subfolder in the Inbox folder named **Pivot** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="4d765-120">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="4d765-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="4d765-121">すべてのピボット アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="4d765-121">Every Pivot item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4d765-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="4d765-122">Before you begin</span></span>

- <span data-ttu-id="4d765-123">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4d765-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="4d765-124">このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。</span><span class="sxs-lookup"><span data-stu-id="4d765-124">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="4d765-125">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4d765-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="4d765-126">手順 1 でピボット コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d765-126">The user who creates the Pivot connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="4d765-127">Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="4d765-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="4d765-128">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="4d765-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="4d765-129">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="4d765-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="4d765-130">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="4d765-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="4d765-131">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d765-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-pivot-connector"></a><span data-ttu-id="4d765-132">手順 1: ピボット コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="4d765-132">Step 1: Set up the Pivot connector</span></span>

<span data-ttu-id="4d765-133">最初の手順は、Microsoft コンプライアンスセンターの [データ コネクタ] ページにアクセスし、ピボット データ用のコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="4d765-133">The first step is to access to the **Data Connectors** page in the Microsoft compliance center and create a connector for Pivot data.</span></span>

1. <span data-ttu-id="4d765-134">[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) ピボット] に移動 **し、[データ コネクタ]**  >  **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d765-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Pivot**.</span></span>

2. <span data-ttu-id="4d765-135">[ピボット製品 **の説明]** ページで、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d765-135">On the **Pivot** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="4d765-136">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d765-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="4d765-137">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d765-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="4d765-138">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="4d765-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-pivot-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="4d765-139">手順 2: Veritas Merge1 サイトでピボット コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="4d765-139">Step 2: Configure the Pivot connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="4d765-140">2 番目の手順は、Merge1 サイトでピボット コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="4d765-140">The second step is to configure the Pivot connector on the Merge1 site.</span></span> <span data-ttu-id="4d765-141">Veritas Merge1 サイトでピボット コネクタを構成する方法については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d765-141">For information about how to configure the Pivot connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="4d765-142">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d765-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="4d765-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="4d765-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="4d765-144">Microsoft 356 コンプライアンス センターでユーザーをマップし、コネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4d765-144">To map users and complete the connector setup in the Microsoft 356 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="4d765-145">[ピボット **ユーザーを Microsoft 365 ユーザーに** マップする] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4d765-145">On the **Map Pivot users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="4d765-146">ピボット アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d765-146">The Pivot items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="4d765-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="4d765-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="4d765-148">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="4d765-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-pivot-connector"></a><span data-ttu-id="4d765-149">手順 4: ピボット コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="4d765-149">Step 4: Monitor the Pivot connector</span></span>

<span data-ttu-id="4d765-150">ピボット コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4d765-150">After you create the Pivot connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="4d765-151">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d765-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="4d765-152">[コネクタ **] タブをクリック** し、ピボット **コネクタを** 選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="4d765-152">Click the **Connectors** tab and then select the **Pivot** connector to display the flyout page.</span></span> <span data-ttu-id="4d765-153">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="4d765-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="4d765-154">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="4d765-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="4d765-155">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d765-155">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="4d765-156">既知の問題</span><span class="sxs-lookup"><span data-stu-id="4d765-156">Known issues</span></span>

- <span data-ttu-id="4d765-157">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4d765-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="4d765-158">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="4d765-158">Support for larger items will be available at a later date.</span></span>