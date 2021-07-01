---
title: Microsoft 365 のエンドポイントのデータ損失防止について説明する
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 のエンドポイントのデータ損失防止は、ファイル アクティビティの監視と、それらのファイルに対する保護アクションをエンドポイントに拡張します。 Microsoft 365 のコンプライアンスソリューションでファイルが表示されます '
ms.openlocfilehash: 39474f54440ba33c8d7140981c1495a5c46bf0fc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226685"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="987c8-104">Microsoft 365 のエンドポイントのデータ損失防止について説明する</span><span class="sxs-lookup"><span data-stu-id="987c8-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="987c8-105">Microsoft 365 のデータ損失防止 (DLP) を使用すると、機密があると判断されたアイテムに対して、発生しているアクションを監視し、それらのアイテムの意図しない共有を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="987c8-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="987c8-106">DLP の詳細については、「[データ損失防止ポリシーについて](dlp-learn-about-dlp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="987c8-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="987c8-107">**エンドポイントデータ損失防止** (エンドポイント DLP) は、Windows 10 デバイスにある機密アイテムについて、DLP のアクティビティの監視と保護機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="987c8-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="987c8-108">デバイスが、 Microsoft 365 コンプライアンス ソリューションに オンボードすると、機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="987c8-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="987c8-109">監視と対処が必要なエンドポイントのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="987c8-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="987c8-110">Microsoft エンドポイント DLP を使用すると、Windows 10 を実行しているデバイスでユーザーが機密アイテムに行っている次のようなアクティビティを監査および管理できます。　　　</span><span class="sxs-lookup"><span data-stu-id="987c8-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="987c8-111">最新情報</span><span class="sxs-lookup"><span data-stu-id="987c8-111">Activity</span></span> |<span data-ttu-id="987c8-112">説明</span><span class="sxs-lookup"><span data-stu-id="987c8-112">Description</span></span>  | <span data-ttu-id="987c8-113">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="987c8-113">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="987c8-114">クラウド サービスへのアップロード、または許可されていないブラウザーによるアクセス</span><span class="sxs-lookup"><span data-stu-id="987c8-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="987c8-115">ユーザーが制限されたサービス ドメインにアイテムをアップロードしようとした場合、またはブラウザーを介してアイテムにアクセスしようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="987c8-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="987c8-116">DLP に許可されていないブラウザーとしてリストされているブラウザーを使用している場合、アップロード アクティビティはブロックされ、ユーザーは Microsoft Edge (Chromium) を使用するようにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="987c8-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="987c8-117">その後、Microsoft Edge (Chromium) では、DLP ポリシー構成に基づいて、アップロードまたはアクセスを許可またはブロックします</span><span class="sxs-lookup"><span data-stu-id="987c8-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="987c8-118">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="987c8-118">auditable and restrictable</span></span>|
|<span data-ttu-id="987c8-119">他のアプリへのコピー</span><span class="sxs-lookup"><span data-stu-id="987c8-119">copy to other app</span></span>    |<span data-ttu-id="987c8-120">ユーザーが保護されたアイテムから情報をコピーし、他のアプリ、プロセス、またはアイテムに貼り付けようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="987c8-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="987c8-121">同一のアプリ、プロセス、またはアイテム内での情報のコピーと貼り付けは、このアクティビティでは検出されません。</span><span class="sxs-lookup"><span data-stu-id="987c8-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="987c8-122">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="987c8-122">auditable and restrictable</span></span>|
|<span data-ttu-id="987c8-123">USB リムーバブル メディアへのコピー</span><span class="sxs-lookup"><span data-stu-id="987c8-123">copy to USB removable media</span></span> |<span data-ttu-id="987c8-124">ユーザーがアイテムまたは情報をリムーバブル メディアまたは USB デバイスにコピーしようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="987c8-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="987c8-125">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="987c8-125">auditable and restrictable</span></span>|
|<span data-ttu-id="987c8-126">ネットワーク共有へのコピー</span><span class="sxs-lookup"><span data-stu-id="987c8-126">copy to a network share</span></span>    |<span data-ttu-id="987c8-127">ユーザーがアイテムをネットワーク共有またはマップされたネットワーク ドライブにコピーしようとした場合に検出します</span><span class="sxs-lookup"><span data-stu-id="987c8-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="987c8-128">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="987c8-128">auditable and restrictable</span></span>|
|<span data-ttu-id="987c8-129">ドキュメントの印刷</span><span class="sxs-lookup"><span data-stu-id="987c8-129">print a document</span></span>    |<span data-ttu-id="987c8-130">ユーザーが保護されたアイテムをローカル プリンターまたはネットワーク プリンターに出力しようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="987c8-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="987c8-131">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="987c8-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="987c8-132">リモート セッションにコピーする</span><span class="sxs-lookup"><span data-stu-id="987c8-132">copy to a remote session</span></span>|<span data-ttu-id="987c8-133">ユーザーがアイテムをリモート デスクトップセッションにコピーしようとしたことを検出します</span><span class="sxs-lookup"><span data-stu-id="987c8-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="987c8-134">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="987c8-134">auditable and restrictable</span></span>|
|<span data-ttu-id="987c8-135">Bluetooth デバイスにコピーする</span><span class="sxs-lookup"><span data-stu-id="987c8-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="987c8-136">ユーザーがアイテムを許可されていない Bluetooth アプリにコピーしようとしたことを検出します (エンドポイント DLP 設定の許可されていない Bluetooth アプリのリストで定義されています)。</span><span class="sxs-lookup"><span data-stu-id="987c8-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="987c8-137">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="987c8-137">auditable and restrictable</span></span>|
|<span data-ttu-id="987c8-138">アイテムの作成</span><span class="sxs-lookup"><span data-stu-id="987c8-138">create an item</span></span>|<span data-ttu-id="987c8-139">ユーザーがアイテムを作成した場合に検出します</span><span class="sxs-lookup"><span data-stu-id="987c8-139">Detects when a user creates an item</span></span>| <span data-ttu-id="987c8-140">監査可能</span><span class="sxs-lookup"><span data-stu-id="987c8-140">auditable</span></span>|
|<span data-ttu-id="987c8-141">アイテムの名前の変更</span><span class="sxs-lookup"><span data-stu-id="987c8-141">rename an item</span></span>|<span data-ttu-id="987c8-142">ユーザーがアイテムの名前を変更した場合に検出します</span><span class="sxs-lookup"><span data-stu-id="987c8-142">Detects when a user renames an item</span></span>| <span data-ttu-id="987c8-143">監査可能</span><span class="sxs-lookup"><span data-stu-id="987c8-143">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="987c8-144">監視対象ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-144">Monitored files</span></span>

