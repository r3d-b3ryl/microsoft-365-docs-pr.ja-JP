---
title: エンドポイント データ損失防止の使用
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Microsoft 365 エンドポイント データ損失防止 (EPDLP) の場所を使用するようにデータ損失防止 (DLP) ポリシーを構成する方法を説明します。
ms.openlocfilehash: 6723f3f0903ba6a0e1833bfae1f3dea2362e2c30
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406211"
---
# <a name="using-endpoint-data-loss-prevention"></a><span data-ttu-id="35f56-103">エンドポイント データ損失防止の使用</span><span class="sxs-lookup"><span data-stu-id="35f56-103">Using Endpoint data loss prevention</span></span>

<span data-ttu-id="35f56-104">この記事では、デバイスを場所として使用する DLP ポリシーを作成および変更する 3 つのシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="35f56-104">This article walks you through three scenarios where you create and modify a DLP policy that uses devices as a location.</span></span>

## <a name="dlp-settings"></a><span data-ttu-id="35f56-105">DLP の設定</span><span class="sxs-lookup"><span data-stu-id="35f56-105">DLP settings</span></span>

<span data-ttu-id="35f56-106">作業を開始する前に、デバイスのすべての DLP ポリシーに適用する DLP 設定を済ませる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f56-106">Before you get started you should set up your DLP settings which are applied to all DLP policies for devices.</span></span> <span data-ttu-id="35f56-107">実施するポリシーを作成する場合は、次のようにこれらを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f56-107">You must configure these if you intend to create policies that enforce:</span></span>

- <span data-ttu-id="35f56-108">クラウド出口制限</span><span class="sxs-lookup"><span data-stu-id="35f56-108">cloud egress restrictions</span></span>
- <span data-ttu-id="35f56-109">許可しないアプリの制限</span><span class="sxs-lookup"><span data-stu-id="35f56-109">unallowed apps restrictions</span></span>

<span data-ttu-id="35f56-110">または</span><span class="sxs-lookup"><span data-stu-id="35f56-110">Or</span></span>

- <span data-ttu-id="35f56-111">監視対象外のファイル パスを除外する場合</span><span class="sxs-lookup"><span data-stu-id="35f56-111">If you want to exclude noisy file paths from monitoring</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="35f56-112">![DLP の設定](../media/endpoint-dlp-1-using-dlp-settings.png)</span><span class="sxs-lookup"><span data-stu-id="35f56-112">![DLP settings](../media/endpoint-dlp-1-using-dlp-settings.png)</span></span>

### <a name="file-path-exclusions"></a><span data-ttu-id="35f56-113">ファイルパスの除外</span><span class="sxs-lookup"><span data-stu-id="35f56-113">File path exclusions</span></span>

<span data-ttu-id="35f56-114">DLP うるさすぎ、関心のあるファイルが含まれないので、デバイス上のDLP 監視、DLP 警告、および DLP ポリシー適用から特定のパスを除外したくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="35f56-114">You may want to exclude certain paths from DLP monitoring, DLP alerting, and DLP policy enforcement on your devices because they are too noisy or don’t contain files you are interested in.</span></span> <span data-ttu-id="35f56-115">これらの場所にあるファイルは監査されず、その場所で作成または変更されたファイルは、DLP ポリシー適応の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="35f56-115">Files in those locations will not be audited and any files that are created or modified in those locations will not be subject to DLP policy enforcement.</span></span> <span data-ttu-id="35f56-116">DLP 設定では、パスを除外するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-116">You can configure path exclusions in DLP settings.</span></span>

<span data-ttu-id="35f56-117">このロジックを使用して、除外パスを構築できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-117">You can use this logic to construct your exclusion paths:</span></span>

- <span data-ttu-id="35f56-118">有効なファイルパスが ' \ ' で終わっている場合は、フォルダーの直下にあるファイルだけになります。</span><span class="sxs-lookup"><span data-stu-id="35f56-118">Valid file path that ends with ‘\’, which means only files directly under folder.</span></span> <br/><span data-ttu-id="35f56-119">例: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="35f56-119">For example: C:\Temp</span></span>\

