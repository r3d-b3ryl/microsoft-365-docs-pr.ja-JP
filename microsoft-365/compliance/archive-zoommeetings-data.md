---
title: Microsoft 365 でズーム会議データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet Zoom Meetings から Microsoft 365 にデータをインポートおよびアーカイブするコネクタを設定できます。 これにより、Microsoft 365 のサード パーティデータ ソースのデータをアーカイブして、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: c61c9a40d85b3bea266df9b1f2dba32301e54e08
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620203"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a><span data-ttu-id="54b87-104">ズーム会議データをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="54b87-104">Set up a connector to archive Zoom Meetings data</span></span>

<span data-ttu-id="54b87-105">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Zoom Meetings から Microsoft 365 組織のユーザー メールボックスにデータをインポートしてアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="54b87-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Zoom Meetings to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="54b87-106">Globanet は、サード パーティのデータ ソースから (定期的に) アイテムをキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された Zoom [Meetings](https://globanet.com/zoom/) コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="54b87-106">Globanet provides a [Zoom Meetings](https://globanet.com/zoom/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="54b87-107">コネクタは、会議のコンテンツ (チャット、記録されたファイル、メタデータを含む) を Zoom Meetings アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="54b87-107">The connector converts the content of the meetings (including chats, recorded files, and metadata) from the Zoom Meetings account to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="54b87-108">ズーム会議のデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="54b87-108">After Zoom Meetings data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="54b87-109">Zoom Meetings コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="54b87-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-meetings-data"></a><span data-ttu-id="54b87-110">ズーム会議データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="54b87-110">Overview of archiving Zoom Meetings data</span></span>

<span data-ttu-id="54b87-111">次の概要では、コネクタを使用して Microsoft 365 のズーム会議データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="54b87-111">The following overview explains the process of using a connector to archive Zoom Meetings data in Microsoft 365.</span></span>

![会議のアーカイブ ワークフローのズーム](../media/ZoomMeetingsConnectorWorkflow.png)

1. <span data-ttu-id="54b87-113">組織はズーム会議と共同で、ズーム会議サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="54b87-113">Your organization works with Zoom Meetings to set up and configure a Zoom Meetings site.</span></span>

2. <span data-ttu-id="54b87-114">24 時間ごとに、Zoom Meetings の会議アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="54b87-114">Once every 24 hours, meeting items from Zoom Meetings are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="54b87-115">コネクタは、会議の内容を電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="54b87-115">The connector also converts the content of the meetings to an email message format.</span></span>

3. <span data-ttu-id="54b87-116">Microsoft 365 コンプライアンス センターで作成した Zoom Meetings コネクタは、毎日 Globanet Merge1 に接続し、会議メッセージを Microsoft クラウド内のセキュリティで保護された Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="54b87-116">The Zoom Meetings connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the meeting messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="54b87-117">コネクタは、手順 3 で説明するように *、Email* プロパティの値と自動ユーザー マッピングを使用して、変換された会議アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="54b87-117">The connector imports the converted meeting items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="54b87-118">Zoom **Meetings** という名前の受信トレイ フォルダーに新しいサブフォルダーがユーザー メールボックスに作成され、会議アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="54b87-118">A new subfolder in the Inbox folder named **Zoom Meetings** is created in user mailboxes, and the meeting items are imported to that folder.</span></span> <span data-ttu-id="54b87-119">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="54b87-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="54b87-120">すべての会議アイテムには、このプロパティが含まれるので、会議のすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="54b87-120">Every meeting item contains this property, which is populated with the email address of every participant of the meeting.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="54b87-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="54b87-121">Before you begin</span></span>

- <span data-ttu-id="54b87-122">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="54b87-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="54b87-123">このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="54b87-123">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="54b87-124">このアカウントは、手順 1 でコネクタを作成するときにサインインします。</span><span class="sxs-lookup"><span data-stu-id="54b87-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="54b87-125">組織の Zoom Business アカウントまたは Zoom Enterprise アカウントのユーザー名とパスワードを取得します。</span><span class="sxs-lookup"><span data-stu-id="54b87-125">Obtain the username and password for your organization's Zoom Business or Zoom Enterprise account.</span></span> <span data-ttu-id="54b87-126">Zoom Meetings コネクタを構成する場合は、手順 2 でこのアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54b87-126">You'll need to sign into this account in Step 2 when you configure the Zoom Meetings connector.</span></span>

