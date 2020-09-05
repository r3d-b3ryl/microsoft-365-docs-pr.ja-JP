---
title: Microsoft 365 のアーカイブ余裕期間電子情報開示データへのコネクタの設定
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
description: 管理者は、Globanet 余裕情報開示から Microsoft 365 にデータをインポートしてアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 86a6595ae12201e5083b524661ef53dba54f8cf3
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399308"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data-preview"></a><span data-ttu-id="7515c-104">コネクタをアーカイブ余裕期間電子情報開示データに設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7515c-104">Set up a connector to archive Slack eDiscovery data (preview)</span></span>

<span data-ttu-id="7515c-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、ソーシャルメディア、インスタントメッセージング、およびドキュメントコラボレーションプラットフォームから Microsoft 365 組織のメールボックスにサードパーティのデータをインポートし、アーカイブします。</span><span class="sxs-lookup"><span data-stu-id="7515c-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive third-party data from social media, instant messaging, and document collaboration platforms to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="7515c-106">Globanet は、サードパーティのデータソースからアイテムを取得するように構成された余裕期間電子情報開示コネクタ (定期的に) を提供し、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="7515c-106">Globanet provides a Slack eDiscovery connector that is configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="7515c-107">余裕期間電子情報開示は、余裕期間 API からメッセージやファイルを取得し、それを電子メールメッセージ形式に変換して、そのアイテムをユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="7515c-107">Slack eDiscovery pulls messages and files from the Slack API and converts them to an email message format and then imports the item to user mailboxes.</span></span>

<span data-ttu-id="7515c-108">余裕期間の電子情報開示データはユーザーのメールボックスに格納されます。訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="7515c-108">After Slack eDiscovery data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="7515c-109">Microsoft 365 でデータをインポートおよびアーカイブするために余裕期間の電子情報開示コネクタを使用することにより、組織は政府および規制ポリシーに準拠したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7515c-109">Using a Slack eDiscovery connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-ediscovery-data"></a><span data-ttu-id="7515c-110">アーカイブ余裕期間の電子情報開示データの概要</span><span class="sxs-lookup"><span data-stu-id="7515c-110">Overview of archiving Slack eDiscovery data</span></span>

<span data-ttu-id="7515c-111">次の概要では、コネクタを使用して、Microsoft 365 で余裕期間電子情報開示情報をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7515c-111">The following overview explains the process of using a connector to archive the Slack eDiscovery information in Microsoft 365.</span></span>

![余裕期間電子情報開示アーカイブワークフロー](../media/SlackeDiscoveryConnectorWorkflow.png)

1. <span data-ttu-id="7515c-113">組織は余裕期間電子情報開示を使用して、余裕期間電子情報開示サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="7515c-113">Your organization works with Slack eDiscovery to set up and configure a Slack eDiscovery site.</span></span>

2. <span data-ttu-id="7515c-114">24時間ごとに、余裕期間電子情報開示からのチャットメッセージは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="7515c-114">Once every 24 hours, chat messages from Slack eDiscovery are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="7515c-115">また、コネクタは、チャットメッセージの内容を電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="7515c-115">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="7515c-116">Microsoft 365 コンプライアンスセンターで作成した余裕期間電子情報開示コネクタは、毎日 Globanet Merge1 サイトに接続し、チャットメッセージを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="7515c-116">The Slack eDiscovery connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the chat messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="7515c-117">手順3で説明されているように、コネクタは、 *電子メール* プロパティの値と自動ユーザーマッピングを使用して、変換されたチャットメッセージアイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="7515c-117">The connector imports the converted chat message items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="7515c-118">ユーザーのメールボックスには、「 **余裕期間電子情報開示** 」という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、チャットメッセージアイテムはそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="7515c-118">A new subfolder in the Inbox folder named **Slack eDiscovery** is created in the user mailboxes, and the chat message items will be imported to that folder.</span></span> <span data-ttu-id="7515c-119">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="7515c-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="7515c-120">すべてのチャットメッセージには、このプロパティが含まれており、チャットメッセージのすべての参加者の電子メールアドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="7515c-120">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7515c-121">開始する前に</span><span class="sxs-lookup"><span data-stu-id="7515c-121">Before you begin</span></span>