- <span data-ttu-id="35f56-120">有効なファイルパスが ‘\*’で終わっている場合は、そのフォルダーの直下のファイルという以外に、サブフォルダーの直下にあるファイルということになります。</span><span class="sxs-lookup"><span data-stu-id="35f56-120">Valid file path that ends with ‘\*’, which means only files under sub-folders, besides the files directly under the folder.</span></span> <br/><span data-ttu-id="35f56-121">例: C:\Temp\*</span><span class="sxs-lookup"><span data-stu-id="35f56-121">For example: C:\Temp\*</span></span>

- <span data-ttu-id="35f56-122">有効なファイルパスが ‘\’ または ‘\*’以外で終わっている場合は、フォルダーとすべてのサブフォルダーの直下にあるすべてのファイルになります。</span><span class="sxs-lookup"><span data-stu-id="35f56-122">Valid file path that ends without ‘\’ or ‘\*’, which means all files directly under folder and all sub-folders.</span></span> <br/><span data-ttu-id="35f56-123">例: C:\Temp</span><span class="sxs-lookup"><span data-stu-id="35f56-123">For example: C:\Temp</span></span>

- <span data-ttu-id="35f56-124">両側の ' \ ' の間にあるワイルドカードを使用したパス。</span><span class="sxs-lookup"><span data-stu-id="35f56-124">A path with wildcard between ‘\’ from each side.</span></span> <br/><span data-ttu-id="35f56-125">例: C:\Users\*¥ Desktop</span><span class="sxs-lookup"><span data-stu-id="35f56-125">For example: C:\Users\*\Desktop</span></span>\

- <span data-ttu-id="35f56-126">両側の ' \ ' の間にあるワイルドカードと' (数値) ' のあるパスは、サブフォルダーの正確な数を指定します。</span><span class="sxs-lookup"><span data-stu-id="35f56-126">A path with wildcard between ‘\’ from each side and with ‘(number)’ to give exact number of subfolders.</span></span> <br/><span data-ttu-id="35f56-127">例: C:\Users\*(1) \Downloads</span><span class="sxs-lookup"><span data-stu-id="35f56-127">For example: C:\Users\*(1)\Downloads</span></span>\

- <span data-ttu-id="35f56-128">システム環境変数を含むパス。</span><span class="sxs-lookup"><span data-stu-id="35f56-128">A path with SYSTEM environment variables.</span></span> <br/><span data-ttu-id="35f56-129">例: %SystemDrive%\Test\*</span><span class="sxs-lookup"><span data-stu-id="35f56-129">For example: %SystemDrive%\Test\*</span></span>

- <span data-ttu-id="35f56-130">上記のすべての組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="35f56-130">A mix of all the above.</span></span> <br/><span data-ttu-id="35f56-131">例: %SystemDrive%\Users\*\Documents\*(2) ¥ Sub</span><span class="sxs-lookup"><span data-stu-id="35f56-131">For example: %SystemDrive%\Users\*\Documents\*(2)\Sub</span></span>\

### <a name="unallowed-apps"></a><span data-ttu-id="35f56-132">許可されていないアプリ</span><span class="sxs-lookup"><span data-stu-id="35f56-132">Unallowed apps</span></span>

<span data-ttu-id="35f56-133">ポリシーで **許可されていないアプリとブラウザーによるアクセス** の設定がオンで、ユーザーがこのアプリを使用して保護ファイルにアクセスする場合、アクティビティが許可されるかブロックされますが、ユーザーはこの制限を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="35f56-133">When a policy's **Access by unallowed apps and browsers** setting is turned on and users attempt to use these apps to access a protected file, the activity will be allowed, blocked, or blocked but users can override the restriction.</span></span> <span data-ttu-id="35f56-134">すべてのアクティビティが監査され、アクティビティエクスプローラーで確認できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-134">All activity is audited and available to review in activity explorer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35f56-135">実行可能ファイルへのパスは含めず、実行可能ファイル名 (browser.exe など) のみを含めてください。</span><span class="sxs-lookup"><span data-stu-id="35f56-135">Do not include the path to the executable, but only the executable name (such as browser.exe).</span></span>


