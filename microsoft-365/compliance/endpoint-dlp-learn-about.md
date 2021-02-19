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
ms.openlocfilehash: d5394499b5514e6e0a49f958a62e70cde61ebf44
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279311"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="f10a5-104">Microsoft 365 のエンドポイントのデータ損失防止について説明する</span><span class="sxs-lookup"><span data-stu-id="f10a5-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="f10a5-105">Microsoft 365 のデータ損失防止 (DLP) を使用すると、機密があると判断されたアイテムに対して、発生しているアクションを監視し、それらのアイテムの意図しない共有を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="f10a5-106">DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f10a5-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="f10a5-107">**エンドポイントデータ損失防止** (エンドポイント DLP) は、Windows 10 デバイスにある機密アイテムについて、DLP のアクティビティの監視と保護機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="f10a5-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="f10a5-108">デバイスが、 Microsoft 365 コンプライアンス ソリューションに オンボードすると、機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="f10a5-109">監視と対処が必要なエンドポイントのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="f10a5-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="f10a5-110">Microsoft エンドポイント DLP を使用すると、Windows 10 を実行しているデバイスでユーザーが機密アイテムに行っている次のようなアクティビティを監査および管理できます。　　　</span><span class="sxs-lookup"><span data-stu-id="f10a5-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="f10a5-111">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="f10a5-111">activity</span></span> |<span data-ttu-id="f10a5-112">説明</span><span class="sxs-lookup"><span data-stu-id="f10a5-112">description</span></span>  | <span data-ttu-id="f10a5-113">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="f10a5-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="f10a5-114">クラウド サービスへのアップロード、または許可されていないブラウザーによるアクセス</span><span class="sxs-lookup"><span data-stu-id="f10a5-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="f10a5-115">ユーザーが制限されたサービス ドメインにアイテムをアップロードしようとした場合、またはブラウザーを介してアイテムにアクセスしようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="f10a5-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="f10a5-116">DLP に許可されていないブラウザーとしてリストされているブラウザーを使用している場合、アップロード アクティビティはブロックされ、ユーザーは Microsoft Edge (Chromium) を使用するようにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="f10a5-117">その後、Microsoft Edge (Chromium) では、DLP ポリシー構成に基づいて、アップロードまたはアクセスを許可またはブロックします</span><span class="sxs-lookup"><span data-stu-id="f10a5-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="f10a5-118">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="f10a5-118">auditable and restrictable</span></span>|
|<span data-ttu-id="f10a5-119">他のアプリへのコピー</span><span class="sxs-lookup"><span data-stu-id="f10a5-119">copy to other app</span></span>    |<span data-ttu-id="f10a5-120">ユーザーが保護されたアイテムから情報をコピーし、他のアプリ、プロセス、またはアイテムに貼り付けようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="f10a5-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="f10a5-121">同一のアプリ、プロセス、またはアイテム内での情報のコピーと貼り付けは、このアクティビティでは検出されません。</span><span class="sxs-lookup"><span data-stu-id="f10a5-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="f10a5-122">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="f10a5-122">auditable and restrictable</span></span>|
|<span data-ttu-id="f10a5-123">USB リムーバブル メディアへのコピー</span><span class="sxs-lookup"><span data-stu-id="f10a5-123">copy to USB removable media</span></span> |<span data-ttu-id="f10a5-124">ユーザーがアイテムまたは情報をリムーバブル メディアまたは USB デバイスにコピーしようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="f10a5-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="f10a5-125">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="f10a5-125">auditable and restrictable</span></span>|
|<span data-ttu-id="f10a5-126">ネットワーク共有へのコピー</span><span class="sxs-lookup"><span data-stu-id="f10a5-126">copy to a network share</span></span>    |<span data-ttu-id="f10a5-127">ユーザーがアイテムをネットワーク共有またはマップされたネットワーク ドライブにコピーしようとした場合に検出します</span><span class="sxs-lookup"><span data-stu-id="f10a5-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="f10a5-128">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="f10a5-128">auditable and restrictable</span></span>|
|<span data-ttu-id="f10a5-129">ドキュメントの印刷</span><span class="sxs-lookup"><span data-stu-id="f10a5-129">print a document</span></span>    |<span data-ttu-id="f10a5-130">ユーザーが保護されたアイテムをローカル プリンターまたはネットワーク プリンターに出力しようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="f10a5-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="f10a5-131">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="f10a5-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="f10a5-132">アイテムの作成</span><span class="sxs-lookup"><span data-stu-id="f10a5-132">create an item</span></span>|<span data-ttu-id="f10a5-133">ユーザーがアイテムを作成した場合に検出します</span><span class="sxs-lookup"><span data-stu-id="f10a5-133">Detects when a user creates an item</span></span>| <span data-ttu-id="f10a5-134">監査可能</span><span class="sxs-lookup"><span data-stu-id="f10a5-134">auditable</span></span>|
|<span data-ttu-id="f10a5-135">アイテムの名前の変更</span><span class="sxs-lookup"><span data-stu-id="f10a5-135">rename an item</span></span>|<span data-ttu-id="f10a5-136">ユーザーがアイテムの名前を変更した場合に検出します</span><span class="sxs-lookup"><span data-stu-id="f10a5-136">Detects when a user renames an item</span></span>| <span data-ttu-id="f10a5-137">監査可能</span><span class="sxs-lookup"><span data-stu-id="f10a5-137">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="f10a5-138">監視対象ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-138">Monitored files</span></span>

