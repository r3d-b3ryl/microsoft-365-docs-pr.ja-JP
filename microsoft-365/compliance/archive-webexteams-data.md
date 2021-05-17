---
title: Webex にコネクタをセットアップし、TeamsデータをMicrosoft 365
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
description: 管理者は、Veritas の Webex からデータをインポートおよびアーカイブするコネクタをセットアップし、TeamsのコネクタMicrosoft 365。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163908"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a><span data-ttu-id="86941-104">Webex データをアーカイブするコネクタをTeamsする</span><span class="sxs-lookup"><span data-stu-id="86941-104">Set up a connector to archive Webex Teams data</span></span>

<span data-ttu-id="86941-105">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、Webex Teams から組織のユーザー メールボックスにデータをインポートMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="86941-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from Webex Teams to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="86941-106">Veritas には[、Webex](https://globanet.com/webex-teams/) Teams通信アイテムをキャプチャしてインポートするように構成された Webex TeamsコネクタがMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="86941-106">Veritas provides a [Webex Teams](https://globanet.com/webex-teams/) connector that is configured to capture Webex Teams communication items and import them to Microsoft 365.</span></span> <span data-ttu-id="86941-107">コネクタは、組織の Webex Teams アカウントからの 1:1 チャット、グループ会話、チャネル会話、添付ファイルなどのコンテンツを Webex Teams から電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="86941-107">The connector converts content from Webex Teams, such as 1:1 chats, group conversations, channel conversations, and attachments from your organization's Webex Teams account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="86941-108">Webex Teamsデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="86941-108">After Webex Teams data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="86941-109">Webex Teamsコネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="86941-109">Using a Webex Teams connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webex-teams-data"></a><span data-ttu-id="86941-110">Webex データのアーカイブTeams概要</span><span class="sxs-lookup"><span data-stu-id="86941-110">Overview of archiving Webex Teams data</span></span>

<span data-ttu-id="86941-111">次の概要では、コネクタを使用して Webex データをアーカイブするプロセスTeams説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="86941-111">The following overview explains the process of using a connector to archive Webex Teams data in Microsoft 365.</span></span>

![Webex データのアーカイブ ワークフロー Teamsする](../media/WebexTeamsConnectorWorkflow.png)

1. <span data-ttu-id="86941-113">組織は Webex Teamsを使用して Webex サイトをTeamsします。</span><span class="sxs-lookup"><span data-stu-id="86941-113">Your organization works with Webex Teams to set up and configure a Webex Teams site.</span></span>

2. <span data-ttu-id="86941-114">24 時間に 1 回、Webex Teamsが Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="86941-114">Once every 24 hours, Webex Teams items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="86941-115">また、コネクタは Webex ファイルTeamsメール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="86941-115">The connector also converts the Webex Teams items to an email message format.</span></span>

3. <span data-ttu-id="86941-116">Microsoft 365 コンプライアンス センターで作成し、毎日 Veritas Merge1 に接続し、Webex Teams アイテムを Microsoft クラウド内の安全な Azure Storage 場所に転送する Webex Teams コネクタ。</span><span class="sxs-lookup"><span data-stu-id="86941-116">The Webex Teams connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 every day, and transfers the Webex Teams items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="86941-117">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="86941-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="86941-118">ユーザー のメールボックスに **Webex Teams** という名前の受信トレイ フォルダー内のサブフォルダーが作成され、そのフォルダーにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="86941-118">A subfolder in the Inbox folder named **Webex Teams** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="86941-119">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="86941-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="86941-120">すべての Webex Teamsには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="86941-120">Every Webex Teams item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="86941-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="86941-121">Before you begin</span></span>