### <a name="browser-and-domain-restrictions"></a><span data-ttu-id="35f56-136">ブラウザーとドメインの制限</span><span class="sxs-lookup"><span data-stu-id="35f56-136">Browser and domain restrictions</span></span>
<span data-ttu-id="35f56-137">ポリシーに一致する機密ファイルが、無制限のクラウド サービス ドメインと共有されるのを制限します。</span><span class="sxs-lookup"><span data-stu-id="35f56-137">Restrict sensitive files that match your policies from being shared with unrestricted cloud service domains.</span></span>

#### <a name="service-domains"></a><span data-ttu-id="35f56-138">サービスドメイン</span><span class="sxs-lookup"><span data-stu-id="35f56-138">Service domains</span></span>

<span data-ttu-id="35f56-139">ポリシーによって保護されている機密ファイルを Microsoft Edge の特定のサービス ドメインにアップロードできるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-139">You can control whether sensitive files protected by your policies can be uploaded to specific service domains from Microsoft Edge.</span></span>

<span data-ttu-id="35f56-140">リストモードが **ブロック** に設定されている場合、ユーザーは、これらのドメインに機密アイテムをアップロードできません。</span><span class="sxs-lookup"><span data-stu-id="35f56-140">If the list mode is set to **Block**, then user will not be able to upload sensitive items to those domains.</span></span> <span data-ttu-id="35f56-141">アイテムが DLP ポリシーと一致するためにアップロードアクションがブロックされた場合、DLP が警告を生成するか、機密アイテムのアップロードをブロックします。</span><span class="sxs-lookup"><span data-stu-id="35f56-141">When an upload action is blocked because an item matches a DLP policy, DLP will either generate a warning or block the upload of the sensitive item.</span></span>

<span data-ttu-id="35f56-142">リスト モードが **許可** に設定されている場合、ユーザーはこれらのドメイン **_限定_** で機密アイテムをアップロードでき、その他すべてのドメインへのアップロードは制限されます。</span><span class="sxs-lookup"><span data-stu-id="35f56-142">If the list mode is set to **Allow**, then users will be able to upload sensitive items **_only_** to those domains, and upload access to all other domains is not allowed.</span></span>

#### <a name="unallowed-browsers"></a><span data-ttu-id="35f56-143">許可されていないブラウザー</span><span class="sxs-lookup"><span data-stu-id="35f56-143">Unallowed browsers</span></span>

<span data-ttu-id="35f56-144">実行可能ファイル名で識別された、クラウド サービスへのアップロードの制限がブロックまたは上書きのブロックに設定されている強制された DLP ポリシーの条件に一致するファイルへのアクセスがブロックされるブラウザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="35f56-144">You add browsers, identified by their executable names, that will be blocked from accessing files that match the conditions of an enforced a DLP policy where the upload to cloud services restriction is set to block or block override.</span></span> <span data-ttu-id="35f56-145">これらのブラウザーがファイルへのアクセスからブロックされている場合、エンドユーザーには、Edge Chromium 経由でファイルを開くように依頼するトースト通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35f56-145">When these browsers are blocked from accessing a file, the end users will see a toast notification asking them to open the file through Edge Chromium.</span></span>

### <a name="business-justification-in-policy-tips"></a><span data-ttu-id="35f56-146">ポリシー ヒントでの業務上の正当な理由</span><span class="sxs-lookup"><span data-stu-id="35f56-146">Business justification in policy tips</span></span>

<span data-ttu-id="35f56-147">DLP ポリシー ヒントの通知で、ユーザーによる業務上の正当な理由オプションの操作を制御します。</span><span class="sxs-lookup"><span data-stu-id="35f56-147">You can control how users interact with the business justification option in DLP policy tip notifications.</span></span> <span data-ttu-id="35f56-148">このオプションは、DLP ポリシーの **[オーバーライド付きブロック]** 設定で保護されているアクティビティをユーザーが実行したときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="35f56-148">This option appears when users perform an activity that's protected by the **Block with override** setting in a DLP policy.</span></span> <span data-ttu-id="35f56-149">以下のいずれかのオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-149">You can choose from one the following options:</span></span>

