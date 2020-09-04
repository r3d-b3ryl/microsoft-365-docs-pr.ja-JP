---
title: Microsoft 365 の Reuters Eikon データをアーカイブするためのコネクタの設定
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
description: 管理者は、Reuters Eikon データを Microsoft 365 の Globanet からインポートおよびアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: ee28cd33e6c4531bf769a1e178d733eff453cb75
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47362016"
---
# <a name="set-up-a-connector-to-archive-reuters-eikon-data-preview"></a><span data-ttu-id="425dc-104">コネクタを Reuters Eikon data にアーカイブするように設定する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="425dc-104">Set up a connector to archive Reuters Eikon data (preview)</span></span>

<span data-ttu-id="425dc-105">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、Reuters Eikon プラットフォームから Microsoft 365 組織のユーザーメールボックスにデータをインポートし、アーカイブします。</span><span class="sxs-lookup"><span data-stu-id="425dc-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Reuters Eikon platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="425dc-106">Globanet では、サードパーティのデータソースからアイテムを取得するように構成された [Reuters Eikon](https://globanet.com/eikon/) connector が提供されています (定期的に)。これらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="425dc-106">Globanet provides a [Reuters Eikon](https://globanet.com/eikon/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="425dc-107">コネクタは、個人のメッセージ、グループのチャット、添付ファイル、免責事項などのコンテンツをユーザーの Reuters Eikon アカウントから電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="425dc-107">The connector converts the content such as person-to-person messages, group chats, attachments, and disclaimers from a user's Reuters Eikon account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="425dc-108">Reuters Eikon のデータがユーザーのメールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="425dc-108">After Reuters Eikon data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="425dc-109">Reuters Eikon コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="425dc-109">Using a Reuters Eikon connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-eikon-data"></a><span data-ttu-id="425dc-110">Reuters Eikon データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="425dc-110">Overview of archiving Reuters Eikon data</span></span>

<span data-ttu-id="425dc-111">次の概要では、コネクタを使用して Microsoft 365 の Reuters Eikon 情報をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="425dc-111">The following overview explains the process of using a connector to archive the Reuters Eikon information in Microsoft 365.</span></span>

![Reuters Eikon データのアーカイブワークフロー](../media/ReutersEikonConnectorWorkflow.png)

1. <span data-ttu-id="425dc-113">組織は Reuters Eikon を使用して、Reuters Eikon サイトをセットアップして構成します。</span><span class="sxs-lookup"><span data-stu-id="425dc-113">Your organization works with Reuters Eikon to set up and configure a Reuters Eikon site.</span></span>

2. <span data-ttu-id="425dc-114">24時間ごとに Reuters Eikon アイテムは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="425dc-114">Once every 24 hours, Reuters Eikon items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="425dc-115">また、コネクタは Reuters Eikon アイテムを電子メールメッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="425dc-115">The connector also converts Reuters Eikon items to an email message format.</span></span>

