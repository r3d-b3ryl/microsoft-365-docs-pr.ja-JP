---
title: Microsoft 365 で XIP ソース データをアーカイブするコネクタを設定する
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
description: 管理者は、Globanet から Microsoft 365 に XIP ソース データをインポートしてアーカイブするコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 のサード パーティのデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、サード パーティのデータを管理できます。
ms.openlocfilehash: 0af68177d51f143dd29d953050ae4e18fb8ad62d
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620194"
---
# <a name="set-up-a-connector-to-archive-xip-source-data"></a><span data-ttu-id="c9763-105">XIP ソース データをアーカイブするコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="c9763-105">Set up a connector to archive XIP source data</span></span>

<span data-ttu-id="c9763-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、XIP ソース プラットフォームから Microsoft 365 組織内のユーザー メールボックスにデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="c9763-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the XIP source platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c9763-107">Globanet は [、XIP](https://globanet.com/xip/) ファイルを使用して Microsoft 365 にアイテムをインポートできる XIP コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="c9763-107">Globanet provides a [XIP](https://globanet.com/xip/) connector that allows using an XIP file to import items to Microsoft 365.</span></span> <span data-ttu-id="c9763-108">XIP ファイルは ZIP ファイルに似ていますが、デジタル署名を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c9763-108">An XIP file is similar to a ZIP file, but allows for a digital signature to be used.</span></span> <span data-ttu-id="c9763-109">デジタル署名は、XIP ソース ファイルが抽出される前に Globanet Merge 1 によって検証されます。</span><span class="sxs-lookup"><span data-stu-id="c9763-109">The digital signature is verified by the Globanet Merge 1 before the XIP source file is extracted.</span></span> <span data-ttu-id="c9763-110">コネクタは、コンテンツを XIP ソース ファイルから電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="c9763-110">The connector converts the content from the XIP source file to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="c9763-111">XIP ソース データがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、アイテム保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="c9763-111">After XIP source data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="c9763-112">XIP コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9763-112">Using an XIP connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-xip-source-data"></a><span data-ttu-id="c9763-113">XIP ソース データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="c9763-113">Overview of archiving the XIP source data</span></span>

<span data-ttu-id="c9763-114">次の概要では、コネクタを使用して Microsoft 365 の XIP ソース データをアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c9763-114">The following overview explains the process of using a connector to archive the XIP source data in Microsoft 365.</span></span>

![XIP ソース データのアーカイブ ワークフロー](../media/XIPConnectorWorkflow.png)

1. <span data-ttu-id="c9763-116">組織は XIP ソースと共同で XIP サイトをセットアップおよび構成します。</span><span class="sxs-lookup"><span data-stu-id="c9763-116">Your organization works with the XIP source to set up and configure an XIP site.</span></span>

2. <span data-ttu-id="c9763-117">24 時間ごとに、XIP ソース アイテムが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c9763-117">Once every 24 hours, XIP source items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="c9763-118">コネクタは、コンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="c9763-118">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="c9763-119">Microsoft 365 コンプライアンス センターで作成する XIP コネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage の場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="c9763-119">The XIP connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="c9763-120">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="c9763-120">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="c9763-121">XIP という名前の受信トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、アイテムがフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c9763-121">A subfolder in the Inbox folder named **XIP** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="c9763-122">コネクタは *、Email* プロパティの値を使用して、アイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="c9763-122">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="c9763-123">すべてのソース アイテムには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="c9763-123">Every source item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c9763-124">はじめに</span><span class="sxs-lookup"><span data-stu-id="c9763-124">Before you begin</span></span>

- <span data-ttu-id="c9763-125">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9763-125">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="c9763-126">アカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/contact-us/)。</span><span class="sxs-lookup"><span data-stu-id="c9763-126">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="c9763-127">手順 1 でコネクタを作成するときに、このアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9763-127">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="c9763-128">手順 1 で XIP コネクタを作成する (および手順 3 で完了する) ユーザーは、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9763-128">The user who creates the XIP connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="c9763-129">この役割は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページでコネクタを追加するために必要です。</span><span class="sxs-lookup"><span data-stu-id="c9763-129">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c9763-130">既定では、この役割は Exchange Online の役割グループには割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="c9763-130">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c9763-131">"Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="c9763-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="c9763-132">または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="c9763-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="c9763-133">詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9763-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-xip-connector"></a><span data-ttu-id="c9763-134">手順 1: XIP コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c9763-134">Step 1: Set up the XIP connector</span></span>

<span data-ttu-id="c9763-135">最初の手順は、Microsoft365 コンプライアンス センターの **[Data Connectors]** ページにアクセスし、XIP ソース データのコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="c9763-135">The first step is to access to the **Data Connectors** page in the Microsoft365 compliance center and create a connector for the XIP source data.</span></span>

1. <span data-ttu-id="c9763-136">[データ [https://compliance.microsoft.com](https://compliance.microsoft.com/) コネクタ \> **XIP] に移動してクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c9763-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **XIP**.</span></span>

2. <span data-ttu-id="c9763-137">**[XIP 製品の説明]** ページで、[新しいコネクタの **追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c9763-137">On the **XIP** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="c9763-138">[サービス条件 **] ページで、[** 承諾] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c9763-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="c9763-139">コネクタを識別する一意の名前を入力し、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="c9763-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="c9763-140">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c9763-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-xip-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="c9763-141">手順 2: Globanet Merge1 サイトで XIP コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="c9763-141">Step 2: Configure the XIP connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="c9763-142">2 番目の手順は、Merge1 サイトで XIP コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="c9763-142">The second step is to configure the XIP connector on the Merge1 site.</span></span> <span data-ttu-id="c9763-143">XIP コネクタを構成する方法については [、「Merge1 Third-Party Connectors User Guide」を参照してください](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf)。</span><span class="sxs-lookup"><span data-stu-id="c9763-143">For information about how to configure the XIP connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="c9763-144">[ Save **& Finish]** をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9763-144">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="c9763-145">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="c9763-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="c9763-146">ユーザーをマップしてコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c9763-146">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="c9763-147">**[XIP ユーザーを Microsoft 365 ユーザーに** マップする] ページで、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c9763-147">On the **Map XIP users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="c9763-148">XIP ソース アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9763-148">The XIP source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="c9763-149">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付けできる場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="c9763-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="c9763-150">[**次へ**] をクリックして設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="c9763-150">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xip-connector"></a><span data-ttu-id="c9763-151">手順 4: XIP コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="c9763-151">Step 4: Monitor the XIP connector</span></span>

<span data-ttu-id="c9763-152">XIP コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9763-152">After you create the XIP connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="c9763-153">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com/) ナビゲーションの **[データ コネクタ]** に移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9763-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="c9763-154">[ **コネクタ] タブ** をクリックし **、XIP** コネクタを選択して、コネクタのプロパティと情報を含むフライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="c9763-154">Click the **Connectors** tab and then select the **XIP** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="c9763-155">[**コネクタの状態とソース**]で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9763-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="c9763-156">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9763-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="c9763-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="c9763-157">Known issues</span></span>

- <span data-ttu-id="c9763-158">現時点では、添付ファイルまたは 10 MB を超えるアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c9763-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="c9763-159">より大きなアイテムのサポートは、後日利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="c9763-159">Support for larger items will be available at a later date.</span></span>
