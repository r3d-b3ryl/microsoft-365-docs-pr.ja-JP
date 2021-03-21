---
title: Microsoft 365 でテキスト区切りデータをアーカイブするコネクタをセットアップする
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
description: 管理者は、Globanet から Microsoft 365 にテキスト区切りデータをインポートおよびアーカイブするコネクタをセットアップできます。 このコネクタを使用すると、Microsoft 365 のサードパーティデータ ソースからデータをアーカイブできます。 このデータをアーカイブした後、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、サードパーティのデータを管理できます。
ms.openlocfilehash: 00003cbd897cc80b0596dbb7e5988f010cd7f7e2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925011"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a><span data-ttu-id="8eacc-105">テキスト区切りデータをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="8eacc-105">Set up a connector to archive text-delimited data</span></span>

<span data-ttu-id="8eacc-106">Microsoft 365 コンプライアンス センターの Globanet コネクタを使用して、Microsoft 365 組織のユーザー メールボックスにテキスト区切りデータをインポートおよびアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="8eacc-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive text-delimited data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="8eacc-107">Globanet は[](https://globanet.com/text-delimited)、サードパーティのデータ ソースからアイテムを (定期的に) キャプチャし、それらのアイテムを Microsoft 365 にインポートするように構成されたテキスト区切りコネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-107">Globanet provides a [text-delimited connector](https://globanet.com/text-delimited) that's configured to capture items from a third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="8eacc-108">コネクタは、テキストで区切られたデータ ソースから電子メール メッセージ形式にコンテンツを変換し、それらのアイテムを Microsoft 365 のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="8eacc-108">The connector converts content from the text-delimited data source to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="8eacc-109">テキストで区切られたデータがユーザー メールボックスに保存された後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどの Microsoft 365 コンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-109">After text-delimited data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="8eacc-110">テキストで区切られたデータ コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすると、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-110">Using a text-delimited data connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-text-delimited-data"></a><span data-ttu-id="8eacc-111">テキスト区切りデータのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="8eacc-111">Overview of archiving the text-delimited data</span></span>

<span data-ttu-id="8eacc-112">次の概要では、Microsoft 365 でコネクタを使用してテキストで区切られたソース情報をアーカイブするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-112">The following overview explains the process of using a connector to archive text-delimited source information in Microsoft 365.</span></span>

![テキストで区切られたデータのアーカイブ ワークフロー](../media/TextDelimitedConnectorWorkflow.png)

1. <span data-ttu-id="8eacc-114">組織は、テキストで区切られたソースを使用して、テキストで区切られたサイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-114">Your organization works with the text-delimited source to set up and configure a text-delimited site.</span></span>

2. <span data-ttu-id="8eacc-115">24 時間に 1 回、テキストで区切られたソースからのチャット メッセージが Globanet Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-115">Once every 24 hours, chat messages from the text-delimited source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="8eacc-116">コネクタは、コンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-116">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="8eacc-117">Microsoft 365 コンプライアンス センターで作成するテキスト区切りコネクタは、毎日 Globanet Merge1 サイトに接続し、Microsoft クラウド内の安全な Azure Storage の場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-117">The text-delimited connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="8eacc-118">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="8eacc-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="8eacc-119">Text- **Delimited** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー のメールボックスに作成され、メッセージ アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-119">A new subfolder in the Inbox folder named **Text- Delimited** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="8eacc-120">コネクタは *、Email* プロパティの値を使用してアイテムをインポートするメールボックスを決定します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="8eacc-121">すべてのメッセージには、このプロパティが含まれるので、すべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-121">Every message contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8eacc-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="8eacc-122">Before you begin</span></span>

- <span data-ttu-id="8eacc-123">Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="8eacc-124">このアカウントを作成するには [、Globanet カスタマー サポートにお問い合わせください](https://globanet.com/ms-connectors-contact)。</span><span class="sxs-lookup"><span data-stu-id="8eacc-124">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="8eacc-125">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="8eacc-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="8eacc-126">手順 1 でテキスト区切りコネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8eacc-126">The user who creates the text-delimited connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8eacc-127">Microsoft 365 コンプライアンス センターの [ **データ** コネクタ] ページにコネクタを追加するには、この役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="8eacc-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8eacc-128">既定では、この役割は Exchange Online の役割グループに割り当てられていない。</span><span class="sxs-lookup"><span data-stu-id="8eacc-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="8eacc-129">Exchange Online の [組織の管理] 役割グループにメールボックスインポートエクスポート役割を追加できます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8eacc-130">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8eacc-131">詳細については、「Exchange Online[で役割](/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の記事の「役割グループの作成」または「役割グループの変更」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eacc-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-text-delimited-connector"></a><span data-ttu-id="8eacc-132">手順 1: テキスト区切りコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="8eacc-132">Step 1: Set up the text-delimited connector</span></span>

<span data-ttu-id="8eacc-133">最初の手順は、Microsoft 365 コンプライアンス センターの [データ コネクタ] ページにアクセスし、テキストで区切られたデータ用のコネクタを作成することです。 </span><span class="sxs-lookup"><span data-stu-id="8eacc-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for text-delimited data.</span></span>

1. <span data-ttu-id="8eacc-134">[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) テキスト区切り] に移動  >  **し、[データ コネクタ] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8eacc-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Text-Delimited**.</span></span>

2. <span data-ttu-id="8eacc-135">[テキストで **区切られた製品の説明] ページ** で、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8eacc-135">On the **text-delimited** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="8eacc-136">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8eacc-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="8eacc-137">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="8eacc-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="8eacc-138">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="8eacc-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="8eacc-139">手順 2: Globanet Merge1 サイトでテキスト区切りコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="8eacc-139">Step 2: Configure the Text-delimited connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="8eacc-140">2 番目の手順は、Merge1 サイトでテキスト区切りコネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="8eacc-140">The second step is to configure the text-delimited connector on the Merge1 site.</span></span> <span data-ttu-id="8eacc-141">Globanet Merge1 サイトでテキスト区切りコネクタを構成する方法については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8eacc-141">For information about configuring  the text-delimited connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="8eacc-142">[ファイルの **保存と&完了**] をクリックすると、Microsoft 365 コンプライアンス センターのコネクタ ウィザードの [ユーザー マッピング] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="8eacc-143">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="8eacc-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="8eacc-144">ユーザーをマップし、Microsoft 365 コンプライアンス センターでコネクタのセットアップを完了するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="8eacc-145">[外部ユーザー **を Microsoft 365 ユーザー** にマップする] ページで、自動ユーザー マッピングを有効にする。</span><span class="sxs-lookup"><span data-stu-id="8eacc-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="8eacc-146">テキスト区切りソース アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-146">The Text- Delimited source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="8eacc-147">コネクタでこのアドレスを Microsoft 365 ユーザーに関連付ける場合、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="8eacc-148">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-148">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-text-delimited-connector"></a><span data-ttu-id="8eacc-149">手順 4: テキスト区切りコネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="8eacc-149">Step 4: Monitor the text-delimited connector</span></span>

<span data-ttu-id="8eacc-150">テキスト区切りコネクタを作成した後、Microsoft 365 コンプライアンス センターでコネクタの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-150">After you create the Text- Delimited connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="8eacc-151">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="8eacc-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8eacc-152">[コネクタ **] タブをクリック** し、[ **テキスト区切りコネクタ]** を選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="8eacc-152">Click the **Connectors** tab and then select the **Text- Delimited** connector to display the flyout page.</span></span> <span data-ttu-id="8eacc-153">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="8eacc-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="8eacc-154">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="8eacc-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="8eacc-155">このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-155">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8eacc-156">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8eacc-156">Known issues</span></span>

- <span data-ttu-id="8eacc-157">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8eacc-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="8eacc-158">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="8eacc-158">Support for larger items will be available at a later date.</span></span>