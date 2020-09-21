---
title: Microsoft 365 で会議のデータをアーカイブするためのコネクタの設定
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
description: 管理者は、Globanet の会議から Microsoft 365 にデータをインポートしてアーカイブするためのコネクタを設定できます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: c7052e7f51108cac93ad8d87402a07acd12df28a
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956234"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data-preview"></a><span data-ttu-id="94061-104">アーカイブへのコネクタの設定アーカイブ会議データ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="94061-104">Set up a connector to archive Zoom Meetings data (preview)</span></span>

<span data-ttu-id="94061-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、ズーム会議のデータを Microsoft 365 組織のユーザーのメールボックスにインポートし、アーカイブします。</span><span class="sxs-lookup"><span data-stu-id="94061-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from Zoom Meetings to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="94061-106">Globanet では、サードパーティのデータソースからアイテムを取得するように構成された (定期的に)、そのアイテムをズームするための [会議](https://globanet.com/zoom/) コネクタが用意されており、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="94061-106">Globanet provides a [Zoom Meetings](https://globanet.com/zoom/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="94061-107">コネクタは会議のコンテンツ (チャット、記録されたファイル、およびメタデータを含む) を電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="94061-107">The connector converts the content of the meetings (including chats, recorded files, and metadata) from the Zoom Meetings account to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="94061-108">ズーム会議データがユーザーのメールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="94061-108">After Zoom Meetings data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="94061-109">Microsoft 365 でデータをインポートおよびアーカイブするためにズーム会議コネクタを使用することにより、組織は政府および規制ポリシーに準拠したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="94061-109">Using a Zoom Meetings connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-meetings-data"></a><span data-ttu-id="94061-110">アーカイブズーム会議データの概要</span><span class="sxs-lookup"><span data-stu-id="94061-110">Overview of archiving Zoom Meetings data</span></span>

<span data-ttu-id="94061-111">次の概要では、コネクタを使用して Microsoft 365 の会議データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="94061-111">The following overview explains the process of using a connector to archive Zoom Meetings data in Microsoft 365.</span></span>

![会議のズームのアーカイブワークフロー](../media/ZoomMeetingsConnectorWorkflow.png)

1. <span data-ttu-id="94061-113">組織は、会議のズームサイトをセットアップして構成するために、ズーム会議を処理します。</span><span class="sxs-lookup"><span data-stu-id="94061-113">Your organization works with Zoom Meetings to set up and configure a Zoom Meetings site.</span></span>

2. <span data-ttu-id="94061-114">24時間ごとに、ズーム会議からの会議アイテムは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="94061-114">Once every 24 hours, meeting items from Zoom Meetings are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="94061-115">また、コネクタは、会議の内容を電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="94061-115">The connector also converts the content of the meetings to an email message format.</span></span>

3. <span data-ttu-id="94061-116">Microsoft 365 コンプライアンスセンターで作成するズーム会議コネクタは、Globanet Merge1 に毎日接続し、Microsoft クラウド内のセキュリティで保護された Azure ストレージの場所に会議メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="94061-116">The Zoom Meetings connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 every day, and transfers the meeting messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="94061-117">このコネクタは、手順3で説明されているように、 *電子メール* プロパティの値と自動ユーザーマッピングを使用して、変換された会議アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="94061-117">The connector imports the converted meeting items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="94061-118">ユーザーのメールボックスには、" **ズーム会議** " という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、会議アイテムはそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="94061-118">A new subfolder in the Inbox folder named **Zoom Meetings** is created in user mailboxes, and the meeting items are imported to that folder.</span></span> <span data-ttu-id="94061-119">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="94061-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="94061-120">すべての会議アイテムには、会議のすべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="94061-120">Every meeting item contains this property, which is populated with the email address of every participant of the meeting.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="94061-121">開始する前に</span><span class="sxs-lookup"><span data-stu-id="94061-121">Before you begin</span></span>

- <span data-ttu-id="94061-122">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="94061-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="94061-123">これを行うには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="94061-123">To do this, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="94061-124">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94061-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="94061-125">組織の拡大または縮小のエンタープライズアカウントのユーザー名とパスワードを取得します。</span><span class="sxs-lookup"><span data-stu-id="94061-125">Obtain the username and password for your organization's Zoom Business or Zoom Enterprise account.</span></span> <span data-ttu-id="94061-126">会議コネクタをズームするには、手順2でこのアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94061-126">You'll need to sign into this account in Step 2 when you configure the Zoom Meetings connector.</span></span>

- <span data-ttu-id="94061-127">[ズーム Marketplace](https://marketplace.zoom.us)で以下のアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="94061-127">Create the following applications in the [Zoom Marketplace](https://marketplace.zoom.us):</span></span>

  - <span data-ttu-id="94061-128">OAuth アプリケーション</span><span class="sxs-lookup"><span data-stu-id="94061-128">OAuth application</span></span>

  - <span data-ttu-id="94061-129">JWT アプリケーション</span><span class="sxs-lookup"><span data-stu-id="94061-129">JWT application</span></span>

  <span data-ttu-id="94061-130">これらのアプリケーションを作成した後、Zoom プラットフォームは、トークンの生成に使用される一意の資格情報のセットを生成します。</span><span class="sxs-lookup"><span data-stu-id="94061-130">After you create these applications, the Zoom platform generates a set of unique credentials used to generate the tokens.</span></span> <span data-ttu-id="94061-131">これらのトークンは、拡大/縮小アカウントに接続してアイテムを Merge1 サイトにコピーするときにコネクタを認証するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="94061-131">These tokens are used to authenticate the connector when it connects to your Zoom account and copies items to the Merge1 site.</span></span> <span data-ttu-id="94061-132">これらのトークンは、手順2でズームコネクタを構成するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="94061-132">You will use these tokens when you configure the Zoom connector in Step 2.</span></span>

  <span data-ttu-id="94061-133">OAuth および JWT アプリケーションを作成する手順については、「 [Merge1 サードパーティコネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94061-133">For step-by step instructions on how to create the OAuth and JWT applications, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="94061-134">手順1で [ズーム] 会議コネクタを作成する (および手順3で完了する) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="94061-134">The user who creates the Zoom Meetings connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="94061-135">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="94061-135">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="94061-136">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="94061-136">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="94061-137">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="94061-137">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="94061-138">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="94061-138">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="94061-139">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94061-139">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-zoom-meetings-connector"></a><span data-ttu-id="94061-140">手順 1: ズーム会議コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="94061-140">Step 1: Set up the Zoom Meetings connector</span></span>

<span data-ttu-id="94061-141">最初の手順として、Microsoft 365 コンプライアンスセンターの **データコネクタ** にアクセスし、会議コネクタのズームを作成します。</span><span class="sxs-lookup"><span data-stu-id="94061-141">The first step is to access the **Data Connectors** in the Microsoft 365 compliance center and create a Zoom Meetings connector.</span></span>

1. <span data-ttu-id="94061-142">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) 、[**データコネクタ**] [  >  **会議のズーム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94061-142">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Zoom Meetings**.</span></span>

2. <span data-ttu-id="94061-143">[会議製品の説明を **拡大/縮小** する] ページで、[ **コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94061-143">On the **Zoom Meetings** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="94061-144">[ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94061-144">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="94061-145">コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94061-145">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="94061-146">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="94061-146">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-zoom-meetings-connector"></a><span data-ttu-id="94061-147">手順 2: ズーム会議コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="94061-147">Step 2: Configure the Zoom Meetings connector</span></span>

<span data-ttu-id="94061-148">2番目の手順では、Merge1 サイト上のズーム会議コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="94061-148">The second step is to configure the Zoom Meetings connector on the Merge1 site.</span></span> <span data-ttu-id="94061-149">Globanet Merge1 サイトにズーム会議コネクタを構成する方法の詳細については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94061-149">For more information about how to configure the Zoom Meetings connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="94061-150">[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター (コネクタウィザードの [ **ユーザーマッピング** ] ページ) に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="94061-150">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="94061-151">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="94061-151">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="94061-152">[ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="94061-152">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="94061-153">会議アイテムをズームするには、組織内のユーザーの電子メールアドレスを含む *電子メール* というプロパティを含みます。</span><span class="sxs-lookup"><span data-stu-id="94061-153">Zoom Meetings items include a property called *Email* that contains email addresses for users in your organization.</span></span> <span data-ttu-id="94061-154">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="94061-154">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox</span></span>

2. <span data-ttu-id="94061-155">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94061-155">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="94061-156">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="94061-156">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="94061-157">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94061-157">Click **Accept** to provide the consent.</span></span>
  
   <span data-ttu-id="94061-158">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="94061-158">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="94061-159">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94061-159">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="94061-160">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="94061-160">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="94061-161">[ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="94061-161">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-zoom-meetings-connector"></a><span data-ttu-id="94061-162">手順 4: ズーム会議コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="94061-162">Step 4: Monitor the Zoom Meetings connector</span></span>

<span data-ttu-id="94061-163">ズーム会議コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="94061-163">After you create the Zoom Meetings connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="94061-164">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94061-164">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="94061-165">[ **コネクタ** ] タブをクリックし、[ **ミーティングのズーム** コネクタ] を選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="94061-165">Click the **Connectors** tab and then select the **Zoom Meetings** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="94061-166">[ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="94061-166">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="94061-167">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="94061-167">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="94061-168">既知の問題</span><span class="sxs-lookup"><span data-stu-id="94061-168">Known issues</span></span>

- <span data-ttu-id="94061-169">現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="94061-169">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>

- <span data-ttu-id="94061-170">会議のズームコネクタを機能させるには、ズーム会議を設定するときに録画を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94061-170">For the Zoom Meetings connector to work, you must enable recordings when setting up Zoom Meetings.</span></span>
