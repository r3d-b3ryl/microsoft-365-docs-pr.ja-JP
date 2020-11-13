---
title: Microsoft 365 で XIP ソースデータをアーカイブするためのコネクタの設定
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
description: 管理者は、Globanet から Microsoft 365 に XIP ソースデータをインポートしてアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 2a91fdd5d0acf5bab7945906b4c7dde511a30f4e
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002796"
---
# <a name="set-up-a-connector-to-archive-xip-source-data-preview"></a><span data-ttu-id="997c8-105">データをアーカイブするためのコネクタの設定ソースデータ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="997c8-105">Set up a connector to archive XIP source data (preview)</span></span>

<span data-ttu-id="997c8-106">Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、XIP ソースプラットフォームから Microsoft 365 組織のユーザーメールボックスにデータをインポートし、アーカイブします。</span><span class="sxs-lookup"><span data-stu-id="997c8-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the XIP source platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="997c8-107">Globanet には、XIP ファイルを使用して Microsoft 365 にアイテムをインポートできる [xip](https://globanet.com/xip/) コネクタが用意されています。</span><span class="sxs-lookup"><span data-stu-id="997c8-107">Globanet provides a [XIP](https://globanet.com/xip/) connector that allows using an XIP file to import items to Microsoft 365.</span></span> <span data-ttu-id="997c8-108">XIP ファイルは ZIP ファイルに似ていますが、デジタル署名を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="997c8-108">An XIP file is similar to a ZIP file, but allows for a digital signature to be used.</span></span> <span data-ttu-id="997c8-109">XIP ソースファイルが抽出される前に、Globanet Merge 1 によってデジタル署名が確認されます。</span><span class="sxs-lookup"><span data-stu-id="997c8-109">The digital signature is verified by the Globanet Merge 1 before the XIP source file is extracted.</span></span> <span data-ttu-id="997c8-110">コネクタは、XIP ソースファイルの内容を電子メールメッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="997c8-110">The connector converts the content from the XIP source file to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="997c8-111">XIP ソースデータがユーザーのメールボックスに格納された後で、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="997c8-111">After XIP source data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="997c8-112">XIP コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="997c8-112">Using an XIP connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-xip-source-data"></a><span data-ttu-id="997c8-113">XIP ソースデータのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="997c8-113">Overview of archiving the XIP source data</span></span>

<span data-ttu-id="997c8-114">次の概要では、コネクタを使用して、Microsoft 365 の XIP ソースデータをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="997c8-114">The following overview explains the process of using a connector to archive the XIP source data in Microsoft 365.</span></span>

![XIP ソースデータのアーカイブワークフロー](../media/XIPConnectorWorkflow.png)

1. <span data-ttu-id="997c8-116">組織は XIP ソースを使用して、XIP サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="997c8-116">Your organization works with the XIP source to set up and configure an XIP site.</span></span>