<span data-ttu-id="f10a5-139">エンドポイント DLP は、次のファイルの種類の監視をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="f10a5-139">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="f10a5-140">Word ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-140">Word files</span></span>
- <span data-ttu-id="f10a5-141">PowerPoint ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-141">PowerPoint files</span></span>
- <span data-ttu-id="f10a5-142">Excel ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-142">Excel files</span></span>
- <span data-ttu-id="f10a5-143">PDF ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-143">PDF files</span></span>
- <span data-ttu-id="f10a5-144">.csv ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-144">.csv files</span></span>
- <span data-ttu-id="f10a5-145">.tsv ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-145">.tsv files</span></span>
- <span data-ttu-id="f10a5-146">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-146">.txt files</span></span>
- <span data-ttu-id="f10a5-147">.rtf ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-147">.rtf files</span></span>
- <span data-ttu-id="f10a5-148">.c ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-148">.c files</span></span>
- <span data-ttu-id="f10a5-149">.class ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-149">.class files</span></span>
- <span data-ttu-id="f10a5-150">.cpp ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-150">.cpp files</span></span>
- <span data-ttu-id="f10a5-151">.cs ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-151">.cs files</span></span>
- <span data-ttu-id="f10a5-152">.h ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-152">.h files</span></span>
- <span data-ttu-id="f10a5-153">.java ファイル</span><span class="sxs-lookup"><span data-stu-id="f10a5-153">.java files</span></span>
 
<span data-ttu-id="f10a5-154">既定では、エンドポイント DLP は、ポリシーの一致がない場合でも、これらのファイルの種類のアクティビティを監査します。</span><span class="sxs-lookup"><span data-stu-id="f10a5-154">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="f10a5-155">ポリシーの一致からのデータの監視のみが必要な場合は、エンドポイント DLP グローバル設定で **[デバイスのファイル アクティビティを常に監査する]** をオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-155">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="f10a5-156">どのような場合でも、Word、PowerPoint、Excel、PDF、および .csv ファイルのアクティビティは常に監査されます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-156">No matter what, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited.</span></span>

<span data-ttu-id="f10a5-157">エンドポイント DLP は MIME の種類に基づいてアクティビティを監視するため、ファイルの拡張子が変更されてもアクティビティはキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-157">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="f10a5-158">エンドポイント DLP との違い</span><span class="sxs-lookup"><span data-stu-id="f10a5-158">What's different in Endpoint DLP</span></span>

<span data-ttu-id="f10a5-159">エンドポイント DLP を掘り下げる前に知っておく必要がある追加の概念がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="f10a5-159">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="f10a5-160">デバイス管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="f10a5-160">Enabling Device management</span></span>

