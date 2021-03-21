---
title: Microsoft 365 でデータを扱うロイターをアーカイブするコネクタをセットアップする
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
description: 管理者は、ロイターのデータを Globanet から Microsoft 365 にインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 3977bd01c87bb3a02ec2027c25bbe8dfb1779c67
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925139"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data"></a><span data-ttu-id="3bb7c-105">ロイターの取引データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="3bb7c-105">Set up a connector to archive Reuters Dealing data</span></span>

<span data-ttu-id="3bb7c-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、ロイター取引プラットフォームから Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters Dealing platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="3bb7c-107">Globanet は、サードパーティ[](https://globanet.com/reuters-dealing/)のデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたロイターの取引コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-107">Globanet provides you with a [Reuters Dealing](https://globanet.com/reuters-dealing/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="3bb7c-108">コネクタは、Reuters Dealing アカウントからの通信を電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-108">The connector converts Dealing communications from the Reuters Dealing account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="3bb7c-109">ロイター 取引データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-109">After Reuters Dealing data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="3bb7c-110">ロイターの取引コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-110">Using a Reuters Dealing connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-dealing-data"></a><span data-ttu-id="3bb7c-111">アーカイブの概要 ロイター データの処理</span><span class="sxs-lookup"><span data-stu-id="3bb7c-111">Overview of archiving Reuters Dealing data</span></span>

<span data-ttu-id="3bb7c-112">次の概要では、コネクタを使用して Microsoft 365 のロイター取引データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-112">The following overview explains the process of using a connector to archive the Reuters Dealing data in Microsoft 365.</span></span>

![ロイターのデータを扱うアーカイブ ワークフロー](../media/ReuetersDealingConnectorWorkflow.png)

1. <span data-ttu-id="3bb7c-114">組織はロイターの取引と一緒にロイター取引サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-114">Your organization works with Reuters Dealing to set up and configure a Reuters Dealing site.</span></span>

2. <span data-ttu-id="3bb7c-115">24 時間に 1 回、ロイター のアイテムは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-115">Once every 24 hours, Reuters Dealing items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="3bb7c-116">コネクタは、アイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="3bb7c-117">Microsoft 365 コンプライアンス センターで作成したロイターの対応コネクタは、毎日 Globanet Merge1 サイトに接続し、コンテンツを Microsoft クラウド内の安全な Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-117">The Reuters Dealing connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="3bb7c-118">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="3bb7c-119">**Reuters Dealing** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-119">A subfolder in the Inbox folder named **Reuters Dealing** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="3bb7c-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="3bb7c-121">すべてのロイターの [取引] アイテムには、アイテムのすべての参加者の電子メール アドレスが設定されたこのプロパティが含まれる。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-121">Every Reuters Dealing item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3bb7c-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="3bb7c-122">Before you begin</span></span>

- <span data-ttu-id="3bb7c-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="3bb7c-124">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us)。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="3bb7c-125">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="3bb7c-126">手順 1 でロイター取引コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-126">The user who creates the Reuters Dealing connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="3bb7c-127">Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3bb7c-128">既定では、この役割は Exchange Online の任意の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="3bb7c-129">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="3bb7c-130">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="3bb7c-131">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-dealing-connector"></a><span data-ttu-id="3bb7c-132">手順 1: ロイターの対応コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="3bb7c-132">Step 1: Set up the Reuters Dealing connector</span></span>

<span data-ttu-id="3bb7c-133">最初の手順は、Microsoft 365 の [データ コネクタ] ページにアクセスし、ロイターのデータを扱うコネクタを作成することです。 </span><span class="sxs-lookup"><span data-stu-id="3bb7c-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters Dealing data.</span></span>

1. <span data-ttu-id="3bb7c-134">[データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ] [**ロイター** 取引]  >  **に移動し、[データ コネクタ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Dealing**.</span></span>

2. <span data-ttu-id="3bb7c-135">[ロイター **取引製品の説明] ページ** で、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-135">On the **Reuters Dealing** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="3bb7c-136">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="3bb7c-137">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="3bb7c-138">コネクタを構成するには、Merge1 アカウントに署名します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="3bb7c-139">手順 2: Globanet Merge1 サイトでロイター取引コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="3bb7c-139">Step 2: Configure the Reuters Dealing connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="3bb7c-140">2 番目の手順は、Merge1 サイトの Globanet でロイター取引コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-140">The second step is to configure the Reuters Dealing connector on Globanet the Merge1 site.</span></span> <span data-ttu-id="3bb7c-141">ロイター対応コネクタの構成の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-141">For information about configuring the Reuters Dealing connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="3bb7c-142">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="3bb7c-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="3bb7c-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="3bb7c-144">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="3bb7c-145">[ユーザー **を Microsoft 365** ユーザーに対応するマップ] ページで、自動ユーザー マッピングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-145">On the **Map Reuters Dealing users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="3bb7c-146">ロイター 取引アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-146">Reuters Dealing items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="3bb7c-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="3bb7c-148">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-dealing-connector"></a><span data-ttu-id="3bb7c-149">手順 4: ロイターの対応コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="3bb7c-149">Step 4: Monitor the Reuters Dealing connector</span></span>

<span data-ttu-id="3bb7c-150">ロイター取引コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-150">After you create the Reuters Dealing connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="3bb7c-151">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3bb7c-152">[コネクタ **] タブをクリック** し、[ロイターの対応] コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-152">Click the **Connectors** tab and then select the **Reuters Dealing** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="3bb7c-153">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="3bb7c-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="3bb7c-154">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="3bb7c-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="3bb7c-155">Known issues</span></span>

- <span data-ttu-id="3bb7c-156">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="3bb7c-157">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="3bb7c-157">Support for larger items will be available at a later date.</span></span>