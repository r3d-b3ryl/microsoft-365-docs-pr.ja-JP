---
title: Web ページ のデータをアーカイブするコネクタを設定Microsoft 365
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
description: 管理者は、Web ページ キャプチャ データをインポートおよびアーカイブするコネクタを Veritas からインポートおよびアーカイブMicrosoft 365。 このコネクタを使用すると、Microsoft 365 のサード パーティデータ ソースからデータをアーカイブし、法的保持、コンテンツ検索、保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティ データを管理できます。
ms.openlocfilehash: d37ed5fdb6995fa9333181d254b1fccd2b08b43b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163858"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a><span data-ttu-id="95500-104">Web ページ データをアーカイブするコネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="95500-104">Set up a connector to archive webpage data</span></span>

<span data-ttu-id="95500-105">コンプライアンス センターの Veritas コネクタをMicrosoft 365、Web ページから組織のユーザー メールボックスにデータをインポートおよびアーカイブMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="95500-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from webpages to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="95500-106">Veritas は、特定の [Web](https://globanet.com/webpage-capture) サイトまたはドメイン全体の特定の Web ページ (およびそれらのページ上のリンク) をキャプチャする Web ページ キャプチャ コネクタを提供します。</span><span class="sxs-lookup"><span data-stu-id="95500-106">Veritas provides a [Webpage Capture](https://globanet.com/webpage-capture) connector that captures specific webpages (and any links on those pages) in a specific website or an entire domain.</span></span> <span data-ttu-id="95500-107">コネクタは、Web ページのコンテンツを PDF、PNG、またはカスタム ファイル形式に変換し、変換されたファイルを電子メール メッセージに添付し、それらの電子メール アイテムを Microsoft 365 のユーザー メールボックスにインポートします。</span><span class="sxs-lookup"><span data-stu-id="95500-107">The connector converts the webpage content to a PDF, PNG, or custom file format and then attaches the converted files to an email message and then imports those email items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="95500-108">Web ページのコンテンツをユーザー メールボックスに保存した後、訴訟ホールド、電子情報開示、保持ポリシー Microsoft 365保持ラベルなどのコンプライアンス機能を適用できます。</span><span class="sxs-lookup"><span data-stu-id="95500-108">After webpage content is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="95500-109">Web ページ キャプチャ コネクタを使用して、組織が政府機関および規制Microsoft 365に準拠し、データをインポートおよびアーカイブできます。</span><span class="sxs-lookup"><span data-stu-id="95500-109">Using a Webpage Capture connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webpage-data"></a><span data-ttu-id="95500-110">Web ページ データのアーカイブの概要</span><span class="sxs-lookup"><span data-stu-id="95500-110">Overview of archiving webpage data</span></span>

<span data-ttu-id="95500-111">次の概要では、コネクタを使用して Web ページ のコンテンツをアーカイブするプロセスについて説明Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="95500-111">The following overview explains the process of using a connector to archive webpage content in Microsoft 365.</span></span>

![Web ページ データのアーカイブ ワークフロー](../media/WebPageCaptureConnectorWorkflow.png)

1. <span data-ttu-id="95500-113">組織は Web ページ ソースと一緒に Web ページ キャプチャ サイトを設定および構成します。</span><span class="sxs-lookup"><span data-stu-id="95500-113">Your organization works with the webpage source to set up and configure a Webpage Capture site.</span></span>

2. <span data-ttu-id="95500-114">24 時間に 1 回、Web ページのソース アイテムが Veritas Merge1 サイトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="95500-114">Once every 24 hours, the webpage sources items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="95500-115">コネクタは、Web ページのコンテンツを電子メール メッセージに変換して添付します。</span><span class="sxs-lookup"><span data-stu-id="95500-115">The connector also converts and attaches the content of a webpage to an email message.</span></span>