<span data-ttu-id="f10a5-161">デバイス管理は、デバイスからテレメトリを収集できる機能です。これは、エンドポイント DLP や [インサイダー リスク管理](insider-risk-management.md)などの 365 Microsoft のコンプライアンスソリューションに導入する機能です。</span><span class="sxs-lookup"><span data-stu-id="f10a5-161">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="f10a5-162">DLP ポリシーの場所として使用するすべてのデバイスをオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f10a5-162">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f10a5-163">![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="f10a5-163">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="f10a5-164">オンボードとオフボードは、デバイス管理センターからダウンロードするスクリプトを通して処理されます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-164">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="f10a5-165">センターには、次の展開方法ごとにカスタムスクリプトがあります：</span><span class="sxs-lookup"><span data-stu-id="f10a5-165">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="f10a5-166">ローカルスクリプト (最大10台のマシン)</span><span class="sxs-lookup"><span data-stu-id="f10a5-166">local script (up to 10 machines)</span></span>
- <span data-ttu-id="f10a5-167">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="f10a5-167">Group policy</span></span>
- <span data-ttu-id="f10a5-168">System Center Configuration Manager （ バージョン 1610以降 ）</span><span class="sxs-lookup"><span data-stu-id="f10a5-168">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="f10a5-169">Mobile Device Management/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f10a5-169">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="f10a5-170">非永続的マシン用の VDI のオンボードスクリプト</span><span class="sxs-lookup"><span data-stu-id="f10a5-170">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f10a5-171">![デバイス オンボード ページ](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="f10a5-171">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="f10a5-172">デバイスをオンボードにするには、[Microsoft 365 エンドポイント DLPの使用を開始する](endpoint-dlp-getting-started.md)の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f10a5-172">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="f10a5-173">[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) を介してデバイスをオンボードした場合、それらのデバイスは自動的にデバイスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-173">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f10a5-174">![管理対象デバイスの一覧](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="f10a5-174">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="f10a5-175">エンドポイント DLP データの表示</span><span class="sxs-lookup"><span data-stu-id="f10a5-175">Viewing Endpoint DLP data</span></span>



<span data-ttu-id="f10a5-176">[DLP 警告管理ダッシュボード](dlp-configure-view-alerts-policies.md)に移動すると、エンドポイント デバイスに適用されている DLP ポリシーに関連する警告を表示できます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-176">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![警告情報](../media/Alert-info-1.png)

<span data-ttu-id="f10a5-178">同じダッシュボードで、リッチ メタデータに関連付けられたイベントの詳細を表示することもできます</span><span class="sxs-lookup"><span data-stu-id="f10a5-178">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![イベント情報](../media/Event-info-1.png)

<span data-ttu-id="f10a5-180">デバイスがオンボードされると、場所としてデバイスを使用する DLP ポリシーを構成し、展開する前でも、監査されたアクティビティに関する情報がアクティビティエクスプローラーに流れます。</span><span class="sxs-lookup"><span data-stu-id="f10a5-180">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f10a5-181">![アクティビティ エクスプローラーでのエンドポイント DLP イベント](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="f10a5-181">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="f10a5-182">エンドポイント DLP は、監査済みアクティビティに関する広範囲にわたる情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="f10a5-182">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="f10a5-183">たとえば、ファイルがリムーバブル USB メディアにコピーされた場合、アクティビティの詳細に次の属性が表示されます：</span><span class="sxs-lookup"><span data-stu-id="f10a5-183">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="f10a5-184">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="f10a5-184">activity type</span></span>
- <span data-ttu-id="f10a5-185">クライアント IP</span><span class="sxs-lookup"><span data-stu-id="f10a5-185">client IP</span></span>
- <span data-ttu-id="f10a5-186">対象ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="f10a5-186">target file path</span></span>
- <span data-ttu-id="f10a5-187">発生したタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="f10a5-187">happened timestamp</span></span>
- <span data-ttu-id="f10a5-188">ファイル名</span><span class="sxs-lookup"><span data-stu-id="f10a5-188">file name</span></span>
- <span data-ttu-id="f10a5-189">ユーザー</span><span class="sxs-lookup"><span data-stu-id="f10a5-189">user</span></span>
- <span data-ttu-id="f10a5-190">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="f10a5-190">file extension</span></span>
- <span data-ttu-id="f10a5-191">ファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="f10a5-191">file size</span></span>
- <span data-ttu-id="f10a5-192">機密情報の種類（該当する場合）</span><span class="sxs-lookup"><span data-stu-id="f10a5-192">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="f10a5-193">sha1 値</span><span class="sxs-lookup"><span data-stu-id="f10a5-193">sha1 value</span></span>
- <span data-ttu-id="f10a5-194">sha256 値</span><span class="sxs-lookup"><span data-stu-id="f10a5-194">sha256 value</span></span>
- <span data-ttu-id="f10a5-195">以前のファイル名</span><span class="sxs-lookup"><span data-stu-id="f10a5-195">previous file name</span></span>
- <span data-ttu-id="f10a5-196">場所</span><span class="sxs-lookup"><span data-stu-id="f10a5-196">location</span></span>
- <span data-ttu-id="f10a5-197">親</span><span class="sxs-lookup"><span data-stu-id="f10a5-197">parent</span></span>
- <span data-ttu-id="f10a5-198">FilePath</span><span class="sxs-lookup"><span data-stu-id="f10a5-198">filepath</span></span>
- <span data-ttu-id="f10a5-199">ソースの場所の種類</span><span class="sxs-lookup"><span data-stu-id="f10a5-199">source location type</span></span>
- <span data-ttu-id="f10a5-200">platform</span><span class="sxs-lookup"><span data-stu-id="f10a5-200">platform</span></span>
- <span data-ttu-id="f10a5-201">デバイス名</span><span class="sxs-lookup"><span data-stu-id="f10a5-201">device name</span></span>
- <span data-ttu-id="f10a5-202">場所の宛先の種類</span><span class="sxs-lookup"><span data-stu-id="f10a5-202">destination location type</span></span>
- <span data-ttu-id="f10a5-203">コピーを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f10a5-203">application that performed the copy</span></span>
- <span data-ttu-id="f10a5-204">Microsoft Defender for Endpoint デバイス ID (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="f10a5-204">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="f10a5-205">リムーバブルメディアデバイスの製造元</span><span class="sxs-lookup"><span data-stu-id="f10a5-205">removable media device manufacturer</span></span>
- <span data-ttu-id="f10a5-206">リムーバブルメディアデバイスのモデル</span><span class="sxs-lookup"><span data-stu-id="f10a5-206">removable media device model</span></span>
- <span data-ttu-id="f10a5-207">リムーバブルメディアデバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="f10a5-207">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f10a5-208">![USB アクティビティ属性へのコピー](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="f10a5-208">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="f10a5-209">次の手順</span><span class="sxs-lookup"><span data-stu-id="f10a5-209">Next steps</span></span>

<span data-ttu-id="f10a5-210">ここまでエンドポイント DLP について学びましたので、次のステップの手順は以下になります：</span><span class="sxs-lookup"><span data-stu-id="f10a5-210">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="f10a5-211">Microsoft エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="f10a5-211">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="f10a5-212">Microsoft エンドポイント データ損失防止を使用する</span><span class="sxs-lookup"><span data-stu-id="f10a5-212">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="f10a5-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="f10a5-213">See also</span></span>

- [<span data-ttu-id="f10a5-214">Microsoft エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="f10a5-214">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="f10a5-215">Microsoft エンドポイント データ損失防止を使用する</span><span class="sxs-lookup"><span data-stu-id="f10a5-215">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="f10a5-216">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="f10a5-216">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="f10a5-217">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="f10a5-217">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="f10a5-218">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="f10a5-218">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="f10a5-219">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f10a5-219">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="f10a5-220">インサイダー リスク管理</span><span class="sxs-lookup"><span data-stu-id="f10a5-220">Insider Risk management</span></span>](insider-risk-management.md)
