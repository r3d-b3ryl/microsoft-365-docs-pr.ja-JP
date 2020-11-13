---
title: Microsoft 365 でデータをアーカイブするためのコネクタの設定 Reuters を処理する
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
description: 管理者は、Globanet から Microsoft 365 にデータを処理する Reuters をインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: bd3eefb1054d8ef9302ffa6f94ddce740bd55a70
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002787"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data-preview"></a><span data-ttu-id="46d6d-105">Reuters のデータをアーカイブするコネクタを設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="46d6d-105">Set up a connector to archive Reuters Dealing data (preview)</span></span>

<span data-ttu-id="46d6d-106">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、Reuters の処理プラットフォームから Microsoft 365 組織のユーザーのメールボックスにデータをインポートし、アーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters Dealing platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="46d6d-107">Globanet では、サードパーティのデータソースからアイテムを取得するように構成された [Reuters の取引](https://globanet.com/reuters-dealing/) コネクタ (定期的に) が提供され、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-107">Globanet provides you with a [Reuters Dealing](https://globanet.com/reuters-dealing/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="46d6d-108">コネクタは、通信を Reuters の処理アカウントから電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-108">The connector converts Dealing communications from the Reuters Dealing account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="46d6d-109">Reuters のデータをユーザーのメールボックスに格納した後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信のコンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-109">After Reuters Dealing data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="46d6d-110">Reuters の取引コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることで、組織は政府および規制ポリシーに準拠したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-110">Using a Reuters Dealing connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-dealing-data"></a><span data-ttu-id="46d6d-111">データを扱うアーカイブ Reuters の概要</span><span class="sxs-lookup"><span data-stu-id="46d6d-111">Overview of archiving Reuters Dealing data</span></span>

<span data-ttu-id="46d6d-112">次の概要では、コネクタを使用して、Microsoft 365 の Reuters を処理するデータをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-112">The following overview explains the process of using a connector to archive the Reuters Dealing data in Microsoft 365.</span></span>

![Reuters を扱うデータをアーカイブするためのアーカイブワークフロー](../media/ReuetersDealingConnectorWorkflow.png)

1. <span data-ttu-id="46d6d-114">組織は Reuters を処理して、Reuters の処理サイトをセットアップして構成します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-114">Your organization works with Reuters Dealing to set up and configure a Reuters Dealing site.</span></span>

2. <span data-ttu-id="46d6d-115">24時間ごとに、Reuters の処理アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-115">Once every 24 hours, Reuters Dealing items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="46d6d-116">また、コネクタは、アイテムを電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-116">The connector also converts the items to an email message format.</span></span>

3. <span data-ttu-id="46d6d-117">Microsoft 365 コンプライアンスセンターで作成した Reuters 取引コネクタは、毎日 Globanet Merge1 サイトに接続し、そのコンテンツを Microsoft クラウド内のセキュリティ保護された Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-117">The Reuters Dealing connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="46d6d-118">コネクタは、 [手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、特定のユーザーのメールボックスにアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="46d6d-119">**Reuters 扱い** という名前の受信トレイフォルダー内のサブフォルダーは、ユーザーメールボックス内に作成され、アイテムはそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-119">A subfolder in the Inbox folder named **Reuters Dealing** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="46d6d-120">コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="46d6d-121">すべての Reuters の処理項目には、アイテムのすべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46d6d-121">Every Reuters Dealing item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="46d6d-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="46d6d-122">Before you begin</span></span>

- <span data-ttu-id="46d6d-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="46d6d-124">アカウントを作成するには、 [Globanet カスタマーサポート](https://globanet.com/contact-us)に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="46d6d-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="46d6d-125">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d6d-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="46d6d-126">手順1で Reuters を処理するコネクタを作成したユーザー (および手順3で完了します) は、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d6d-126">The user who creates the Reuters Dealing connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="46d6d-127">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="46d6d-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="46d6d-128">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="46d6d-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="46d6d-129">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="46d6d-130">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="46d6d-131">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d6d-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article “Manage role groups in Exchange Online”.</span></span>

## <a name="step-1-set-up-the-reuters-dealing-connector"></a><span data-ttu-id="46d6d-132">手順 1: Reuters を処理するコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="46d6d-132">Step 1: Set up the Reuters Dealing connector</span></span>

<span data-ttu-id="46d6d-133">最初の手順として、Microsoft 365 の [ **データコネクタ** ] ページにアクセスして、Reuters を処理するデータ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 and create a connector for Reuters Dealing data.</span></span>

1. <span data-ttu-id="46d6d-134">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) て、[ **データコネクタ**  >  **Reuters 処理** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Dealing**.</span></span>

2. <span data-ttu-id="46d6d-135">[ **Reuters の取引** 製品の説明] ページで、[ **コネクタの追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-135">On the **Reuters Dealing** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="46d6d-136">[ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="46d6d-137">コネクタを識別する一意の名前を入力し、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="46d6d-138">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-138">Sign to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="46d6d-139">手順 2: Globanet Merge1 サイト上の Reuters 取引コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="46d6d-139">Step 2: Configure the Reuters Dealing connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="46d6d-140">2番目の手順では、Merge1 サイトの Globanet の Reuters 処理コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-140">The second step is to configure the Reuters Dealing connector on Globanet the Merge1 site.</span></span> <span data-ttu-id="46d6d-141">Reuters 扱いコネクタの構成の詳細については、「 [Merge1 サードパーティ製コネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46d6d-141">For information about configuring the Reuters Dealing connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="46d6d-142">[ **保存 & 完了** ] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="46d6d-143">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="46d6d-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="46d6d-144">ユーザーをマップし、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="46d6d-145">[ **Map Reuters users To Microsoft 365 users** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-145">On the **Map Reuters Dealing users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="46d6d-146">Reuters のアイテムの処理には、組織内のユーザーの電子メールアドレスを含む *email* というプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46d6d-146">Reuters Dealing items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="46d6d-147">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="46d6d-148">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-148">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="46d6d-149">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="46d6d-150">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-150">Click **Accept** to provide the consent.</span></span>

    <span data-ttu-id="46d6d-151">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d6d-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="46d6d-152">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46d6d-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="46d6d-153">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="46d6d-154">[ **次へ** ] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-154">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-dealing-connector"></a><span data-ttu-id="46d6d-155">手順 4: Reuters の処理コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="46d6d-155">Step 4: Monitor the Reuters Dealing connector</span></span>

<span data-ttu-id="46d6d-156">Reuters の処理コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-156">After you create the Reuters Dealing connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="46d6d-157">[https://compliance.microsoft.com](https://compliance.microsoft.com/)左側のナビゲーションに移動し、[ **データコネクタ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46d6d-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="46d6d-158">[ **コネクタ** ] タブをクリックし、[ **Reuters** ] を選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-158">Click the **Connectors** tab and then select the **Reuters Dealing** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="46d6d-159">[ **コネクタの状態 (ソース付き** )] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="46d6d-159">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="46d6d-160">このログには、Microsoft クラウドにインポートされたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46d6d-160">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="46d6d-161">既知の問題</span><span class="sxs-lookup"><span data-stu-id="46d6d-161">Known issues</span></span>

- <span data-ttu-id="46d6d-162">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="46d6d-162">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="46d6d-163">より大きいアイテムのサポートは、後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="46d6d-163">Support for larger items will be available at a later date.</span></span>