- <span data-ttu-id="35f56-150">既定では、ユーザーは組み込みの業務上の正当な理由を選択するか、独自のテキストを入力できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-150">By default, users can select either a built-in justification, or enter their own text.</span></span>
- <span data-ttu-id="35f56-151">ユーザーは、組み込みの業務上の正当な理由のみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-151">Users can only select a built-in justification.</span></span>
- <span data-ttu-id="35f56-152">ユーザーは、自分自身の正当な理由のみを入力できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-152">Users can only enter their own justification.</span></span>


## <a name="tying-dlp-settings-together"></a><span data-ttu-id="35f56-153">DLP 設定の結合</span><span class="sxs-lookup"><span data-stu-id="35f56-153">Tying DLP settings together</span></span>

<span data-ttu-id="35f56-154">エンドポイント DLP および Microsoft Edge Chromium Web ブラウザーを使用すると、許可されていないクラウドアプリとサービスで意図しない機密アイテムの共有を制限できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-154">With Endpoint DLP and Edge Chromium Web browser, you can restrict unintentional sharing of sensitive items to unallowed cloud apps and services.</span></span> <span data-ttu-id="35f56-155">Microsoft Edge Chromium では、アイテムがエンドポイント DLP ポリシーによって制限される場合を把握して、、アクセス制限を適用しています。</span><span class="sxs-lookup"><span data-stu-id="35f56-155">Edge Chromium understands when an item is restricted by an Endpoint DLP policy and enforces access restrictions.</span></span>

<span data-ttu-id="35f56-156">正常に構成されている DLP ポリシーと Microsoft Edge Chromium ブラウザーがある場所としてエンドポイント DLP を使用する場合、これらの設定で定義されている許可されていないブラウザーは、DLP ポリシーコントロールに一致する機密アイテムへアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="35f56-156">When you use Endpoint DLP as a location in a properly configured DLP policy and the Edge Chromium browser, the unallowed browsers that you've defined in these settings will be prevented from accessing the sensitive items that match your DLP policy controls.</span></span> <span data-ttu-id="35f56-157">その代わりに、ユーザーは Microsoft Edge Chromium および Microsoft Edge Chromium を使用するようにリダイレクトされます。 DLP ポリシーが適応される制限を把握することで、DLP ポリシーの条件が満たされた場合にアクティビティをブロックまたは制限することができます。</span><span class="sxs-lookup"><span data-stu-id="35f56-157">Instead, users will be redirected to use Edge Chromium and Edge Chromium, with its understanding of DLP imposed restrictions, can block or restrict activities when the conditions in the DLP policy are met.</span></span>

<span data-ttu-id="35f56-158">この制限を使用するには、次の3つの重要な要素を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f56-158">To use this restriction you’ll need to configure three important pieces:</span></span>

1. <span data-ttu-id="35f56-159">機密アイテムの共有を禁止する場所 (サービス、ドメイン、IP アドレス) を指定します。</span><span class="sxs-lookup"><span data-stu-id="35f56-159">Specify the places – services, domains, IP addresses – that you want to prevent sensitive items from being shared to.</span></span>

2. <span data-ttu-id="35f56-160">DLP ポリシーが一致した場合に、特定の機密アイテムへのアクセスを許可しないブラウザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="35f56-160">Add the browsers that aren’t allowed to access certain sensitive items when a DLP policy match occurs.</span></span>

3. <span data-ttu-id="35f56-161">**クラウドサービスへアップロード** と **許可していないブラウザーからのアクセス** の設定をオンにし、DLP ポリシーを構成してから、これらの場所でアップロードを制限する機密アイテムの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="35f56-161">Configure DLP policies to define the kinds of sensitive items for which upload should be restricted to these places by turning on **Upload to cloud services** and **Access from unallowed browser**.</span></span>

<span data-ttu-id="35f56-162">新しいサービス、アプリ、およびポリシーを継続的に追加して、制限を拡張、強化しながら、ビジネスへのニーズを満たし機密データを保護できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-162">You can continue to add new services, apps, and policies to extend and augment your restrictions to meet your business needs and protect sensitive data.</span></span> 

