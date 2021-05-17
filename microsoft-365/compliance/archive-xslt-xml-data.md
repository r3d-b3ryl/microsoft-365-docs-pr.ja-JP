---
title: XSLT/XML データをアーカイブするコネクタを設定Microsoft 365
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
description: 管理者は、Veritas から XSLT/XML データをインポートおよびアーカイブするコネクタを、Microsoft 365。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: 51b05f83c51626bc60dc19b5ec9a63750903281c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163761"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a><span data-ttu-id="ca6d9-104">XSLT/XML データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ca6d9-104">Set up a connector to archive XSLT/XML data</span></span>

<span data-ttu-id="ca6d9-105">コンプライアンス センターの Veritas コネクタをMicrosoft 365して、Web ページ ソースから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Web page source to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="ca6d9-106">Veritas には、XSLT (拡張可能スタイル シート言語変換) を使用して作成されたファイルを迅速に開発して、XML ファイルを Microsoft 365 にインポートできる他のファイル形式 (HTML やテキストなど) に変換できる[XSLT/XML](https://globanet.com/xslt-xml)コネクタが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-106">Veritas provides you with an [XSLT/XML connector](https://globanet.com/xslt-xml) that allows the rapid development of files created by using XSLT (Extensible Style sheet Language Transformations) to transform XML files into other file formats (such as HTML or text) that can be imported to Microsoft 365.</span></span> <span data-ttu-id="ca6d9-107">コネクタは、アイテムのコンテンツを XSLT/XML ソースから電子メール メッセージ形式に変換し、変換されたアイテムを別のメールボックスMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-107">The connector converts the content of an item from the XSLT/XML source to an email message format and then imports the converted item to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="ca6d9-108">XSLT/XML データがユーザー メールボックスに格納された後、訴訟ホールド、電子情報開示、保持ポリシー、保持ラベルなどのコンプライアンス機能Microsoft 365を適用できます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-108">After XSLT/XML data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="ca6d9-109">XSLT/XML コネクタを使用してデータをインポートおよびアーカイブMicrosoft 365、組織が政府機関および規制ポリシーに準拠しつ付けるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-109">Using an XSLT/XML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-xsltxml-data"></a><span data-ttu-id="ca6d9-110">XSLT/XML データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="ca6d9-110">Overview of archiving XSLT/XML data</span></span>

<span data-ttu-id="ca6d9-111">次の概要では、コネクタを使用して XSLT/XML ソース データをアーカイブするプロセスについて説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-111">The following overview explains the process of using a connector to archive XSLT/XML source data in Microsoft 365.</span></span>

![XSLT/XML データのアーカイブ ワークフロー](../media/XSLT-XMLConnectorWorkflow.png)

1. <span data-ttu-id="ca6d9-113">組織は XSLT/XML ソースを使用して XSLT/XML サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-113">Your organization works with the XSLT/XML source to set up and configure an XSLT/XML site.</span></span>

2. <span data-ttu-id="ca6d9-114">24 時間に 1 回、XSLT/XML ソースからのチャット メッセージが Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-114">Once every 24 hours, chat messages from the XSLT/XML source are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="ca6d9-115">コネクタは、コンテンツを電子メール メッセージ形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-115">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="ca6d9-116">Microsoft 365 コンプライアンス センターで作成した XSLT/XML コネクタは、毎日 Veritas Merge1 サイトに接続し、Microsoft クラウド内のセキュリティで保護された Azure Storage 場所にメッセージを転送します。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-116">The XSLT/XML connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="ca6d9-117">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換されたメッセージ アイテムを特定のユーザーのメールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="ca6d9-118">**XSLT/XML** という名前の受信トレイ フォルダー内の新しいサブフォルダーがユーザー メールボックスに作成され、メッセージ アイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-118">A new subfolder in the Inbox folder named **XSLT/XML** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="ca6d9-119">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="ca6d9-120">すべてのメッセージには、このプロパティが含まれるので、メッセージのすべての参加者の電子メール アドレスが設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-120">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ca6d9-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="ca6d9-121">Before you begin</span></span>

- <span data-ttu-id="ca6d9-122">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="ca6d9-123">このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-123">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="ca6d9-124">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="ca6d9-125">手順 1 で XSLT/XML コネクタを作成し (手順 3 で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポートの役割に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-125">The user who creates the XSLT/XML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="ca6d9-126">この役割は、コンプライアンス センターの [**データ** コネクタ] ページにコネクタを追加Microsoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="ca6d9-127">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="ca6d9-128">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="ca6d9-129">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="ca6d9-130">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-xsltxml-connector"></a><span data-ttu-id="ca6d9-131">手順 1: XSLT/XML コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ca6d9-131">Step 1: Set up an XSLT/XML connector</span></span>

<span data-ttu-id="ca6d9-132">最初の手順は、コンプライアンス センターの **データ** コネクタMicrosoft 365 XSLT/XML データのコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-132">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for XSLT/XML data.</span></span>

1. <span data-ttu-id="ca6d9-133">に移動し [https://compliance.microsoft.com](https://compliance.microsoft.com/) 、[データコネクタ  >  **XSLT/XML] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **XSLT/XML**.</span></span>

2. <span data-ttu-id="ca6d9-134">**[XSLT/XML 製品の説明]** ページで、[新しいコネクタの **追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-134">On the **XSLT/XML** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="ca6d9-135">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="ca6d9-136">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="ca6d9-137">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-an-xsltxml-connector"></a><span data-ttu-id="ca6d9-138">手順 2: XSLT/XML コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="ca6d9-138">Step 2: Configure an XSLT/XML connector</span></span>

<span data-ttu-id="ca6d9-139">2 番目の手順は、Merge1 サイトで XSLT/XML コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-139">The second step is to configure the XSLT/XML connector on the Merge1 site.</span></span> <span data-ttu-id="ca6d9-140">Veritas Merge1 サイトで XSLT/XML コネクタを構成する方法については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-140">For information about how to configure the XSLT/XML connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="ca6d9-141">[ファイルの **保存と&完了**] をクリックすると、コンプライアンス センターのコネクタ ウィザードの [ユーザー Microsoft 365] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="ca6d9-142">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="ca6d9-142">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="ca6d9-143">ユーザーをマップし、コンプライアンス センターでコネクタMicrosoft 365するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

2. <span data-ttu-id="ca6d9-144">**[XSLT/XML ユーザーをユーザーにマップMicrosoft 365] ページ** で、自動ユーザー マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-144">On the **Map XSLT/XML users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="ca6d9-145">XSLT/XML アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-145">The XSLT/XML items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="ca6d9-146">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

3. <span data-ttu-id="ca6d9-147">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-147">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xsltxml-connector"></a><span data-ttu-id="ca6d9-148">手順 4: XSLT/XML コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="ca6d9-148">Step 4: Monitor the XSLT/XML connector</span></span>

<span data-ttu-id="ca6d9-149">XSLT/XML コネクタを作成した後、コンプライアンス センターでコネクタのMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-149">After you create the XSLT/XML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="ca6d9-150">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-150">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="ca6d9-151">[コネクタ **] タブをクリック** し **、XSLT/XML** コネクタを選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-151">Click the **Connectors** tab and then select the **XSLT/XML** connector to display the flyout page.</span></span> <span data-ttu-id="ca6d9-152">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="ca6d9-153">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="ca6d9-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="ca6d9-154">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ca6d9-155">既知の問題</span><span class="sxs-lookup"><span data-stu-id="ca6d9-155">Known issues</span></span>

- <span data-ttu-id="ca6d9-156">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="ca6d9-157">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="ca6d9-157">Support for larger items will be available at a later date.</span></span>