<span data-ttu-id="987c8-145">エンドポイント DLP は、次のファイルの種類の監視をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="987c8-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="987c8-146">Word ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-146">Word files</span></span>
- <span data-ttu-id="987c8-147">PowerPoint ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-147">PowerPoint files</span></span>
- <span data-ttu-id="987c8-148">Excel ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-148">Excel files</span></span>
- <span data-ttu-id="987c8-149">PDF ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-149">PDF files</span></span>
- <span data-ttu-id="987c8-150">.csv ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-150">.csv files</span></span>
- <span data-ttu-id="987c8-151">.tsv ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-151">.tsv files</span></span>
- <span data-ttu-id="987c8-152">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-152">.txt files</span></span>
- <span data-ttu-id="987c8-153">.rtf ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-153">.rtf files</span></span>
- <span data-ttu-id="987c8-154">.c ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-154">.c files</span></span>
- <span data-ttu-id="987c8-155">.class ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-155">.class files</span></span>
- <span data-ttu-id="987c8-156">.cpp ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-156">.cpp files</span></span>
- <span data-ttu-id="987c8-157">.cs ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-157">.cs files</span></span>
- <span data-ttu-id="987c8-158">.h ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-158">.h files</span></span>
- <span data-ttu-id="987c8-159">.java ファイル</span><span class="sxs-lookup"><span data-stu-id="987c8-159">.java files</span></span>