2. <span data-ttu-id="997c8-117">24時間ごとに、XIP ソースアイテムは Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="997c8-117">Once every 24 hours, XIP source items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="997c8-118">また、コネクタは、コンテンツを電子メールメッセージの形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="997c8-118">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="997c8-119">Microsoft 365 コンプライアンスセンターで作成する XIP コネクタは、毎日 Globanet Merge1 サイトに接続し、メッセージを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="997c8-119">The XIP connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="997c8-120">このコネクタは、 [手順 3](#step-3-map-users-and-complete-the-connector-setup)で説明されているように、自動ユーザーマッピングの *Email* プロパティの値を使用して、変換されたメッセージアイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="997c8-120">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="997c8-121">ユーザーメールボックス内に、 **XIP** という名前の受信トレイフォルダー内のサブフォルダーが作成され、そのフォルダーにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="997c8-121">A subfolder in the Inbox folder named **XIP** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="997c8-122">コネクタは、 *Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="997c8-122">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="997c8-123">すべてのソースアイテムには、すべての参加者の電子メールアドレスが設定されたこのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="997c8-123">Every source item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="997c8-124">はじめに</span><span class="sxs-lookup"><span data-stu-id="997c8-124">Before you begin</span></span>

- <span data-ttu-id="997c8-125">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="997c8-125">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="997c8-126">アカウントを作成するには、 [Globanet カスタマーサポート](https://globanet.com/contact-us/)に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="997c8-126">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="997c8-127">手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="997c8-127">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="997c8-128">手順1で XIP コネクタを作成して (手順3で完了させる) ユーザーは、Exchange Online のメールボックスのインポートのエクスポート役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="997c8-128">The user who creates the XIP connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="997c8-129">この役割は、Microsoft 365 コンプライアンスセンターの [データコネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="997c8-129">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="997c8-130">既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="997c8-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="997c8-131">Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="997c8-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="997c8-132">または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="997c8-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="997c8-133">詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="997c8-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-xip-connector"></a><span data-ttu-id="997c8-134">手順 1: XIP コネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="997c8-134">Step 1: Set up the XIP connector</span></span>

<span data-ttu-id="997c8-135">最初の手順として、Microsoft365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、XIP ソースデータ用のコネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="997c8-135">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the XIP source data.</span></span>

1. <span data-ttu-id="997c8-136">に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **データコネクタ** の XIP] をクリックし \> **XIP** ます。</span><span class="sxs-lookup"><span data-stu-id="997c8-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **XIP**.</span></span>

2. <span data-ttu-id="997c8-137">[ **XIP** 製品の説明] ページで、[ **新しいコネクタの追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="997c8-137">On the **XIP** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="997c8-138">[ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="997c8-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="997c8-139">コネクタを識別する一意の名前を入力し、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="997c8-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="997c8-140">Merge1 アカウントにサインインして、コネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="997c8-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-xip-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="997c8-141">手順 2: Globanet Merge1 サイトで XIP コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="997c8-141">Step 2: Configure the XIP connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="997c8-142">2番目の手順は、Merge1 サイトで XIP コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="997c8-142">The second step is to configure the XIP connector on the Merge1 site.</span></span> <span data-ttu-id="997c8-143">XIP コネクタを構成する方法については、「 [Merge1 サードパーティコネクタのユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="997c8-143">For information about how to configure the XIP connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="997c8-144">[ **保存 & 完了** ] をクリックすると、Microsoft 365 コンプライアンスセンターのコネクタウィザードの [ **ユーザーマッピング** ] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="997c8-144">After you click **Save & Finish** , the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="997c8-145">手順 3: ユーザーをマップしてコネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="997c8-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="997c8-146">ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="997c8-146">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="997c8-147">[ **XIP ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="997c8-147">On the **Map XIP users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="997c8-148">XIP ソースの項目には、 *電子メール* というプロパティが含まれています。これには、組織内のユーザーの電子メールアドレスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="997c8-148">The XIP source items include a property called *Email* , which contains email addresses for users in your organization.</span></span> <span data-ttu-id="997c8-149">コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="997c8-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="997c8-150">[ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="997c8-150">On the **Admin Consent** page, click the **Provide Consent** button.</span></span> <span data-ttu-id="997c8-151">Microsoft サイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="997c8-151">You will be redirected to the Microsoft site.</span></span> <span data-ttu-id="997c8-152">同意を得るには、[ **承諾** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="997c8-152">Click **Accept** to provide the consent.</span></span>

   <span data-ttu-id="997c8-153">組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。</span><span class="sxs-lookup"><span data-stu-id="997c8-153">Your organization must consent to allow the Office 365 Import service to access mailbox data in your organization.</span></span> <span data-ttu-id="997c8-154">管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="997c8-154">To provide admin consent, you must be signed in with the credentials of a Microsoft 365 global admin, and then accept the consent request.</span></span> <span data-ttu-id="997c8-155">グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。</span><span class="sxs-lookup"><span data-stu-id="997c8-155">If you aren't signed in as a global admin, you can go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using global admin credentials to accept the request.</span></span>

3. <span data-ttu-id="997c8-156">[ **次へ** ] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="997c8-156">Click **Next** , review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xip-connector"></a><span data-ttu-id="997c8-157">手順 4: XIP コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="997c8-157">Step 4: Monitor the XIP connector</span></span>

<span data-ttu-id="997c8-158">XIP コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="997c8-158">After you create the XIP connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="997c8-159">[https://compliance.microsoft.com](https://compliance.microsoft.com/)左側のナビゲーションに移動し、[ **データコネクタ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="997c8-159">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="997c8-160">[ **コネクタ** ] タブをクリックし、[ **XIP** ] コネクタを選択して、コネクタに関するプロパティと情報を含むフライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="997c8-160">Click the **Connectors** tab and then select the **XIP** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="997c8-161">[ **コネクタの状態 (ソース付き** )] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。</span><span class="sxs-lookup"><span data-stu-id="997c8-161">Under **Connector status with source** , click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="997c8-162">このログには、Microsoft クラウドにインポートされたデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="997c8-162">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="997c8-163">既知の問題</span><span class="sxs-lookup"><span data-stu-id="997c8-163">Known issues</span></span>

- <span data-ttu-id="997c8-164">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="997c8-164">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="997c8-165">より大きいアイテムのサポートは、後日提供されます。</span><span class="sxs-lookup"><span data-stu-id="997c8-165">Support for larger items will be available at a later date.</span></span>
