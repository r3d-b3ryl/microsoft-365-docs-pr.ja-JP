---
title: Microsoft 365 で FX 接続データをアーカイブするためのコネクタの設定
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
description: 管理者は、Microsoft 365 で Globanet FX Connect からデータをインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: d22313ab1de1700c14ee4b35f6a0e3dbcae73ae3
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405588"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data-preview"></a><span data-ttu-id="f1ec3-104">コネクタを設定して、FX 接続データをアーカイブする (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f1ec3-104">Set up a connector to archive FX Connect data (preview)</span></span>

<span data-ttu-id="f1ec3-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、FX Connect コラボレーションプラットフォームから Microsoft 365 組織のユーザーメールボックスへのデータのインポートとアーカイブを行います。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the FX Connect collaboration platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="f1ec3-106">Globanet には、FX 接続項目をキャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された [Fx 接続](https://globanet.com/fx-connect/) コネクタが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-106">Globanet provides an [FX Connect](https://globanet.com/fx-connect/) connector that is configured to capture FX Connect items and import those items to Microsoft 365.</span></span> <span data-ttu-id="f1ec3-107">コネクタは、組織の FX Connect アカウントからの、取引、メッセージ、その他の詳細などの FX Connect からのコンテンツを電子メールメッセージの形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-107">The connector converts the content from FX Connect, such as  trades, messages, and other details from your organization's FX Connect account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="f1ec3-108">FX Connect データがユーザーのメールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信のコンプライアンスなど、Microsoft 365 のコンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-108">After FX Connect data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="f1ec3-109">Microsoft 365 でのデータのインポートおよびアーカイブに FX Connect コネクタを使用することで、組織は政府および規制ポリシーに準拠したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-109">Using a FX Connect connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-fx-connect-data"></a><span data-ttu-id="f1ec3-110">FX 接続データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="f1ec3-110">Overview of archiving FX Connect data</span></span>

<span data-ttu-id="f1ec3-111">次の概要では、コネクタを使用して Microsoft 365 の FX 接続情報をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-111">The following overview explains the process of using a connector to archive the FX Connect information in Microsoft 365.</span></span>

![FX 接続データのアーカイブワークフロー](../media/FXConnectConnectorWorkflow.png)

1. <span data-ttu-id="f1ec3-113">組織は FX Connect を使用して、FX 接続サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-113">Your organization works with FX Connect to set up and configure an FX Connect site.</span></span>

2. <span data-ttu-id="f1ec3-114">24時間ごとに、FX Connect アカウントからのアイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-114">Once every 24 hours, items from FX Connect accounts are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="f1ec3-115">また、コネクタは、FX Connect アイテムを電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-115">The connector also converts the FX Connect items to an email message format.</span></span>

3. <span data-ttu-id="f1ec3-116">Microsoft 365 コンプライアンスセンターで作成する FX 接続コネクタは、Globanet Merge1 サイトに毎日接続し、Microsoft クラウド内のセキュアな Azure ストレージの場所に FX Connect アイテムを転送します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-116">The FX Connect connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the FX Connect items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="f1ec3-117">コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの*Email*プロパティの値を使用して、特定のユーザーのメールボックスにアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="f1ec3-118">ユーザーメールボックスに [ **FX Connect** ] という名前の受信トレイフォルダー内のサブフォルダーが作成され、アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-118">A subfolder in the Inbox folder named **FX Connect** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="f1ec3-119">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="f1ec3-120">すべての FX Connect アイテムには、アイテムのすべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-120">Every FX Connect item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f1ec3-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="f1ec3-121">Before you begin</span></span>

- <span data-ttu-id="f1ec3-122">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span>  <span data-ttu-id="f1ec3-123">これを行うには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="f1ec3-124">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="f1ec3-125">手順1で FX の接続コネクタを作成したユーザー (および手順3で完了したもの) は、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-125">The user who creates the FX Connect connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="f1ec3-126">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f1ec3-127">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="f1ec3-128">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="f1ec3-129">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="f1ec3-130">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-fx-connect-connector"></a><span data-ttu-id="f1ec3-131">手順 1: FX 接続コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="f1ec3-131">Step 1: Set up the FX Connect connector</span></span>

<span data-ttu-id="f1ec3-132">最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、FX Connect データ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for FX Connect data.</span></span>

1. <span data-ttu-id="f1ec3-133">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) して、[**データコネクタ**  >  **FX Connect**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **FX Connect**.</span></span>

2. <span data-ttu-id="f1ec3-134">[ **FX Connect** 製品の説明] ページで、[ **コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-134">On the **FX Connect** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="f1ec3-135">[ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="f1ec3-136">コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="f1ec3-137">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-fx-connect-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="f1ec3-138">手順 2: Globanet Merge1 サイトで FX 接続コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="f1ec3-138">Step 2: Configure the FX Connect connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="f1ec3-139">2番目の手順は、Merge1 サイトで FX Connect コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-139">The second step is to configure the FX Connect connector on the Merge1 site.</span></span> <span data-ttu-id="f1ec3-140">FX 接続コネクタを構成する方法については、「 [Merge1 サードパーティコネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-140">For information about how to configure the FX Connect connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="f1ec3-141">[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター (コネクタウィザードの [ **ユーザーマッピング** ] ページ) に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-141">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="f1ec3-142">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="f1ec3-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="f1ec3-143">ユーザーをマップし、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="f1ec3-144">[FX へのユーザーの **Microsoft 365 ユーザーへの接続** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-144">On the **Map FX Connect users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="f1ec3-145">FX Connect 項目には、 *電子メール*というプロパティがあります。このプロパティには、組織内のユーザーの電子メールアドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-145">The FX Connect items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="f1ec3-146">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="f1ec3-147">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-147">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="f1ec3-148">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="f1ec3-149">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="f1ec3-150">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="f1ec3-151">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="f1ec3-152">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="f1ec3-153">[ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-153">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-fx-connect-connector"></a><span data-ttu-id="f1ec3-154">手順 4: FX Connect connector を監視する</span><span class="sxs-lookup"><span data-stu-id="f1ec3-154">Step 4: Monitor the FX Connect connector</span></span>

<span data-ttu-id="f1ec3-155">FX 接続コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-155">After you create the FX Connect connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="f1ec3-156"><https://compliance.microsoft.com/>左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-156">Go to <https://compliance.microsoft.com/> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="f1ec3-157">[ **コネクタ** ] タブをクリックし、[ **FX Connect** コネクタ] を選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-157">Click the **Connectors** tab and then select the **FX Connect** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="f1ec3-158">[ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="f1ec3-159">このログには、Microsoft クラウドにインポートされたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-159">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f1ec3-160">既知の問題</span><span class="sxs-lookup"><span data-stu-id="f1ec3-160">Known issues</span></span>

- <span data-ttu-id="f1ec3-161">現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="f1ec3-161">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
