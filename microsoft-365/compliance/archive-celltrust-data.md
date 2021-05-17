---
title: セルトラスト データをアーカイブするコネクタをセットアップMicrosoft 365
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
description: 管理者は、Veritas からユーザーに CellTrust データをインポートおよびアーカイブするコネクタをMicrosoft 365。 このコネクタを使用すると、サードパーティのデータ ソースからデータをアーカイブできます。Microsoft 365。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 855d48303c7c35c32951105799aa117675820420
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164391"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a><span data-ttu-id="1d7ca-105">CellTrust データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="1d7ca-105">Set up a connector to archive CellTrust data</span></span>

<span data-ttu-id="1d7ca-106">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、CellTrust プラットフォームから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the CellTrust platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="1d7ca-107">Veritas には[、サード](https://globanet.com/celltrust/)パーティ製のデータ ソースからアイテムをキャプチャし、それらのアイテムをデータ ソースにインポートする CellTrust コネクタMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-107">Veritas provides a [CellTrust](https://globanet.com/celltrust/) connector that captures items from the third-party data source and imports those items to Microsoft 365.</span></span> <span data-ttu-id="1d7ca-108">コネクタは、CellTrust アカウントから 携帯ショートメール メッセージのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムをユーザーのメールボックスにインポートMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-108">The connector converts the content of SMS messages from CellTrust accounts to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="1d7ca-109">CellTrust データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-109">After CellTrust data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="1d7ca-110">CellTrust コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-110">Using a CellTrust connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-celltrust-data"></a><span data-ttu-id="1d7ca-111">CellTrust データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="1d7ca-111">Overview of archiving CellTrust data</span></span>

<span data-ttu-id="1d7ca-112">次の概要では、コネクタを使用してセルトラスト データをアーカイブするプロセスについて説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-112">The following overview explains the process of using a connector to archive CellTrust data in Microsoft 365.</span></span>

![CellTrust データのアーカイブ ワークフロー](../media/CellTrustConnectorWorkflow.png)

1. <span data-ttu-id="1d7ca-114">組織は CellTrust を使用して、CellTrust サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-114">Your organization works with CellTrust to set up and configure a CellTrust site.</span></span>

2. <span data-ttu-id="1d7ca-115">24 時間に 1 回、CellTrust アイテムは Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-115">Once every 24 hours, CellTrust items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="1d7ca-116">コネクタは、メッセージのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-116">The connector also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="1d7ca-117">Microsoft 365 コンプライアンス センターで作成する CellTrust コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-117">The CellTrust connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="1d7ca-118">コネクタとしての自動ユーザー マッピングは、手順 3 で説明されている *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="1d7ca-119">**CellTrust** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、メッセージ アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-119">A subfolder in the Inbox folder named **CellTrust** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="1d7ca-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="1d7ca-121">すべての CellTrust アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-121">Every CellTrust item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1d7ca-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="1d7ca-122">Before you begin</span></span>

- <span data-ttu-id="1d7ca-123">Microsoft コネクタ用の Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="1d7ca-124">アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-124">To create an account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="1d7ca-125">手順 1 でコネクタを作成する場合は、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="1d7ca-126">手順 1 で CellTrust コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-126">The user who creates the CellTrust connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="1d7ca-127">この役割は、コンプライアンス センターの [**データ** コネクタ] ページにコネクタを追加Microsoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1d7ca-128">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-128">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="1d7ca-129">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="1d7ca-130">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="1d7ca-131">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-celltrust-connector"></a><span data-ttu-id="1d7ca-132">手順 1: CellTrust コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="1d7ca-132">Step 1: Set up the CellTrust connector</span></span>

<span data-ttu-id="1d7ca-133">最初の手順は、コンプライアンス センターの **データ** コネクタMicrosoft 365、CellTrust データ用のコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-133">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for CellTrust data.</span></span>

1. <span data-ttu-id="1d7ca-134">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) 、[データ コネクタ **] [CellTrust]** \> **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **CellTrust**.</span></span>

2. <span data-ttu-id="1d7ca-135">**[CellTrust 製品の説明]** ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-135">On the **CellTrust** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="1d7ca-136">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="1d7ca-137">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="1d7ca-138">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-celltrust-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="1d7ca-139">手順 2: Veritas Merge1 サイトで CellTrust コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="1d7ca-139">Step 2: Configure the CellTrust connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="1d7ca-140">2 番目の手順は、Veritas Merge1 サイトで CellTrust コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-140">The second step is to configure the CellTrust connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="1d7ca-141">CellTrust コネクタを構成する方法の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-141">For information about how to configure the CellTrust connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="1d7ca-142">[ファイルの **保存と&完了**] をクリックすると、コンプライアンス センターのコネクタ ウィザードの [ユーザー Microsoft 365] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="1d7ca-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="1d7ca-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="1d7ca-144">ユーザーをマップし、コンプライアンス センターでセットアップされたコネクタをMicrosoft 365するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-144">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="1d7ca-145">**[CellTrust ユーザーをユーザーにマップMicrosoft 365]** ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-145">On the **Map CellTrust users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="1d7ca-146">CellTrust アイテムには、組織内のユーザーのメール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-146">The CellTrust items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="1d7ca-147">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="1d7ca-148">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-celltrust-connector"></a><span data-ttu-id="1d7ca-149">手順 4: CellTrust コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="1d7ca-149">Step 4: Monitor the CellTrust connector</span></span>

<span data-ttu-id="1d7ca-150">CellTrust コネクタを作成した後、コンプライアンス センターでコネクタのMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-150">After you create the CellTrust connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="1d7ca-151">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="1d7ca-152">[コネクタ **] タブをクリック** し **、CellTrust** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-152">Click the **Connectors** tab and then select the **CellTrust** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="1d7ca-153">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="1d7ca-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="1d7ca-154">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="1d7ca-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="1d7ca-155">Known issues</span></span>

- <span data-ttu-id="1d7ca-156">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="1d7ca-157">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="1d7ca-157">Support for larger items will be available at a later date.</span></span>