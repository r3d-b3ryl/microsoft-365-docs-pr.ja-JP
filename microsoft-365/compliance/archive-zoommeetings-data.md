---
title: Microsoft 365 でズーム 会議データをアーカイブするコネクタをセットアップする
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
description: 管理者は、Veritas Zoom Meetings から Microsoft 365 にデータをインポートおよびアーカイブするコネクタをセットアップできます。 これにより、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサード パーティデータを管理できます。
ms.openlocfilehash: b67098f3ddb1149927f4b82270c8fa4f14bbe558
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163731"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a><span data-ttu-id="2f875-104">ズーム 会議データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="2f875-104">Set up a connector to archive Zoom Meetings data</span></span>

<span data-ttu-id="2f875-105">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、Zoom Meetings から Microsoft 365 組織のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="2f875-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from Zoom Meetings to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="2f875-106">Veritas には、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された Zoom [Meetings](https://globanet.com/zoom/) コネクタが提供されています。</span><span class="sxs-lookup"><span data-stu-id="2f875-106">Veritas provides a [Zoom Meetings](https://globanet.com/zoom/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="2f875-107">コネクタは、会議のコンテンツ (チャット、記録されたファイル、メタデータを含む) を Zoom Meetings アカウントから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="2f875-107">The connector converts the content of the meetings (including chats, recorded files, and metadata) from the Zoom Meetings account to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="2f875-108">Zoom Meetings データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="2f875-108">After Zoom Meetings data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="2f875-109">ズーム 会議コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2f875-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-meetings-data"></a><span data-ttu-id="2f875-110">ズーム 会議データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="2f875-110">Overview of archiving Zoom Meetings data</span></span>

<span data-ttu-id="2f875-111">次の概要では、コネクタを使用して Microsoft 365 の Zoom Meetings データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f875-111">The following overview explains the process of using a connector to archive Zoom Meetings data in Microsoft 365.</span></span>

![会議のアーカイブ ワークフローのズーム](../media/ZoomMeetingsConnectorWorkflow.png)

1. <span data-ttu-id="2f875-113">組織は、ズーム会議を使用して、ズーム会議サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="2f875-113">Your organization works with Zoom Meetings to set up and configure a Zoom Meetings site.</span></span>

2. <span data-ttu-id="2f875-114">24 時間に 1 回、ズーム会議の会議アイテムが Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="2f875-114">Once every 24 hours, meeting items from Zoom Meetings are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="2f875-115">また、コネクタは会議のコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="2f875-115">The connector also converts the content of the meetings to an email message format.</span></span>

3. <span data-ttu-id="2f875-116">Microsoft 365 コンプライアンス センターで作成した Zoom Meetings コネクタは、毎日 Veritas Merge1 に接続し、会議メッセージを Microsoft クラウドの安全な Azure Storage の場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="2f875-116">The Zoom Meetings connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 every day, and transfers the meeting messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="2f875-117">コネクタは、手順 3 で説明したように *、Email* プロパティと自動ユーザー マッピングの値を使用して、変換された会議アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="2f875-117">The connector imports the converted meeting items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="2f875-118">Zoom **Meetings** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー のメールボックスに作成され、そのフォルダーに会議アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="2f875-118">A new subfolder in the Inbox folder named **Zoom Meetings** is created in user mailboxes, and the meeting items are imported to that folder.</span></span> <span data-ttu-id="2f875-119">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="2f875-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="2f875-120">すべての会議アイテムには、このプロパティが含まれるので、会議のすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="2f875-120">Every meeting item contains this property, which is populated with the email address of every participant of the meeting.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="2f875-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="2f875-121">Before you begin</span></span>

- <span data-ttu-id="2f875-122">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f875-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="2f875-123">このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="2f875-123">To create this account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="2f875-124">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2f875-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="2f875-125">組織の Zoom Business または Zoom Enterprise アカウントのユーザー名とパスワードを取得します。</span><span class="sxs-lookup"><span data-stu-id="2f875-125">Obtain the username and password for your organization's Zoom Business or Zoom Enterprise account.</span></span> <span data-ttu-id="2f875-126">Zoom Meetings コネクタを構成する場合は、手順 2 でこのアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f875-126">You'll need to sign into this account in Step 2 when you configure the Zoom Meetings connector.</span></span>