<span data-ttu-id="35f56-163">この構成により、データが安全に維持でき、ユーザーが機密情報以外のアイテムにアクセスしたり、共有したりすることを禁止または制限する不必要な制約も回避できます。</span><span class="sxs-lookup"><span data-stu-id="35f56-163">This configuration will help ensure your data remains safe while also avoiding unnecessary restrictions that prevent or restrict users from accessing and sharing non-sensitive items.</span></span>

## <a name="endpoint-dlp-policy-scenarios"></a><span data-ttu-id="35f56-164">エンドポイント DLP ポリシーシナリオ</span><span class="sxs-lookup"><span data-stu-id="35f56-164">Endpoint DLP policy scenarios</span></span>

<span data-ttu-id="35f56-165">エンドポイント DLP 機能、および DLP ポリシーで表示される方法を把握するために、いくつかのシナリオをまとめてましたので、確認してください。</span><span class="sxs-lookup"><span data-stu-id="35f56-165">To help familiarize you with Endpoint DLP features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35f56-166">これらのエンドポイント DLP シナリオは、DLP ポリシーの作成と調整に関する公式な手順ではありません。</span><span class="sxs-lookup"><span data-stu-id="35f56-166">These Endpoint DLP scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="35f56-167">一般的な状況で DLP ポリシーを使用する必要がある場合は、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35f56-167">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="35f56-168">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="35f56-168">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
>- [<span data-ttu-id="35f56-169">DLP の既定ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="35f56-169">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="35f56-170">テンプレートから DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="35f56-170">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="35f56-171">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="35f56-171">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a><span data-ttu-id="35f56-172">シナリオ 1: テンプレートからポリシーを作成 (監査のみ)</span><span class="sxs-lookup"><span data-stu-id="35f56-172">Scenario 1: Create a policy from a template, audit only</span></span>

<span data-ttu-id="35f56-173">これらのシナリオでは、デバイスが既にオンで、アクティビティエクスプローラーに報告されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="35f56-173">These scenarios require that you already have devices onboarded and reporting into Activity explorer.</span></span> <span data-ttu-id="35f56-174">まだデバイスをオンにしていない場合は、[エンドポイントのデータ損失防止 (プレビュー) を開始](endpoint-dlp-getting-started.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35f56-174">If you haven't onboarded devices yet, see [Get started with Endpoint data loss prevention](endpoint-dlp-getting-started.md).</span></span>

1. <span data-ttu-id="35f56-175">[データ損失防止ポリシー ページ](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開きます。</span><span class="sxs-lookup"><span data-stu-id="35f56-175">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="35f56-176">**[ポリシーの作成]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="35f56-176">Choose **Create policy**.</span></span>

3. <span data-ttu-id="35f56-177">このシナリオでは、**[プライバシー]** を選択して、"**米国の個人情報 (PII) データ**" を選んでから、**[次へ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="35f56-177">For this scenario, choose **Privacy**, then **U.S. Personally Identifiable Information (PII) Data** and choose **Next**.</span></span>

4. <span data-ttu-id="35f56-178">**状態** フィールドを **デバイス** を除くすべての場所でオフにします。</span><span class="sxs-lookup"><span data-stu-id="35f56-178">Toggle the **Status** field to off for all locations except **Devices**.</span></span> <span data-ttu-id="35f56-179">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-179">Choose **Next**.</span></span>

5. <span data-ttu-id="35f56-180">規定の **確認してテンプレートから設定をカスタマイズ** の選択を承認して、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-180">Accept the default **Review and customize settings from the template** selection and choose **Next**.</span></span>

6. <span data-ttu-id="35f56-181">既定の **保護アクション** の値を承認して、**次へ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-181">Accept the default **Protection actions** values and choose **Next**.</span></span>

7. <span data-ttu-id="35f56-182">**Windows デバイスのアクティビティを監査または制限** を選択して、**監査のみ** に設定されたアクションはそのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="35f56-182">Select **Audit or restrict activities on Windows devices** and leave the actions set to **Audit only**.</span></span> <span data-ttu-id="35f56-183">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-183">Choose **Next**.</span></span>

8. <span data-ttu-id="35f56-184">規定の **初めにテストします** を承認し、**テストモードでポリシーのヒントを表示** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-184">Accept the default **I'd like to test it out first** value and choose **Show policy tips while in test mode**.</span></span> <span data-ttu-id="35f56-185">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-185">Choose **Next**.</span></span>

9. <span data-ttu-id="35f56-186">設定を確認し、**送信** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-186">Review your settings and choose **Submit**.</span></span>

10. <span data-ttu-id="35f56-187">新しい DLP ポリシーがポリシー一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="35f56-187">The new DLP policy will appear in the policy list.</span></span>

11. <span data-ttu-id="35f56-188">監視対象エンドポイントのデータのアクティビティエクスプローラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="35f56-188">Check Activity explorer for data from the monitored endpoints.</span></span> <span data-ttu-id="35f56-189">デバイスがある場所のフィルターを設定し、ポリシーを追加してから、ポリシー名でフィルター処理を行って、このポリシーの影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="35f56-189">Set the location filter for devices and add the policy, then filter by policy name to see the impact of this policy.</span></span> <span data-ttu-id="35f56-190">必要に応じて、[アクティビティ エクスプローラーの使用を開始](data-classification-activity-explorer.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35f56-190">See, [Get started with activity explorer](data-classification-activity-explorer.md) if needed.</span></span>

12. <span data-ttu-id="35f56-191">組織外のユーザーと米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを共有。</span><span class="sxs-lookup"><span data-stu-id="35f56-191">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="35f56-192">これによって、ポリシーがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="35f56-192">This should trigger the policy.</span></span>

13. <span data-ttu-id="35f56-193">イベントのアクティビティエクスプローラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="35f56-193">Check Activity explorer for the event.</span></span>

### <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a><span data-ttu-id="35f56-194">シナリオ 2: 既存のポリシーを変更し、通知を設定</span><span class="sxs-lookup"><span data-stu-id="35f56-194">Scenario 2: Modify the existing policy, set an alert</span></span>

1. <span data-ttu-id="35f56-195">[データ損失防止ポリシー](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開く。</span><span class="sxs-lookup"><span data-stu-id="35f56-195">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="35f56-196">シナリオ １ で作成した **米国の個人情報 (PII) データ** ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-196">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="35f56-197">**[ポリシーの編集]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="35f56-197">Choose **edit policy**.</span></span>

4. <span data-ttu-id="35f56-198">**詳細な DLP ルール** ページに移動し、**米国の個人を特定できる情報が検出された低ボリュームのコンテンツ** を編集します。</span><span class="sxs-lookup"><span data-stu-id="35f56-198">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="35f56-199">**インシデントリポート** セクションまでスクロールして、**ルールが一致する場合、管理者に通知を送信** を **オン** に設定します。</span><span class="sxs-lookup"><span data-stu-id="35f56-199">Scroll down to the **Incident reports** section and set **Send an alert to admins when a rule match occurs** to **On**.</span></span> <span data-ttu-id="35f56-200">メールの通知は、管理者と、受信者のリストに追加する他のユーザーに自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="35f56-200">Email alerts will be automatically sent to the administrator and anyone else you add to the list of recipients.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="35f56-201">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span><span class="sxs-lookup"><span data-stu-id="35f56-201">![turn-on-incident-reports](../media/endpoint-dlp-2-using-dlp-incident-reports.png)</span></span>
   
6. <span data-ttu-id="35f56-202">このシナリオの目的で、**アクティビティーがこのルールに一致する度に通知を送信** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-202">For the purposes of this scenario, choose **Send alert every time an activity matches the rule**.</span></span>

7. <span data-ttu-id="35f56-203">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-203">Choose **Save**.</span></span>

8. <span data-ttu-id="35f56-204">**次へ** を選択して、ポリシーの変更を **送信** を選択することで、すべての前の設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="35f56-204">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="35f56-205">組織外のユーザーと米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを共有。</span><span class="sxs-lookup"><span data-stu-id="35f56-205">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="35f56-206">これによって、ポリシーがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="35f56-206">This should trigger the policy.</span></span>

10. <span data-ttu-id="35f56-207">イベントのアクティビティエクスプローラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="35f56-207">Check Activity explorer for the event.</span></span>

### <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a><span data-ttu-id="35f56-208">シナリオ 3: 既存のポリシーを変更し、上書きを許可する操作をブロック</span><span class="sxs-lookup"><span data-stu-id="35f56-208">Scenario 3: Modify the existing policy, block the action with allow override</span></span>

1. <span data-ttu-id="35f56-209">[データ損失防止ポリシー](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開く。</span><span class="sxs-lookup"><span data-stu-id="35f56-209">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies).</span></span>

2. <span data-ttu-id="35f56-210">シナリオ １ で作成した **米国の個人情報 (PII) データ** ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-210">Choose the **U.S. Personally Identifiable Information (PII) Data** policy that you created in scenario 1.</span></span>

3. <span data-ttu-id="35f56-211">**[ポリシーの編集]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="35f56-211">Choose **edit policy**.</span></span>

4. <span data-ttu-id="35f56-212">**詳細な DLP ルール** ページに移動し、**米国の個人を特定できる情報が検出された低ボリュームのコンテンツ** を編集します。</span><span class="sxs-lookup"><span data-stu-id="35f56-212">Go to the **Advanced DLP rules** page and edit the **Low volume of content detected U.S. Personally Identifiable Inf**.</span></span>

5. <span data-ttu-id="35f56-213">**Windows デバイスでアクティビティを監査または制限** セクションまでスクロールして、アクティビティごと対応するアクションに **上書きをブロック** を設定します。</span><span class="sxs-lookup"><span data-stu-id="35f56-213">Scroll down to the **Audit or restrict activities on Windows device** section and for each activity set the corresponding action to  **Block with override**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="35f56-214">![上書きアクションのブロックを設定](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span><span class="sxs-lookup"><span data-stu-id="35f56-214">![set block with override action](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)</span></span>
   
6. <span data-ttu-id="35f56-215">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="35f56-215">Choose **Save**.</span></span>

7. <span data-ttu-id="35f56-216">**米国の個人情報が検出された大量のコンテンツ** の手順4から手順７を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="35f56-216">Repeat steps 4-7 for the **High volume of content detected U.S. Personally Identifiable Inf**.</span></span>

8. <span data-ttu-id="35f56-217">**次へ** を選択して、ポリシーの変更を **送信** を選択することで、すべての前の設定を保持します。</span><span class="sxs-lookup"><span data-stu-id="35f56-217">Retain all your previous settings by choosing **Next** and then **Submit** the policy changes.</span></span>

9. <span data-ttu-id="35f56-218">組織外のユーザーと米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを共有。</span><span class="sxs-lookup"><span data-stu-id="35f56-218">Attempt to share a test that contains content that will trigger the U.S. Personally Identifiable Information (PII) Data condition with someone outside your organization.</span></span> <span data-ttu-id="35f56-219">これによって、ポリシーがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="35f56-219">This should trigger the policy.</span></span>

   <span data-ttu-id="35f56-220">クライアントデバイスに次のようなポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35f56-220">You'll see a popup like this on the client device:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="35f56-221">![エンドポイント DLP クライアントが上書き通知をブロックしました](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span><span class="sxs-lookup"><span data-stu-id="35f56-221">![endpoint dlp client blocked override notification](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)</span></span>

10. <span data-ttu-id="35f56-222">イベントのアクティビティエクスプローラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="35f56-222">Check Activity explorer for the event.</span></span>

## <a name="see-also"></a><span data-ttu-id="35f56-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="35f56-223">See also</span></span>

- [<span data-ttu-id="35f56-224">エンドポイント データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="35f56-224">Learn about Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="35f56-225">エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="35f56-225">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="35f56-226">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="35f56-226">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="35f56-227">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="35f56-227">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="35f56-228">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="35f56-228">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="35f56-229">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35f56-229">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="35f56-230">Windows 10 マシン用のオンボーディングツールとメソッド</span><span class="sxs-lookup"><span data-stu-id="35f56-230">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="35f56-231">Microsoft 365 サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="35f56-231">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="35f56-232">Azure Active Directory (AAD) が参加しました</span><span class="sxs-lookup"><span data-stu-id="35f56-232">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="35f56-233">Chromium ベースの新しい Microsoft Edge をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="35f56-233">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [<span data-ttu-id="35f56-234">DLP の既定ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="35f56-234">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
- [<span data-ttu-id="35f56-235">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="35f56-235">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