<span data-ttu-id="987c8-160">既定では、エンドポイント DLP は、ポリシーの一致がない場合でも、これらのファイルの種類のアクティビティを監査します。</span><span class="sxs-lookup"><span data-stu-id="987c8-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="987c8-161">ポリシーの一致からのデータの監視のみが必要な場合は、エンドポイント DLP グローバル設定で **[デバイスのファイル アクティビティを常に監査する]** をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="987c8-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="987c8-162">この設定がオンの場合、デバイスがポリシーの対象になっていない場合でも、Word、PowerPoint、Excel、PDF、および .csv ァイルでのアクティビティは常に監査されます。</span><span class="sxs-lookup"><span data-stu-id="987c8-162">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="987c8-163">エンドポイント DLP は MIME の種類に基づいてアクティビティを監視するため、ファイルの拡張子が変更されてもアクティビティはキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="987c8-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="987c8-164">エンドポイント DLP との違い</span><span class="sxs-lookup"><span data-stu-id="987c8-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="987c8-165">エンドポイント DLP を掘り下げる前に知っておく必要がある追加の概念がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="987c8-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="987c8-166">デバイス管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="987c8-166">Enabling Device management</span></span>

<span data-ttu-id="987c8-167">デバイス管理は、デバイスからテレメトリを収集できる機能です。これは、エンドポイント DLP や [インサイダー リスク管理](insider-risk-management.md)などの 365 Microsoft のコンプライアンスソリューションに導入する機能です。</span><span class="sxs-lookup"><span data-stu-id="987c8-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="987c8-168">DLP ポリシーの場所として使用するすべてのデバイスをオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="987c8-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="987c8-169">![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="987c8-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="987c8-170">オンボードとオフボードは、デバイス管理センターからダウンロードするスクリプトを通して処理されます。</span><span class="sxs-lookup"><span data-stu-id="987c8-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="987c8-171">センターには、次の展開方法ごとにカスタムスクリプトがあります：</span><span class="sxs-lookup"><span data-stu-id="987c8-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="987c8-172">ローカルスクリプト (最大10台のマシン)</span><span class="sxs-lookup"><span data-stu-id="987c8-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="987c8-173">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="987c8-173">Group policy</span></span>
- <span data-ttu-id="987c8-174">System Center Configuration Manager （ バージョン 1610以降 ）</span><span class="sxs-lookup"><span data-stu-id="987c8-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="987c8-175">Mobile Device Management/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="987c8-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="987c8-176">非永続的マシン用の VDI のオンボードスクリプト</span><span class="sxs-lookup"><span data-stu-id="987c8-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="987c8-177">![デバイス オンボード ページ](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="987c8-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="987c8-178">デバイスをオンボードにするには、[Microsoft 365 エンドポイント DLPの使用を開始する](endpoint-dlp-getting-started.md)の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="987c8-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="987c8-179">[Microsoft Defender for Endpoint](/windows/security/threat-protection/) を介してデバイスをオンボードした場合、それらのデバイスは自動的にデバイスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="987c8-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="987c8-180">![管理対象デバイスの一覧](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="987c8-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="987c8-181">エンドポイント DLP データの表示</span><span class="sxs-lookup"><span data-stu-id="987c8-181">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="987c8-182">[DLP 警告管理ダッシュボード](dlp-configure-view-alerts-policies.md)に移動すると、エンドポイント デバイスに適用されている DLP ポリシーに関連する警告を表示できます。</span><span class="sxs-lookup"><span data-stu-id="987c8-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="987c8-183">![警告情報](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="987c8-183">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="987c8-184">同じダッシュボードで、リッチ メタデータに関連付けられたイベントの詳細を表示することもできます</span><span class="sxs-lookup"><span data-stu-id="987c8-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="987c8-185">![イベント情報](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="987c8-185">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="987c8-186">デバイスがオンボードされると、場所としてデバイスを使用する DLP ポリシーを構成し、展開する前でも、監査されたアクティビティに関する情報がアクティビティエクスプローラーに流れます。</span><span class="sxs-lookup"><span data-stu-id="987c8-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="987c8-187">![アクティビティ エクスプローラーでのエンドポイント DLP イベント](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="987c8-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="987c8-188">エンドポイント DLP は、監査済みアクティビティに関する広範囲にわたる情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="987c8-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="987c8-189">たとえば、ファイルがリムーバブル USB メディアにコピーされた場合、アクティビティの詳細に次の属性が表示されます：</span><span class="sxs-lookup"><span data-stu-id="987c8-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="987c8-190">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="987c8-190">activity type</span></span>
- <span data-ttu-id="987c8-191">クライアント IP</span><span class="sxs-lookup"><span data-stu-id="987c8-191">client IP</span></span>
- <span data-ttu-id="987c8-192">対象ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="987c8-192">target file path</span></span>
- <span data-ttu-id="987c8-193">発生したタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="987c8-193">happened timestamp</span></span>
- <span data-ttu-id="987c8-194">ファイル名</span><span class="sxs-lookup"><span data-stu-id="987c8-194">file name</span></span>
- <span data-ttu-id="987c8-195">ユーザー</span><span class="sxs-lookup"><span data-stu-id="987c8-195">user</span></span>
- <span data-ttu-id="987c8-196">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="987c8-196">file extension</span></span>
- <span data-ttu-id="987c8-197">ファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="987c8-197">file size</span></span>
- <span data-ttu-id="987c8-198">機密情報の種類（該当する場合）</span><span class="sxs-lookup"><span data-stu-id="987c8-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="987c8-199">sha1 値</span><span class="sxs-lookup"><span data-stu-id="987c8-199">sha1 value</span></span>
- <span data-ttu-id="987c8-200">sha256 値</span><span class="sxs-lookup"><span data-stu-id="987c8-200">sha256 value</span></span>
- <span data-ttu-id="987c8-201">以前のファイル名</span><span class="sxs-lookup"><span data-stu-id="987c8-201">previous file name</span></span>
- <span data-ttu-id="987c8-202">場所</span><span class="sxs-lookup"><span data-stu-id="987c8-202">location</span></span>
- <span data-ttu-id="987c8-203">親</span><span class="sxs-lookup"><span data-stu-id="987c8-203">parent</span></span>
- <span data-ttu-id="987c8-204">FilePath</span><span class="sxs-lookup"><span data-stu-id="987c8-204">filepath</span></span>
- <span data-ttu-id="987c8-205">ソースの場所の種類</span><span class="sxs-lookup"><span data-stu-id="987c8-205">source location type</span></span>
- <span data-ttu-id="987c8-206">platform</span><span class="sxs-lookup"><span data-stu-id="987c8-206">platform</span></span>
- <span data-ttu-id="987c8-207">デバイス名</span><span class="sxs-lookup"><span data-stu-id="987c8-207">device name</span></span>
- <span data-ttu-id="987c8-208">場所の宛先の種類</span><span class="sxs-lookup"><span data-stu-id="987c8-208">destination location type</span></span>
- <span data-ttu-id="987c8-209">コピーを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="987c8-209">application that performed the copy</span></span>
- <span data-ttu-id="987c8-210">Microsoft Defender for Endpoint デバイス ID (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="987c8-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="987c8-211">リムーバブルメディアデバイスの製造元</span><span class="sxs-lookup"><span data-stu-id="987c8-211">removable media device manufacturer</span></span>
- <span data-ttu-id="987c8-212">リムーバブルメディアデバイスのモデル</span><span class="sxs-lookup"><span data-stu-id="987c8-212">removable media device model</span></span>
- <span data-ttu-id="987c8-213">リムーバブルメディアデバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="987c8-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="987c8-214">![USB アクティビティ属性へのコピー](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="987c8-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="987c8-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="987c8-215">Next steps</span></span>

<span data-ttu-id="987c8-216">ここまでエンドポイント DLP について学びましたので、次のステップの手順は以下になります：</span><span class="sxs-lookup"><span data-stu-id="987c8-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="987c8-217">Microsoft エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="987c8-217">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="987c8-218">Microsoft エンドポイント データ損失防止を使用する</span><span class="sxs-lookup"><span data-stu-id="987c8-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="987c8-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="987c8-219">See also</span></span>

- [<span data-ttu-id="987c8-220">Microsoft エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="987c8-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="987c8-221">Microsoft エンドポイント データ損失防止を使用する</span><span class="sxs-lookup"><span data-stu-id="987c8-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="987c8-222">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="987c8-222">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="987c8-223">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="987c8-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="987c8-224">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="987c8-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="987c8-225">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="987c8-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="987c8-226">インサイダー リスク管理</span><span class="sxs-lookup"><span data-stu-id="987c8-226">Insider Risk management</span></span>](insider-risk-management.md)
