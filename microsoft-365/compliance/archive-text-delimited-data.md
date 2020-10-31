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
description: 管理者は、Globanet から Microsoft 365 にテキスト区切りのデータをインポートしてアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 89c9894400cd3d10544ec43974903d99e8d0a7f8
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816802"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a><span data-ttu-id="c9a5c-105">テキスト区切りのデータをアーカイブするためのコネクタの設定</span><span class="sxs-lookup"><span data-stu-id="c9a5c-105">Set up a connector to archive text-delimited data</span></span>

<span data-ttu-id="c9a5c-106">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、テキスト区切りのデータを Microsoft 365 組織のユーザーのメールボックスにインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive text-delimited data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c9a5c-107">Globanet では、サードパーティのデータソースからアイテムを取得するように構成された [テキスト区切りのコネクタ](https://globanet.com/text-delimited) が用意されており (定期的に)、それらのアイテムを Microsoft 365 にインポートします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-107">Globanet provides a [text-delimited connector](https://globanet.com/text-delimited) that's configured to capture items from a third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="c9a5c-108">コネクタは、コンテンツをテキスト区切りデータソースから電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-108">The connector converts content from the text-delimited data source to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="c9a5c-109">テキスト区切りのデータがユーザーのメールボックスに格納された後、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-109">After text-delimited data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="c9a5c-110">Microsoft 365 でテキスト区切りデータコネクタを使用してデータをインポートおよびアーカイブすることにより、組織は政府ポリシーおよび規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-110">Using a text-delimited data connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-text-delimited-data"></a><span data-ttu-id="c9a5c-111">テキスト区切りデータのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="c9a5c-111">Overview of archiving the text-delimited data</span></span>

<span data-ttu-id="c9a5c-112">次の概要では、コネクタを使用して Microsoft 365 のテキスト区切りのソース情報をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-112">The following overview explains the process of using a connector to archive text-delimited source information in Microsoft 365.</span></span>

![テキストで区切られたデータのアーカイブワークフロー](../media/TextDelimitedConnectorWorkflow.png)

1. <span data-ttu-id="c9a5c-114">組織はテキスト区切りのソースを使用して、テキスト区切りのサイトを設定し、構成します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-114">Your organization works with the text-delimited source to set up and configure a text-delimited site.</span></span>

2. <span data-ttu-id="c9a5c-115">24時間ごとに、テキスト区切りソースからのチャットメッセージが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-115">Once every 24 hours, chat messages from the text-delimited source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="c9a5c-116">また、コネクタは、コンテンツを電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-116">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="c9a5c-117">Microsoft 365 コンプライアンスセンターで作成したテキスト区切りコネクタは、Globanet Merge1 サイトに毎日接続して、Microsoft クラウド内のセキュアな Azure ストレージの場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-117">The text-delimited connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="c9a5c-118">このコネクタは、手順3で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換されたメッセージアイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="c9a5c-119">[ **テキスト区切り** ] という名前の受信トレイフォルダーに新しいサブフォルダーが作成され、ユーザーのメールボックスにメッセージアイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-119">A new subfolder in the Inbox folder named **Text- Delimited** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="c9a5c-120">コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="c9a5c-121">すべてのメッセージにこのプロパティが含まれており、すべての参加者の電子メールアドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-121">Every message contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c9a5c-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="c9a5c-122">Before you begin</span></span>

- <span data-ttu-id="c9a5c-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="c9a5c-124">このアカウントを作成するには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact)に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-124">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="c9a5c-125">このアカウントは、手順1でコネクタを作成するときにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="c9a5c-126">手順1でテキスト区切りコネクタを作成し、(手順3で完了する) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-126">The user who creates the text-delimited connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c9a5c-127">この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c9a5c-128">既定では、この役割は Exchange Online の役割グループに割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="c9a5c-129">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c9a5c-130">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c9a5c-131">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-text-delimited-connector"></a><span data-ttu-id="c9a5c-132">手順 1: テキスト区切りコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="c9a5c-132">Step 1: Set up the text-delimited connector</span></span>

<span data-ttu-id="c9a5c-133">最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、テキスト区切りのデータ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for text-delimited data.</span></span>

1. <span data-ttu-id="c9a5c-134">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) て、[ **データコネクタ** ]  >  **テキストを区切り** ます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Text-Delimited** .</span></span>

2. <span data-ttu-id="c9a5c-135">[ **テキスト区切り** 製品の説明] ページで、[ **コネクタの追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-135">On the **text-delimited** product description page, click **Add connector** .</span></span>

3. <span data-ttu-id="c9a5c-136">[ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-136">On the **Terms of service** page, click **Accept** .</span></span>

4. <span data-ttu-id="c9a5c-137">コネクタを識別する一意の名前を入力し、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-137">Enter a unique name that identifies the connector, and then click **Next** .</span></span>

5. <span data-ttu-id="c9a5c-138">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="c9a5c-139">手順 2: Globanet Merge1 サイト上のテキスト区切りコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="c9a5c-139">Step 2: Configure the Text-delimited connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="c9a5c-140">2番目の手順は、Merge1 サイトでテキスト区切りコネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-140">The second step is to configure the text-delimited connector on the Merge1 site.</span></span> <span data-ttu-id="c9a5c-141">Globanet Merge1 サイトでテキスト区切りコネクタを構成する方法については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-141">For information about configuring  the text-delimited connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="c9a5c-142">[ **保存 & 完了** ] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-142">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="c9a5c-143">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="c9a5c-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="c9a5c-144">ユーザーをマップし、Microsoft 365 コンプライアンスセンターでコネクタの設定を完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="c9a5c-145">[ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="c9a5c-146">テキスト区切りのソース項目には、 *電子メール* というプロパティが含まれています。これには、組織内のユーザーの電子メールアドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-146">The Text- Delimited source items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="c9a5c-147">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="c9a5c-148">[ **管理者の同意** ] ページで、[ **同意を提供** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-148">On the **Admin Consent** page, click **Provide Consent** .</span></span> <span data-ttu-id="c9a5c-149">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-149">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="c9a5c-150">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-150">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="c9a5c-151">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-151">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="c9a5c-152">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-152">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="c9a5c-153">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-153">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="c9a5c-154">[ **次へ** ] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-154">Click **Next** , review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-text-delimited-connector"></a><span data-ttu-id="c9a5c-155">手順 4: テキスト区切りコネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="c9a5c-155">Step 4: Monitor the text-delimited connector</span></span>

<span data-ttu-id="c9a5c-156">テキスト区切りコネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-156">After you create the Text- Delimited connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="c9a5c-157">[https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[ **データコネクタ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-157">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="c9a5c-158">[ **コネクタ** ] タブをクリックし、 **テキスト区切り** コネクタを選択して、フライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-158">Click the **Connectors** tab and then select the **Text- Delimited** connector to display the flyout page.</span></span> <span data-ttu-id="c9a5c-159">このページには、コネクタに関するプロパティと情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-159">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="c9a5c-160">[ **コネクタの状態 (ソース付き** )] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-160">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="c9a5c-161">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-161">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="c9a5c-162">既知の問題</span><span class="sxs-lookup"><span data-stu-id="c9a5c-162">Known issues</span></span>

- <span data-ttu-id="c9a5c-163">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-163">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="c9a5c-164">より大きいアイテムのサポートは、後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="c9a5c-164">Support for larger items will be available at a later date.</span></span>
