---
title: Microsoft 365 で Webex Teams データへのコネクタを設定する
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
description: 管理者は、Microsoft 365 で Globanet の Webex Teams コネクタからデータをインポートおよびアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: e116b02a53538f7eff4188b670fa6b42b873a9e9
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620223"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a><span data-ttu-id="b13ab-104">Webex Teams データをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="b13ab-104">Set up a connector to archive Webex Teams data</span></span>

<span data-ttu-id="b13ab-105">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Webex Teams から Microsoft 365 組織のユーザー メールボックスにデータをインポートしてアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="b13ab-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Webex Teams to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="b13ab-106">Globanet は [、Webex Teams](https://globanet.com/webex-teams/) 通信アイテムをキャプチャして Microsoft 365 にインポートするように構成された Webex Teams コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-106">Globanet provides a [Webex Teams](https://globanet.com/webex-teams/) connector that is configured to capture Webex Teams communication items and import them to Microsoft 365.</span></span> <span data-ttu-id="b13ab-107">コネクタは、1 対 1 のチャット、グループ会話、チャネル会話、添付ファイルなどの Webex Teams のコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="b13ab-107">The connector converts content from Webex Teams, such as 1:1 chats, group conversations, channel conversations, and attachments from your organization's Webex Teams account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="b13ab-108">Webex Teams データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-108">After Webex Teams data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="b13ab-109">Webex Teams コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府および規制ポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-109">Using a Webex Teams connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webex-teams-data"></a><span data-ttu-id="b13ab-110">Webex Teams データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="b13ab-110">Overview of archiving Webex Teams data</span></span>

<span data-ttu-id="b13ab-111">次の概要では、コネクタを使用して Microsoft 365 の Webex Teams データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-111">The following overview explains the process of using a connector to archive Webex Teams data in Microsoft 365.</span></span>

![Webex Teams データのアーカイブ ワークフロー](../media/WebexTeamsConnectorWorkflow.png)

1. <span data-ttu-id="b13ab-113">組織は Webex Teams と共同で Webex Teams サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-113">Your organization works with Webex Teams to set up and configure a Webex Teams site.</span></span>

2. <span data-ttu-id="b13ab-114">24 時間ごとに、Webex Teams アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-114">Once every 24 hours, Webex Teams items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="b13ab-115">コネクタは、Webex Teams アイテムを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-115">The connector also converts the Webex Teams items to an email message format.</span></span>

3. <span data-ttu-id="b13ab-116">Microsoft 365 コンプライアンス センターで作成する Webex Teams コネクタは、毎日 Globanet Merge1 に接続し、Webex Teams アイテムを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-116">The Webex Teams connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the Webex Teams items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="b13ab-117">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテム [をインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="b13ab-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="b13ab-118">**Webex Teams** という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-118">A subfolder in the Inbox folder named **Webex Teams** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="b13ab-119">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="b13ab-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="b13ab-120">すべての Webex Teams アイテムには、このプロパティが含まれるので、アイテムのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-120">Every Webex Teams item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b13ab-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="b13ab-121">Before you begin</span></span>

- <span data-ttu-id="b13ab-122">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="b13ab-123">このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="b13ab-123">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="b13ab-124">このアカウントは、手順 1 でコネクタを作成するときにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b13ab-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="b13ab-125">Webex Teams アカウントから [https://developer.webex.com/](https://developer.webex.com) データを取得するアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-125">Create an application at [https://developer.webex.com/](https://developer.webex.com) to fetch data from your Webex Teams account.</span></span> <span data-ttu-id="b13ab-126">アプリケーションの作成に関する詳しい手順については[、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b13ab-126">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span></span>

   <span data-ttu-id="b13ab-127">このアプリケーションを作成すると、Webex プラットフォームは一意の資格情報のセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-127">When you create this application, the Webex platform generates a set of unique credentials.</span></span> <span data-ttu-id="b13ab-128">これらの資格情報は、グローバル Merge1 サイトで Webex Teams コネクタを構成するときに、手順 2 で使用されます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-128">These credentials are used in Step 2 when you configure the Webex Teams connector on the Global Merge1 site.</span></span>

- <span data-ttu-id="b13ab-129">手順 1 で Webex Teams コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b13ab-129">The user who creates the Webex Teams connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="b13ab-130">この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="b13ab-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b13ab-131">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="b13ab-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="b13ab-132">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="b13ab-133">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="b13ab-134">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b13ab-134">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webex-teams-connector"></a><span data-ttu-id="b13ab-135">手順 1: Webex Teams コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="b13ab-135">Step 1: Set up the Webex Teams connector</span></span>

<span data-ttu-id="b13ab-136">最初の手順は、 **データ** コネクタにアクセスし [、Webex Teams コネクタをセットアップ](https://globanet.com/webex-teams/) することです。</span><span class="sxs-lookup"><span data-stu-id="b13ab-136">The first step is to gain access to the **Data Connectors** and set up the [Webex Teams](https://globanet.com/webex-teams/) connector.</span></span>

1. <span data-ttu-id="b13ab-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **Webex Teams**.</span><span class="sxs-lookup"><span data-stu-id="b13ab-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webex Teams**.</span></span>

2. <span data-ttu-id="b13ab-138">**Webex Teams 製品の説明ページ** で、[コネクタの追加]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="b13ab-138">On the **Webex Teams** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="b13ab-139">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b13ab-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="b13ab-140">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="b13ab-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="b13ab-141">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b13ab-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webex-teams-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="b13ab-142">手順 2: Globanet Merge1 サイトで Webex Teams コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="b13ab-142">Step 2: Configure the Webex Teams connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="b13ab-143">2 番目の手順は、Merge1 サイトで Webex Teams コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="b13ab-143">The second step is to configure the Webex Teams connector on the Merge1 site.</span></span> <span data-ttu-id="b13ab-144">Webex Teams コネクタを構成する方法の詳細については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="b13ab-144">For information about how to configure the Webex Teams connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="b13ab-145">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="b13ab-146">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="b13ab-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="b13ab-147">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-147">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="b13ab-148">**[Webex Teams ユーザーを Microsoft 365 ユーザーに** マップする] ページで、ユーザーの自動マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b13ab-148">On the **Map Webex Teams users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="b13ab-149">Webex Teams アイテムには、組織内のユーザーの電子メール アドレスを含む Email というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-149">The Webex Teams items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="b13ab-150">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="b13ab-151">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-151">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webex-teams-connector"></a><span data-ttu-id="b13ab-152">手順 4: Webex Teams コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="b13ab-152">Step 4: Monitor the Webex Teams connector</span></span>

<span data-ttu-id="b13ab-153">Webex Teams コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-153">After you create the Webex Teams connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="b13ab-154">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="b13ab-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b13ab-155">[ **コネクタ] タブを** クリックし **、Webex Teams** コネクタを選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="b13ab-155">Click the **Connectors** tab and then select the **Webex Teams** connector to display the flyout page.</span></span> <span data-ttu-id="b13ab-156">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="b13ab-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="b13ab-157">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="b13ab-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="b13ab-158">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b13ab-158">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="b13ab-159">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b13ab-159">Known issues</span></span>

- <span data-ttu-id="b13ab-160">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b13ab-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="b13ab-161">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="b13ab-161">Support for larger items will be available at a later date.</span></span>
