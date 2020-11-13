---
title: Microsoft 365 で CellTrust データをアーカイブするためのコネクタの設定
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
description: 管理者は、Globanet から Microsoft 365 に対して、セルの信頼データをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: c5ed8af29ad3b81b19e80cfe98702b5e357d9815
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002792"
---
# <a name="set-up-a-connector-to-archive-celltrust-data-preview"></a><span data-ttu-id="a5e07-105">コネクタを設定して、セルをアーカイブする信頼データをアーカイブする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a5e07-105">Set up a connector to archive CellTrust data (preview)</span></span>

<span data-ttu-id="a5e07-106">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、CellTrust プラットフォームから Microsoft 365 組織のユーザーメールボックスにデータをインポートし、アーカイブします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the CellTrust platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="a5e07-107">Globanet には、サードパーティのデータソースからアイテムを取得するように構成されている (定期的に) [Celltrust](https://globanet.com/celltrust/) コネクタが用意されており、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-107">Globanet provides a [CellTrust](https://globanet.com/celltrust/) connector that's configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="a5e07-108">コネクタは、SMS メッセージの内容を CellTrust アカウントから電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-108">The connector converts the content of SMS messages from CellTrust accounts to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="a5e07-109">CellTrust データがユーザーのメールボックスに格納されている場合は、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-109">After CellTrust data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="a5e07-110">Microsoft 365 で CellTrust コネクタを使用してデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-110">Using a CellTrust connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-celltrust-data"></a><span data-ttu-id="a5e07-111">セルのアーカイブの概要データの信頼データ</span><span class="sxs-lookup"><span data-stu-id="a5e07-111">Overview of archiving CellTrust data</span></span>

<span data-ttu-id="a5e07-112">次の概要では、コネクタを使用して、Microsoft 365 で CellTrust データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-112">The following overview explains the process of using a connector to archive CellTrust data in Microsoft 365.</span></span>

![CellTrust データのアーカイブワークフロー](../media/CellTrustConnectorWorkflow.png)

1. <span data-ttu-id="a5e07-114">組織は CellTrust を使用して、CellTrust サイトをセットアップして構成します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-114">Your organization works with CellTrust to set up and configure a CellTrust site.</span></span>

2. <span data-ttu-id="a5e07-115">24時間ごとに、CellTrust アイテムは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-115">Once every 24 hours, CellTrust items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="a5e07-116">また、コネクタは、メッセージの内容を電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-116">The connector also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="a5e07-117">Microsoft 365 コンプライアンスセンターで作成した CellTrust コネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-117">The CellTrust connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="a5e07-118">[自動ユーザーマッピング] コネクタは、 [手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されている *電子メール* プロパティの値を使用して、特定のユーザーのメールボックスにアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="a5e07-119">ユーザーメールボックスに " **Celltrust** " という名前の受信トレイフォルダー内のサブフォルダーが作成され、そのフォルダーにメッセージアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-119">A subfolder in the Inbox folder named **CellTrust** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="a5e07-120">コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="a5e07-121">各 CellTrust アイテムには、すべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5e07-121">Every CellTrust item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a5e07-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="a5e07-122">Before you begin</span></span>

- <span data-ttu-id="a5e07-123">Microsoft コネクタの Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="a5e07-124">アカウントを作成するには、 [Globanet カスタマーサポート](https://globanet.com/contact-us/)に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="a5e07-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="a5e07-125">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e07-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="a5e07-126">手順1で CellTrust コネクタを作成して (手順3で完了させる) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e07-126">The user who creates the CellTrust connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a5e07-127">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="a5e07-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a5e07-128">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="a5e07-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="a5e07-129">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a5e07-130">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a5e07-131">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e07-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-celltrust-connector"></a><span data-ttu-id="a5e07-132">手順 1: CellTrust コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="a5e07-132">Step 1: Set up the CellTrust connector</span></span>

<span data-ttu-id="a5e07-133">最初の手順として、Microsoft 365 コンプライアンスセンターの **データコネクタ** にアクセスし、celltrust データ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-133">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for CellTrust data.</span></span>

1. <span data-ttu-id="a5e07-134">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **データコネクタ** の \> **セル信頼** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **CellTrust**.</span></span>

2. <span data-ttu-id="a5e07-135">[ **Celltrust** product description] ページで、[ **コネクタの追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-135">On the **CellTrust** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="a5e07-136">[ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="a5e07-137">コネクタを識別する一意の名前を入力し、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="a5e07-138">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-celltrust-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="a5e07-139">手順 2: Globanet Merge1 サイトで CellTrust コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="a5e07-139">Step 2: Configure the CellTrust connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="a5e07-140">2番目の手順は、Globanet Merge1 サイトで CellTrust コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="a5e07-140">The second step is to configure the CellTrust connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="a5e07-141">CellTrust コネクタを構成する方法については、「 [Merge1 サードパーティコネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5e07-141">For information about how to configure the CellTrust connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="a5e07-142">[ **保存 & 完了** ] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="a5e07-143">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="a5e07-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="a5e07-144">ユーザーをマップし、Microsoft 365 コンプライアンスセンターで設定したコネクタを完成させるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-144">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="a5e07-145">[ **マップのセルを Microsoft 365 ユーザーに信頼する** ] ページで、自動ユーザーマッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-145">On the **Map CellTrust users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="a5e07-146">CellTrust アイテムには、 *電子メール* というプロパティが含まれています。このプロパティには、組織内のユーザーの電子メールアドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5e07-146">The CellTrust items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="a5e07-147">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="a5e07-148">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="a5e07-149">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="a5e07-150">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="a5e07-151">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e07-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="a5e07-152">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5e07-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="a5e07-153">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="a5e07-154">[ **次へ** ] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-154">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-celltrust-connector"></a><span data-ttu-id="a5e07-155">手順 4: CellTrust コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="a5e07-155">Step 4: Monitor the CellTrust connector</span></span>

<span data-ttu-id="a5e07-156">CellTrust コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-156">After you create the CellTrust connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a5e07-157">[https://compliance.microsoft.com](https://compliance.microsoft.com/)左側のナビゲーションに移動し、[ **データコネクタ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5e07-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a5e07-158">[ **コネクタ** ] タブをクリックしてから、[ **celltrust** コネクタ] を選択して、フライアウトページを表示します。このページには、コネクタに関するプロパティと情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5e07-158">Click the **Connectors** tab and then select the **CellTrust** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="a5e07-159">[ **コネクタの状態 (ソース付き** )] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="a5e07-159">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="a5e07-160">このログには、Microsoft クラウドにインポートされたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a5e07-160">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a5e07-161">既知の問題</span><span class="sxs-lookup"><span data-stu-id="a5e07-161">Known issues</span></span>

- <span data-ttu-id="a5e07-162">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a5e07-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="a5e07-163">より大きいアイテムのサポートは、後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="a5e07-163">Support for larger items will be available at a later date.</span></span>
