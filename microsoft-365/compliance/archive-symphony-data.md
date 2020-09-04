---
title: Microsoft 365 で Symphony データをアーカイブするためのコネクタをセットアップする
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
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Globanet Symphony から Microsoft 365 にデータをインポートしてアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 29af0cda6d1f6b194c13047382ab7e01b6b200dc
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361798"
---
# <a name="set-up-a-connector-to-archive-symphony-data-preview"></a><span data-ttu-id="cfe6f-104">Symphony データをアーカイブするためのコネクタを設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cfe6f-104">Set up a connector to archive Symphony data (preview)</span></span>

<span data-ttu-id="cfe6f-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、Symphony データを Microsoft 365 組織のユーザーのメールボックスにインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive Symphony data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="cfe6f-106">Symphony は、金融サービス業界で使用されるメッセージングおよびコラボレーションのプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-106">Symphony is a messaging and collaboration platform used in the financial services industry.</span></span> <span data-ttu-id="cfe6f-107">Globanet は、Microsoft 365 コンプライアンスセンターで、サードパーティのデータソースからアイテムを取得するように構成できる [Symphony データコネクタ](https://globanet.com/symphony) を (定期的に) 提供し、それらのアイテムをユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-107">Globanet provides a [Symphony data connector](https://globanet.com/symphony) in the Microsoft 365 compliance center that you can configured to capture items from the third-party data source (on a regular basis) and then import those items to user mailboxes.</span></span> <span data-ttu-id="cfe6f-108">コネクタは、アイテムのコンテンツを Symphony アカウントから電子メールメッセージ形式に変換し、そのアイテムを Microsoft 365 のメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-108">The connector converts the content of an item from the Symphony account to an email message format and then imports the item to a mailbox in Microsoft 365.</span></span>

<span data-ttu-id="cfe6f-109">Symphony 通信がユーザーのメールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-109">After Symphony communications are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="cfe6f-110">Symphony コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることで、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-110">Using a Symphony connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-symphony-data"></a><span data-ttu-id="cfe6f-111">Symphony データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="cfe6f-111">Overview of archiving Symphony data</span></span>

<span data-ttu-id="cfe6f-112">次の概要では、データコネクタを使用して Microsoft 365 の Symphony 通信をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-112">The following overview explains the process of using a data connector to archive Symphony communications in Microsoft 365.</span></span>

![Symphony アーカイブワークフロー](../media/SymphonyConnectorWorkflow.png)

1. <span data-ttu-id="cfe6f-114">組織は Symphony を使用して、Symphony サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-114">Your organization works with Symphony to set up and configure a Symphony site.</span></span>

2. <span data-ttu-id="cfe6f-115">24時間ごとに、Symphony からのチャットメッセージが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-115">Once every 24 hours, chat messages from Symphony are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="cfe6f-116">また、コネクタは、チャットメッセージの内容を電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-116">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="cfe6f-117">Microsoft 365 コンプライアンスセンターで作成した Symphony コネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-117">The Symphony connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="cfe6f-118">このコネクタは、手順3で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換されたメッセージアイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="cfe6f-119">ユーザーメールボックスに **Symphony** という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、そのフォルダーにメッセージアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-119">A new subfolder in the Inbox folder named **Symphony** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="cfe6f-120">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="cfe6f-121">すべてのチャットメッセージには、このプロパティが含まれており、チャットメッセージのすべての参加者の電子メールアドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-121">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cfe6f-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="cfe6f-122">Before you begin</span></span>

- <span data-ttu-id="cfe6f-123">Symphony コネクタの使用条件に同意して、Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-123">Create a Globanet Merge1 account by accepting the terms and conditions for the Symphony connector.</span></span> <span data-ttu-id="cfe6f-124">これを行うには、 [Globanet カスタマーサポート](https://globanet.com/contact-us)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-124">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="cfe6f-125">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="cfe6f-126">手順1で Symphony コネクタを作成したユーザー (手順3で完了します) は、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-126">The user who creates the Symphony connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="cfe6f-127">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="cfe6f-128">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="cfe6f-129">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="cfe6f-130">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="cfe6f-131">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-symphony-connector"></a><span data-ttu-id="cfe6f-132">手順 1: Symphony コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="cfe6f-132">Step 1: Set up the Symphony connector</span></span>

<span data-ttu-id="cfe6f-133">最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、Symphony データ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Symphony data.</span></span>

1. <span data-ttu-id="cfe6f-134">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データコネクタ**の Symphony] をクリックし  >  **Symphony**ます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Symphony**.</span></span>

2. <span data-ttu-id="cfe6f-135">**Symphony**製品の説明ページで、[**コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-135">On the **Symphony** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="cfe6f-136">[ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="cfe6f-137">コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="cfe6f-138">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="configure-the-symphony-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="cfe6f-139">Globanet Merge1 サイトで Symphony コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="cfe6f-139">Configure the Symphony connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="cfe6f-140">2番目の手順は、Merge1 サイト上の Symphony コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-140">The second step is to configure the Symphony connector on the Merge1 site.</span></span> <span data-ttu-id="cfe6f-141">Globanet Merge1 サイトでの Symphony コネクタの構成の詳細については、「 [Merge1 サードパーティ製コネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-141">For information about configuring  the Symphony connector in the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Symphony%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="cfe6f-142">[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター、コネクタウィザードの [ **ユーザーマッピング** ] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-142">After you click **Save & Finish**, you are returned to the Microsoft 365 compliance center, to the **User mapping** page of the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="cfe6f-143">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="cfe6f-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="cfe6f-144">ユーザーをマップし、Microsoft 365 コンプライアンスセンターで設定したコネクタを完成させるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-144">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="cfe6f-145">[ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="cfe6f-146">Symphony のアイテムには、組織内のユーザーの電子メールアドレスを含む *email*というプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-146">The Symphony items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="cfe6f-147">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="cfe6f-148">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="cfe6f-149">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="cfe6f-150">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="cfe6f-151">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="cfe6f-152">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="cfe6f-153">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="cfe6f-154">[ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-154">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-symphony-connector"></a><span data-ttu-id="cfe6f-155">手順 4: Symphony コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="cfe6f-155">Step 4: Monitor the Symphony connector</span></span>

<span data-ttu-id="cfe6f-156">Symphony コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-156">After you create the Symphony connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="cfe6f-157">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="cfe6f-158">[ **コネクタ** ] タブをクリックし、[ **Symphony** コネクタ] を選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-158">Click the **Connectors** tab and then select the **Symphony** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="cfe6f-159">[ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="cfe6f-160">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="cfe6f-161">既知の問題</span><span class="sxs-lookup"><span data-stu-id="cfe6f-161">Known issues</span></span>

- <span data-ttu-id="cfe6f-162">現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="cfe6f-162">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