- <span data-ttu-id="2f875-127">Zoom Marketplace で次のアプリケーション [を作成します](https://marketplace.zoom.us)。</span><span class="sxs-lookup"><span data-stu-id="2f875-127">Create the following applications in the [Zoom Marketplace](https://marketplace.zoom.us):</span></span>

  - <span data-ttu-id="2f875-128">OAuth アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2f875-128">OAuth application</span></span>

  - <span data-ttu-id="2f875-129">JWT アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2f875-129">JWT application</span></span>

  <span data-ttu-id="2f875-130">これらのアプリケーションを作成すると、Zoom プラットフォームはトークンの生成に使用される一意の資格情報のセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="2f875-130">After you create these applications, the Zoom platform generates a set of unique credentials used to generate the tokens.</span></span> <span data-ttu-id="2f875-131">これらのトークンは、Zoom アカウントに接続し、アイテムを Merge1 サイトにコピーするときにコネクタを認証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f875-131">These tokens are used to authenticate the connector when it connects to your Zoom account and copies items to the Merge1 site.</span></span> <span data-ttu-id="2f875-132">これらのトークンは、手順 2 でズーム コネクタを構成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="2f875-132">You will use these tokens when you configure the Zoom connector in Step 2.</span></span>

  <span data-ttu-id="2f875-133">OAuth アプリケーションと JWT アプリケーションを作成する方法の詳細な手順については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f875-133">For step-by step instructions on how to create the OAuth and JWT applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="2f875-134">手順 1 でズーム 会議コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f875-134">The user who creates the Zoom Meetings connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="2f875-135">Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="2f875-135">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2f875-136">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="2f875-136">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="2f875-137">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2f875-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="2f875-138">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="2f875-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="2f875-139">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f875-139">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-zoom-meetings-connector"></a><span data-ttu-id="2f875-140">手順 1: Zoom Meetings コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="2f875-140">Step 1: Set up the Zoom Meetings connector</span></span>

<span data-ttu-id="2f875-141">最初の手順は、Microsoft  365 コンプライアンス センターのデータ コネクタにアクセスし、Zoom Meetings コネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="2f875-141">The first step is to access the **Data Connectors** in the Microsoft 365 compliance center and create a Zoom Meetings connector.</span></span>

1. <span data-ttu-id="2f875-142">[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) のズーム会議 **] に移動し**  >  **、[データ コネクタ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2f875-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Zoom Meetings**.</span></span>

2. <span data-ttu-id="2f875-143">[会議の **ズーム] 製品の** 説明ページで、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="2f875-143">On the **Zoom Meetings** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="2f875-144">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2f875-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="2f875-145">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2f875-145">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="2f875-146">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="2f875-146">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-zoom-meetings-connector"></a><span data-ttu-id="2f875-147">手順 2: Zoom Meetings コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="2f875-147">Step 2: Configure the Zoom Meetings connector</span></span>

<span data-ttu-id="2f875-148">2 番目の手順は、Merge1 サイトで Zoom Meetings コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="2f875-148">The second step is to configure the Zoom Meetings connector on the Merge1 site.</span></span> <span data-ttu-id="2f875-149">Veritas Merge1 サイトで Zoom Meetings コネクタを構成する方法の詳細については [、「Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)サード パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f875-149">For more information about how to configure the Zoom Meetings connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="2f875-150">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f875-150">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="2f875-151">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="2f875-151">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="2f875-152">[外部ユーザー **を Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="2f875-152">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="2f875-153">Zoom Meetings アイテムには、組織内のユーザーの電子メール アドレスを含む Email というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f875-153">Zoom Meetings items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="2f875-154">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="2f875-154">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox</span></span>

2. <span data-ttu-id="2f875-155">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="2f875-155">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-zoom-meetings-connector"></a><span data-ttu-id="2f875-156">手順 4: Zoom Meetings コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="2f875-156">Step 4: Monitor the Zoom Meetings connector</span></span>

<span data-ttu-id="2f875-157">Zoom Meetings コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2f875-157">After you create the Zoom Meetings connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="2f875-158">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f875-158">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="2f875-159">[コネクタ **] タブをクリック** し、[会議のズーム] **コネクタを選択** して、飛び出しページを表示します。</span><span class="sxs-lookup"><span data-stu-id="2f875-159">Click the **Connectors** tab and then select the **Zoom Meetings** connector to display the flyout page.</span></span> <span data-ttu-id="2f875-160">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="2f875-160">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="2f875-161">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="2f875-161">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="2f875-162">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2f875-162">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2f875-163">既知の問題</span><span class="sxs-lookup"><span data-stu-id="2f875-163">Known issues</span></span>

- <span data-ttu-id="2f875-164">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2f875-164">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="2f875-165">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="2f875-165">Support for larger items will be available at a later date.</span></span>

- <span data-ttu-id="2f875-166">Zoom Meetings コネクタを機能するには、ズーム会議を設定するときに録音を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f875-166">For the Zoom Meetings connector to work, you must enable recordings when setting up Zoom Meetings.</span></span>