3. <span data-ttu-id="425dc-116">Microsoft 365 コンプライアンスセンターで作成した Reuters Eikon コネクタは、毎日 Globanet Merge1 サイトに接続し、そのコンテンツを Microsoft クラウド内のセキュリティ保護された Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="425dc-116">The Reuters Eikon connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="425dc-117">コネクタは、[手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの*Email*プロパティの値を使用して、特定のユーザーのメールボックスにアイテムをインポートします。</span><span class="sxs-lookup"><span data-stu-id="425dc-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="425dc-118">ユーザーメールボックスに **Reuters Eikon** という名前の受信トレイフォルダー内のサブフォルダーが作成され、そのフォルダーにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="425dc-118">A subfolder in the Inbox folder named **Reuters Eikon** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="425dc-119">コネクタは、 *Email* プロパティの値を使用してこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="425dc-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="425dc-120">すべての Reuters Eikon item には、アイテムのすべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="425dc-120">Every Reuters Eikon item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="425dc-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="425dc-121">Before you begin</span></span>

- <span data-ttu-id="425dc-122">Globanet Merge1 アカウントを作成するには、余裕期間電子情報開示コネクタの使用条件に同意します。</span><span class="sxs-lookup"><span data-stu-id="425dc-122">Create a Globanet Merge1 account by accepting the terms and conditions for a Slack eDiscovery connector.</span></span> <span data-ttu-id="425dc-123">これを行うには、 [Globanet カスタマーサポート](https://globanet.com/contact-us)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="425dc-123">To do this, contact [Globanet Customer Support](https://globanet.com/contact-us).</span></span> <span data-ttu-id="425dc-124">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="425dc-124">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="425dc-125">手順1で Reuters Eikon コネクタを作成したユーザー (および手順3で完了します) は、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="425dc-125">The user who creates the Reuters Eikon connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="425dc-126">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="425dc-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="425dc-127">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="425dc-127">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="425dc-128">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="425dc-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="425dc-129">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="425dc-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="425dc-130">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="425dc-130">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-reuters-eikon-connector"></a><span data-ttu-id="425dc-131">手順 1: Reuters Eikon コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="425dc-131">Step 1: Set up the Reuters Eikon connector</span></span>

<span data-ttu-id="425dc-132">最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、Reuters Eikon Data のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="425dc-132">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Reuters Eikon data.</span></span>

1. <span data-ttu-id="425dc-133">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データコネクタ**  >  **Reuters Eikon**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="425dc-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Eikon**.</span></span>

2. <span data-ttu-id="425dc-134">[ **Reuters Eikon** product description] ページで、[ **コネクタの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="425dc-134">On the **Reuters Eikon** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="425dc-135">[ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="425dc-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="425dc-136">コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="425dc-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="425dc-137">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="425dc-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-eikon-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="425dc-138">手順 2: Globanet Merge1 サイト上の Reuters Eikon コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="425dc-138">Step 2: Configure the Reuters Eikon connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="425dc-139">2番目の手順は、Merge1 サイトで Reuters Eikon コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="425dc-139">The second step is to configure the Reuters Eikon connector on the Merge1 site.</span></span> <span data-ttu-id="425dc-140">Globanet Merge1 サイトで Reuters Eikon コネクタを構成する方法については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="425dc-140">For information about how to configure the Reuters Eikon connector in the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="425dc-141">[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター (コネクタウィザードの [ **ユーザーマッピング** ] ページ) に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="425dc-141">After you click **Save & Finish**, you are directed back to the Microsoft 365 compliance center, to the **User mapping** page in the connector wizard.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="425dc-142">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="425dc-142">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="425dc-143">ユーザーをマップし、Microsoft 365 コンプライアンスセンターで設定したコネクタを完成させるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="425dc-143">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="425dc-144">[ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="425dc-144">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="425dc-145">Reuters Eikon のアイテムには、組織内のユーザーの電子メールアドレスを含む *email*というプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="425dc-145">The Reuters Eikon items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="425dc-146">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="425dc-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="425dc-147">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="425dc-147">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="425dc-148">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="425dc-148">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="425dc-149">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="425dc-149">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="425dc-150">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="425dc-150">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="425dc-151">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="425dc-151">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="425dc-152">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="425dc-152">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="425dc-153">[ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="425dc-153">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-eikon-connector"></a><span data-ttu-id="425dc-154">手順 4: Reuters Eikon コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="425dc-154">Step 4: Monitor the Reuters Eikon connector</span></span>

<span data-ttu-id="425dc-155">Reuters Eikon コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="425dc-155">After you create the Reuters Eikon connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="425dc-156">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="425dc-156">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="425dc-157">[ **コネクタ** ] タブをクリックし、[ **Reuters Eikon** コネクタ] を選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="425dc-157">Click the **Connectors** tab and then select the **Reuters Eikon** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="425dc-158">[ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="425dc-158">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="425dc-159">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="425dc-159">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="425dc-160">既知の問題</span><span class="sxs-lookup"><span data-stu-id="425dc-160">Known issues</span></span>

- <span data-ttu-id="425dc-161">現時点では、10 MB を超える添付ファイルのインポートをサポートしていませんが、より大きいアイテムのサポートは後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="425dc-161">At this time, we don't support importing attachments larger than 10 MB but support for larger items will be available at a later date.</span></span>