- <span data-ttu-id="86941-122">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="86941-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="86941-123">このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="86941-123">To create this account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="86941-124">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="86941-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="86941-125">Webex アカウントからデータ [https://developer.webex.com/](https://developer.webex.com) をフェッチするアプリケーションをTeamsします。</span><span class="sxs-lookup"><span data-stu-id="86941-125">Create an application at [https://developer.webex.com/](https://developer.webex.com) to fetch data from your Webex Teams account.</span></span> <span data-ttu-id="86941-126">アプリケーションの作成の手順については、「Merge1 サード パーティ コネクタ ユーザー [ガイド」を参照してください。](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="86941-126">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span></span>

   <span data-ttu-id="86941-127">このアプリケーションを作成すると、Webex プラットフォームは一意の資格情報のセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="86941-127">When you create this application, the Webex platform generates a set of unique credentials.</span></span> <span data-ttu-id="86941-128">これらの資格情報は、グローバル Merge1 サイトで Webex Teamsコネクタを構成するときに、手順 2 で使用されます。</span><span class="sxs-lookup"><span data-stu-id="86941-128">These credentials are used in Step 2 when you configure the Webex Teams connector on the Global Merge1 site.</span></span>

- <span data-ttu-id="86941-129">手順 1 で Webex Teams コネクタを作成し (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="86941-129">The user who creates the Webex Teams connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="86941-130">この役割は、コンプライアンス センターの [**データ** コネクタ] ページにコネクタを追加Microsoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="86941-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="86941-131">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="86941-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="86941-132">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="86941-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="86941-133">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="86941-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="86941-134">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="86941-134">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webex-teams-connector"></a><span data-ttu-id="86941-135">手順 1: Webex コネクタをTeamsする</span><span class="sxs-lookup"><span data-stu-id="86941-135">Step 1: Set up the Webex Teams connector</span></span>

<span data-ttu-id="86941-136">最初の手順は、データ コネクタにアクセスし[、Webex](https://globanet.com/webex-teams/)コネクタをセットアップTeamsです。</span><span class="sxs-lookup"><span data-stu-id="86941-136">The first step is to gain access to the **Data Connectors** and set up the [Webex Teams](https://globanet.com/webex-teams/) connector.</span></span>

1. <span data-ttu-id="86941-137">[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) Webex]**に** 移動して  >  **、[Webex Teams] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="86941-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webex Teams**.</span></span>

2. <span data-ttu-id="86941-138">**[Webex Teams** 説明] ページで、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="86941-138">On the **Webex Teams** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="86941-139">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="86941-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="86941-140">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="86941-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="86941-141">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="86941-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="86941-142">手順 2: Veritas Merge1 サイトで webex Teamsコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="86941-142">Step 2: Configure the Webex Teams connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="86941-143">2 番目の手順は、Merge1 サイトTeams Webex コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="86941-143">The second step is to configure the Webex Teams connector on the Merge1 site.</span></span> <span data-ttu-id="86941-144">Webex コネクタを構成するTeamsについては[、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86941-144">For information about how to configure the Webex Teams connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="86941-145">[ファイルの **保存と&完了**] をクリックすると、コンプライアンス センターのコネクタ ウィザードの [ユーザー Microsoft 365] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="86941-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="86941-146">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="86941-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="86941-147">ユーザーをマップし、コンプライアンス センターでコネクタMicrosoft 365するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="86941-147">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="86941-148">**[Webex ユーザーにユーザーをTeamsするMicrosoft 365]** ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="86941-148">On the **Map Webex Teams users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="86941-149">Webex Teamsには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="86941-149">The Webex Teams items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="86941-150">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="86941-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="86941-151">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="86941-151">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webex-teams-connector"></a><span data-ttu-id="86941-152">手順 4: Webex コネクタTeamsする</span><span class="sxs-lookup"><span data-stu-id="86941-152">Step 4: Monitor the Webex Teams connector</span></span>

<span data-ttu-id="86941-153">Webex コネクタを作成Teams、コンプライアンス センターでコネクタのMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="86941-153">After you create the Webex Teams connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="86941-154">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="86941-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="86941-155">[コネクタ **] タブをクリック** し **、Webex** Teamsを選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="86941-155">Click the **Connectors** tab and then select the **Webex Teams** connector to display the flyout page.</span></span> <span data-ttu-id="86941-156">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="86941-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="86941-157">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="86941-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="86941-158">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="86941-158">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="86941-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="86941-159">Known issues</span></span>

- <span data-ttu-id="86941-160">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="86941-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="86941-161">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="86941-161">Support for larger items will be available at a later date.</span></span>