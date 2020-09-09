---
title: Microsoft 365 で EML データをアーカイブするためのコネクタの設定
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
description: 管理者は、Globanet から Microsoft 365 に EML データをインポートしてアーカイブするためのコネクタを設定できます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 99b32960b46853ed4766c255e36df05c8fe9086a
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405598"
---
# <a name="set-up-a-connector-to-archive-eml-data-preview"></a><span data-ttu-id="c504c-104">EML データをアーカイブするようにコネクタを設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="c504c-104">Set up a connector to archive EML data (preview)</span></span>

<span data-ttu-id="c504c-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、EML データを Microsoft 365 組織のユーザーのメールボックスにインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="c504c-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive EML data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c504c-106">EML は、ファイルに保存される電子メールメッセージのファイル拡張子です。</span><span class="sxs-lookup"><span data-stu-id="c504c-106">EML is the file extension for an email message saved to a file.</span></span> <span data-ttu-id="c504c-107">コネクタは、アイテムのコンテンツをソース形式から電子メールメッセージ形式に変換し、そのアイテムをユーザーメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="c504c-107">The connector converts the content of an item from the source format to an email message format and then imports the item to a user mailbox.</span></span>

<span data-ttu-id="c504c-108">EML メッセージをユーザーのメールボックスに格納した後は、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="c504c-108">After EML messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="c504c-109">EML コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="c504c-109">Using an EML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-eml-data"></a><span data-ttu-id="c504c-110">EML データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="c504c-110">Overview of archiving EML data</span></span>

<span data-ttu-id="c504c-111">次の概要では、コネクタを使用して Microsoft 365 の EML データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c504c-111">The following overview explains the process of using a connector to archive EML data in Microsoft 365.</span></span>

![EML データのアーカイブワークフロー](../media/EMLConnectorWorkflow.png)

1. <span data-ttu-id="c504c-113">組織は EML ソースを使用して、EML サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="c504c-113">Your organization works with the EML source to set up and configure an EML site.</span></span>

2. <span data-ttu-id="c504c-114">24時間ごとに、EML ソースのコンテンツアイテムは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c504c-114">Once every 24 hours, content items from the EML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="c504c-115">このプロセスでは、EML ファイルの内容が電子メールメッセージの形式に変換されます。</span><span class="sxs-lookup"><span data-stu-id="c504c-115">During this process, the content of an EML file is converted to an email message format.</span></span>

3. <span data-ttu-id="c504c-116">Microsoft 365 コンプライアンスセンターで作成した EML コネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="c504c-116">The EML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="c504c-117">コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されている自動ユーザーマッピングプロセスの*Email*プロパティの値を使用して、変換されたメッセージアイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="c504c-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping process that's described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="c504c-118">このプロセスでは、 **eml**という名前の受信トレイフォルダー内のサブフォルダーがユーザーのメールボックス内に作成され、そのフォルダーに eml アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c504c-118">During this process, a subfolder in the Inbox folder named **EML**is created in the user mailboxes, and the EML items are imported to that folder.</span></span> <span data-ttu-id="c504c-119">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="c504c-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="c504c-120">すべてのメッセージにこのプロパティが含まれており、コンテンツ項目のすべての参加者の電子メールアドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c504c-120">Every message contains this property, which is populated with the email address of every participant of the content item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c504c-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="c504c-121">Before you begin</span></span>

- <span data-ttu-id="c504c-122">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c504c-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="c504c-123">これを行うには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c504c-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="c504c-124">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c504c-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="c504c-125">手順1で EML コネクタを作成して (手順3で完了させる) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c504c-125">The user who creates the EML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c504c-126">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c504c-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c504c-127">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="c504c-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c504c-128">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c504c-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c504c-129">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c504c-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c504c-130">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c504c-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-eml-connector"></a><span data-ttu-id="c504c-131">手順 1: EML コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="c504c-131">Step 1: Set up an EML Connector</span></span>

<span data-ttu-id="c504c-132">最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、EML データ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="c504c-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for EML data.</span></span>

1. <span data-ttu-id="c504c-133">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データコネクタ**の EML] をクリックし  >  **EML**ます。</span><span class="sxs-lookup"><span data-stu-id="c504c-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **EML**.</span></span>

2. <span data-ttu-id="c504c-134">[ **EML** product description] ページで、[ **コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c504c-134">On the **EML** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="c504c-135">[ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c504c-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="c504c-136">コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c504c-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="c504c-137">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="c504c-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="c504c-138">手順 2: Globanet Merge1 サイトで EML コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="c504c-138">Step 2: Configure the EML connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="c504c-139">2番目の手順は、Globanet Merge1 サイトで EML コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="c504c-139">The second step is to configure the EML connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="c504c-140">EML コネクタの構成の詳細については、「 [Merge1 サードパーティコネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c504c-140">For information about configuring  the EML connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="c504c-141">[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター、コネクタウィザードの [ **ユーザーマッピング** ] ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c504c-141">After you click **Save & Finish**, you are returned to the Microsoft 365 compliance center, to the **User mapping** page of the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="c504c-142">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="c504c-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="c504c-143">ユーザーをマップし、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c504c-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="c504c-144">[ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c504c-144">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="c504c-145">EML ソースのアイテムには、 *電子メール*というプロパティが含まれています。これには、組織内のユーザーの電子メールアドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c504c-145">The EML source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="c504c-146">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスに EML アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c504c-146">If the connector can associate this address with a Microsoft 365 user, the EML items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="c504c-147">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c504c-147">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="c504c-148">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c504c-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="c504c-149">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c504c-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="c504c-150">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c504c-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="c504c-151">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c504c-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="c504c-152">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="c504c-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="c504c-153">[ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="c504c-153">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-eml-connector"></a><span data-ttu-id="c504c-154">手順 4: EML コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="c504c-154">Step 4: Monitor the EML connector</span></span>

<span data-ttu-id="c504c-155">EML コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c504c-155">After you create the EML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="c504c-156">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c504c-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="c504c-157">[ **コネクタ** ] タブをクリックし、[ **EML** ] コネクタを選択して、フライアウトページを表示します。このページには、コネクタに関するプロパティと情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c504c-157">Click the **Connectors** tab and then select the **EML** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="c504c-158">[ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="c504c-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="c504c-159">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c504c-159">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="c504c-160">既知の問題</span><span class="sxs-lookup"><span data-stu-id="c504c-160">Known issues</span></span>

- <span data-ttu-id="c504c-161">現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="c504c-161">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
