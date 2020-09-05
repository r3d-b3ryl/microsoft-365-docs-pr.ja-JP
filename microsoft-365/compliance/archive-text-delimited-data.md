---
title: Microsoft 365 でテキスト区切りのデータをアーカイブするためのコネクタの設定
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
description: 管理者は、Globanet から Microsoft 365 にテキスト区切りのデータをインポートしてアーカイブするためのコネクタを設定できます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: e57e9693da77a246bafcdf30561fd1414761355f
ms.sourcegitcommit: 37ce0658336bea7b27bf8d6aa759deadc97e7365
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "47399298"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data-preview"></a><span data-ttu-id="db998-104">テキスト区切りのデータをアーカイブするようにコネクタを設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="db998-104">Set up a connector to archive text-delimited data (preview)</span></span>

<span data-ttu-id="db998-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、テキスト区切りのデータを Microsoft 365 組織のユーザーのメールボックスにインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="db998-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive text-delimited data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="db998-106">[Globanet](https://globanet.com/merge1/) には、サードパーティのデータソースからアイテムを取得するように構成されたテキスト区切りコネクタがあり (定期的に)、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="db998-106">[Globanet](https://globanet.com/merge1/) provides a Text-Delimited connector that is configured to capture items from a third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="db998-107">コネクタは、コンテンツをテキスト区切りデータソースから電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="db998-107">The connector converts content from the text-delimited data source to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="db998-108">テキスト区切りのデータがユーザーのメールボックスに格納された後は、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="db998-108">After text-delimited data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="db998-109">Microsoft 365 でデータをインポートおよびアーカイブするためにズーム会議コネクタを使用することにより、組織は政府および規制ポリシーに準拠したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="db998-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="db998-110">アーカイブ後、テキスト区切りのソース通信は保持され、コンプライアンスを監視し、eDiscovery および内部情報ガバナンスのために取得することができます。</span><span class="sxs-lookup"><span data-stu-id="db998-110">Once archived, the Text-Delimited source communications can be retained, supervised for compliance, and retrieved for eDiscovery and internal Information Governance.</span></span>

## <a name="overview-of-archiving-the-text-delimited-source"></a><span data-ttu-id="db998-111">テキスト区切りソースのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="db998-111">Overview of archiving the Text-Delimited source</span></span>

<span data-ttu-id="db998-112">次の概要では、コネクタを使用して Microsoft 365 のテキスト区切りのソース情報をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="db998-112">The following overview explains the process of using a connector to archive the Text-Delimited source information in Microsoft 365.</span></span>

![テキストで区切られたデータのアーカイブワークフロー](../media/TextDelimitedConnectorWorkflow.png)

1. <span data-ttu-id="db998-114">組織はテキスト区切りのソースを使用して、テキスト区切りのサイトを設定し、構成します。</span><span class="sxs-lookup"><span data-stu-id="db998-114">Your organization works with the Text-Delimited source to set up and configure a Text-Delimited site.</span></span>

2. <span data-ttu-id="db998-115">24時間ごとに、テキスト区切りソースからのチャットメッセージが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="db998-115">Once every 24 hours, chat messages from the Text-Delimited source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="db998-116">また、コネクタは、コンテンツを電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="db998-116">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="db998-117">Microsoft 365 コンプライアンスセンターで作成するテキスト区切りコネクタは、Globanet Merge1 サイトに毎日接続して、Microsoft クラウド内のセキュアな Azure ストレージの場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="db998-117">The Text-Delimited connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="db998-118">このコネクタは、手順3で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換されたメッセージアイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="db998-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="db998-119">[ **テキスト区切り** ] という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、ユーザーのメールボックスにメッセージアイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="db998-119">A new subfolder in the Inbox folder named **Text- Delimited** will be created in the user mailboxes, and the message items will be imported to that folder.</span></span> <span data-ttu-id="db998-120">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="db998-120">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="db998-121">すべてのメッセージにこのプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メールアドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="db998-121">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="db998-122">開始する前に</span><span class="sxs-lookup"><span data-stu-id="db998-122">Before you begin</span></span>

- <span data-ttu-id="db998-123">Globanet Merge1 アカウントを作成するには、テキスト区切りコネクタの使用条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="db998-123">Create a Globanet Merge1 account by accepting the terms and conditions for the Text-Delimited connector.</span></span> <span data-ttu-id="db998-124">これを行うには、 [Globanet カスタマーサポート](https://globanet.com/contact-us)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="db998-124">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="db998-125">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db998-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="db998-126">手順1でテキスト区切りコネクタを作成し、(手順3で完了する) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db998-126">The user who creates the Text-Delimited connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="db998-127">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="db998-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="db998-128">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="db998-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="db998-129">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="db998-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="db998-130">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="db998-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="db998-131">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db998-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-text-delimited-connector"></a><span data-ttu-id="db998-132">手順 1: テキスト区切りコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="db998-132">Step 1: Set up the Text-Delimited connector</span></span>

<span data-ttu-id="db998-133">最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、テキスト区切りのデータ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="db998-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for text-delimited data.</span></span>

1. <span data-ttu-id="db998-134">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) て、[**データコネクタ**]  >  **テキストを区切り**ます。</span><span class="sxs-lookup"><span data-stu-id="db998-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Text-Delimited**.</span></span>

2. <span data-ttu-id="db998-135">[ **テキスト区切り** 製品の説明] ページで、[ **コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db998-135">On the **Text-Delimited** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="db998-136">[ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db998-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="db998-137">コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db998-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="db998-138">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="db998-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="db998-139">手順 2: Globanet Merge1 サイト上のテキスト区切りコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="db998-139">Step 2: Configure the Text-delimited connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="db998-140">2番目の手順は、Merge1 サイトでテキスト区切りコネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="db998-140">The second step is to configure the Text-Delimited connector in the Merge1 site.</span></span> <span data-ttu-id="db998-141">Globanet Merge1 サイトでテキスト区切りコネクタを構成する方法については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Text-Delimited%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db998-141">For information about configuring  the Text-Delimited connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Text-Delimited%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="db998-142">[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター、コネクタウィザードの [ **ユーザーマッピング** ] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="db998-142">After you click **Save & Finish**, you are returned to the Microsoft 365 compliance center, to the **User mapping** page of the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="db998-143">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="db998-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="db998-144">ユーザーをマップし、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="db998-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="db998-145">[ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="db998-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="db998-146">テキスト区切りのソース項目には、 *電子メール*というプロパティが含まれています。これには、組織内のユーザーの電子メールアドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="db998-146">The Text- Delimited source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="db998-147">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="db998-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="db998-148">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="db998-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="db998-149">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="db998-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="db998-150">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db998-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="db998-151">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="db998-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="db998-152">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db998-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="db998-153">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="db998-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="db998-154">[ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="db998-154">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-text-delimited-connector"></a><span data-ttu-id="db998-155">手順 4: テキスト区切りコネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="db998-155">Step 4: Monitor the text-delimited connector</span></span>

<span data-ttu-id="db998-156">テキスト区切りコネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="db998-156">After you create the Text- Delimited connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="db998-157">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db998-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="db998-158">[ **コネクタ** ] タブをクリックし、 **テキスト区切り** コネクタを選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="db998-158">Click the **Connectors** tab and then select the **Text- Delimited** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="db998-159">[ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="db998-159">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="db998-160">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db998-160">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="db998-161">既知の問題</span><span class="sxs-lookup"><span data-stu-id="db998-161">Known issues</span></span>

- <span data-ttu-id="db998-162">現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="db998-162">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