3. <span data-ttu-id="95500-116">Microsoft 365 コンプライアンス センターで作成した Web ページ キャプチャ コネクタは、毎日 Veritas Merge1 サイトに接続し、Web ページアイテムを Microsoft クラウド内の安全な Azure Storage 場所に転送します。</span><span class="sxs-lookup"><span data-stu-id="95500-116">The Webpage Capture connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the webpage items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="95500-117">コネクタは、手順 3 で説明したように、自動ユーザー マッピングの *Email* プロパティの値を使用して、変換された Web ページ アイテムを特定のユーザーのメールボックス [にインポートします](#step-3-map-users-and-complete-the-connector-setup)。</span><span class="sxs-lookup"><span data-stu-id="95500-117">The connector imports the converted webpage items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="95500-118">[Web ページ キャプチャ] という名前の **受信** トレイ フォルダー内のサブフォルダーがユーザー メールボックスに作成され、Web ページアイテムがそのフォルダーにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="95500-118">A subfolder in the Inbox folder named **Webpage Capture** is created in the user mailboxes, and the webpage items are imported to that folder.</span></span> <span data-ttu-id="95500-119">コネクタは、Email プロパティの値を使用して *これを行* います。</span><span class="sxs-lookup"><span data-stu-id="95500-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="95500-120">すべての Web ページ アイテムには、このプロパティが含まれます。このプロパティには、手順 2 で Web ページ キャプチャ コネクタを構成するときに提供される電子メール アドレスが [入力されます](#step-2-configure-the-webpage-capture-connector-on-the-veritas-merge1-site)。</span><span class="sxs-lookup"><span data-stu-id="95500-120">Every webpage item contains this property, which is populated with the email addresses provided when you configure the Webpage Capture connector in [Step 2](#step-2-configure-the-webpage-capture-connector-on-the-veritas-merge1-site).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="95500-121">はじめに</span><span class="sxs-lookup"><span data-stu-id="95500-121">Before you begin</span></span>

- <span data-ttu-id="95500-122">Microsoft コネクタ用の Veritas Merge1 アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="95500-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="95500-123">このアカウントを作成するには [、Veritas カスタマー サポートにお問い合わせください](https://www.veritas.com/content/support/)。</span><span class="sxs-lookup"><span data-stu-id="95500-123">To create this account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="95500-124">手順 1 でコネクタを作成するときに、このアカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="95500-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="95500-125">Veritas サポートを使用して、Web ページ アイテムを変換するカスタム ファイル形式を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95500-125">You need to work with Veritas support to set up a custom file format to convert the webpage items to.</span></span> <span data-ttu-id="95500-126">詳細については [、「Merge1 サードパーティ](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95500-126">For more information, see the [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).</span></span>

- <span data-ttu-id="95500-127">手順 1 で Web ページ キャプチャ コネクタを作成し (および手順 3 で完了する) ユーザーは、Web ページのメールボックスインポートエクスポートの役割に割り当てる必要Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95500-127">The user who creates the Webpage Capture connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="95500-128">この役割は、コンプライアンス センターの [**データ** コネクタ] ページにコネクタを追加Microsoft 365必要です。</span><span class="sxs-lookup"><span data-stu-id="95500-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="95500-129">既定では、この役割はグループ内の役割グループExchange Online。</span><span class="sxs-lookup"><span data-stu-id="95500-129">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="95500-130">[メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95500-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="95500-131">または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="95500-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="95500-132">詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95500-132">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webpage-capture-connector"></a><span data-ttu-id="95500-133">手順 1: Web ページ キャプチャ コネクタをセットアップする</span><span class="sxs-lookup"><span data-stu-id="95500-133">Step 1: Set up the Webpage Capture connector</span></span>

<span data-ttu-id="95500-134">最初の手順は、データ コネクタ **にアクセス** し、Web ページ ソース データのコネクタを作成することです。</span><span class="sxs-lookup"><span data-stu-id="95500-134">The first step is to access to the **Data Connectors** and create a connector for Web Page source data.</span></span>

1. <span data-ttu-id="95500-135">[データ コネクタ [https://compliance.microsoft.com](https://compliance.microsoft.com/) の Web ページ キャプチャ] に移動し、[データ **コネクタ**  >  **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95500-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webpage Capture**.</span></span>

2. <span data-ttu-id="95500-136">[Web **ページ キャプチャ製品の説明]** ページで、[コネクタの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95500-136">On the **Webpage Capture** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="95500-137">[サービス条件 **] ページで、[** 同意する] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="95500-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="95500-138">コネクタを識別する一意の名前を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="95500-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="95500-139">コネクタを構成するには、Merge1 アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="95500-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webpage-capture-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="95500-140">手順 2: Veritas Merge1 サイトで Web ページ キャプチャ コネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="95500-140">Step 2: Configure the Webpage Capture connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="95500-141">2 番目の手順は、Veritas Merge1 サイトで Web ページ キャプチャ コネクタを構成することです。</span><span class="sxs-lookup"><span data-stu-id="95500-141">The second step is to configure the Webpage Capture connector on the Veritas Merge1 site.</span></span> <span data-ttu-id="95500-142">Web ページ キャプチャ コネクタを構成する方法の詳細については [、「Merge1 サード](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)パーティ コネクタ ユーザー ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95500-142">For information about how to configure the Webpage Capture connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="95500-143">[ファイルの **保存と&完了**] をクリックすると、コンプライアンス センターのコネクタ ウィザードの [ユーザー Microsoft 365] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95500-143">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="95500-144">手順 3: ユーザーをマップし、コネクタのセットアップを完了する</span><span class="sxs-lookup"><span data-stu-id="95500-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="95500-145">ユーザーをマップし、コンプライアンス センターでコネクタMicrosoft 365するには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="95500-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="95500-146">[Web **ページ のキャプチャ ユーザーをユーザーにMicrosoft 365]** ページで、ユーザーの自動マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="95500-146">On the **Map Webpage Capture users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="95500-147">Web ページ キャプチャ アイテムには、組織内のユーザーの電子メール アドレスを含む *Email* というプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="95500-147">The Webpage Capture items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="95500-148">コネクタでこのアドレスをユーザーに関連付Microsoft 365、アイテムはユーザーのメールボックスにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="95500-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="95500-149">[**次へ**] をクリックし、設定を確認し、[データ コネクタ] ページに移動して、新しいコネクタのインポート プロセスの進行状況を確認します。</span><span class="sxs-lookup"><span data-stu-id="95500-149">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webpage-capture-connector"></a><span data-ttu-id="95500-150">手順 4: Web ページ キャプチャ コネクタを監視する</span><span class="sxs-lookup"><span data-stu-id="95500-150">Step 4: Monitor the Webpage Capture connector</span></span>

<span data-ttu-id="95500-151">Web ページ キャプチャ コネクタを作成した後、コンプライアンス センターでコネクタのMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="95500-151">After you create the Webpage Capture connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="95500-152">左側の [https://compliance.microsoft.com](https://compliance.microsoft.com) ナビゲーションで [ **データ コネクタ] に** 移動してクリックします。</span><span class="sxs-lookup"><span data-stu-id="95500-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="95500-153">[コネクタ **] タブをクリック** し **、[Web** ページ キャプチャ コネクタ] を選択して、フライアウト ページを表示します。</span><span class="sxs-lookup"><span data-stu-id="95500-153">Click the **Connectors** tab and then select the **Webpage Capture** connector to display the flyout page.</span></span> <span data-ttu-id="95500-154">このページには、コネクタに関するプロパティと情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="95500-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="95500-155">[**ソースを含むコネクタの状態**] で、[ログのダウンロード] リンクをクリックして、コネクタの状態ログを開く (または保存) します。 </span><span class="sxs-lookup"><span data-stu-id="95500-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="95500-156">このログには、Microsoft クラウドにインポートされたデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="95500-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="95500-157">既知の問題</span><span class="sxs-lookup"><span data-stu-id="95500-157">Known issues</span></span>

- <span data-ttu-id="95500-158">現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="95500-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="95500-159">大きいアイテムのサポートは、後日利用できます。</span><span class="sxs-lookup"><span data-stu-id="95500-159">Support for larger items will be available at a later date.</span></span>