- <span data-ttu-id="7515c-122">Globanet Merge1 アカウントを作成するには、余裕期間電子情報開示コネクタの使用条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="7515c-122">Create a Globanet Merge1 account by accepting the terms and conditions for the Slack eDiscovery connector.</span></span> <span data-ttu-id="7515c-123">これを行うには、 [Globanet カスタマーサポート](https://globanet.com/contact-us)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7515c-123">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="7515c-124">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7515c-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="7515c-125">組織の余裕期間エンタープライズアカウントのユーザー名とパスワードを取得します。</span><span class="sxs-lookup"><span data-stu-id="7515c-125">Obtain the username and password for your organization's Slack enterprise account.</span></span> <span data-ttu-id="7515c-126">余裕期間の電子情報開示を構成する場合は、手順2でこのアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7515c-126">You'll need to sign into this account in Step 2 when you configure Slack eDiscovery.</span></span>

- <span data-ttu-id="7515c-127">手順1で余裕期間の電子情報開示コネクタを作成する (および手順3で完了する) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7515c-127">The user who creates the Slack eDiscovery connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="7515c-128">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="7515c-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7515c-129">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="7515c-129">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="7515c-130">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7515c-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="7515c-131">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="7515c-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="7515c-132">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7515c-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a><span data-ttu-id="7515c-133">手順 1: 余裕期間電子情報開示コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="7515c-133">Step 1: Set up the Slack eDiscovery connector</span></span>

<span data-ttu-id="7515c-134">最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスして、余裕期間電子情報開示データ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="7515c-134">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Slack eDiscovery data.</span></span>

1. <span data-ttu-id="7515c-135">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データコネクタ**の  >  **余裕期間電子情報開示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7515c-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Slack eDiscovery**.</span></span>

2. <span data-ttu-id="7515c-136">[ **余裕期間の電子情報開示** の製品の説明] ページで、[ **コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7515c-136">On the **Slack eDiscovery** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="7515c-137">[ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7515c-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="7515c-138">コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7515c-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="7515c-139">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="7515c-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-slack-ediscovery"></a><span data-ttu-id="7515c-140">手順 2: 余裕期間の電子情報開示を構成する</span><span class="sxs-lookup"><span data-stu-id="7515c-140">Step 2: Configure Slack eDiscovery</span></span>

<span data-ttu-id="7515c-141">2番目の手順は、Merge1 サイトで余裕期間電子情報開示コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="7515c-141">The second step is to configure the Slack eDiscovery connector on the Merge1 site.</span></span> <span data-ttu-id="7515c-142">Globanet Merge1 サイトで余裕期間電子情報開示コネクタを構成する方法の詳細については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7515c-142">For more information about how to configure the Slack eDiscovery connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span></span>

<span data-ttu-id="7515c-143">[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター (コネクタウィザードの [ **ユーザーマッピング** ] ページ) に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="7515c-143">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="7515c-144">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="7515c-144">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="7515c-145">[ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7515c-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="7515c-146">余裕期間電子情報開示アイテムには、 *電子メール*というプロパティが含まれています。これには、組織内のユーザーの電子メールアドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7515c-146">Slack eDiscovery items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="7515c-147">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="7515c-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="7515c-148">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7515c-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="7515c-149">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="7515c-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="7515c-150">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7515c-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="7515c-151">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="7515c-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="7515c-152">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7515c-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="7515c-153">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="7515c-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="7515c-154">[ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="7515c-154">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a><span data-ttu-id="7515c-155">手順 4: 余裕期間電子情報開示コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="7515c-155">Step 4: Monitor the Slack eDiscovery connector</span></span>

<span data-ttu-id="7515c-156">余裕期間の電子情報開示コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7515c-156">After you create the Slack eDiscovery connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="7515c-157">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7515c-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="7515c-158">[ **コネクタ** ] タブをクリックし、[ **余裕期間の電子情報開示** ] コネクタを選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="7515c-158">Click the **Connectors** tab and then select the **Slack eDiscovery** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="7515c-159">[ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="7515c-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="7515c-160">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7515c-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="7515c-161">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7515c-161">Known issues</span></span>

- <span data-ttu-id="7515c-162">現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="7515c-162">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
