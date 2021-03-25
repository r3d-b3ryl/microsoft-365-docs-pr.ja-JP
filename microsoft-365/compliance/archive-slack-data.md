---
title: Microsoft 365 で Slack 電子情報開示データをアーカイブするコネクタをセットアップする
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
description: 管理者は、Veritas Slack 電子情報開示から Microsoft 365 にデータをインポートおよびアーカイブするコネクタをセットアップできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 48b0a6d4d5e8f6eafaaf900aa5c773cf4f99fe72
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163961"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a><span data-ttu-id="16adf-105">Slack 電子情報開示データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="16adf-105">Set up a connector to archive Slack eDiscovery data</span></span>

<span data-ttu-id="16adf-106">Microsoft 365 コンプライアンス センターの Veritas コネクタを使用して、サードパーティ のデータをソーシャル メディア、インスタント メッセージング、ドキュメント コラボレーション プラットフォームから Microsoft 365 組織のメールボックスにインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="16adf-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive third-party data from social media, instant messaging, and document collaboration platforms to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="16adf-107">Veritas には [、サードパーティ](https://globanet.com/slack/) のデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成された Slack コネクタが提供されています。</span><span class="sxs-lookup"><span data-stu-id="16adf-107">Veritas provides a [Slack](https://globanet.com/slack/) connector that's configured to capture items from the third-party data source (on a regular basis) and then import those items to Microsoft 365.</span></span> <span data-ttu-id="16adf-108">Slack は Slack API からメッセージとファイルをプルし、メール メッセージ形式に変換してから、アイテムをユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="16adf-108">Slack pulls messages and files from the Slack API and converts them to an email message format and then imports the item to user mailboxes.</span></span>

<span data-ttu-id="16adf-109">Slack 電子情報開示データをユーザー メールボックスに格納した後、訴訟ホールド、電子情報開示、保持ポリシーと保持ラベル、通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="16adf-109">After Slack eDiscovery data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="16adf-110">Slack コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="16adf-110">Using a Slack connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-slack-ediscovery-data"></a><span data-ttu-id="16adf-111">Slack 電子情報開示データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="16adf-111">Overview of archiving Slack eDiscovery data</span></span>

<span data-ttu-id="16adf-112">次の概要では、コネクタを使用して Microsoft 365 の Slack 情報をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="16adf-112">The following overview explains the process of using a connector to archive the Slack information in Microsoft 365.</span></span>

![Slack アーカイブ ワークフロー](../media/SlackConnectorWorkflow.png)

1. <span data-ttu-id="16adf-114">組織は Slack を使用して Slack サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="16adf-114">Your organization works with Slack to set up and configure a Slack site.</span></span>

2. <span data-ttu-id="16adf-115">24 時間に 1 回、Slack 電子情報開示からのチャット メッセージが Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="16adf-115">Once every 24 hours, chat messages from Slack eDiscovery are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="16adf-116">また、コネクタはチャット メッセージのコンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="16adf-116">The connector also converts the content of a chat message to an email message format.</span></span>

3. <span data-ttu-id="16adf-117">Microsoft 365 コンプライアンス センターで作成した Slack 電子情報開示コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage の場所にチャット メッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="16adf-117">The Slack eDiscovery connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the chat messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="16adf-118">コネクタは、手順 3 で説明したように *、Email* プロパティと自動ユーザー マッピングの値を使用して、変換されたチャット メッセージ アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="16adf-118">The connector imports the converted chat message items to the mailboxes of specific users using the value of the *Email* property and automatic user mapping, as described in Step 3.</span></span> <span data-ttu-id="16adf-119">**Slack eDiscovery** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー メールボックスに作成され、そのフォルダーにチャット メッセージ アイテムがインポートされます。</span><span class="sxs-lookup"><span data-stu-id="16adf-119">A new subfolder in the Inbox folder named **Slack eDiscovery** is created in the user mailboxes, and the chat message items are imported to that folder.</span></span> <span data-ttu-id="16adf-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="16adf-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="16adf-121">すべてのチャット メッセージには、このプロパティが含まれるので、チャット メッセージのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="16adf-121">Every chat message contains this property, which is populated with the email address of every participant of the chat message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="16adf-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="16adf-122">Before you begin</span></span>