- <span data-ttu-id="54b87-127">Zoom Marketplace で次のアプリケーション [を作成します](https://marketplace.zoom.us)。</span><span class="sxs-lookup"><span data-stu-id="54b87-127">Create the following applications in the [Zoom Marketplace](https://marketplace.zoom.us):</span></span>

  - <span data-ttu-id="54b87-128">OAuth アプリケーション</span><span class="sxs-lookup"><span data-stu-id="54b87-128">OAuth application</span></span>

  - <span data-ttu-id="54b87-129">JWT アプリケーション</span><span class="sxs-lookup"><span data-stu-id="54b87-129">JWT application</span></span>

  <span data-ttu-id="54b87-130">これらのアプリケーションを作成すると、Zoom プラットフォームはトークンの生成に使用される一意の資格情報のセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="54b87-130">After you create these applications, the Zoom platform generates a set of unique credentials used to generate the tokens.</span></span> <span data-ttu-id="54b87-131">これらのトークンは、Zoom アカウントに接続してアイテムを Merge1 サイトにコピーするときにコネクタを認証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="54b87-131">These tokens are used to authenticate the connector when it connects to your Zoom account and copies items to the Merge1 site.</span></span> <span data-ttu-id="54b87-132">これらのトークンは、手順 2 でズーム コネクタを構成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="54b87-132">You will use these tokens when you configure the Zoom connector in Step 2.</span></span>

  <span data-ttu-id="54b87-133">OAuth アプリケーションと JWT アプリケーションを作成する方法の詳細な手順については [、「Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b87-133">For step-by step instructions on how to create the OAuth and JWT applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="54b87-134">手順 1 で Zoom Meetings コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の Mailbox Import Export 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="54b87-134">The user who creates the Zoom Meetings connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="54b87-135">この役割は、Microsoft 365コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="54b87-135">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="54b87-136">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="54b87-136">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="54b87-137">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="54b87-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="54b87-138">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="54b87-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="54b87-139">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b87-139">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-zoom-meetings-connector"></a><span data-ttu-id="54b87-140">手順 1: 会議のズーム コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="54b87-140">Step 1: Set up the Zoom Meetings connector</span></span>

<span data-ttu-id="54b87-141">最初の手順は、Microsoft 365 コンプライアンス センターの **Data Connector に** アクセスし、Zoom Meetings コネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="54b87-141">The first step is to access the **Data Connectors** in the Microsoft 365 compliance center and create a Zoom Meetings connector.</span></span>

1. <span data-ttu-id="54b87-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **Zoom Meetings**.</span><span class="sxs-lookup"><span data-stu-id="54b87-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Zoom Meetings**.</span></span>

2. <span data-ttu-id="54b87-143">[ **会議のズーム] 製品の** 説明ページで、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="54b87-143">On the **Zoom Meetings** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="54b87-144">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="54b87-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="54b87-145">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="54b87-145">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="54b87-146">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="54b87-146">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-zoom-meetings-connector"></a><span data-ttu-id="54b87-147">手順 2: 会議のズーム コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="54b87-147">Step 2: Configure the Zoom Meetings connector</span></span>

<span data-ttu-id="54b87-148">2 番目の手順は、Merge1 サイトで会議のズーム コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="54b87-148">The second step is to configure the Zoom Meetings connector on the Merge1 site.</span></span> <span data-ttu-id="54b87-149">Globanet Merge1 サイトで Zoom Meetings コネクタを構成する方法の詳細については [、「Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54b87-149">For more information about how to configure the Zoom Meetings connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="54b87-150">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="54b87-150">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="54b87-151">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="54b87-151">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="54b87-152">[外部ユーザー **を Microsoft 365 ユーザーに** マップする] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="54b87-152">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="54b87-153">会議アイテムのズームには、組織内のユーザーの電子メール アドレスを含む [電子メール] というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="54b87-153">Zoom Meetings items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="54b87-154">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="54b87-154">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox</span></span>

2. <span data-ttu-id="54b87-155">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="54b87-155">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-zoom-meetings-connector"></a><span data-ttu-id="54b87-156">手順 4: 会議のズーム コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="54b87-156">Step 4: Monitor the Zoom Meetings connector</span></span>

<span data-ttu-id="54b87-157">Zoom Meetings コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="54b87-157">After you create the Zoom Meetings connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="54b87-158">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="54b87-158">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="54b87-159">[ **コネクタ] タブをクリック** し、[ **会議コネクタのズーム]** を選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="54b87-159">Click the **Connectors** tab and then select the **Zoom Meetings** connector to display the flyout page.</span></span> <span data-ttu-id="54b87-160">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="54b87-160">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="54b87-161">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="54b87-161">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="54b87-162">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="54b87-162">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="54b87-163">既知の問題</span><span class="sxs-lookup"><span data-stu-id="54b87-163">Known issues</span></span>

- <span data-ttu-id="54b87-164">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="54b87-164">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="54b87-165">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="54b87-165">Support for larger items will be available at a later date.</span></span>

- <span data-ttu-id="54b87-166">Zoom Meetings コネクタが機能するには、Zoom Meetings を設定するときにレコーディングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54b87-166">For the Zoom Meetings connector to work, you must enable recordings when setting up Zoom Meetings.</span></span>