- <span data-ttu-id="16adf-123">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="16adf-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="16adf-124">アカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="16adf-124">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="16adf-125">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="16adf-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="16adf-126">組織の Slack エンタープライズ アカウントのユーザー名とパスワードを取得します。</span><span class="sxs-lookup"><span data-stu-id="16adf-126">Obtain the username and password for your organization's Slack enterprise account.</span></span> <span data-ttu-id="16adf-127">Slack を構成する場合は、手順 2 でこのアカウントにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16adf-127">You'll need to sign into this account in Step 2 when you configure Slack.</span></span>

- <span data-ttu-id="16adf-128">手順 1 で Slack 電子情報開示コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16adf-128">The user who creates the Slack eDiscovery connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="16adf-129">Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="16adf-129">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="16adf-130">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="16adf-130">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="16adf-131">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="16adf-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="16adf-132">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="16adf-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="16adf-133">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16adf-133">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a><span data-ttu-id="16adf-134">手順 1: Slack 電子情報開示コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="16adf-134">Step 1: Set up the Slack eDiscovery connector</span></span>

<span data-ttu-id="16adf-135">最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、Slack データ用のコネクタを作成することです。 </span><span class="sxs-lookup"><span data-stu-id="16adf-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Slack data.</span></span>

1. <span data-ttu-id="16adf-136">[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) の Slack 電子 **情報開示**]  >  **に移動し、[データ コネクタ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="16adf-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Slack eDiscovery**.</span></span>

2. <span data-ttu-id="16adf-137">Slack 電子 **情報開示製品の説明** ページで、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="16adf-137">On the **Slack eDiscovery** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="16adf-138">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="16adf-138">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="16adf-139">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="16adf-139">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="16adf-140">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="16adf-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-slack-ediscovery"></a><span data-ttu-id="16adf-141">手順 2: Slack 電子情報開示を構成する</span><span class="sxs-lookup"><span data-stu-id="16adf-141">Step 2: Configure Slack eDiscovery</span></span>

<span data-ttu-id="16adf-142">2 番目の手順は、Merge1 サイトで Slack 電子情報開示コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="16adf-142">The second step is to configure the Slack eDiscovery connector on the Merge1 site.</span></span> <span data-ttu-id="16adf-143">Veritas Merge1 サイトで Slack 電子情報開示コネクタを構成する方法の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16adf-143">For more information about how to configure the Slack eDiscovery connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).</span></span>

<span data-ttu-id="16adf-144">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="16adf-144">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="16adf-145">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="16adf-145">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="16adf-146">[外部ユーザー **を Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="16adf-146">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span>

   <span data-ttu-id="16adf-147">Slack 電子情報開示アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="16adf-147">Slack eDiscovery items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="16adf-148">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="16adf-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="16adf-149">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="16adf-149">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a><span data-ttu-id="16adf-150">手順 4: Slack 電子情報開示コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="16adf-150">Step 4: Monitor the Slack eDiscovery connector</span></span>

<span data-ttu-id="16adf-151">Slack 電子情報開示コネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="16adf-151">After you create the Slack eDiscovery connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="16adf-152">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="16adf-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="16adf-153">[コネクタ **] タブをクリック** し **、Slack 電子情報開示** コネクタを選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="16adf-153">Click the **Connectors** tab and then select the **Slack eDiscovery** connector to display the flyout page.</span></span> <span data-ttu-id="16adf-154">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="16adf-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="16adf-155">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="16adf-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="16adf-156">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="16adf-156">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="16adf-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="16adf-157">Known issues</span></span>

- <span data-ttu-id="16adf-158">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="16adf-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="16adf-159">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="16adf-159">Support for larger items will be available at a later date.</span></span>