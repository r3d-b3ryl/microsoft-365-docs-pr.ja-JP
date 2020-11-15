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
description: 'Microsoft 365 のエンドポイントのデータ損失防止は、ファイル アクティビティの監視と、それらのファイルに対する保護アクションをエンドポイントに拡張します。ファイルは Microsoft 365 コンプライアンス ソリューションで表示されます '
ms.openlocfilehash: e469872dac19db08f7b525c8a5ada725c75bfa10
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072976"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="ed4cf-104">Microsoft 365 のエンドポイントのデータ損失防止について説明する</span><span class="sxs-lookup"><span data-stu-id="ed4cf-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="ed4cf-p102">Microsoft 365 のデータ損失防止 (DLP) を使用すると、機密があると判断されたアイテムに対して、発生しているアクションを監視し、それらのアイテムの意図しない共有を防ぐことができます。DLPの詳細については、[データ損失防止の概要](data-loss-prevention-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="ed4cf-p103">**エンドポイントデータ損失防止** (エンドポイント DLP) は、DLP のアクティビティ監視および保護機能を Windows 10 デバイス上にある機密性の高いアイテムに拡張します。デバイスが、 Microsoft 365 コンプライアンス ソリューションに オンボードすると、機密アイテムを使用してユーザーが行っていることに関する情報が [Activity Explorer](data-classification-activity-explorer.md) に表示され、 [DLP ポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="ed4cf-109">監視と対処が必要なエンドポイントのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="ed4cf-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="ed4cf-p104">Microsoft エンドポイント DLP を使用すると、Windows 10 を実行しているデバイスでユーザーが機密アイテムに行っている次のようなアクティビティを監査および管理できます。これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="ed4cf-112">アイテムのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="ed4cf-112">activity on item</span></span> |<span data-ttu-id="ed4cf-113">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="ed4cf-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="ed4cf-114">作成済み</span><span class="sxs-lookup"><span data-stu-id="ed4cf-114">created</span></span>    | <span data-ttu-id="ed4cf-115">監査可能</span><span class="sxs-lookup"><span data-stu-id="ed4cf-115">auditable</span></span>      |
|<span data-ttu-id="ed4cf-116">名前の変更</span><span class="sxs-lookup"><span data-stu-id="ed4cf-116">renamed</span></span>    |  <span data-ttu-id="ed4cf-117">監査可能</span><span class="sxs-lookup"><span data-stu-id="ed4cf-117">auditable</span></span>       |
|<span data-ttu-id="ed4cf-118">リムーバブルメディアへのコピーと作成</span><span class="sxs-lookup"><span data-stu-id="ed4cf-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="ed4cf-119">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="ed4cf-119">auditable and restrictable</span></span>|
|<span data-ttu-id="ed4cf-120">\\my-server\fileshare などのネットワーク共有にコピーされます</span><span class="sxs-lookup"><span data-stu-id="ed4cf-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="ed4cf-121">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="ed4cf-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="ed4cf-122">印刷済み</span><span class="sxs-lookup"><span data-stu-id="ed4cf-122">printed</span></span> |    <span data-ttu-id="ed4cf-123">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="ed4cf-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="ed4cf-124">Chromium Edge 経由でクラウドにコピー</span><span class="sxs-lookup"><span data-stu-id="ed4cf-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="ed4cf-125">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="ed4cf-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="ed4cf-126">許可されていないアプリによってアクセスされました</span><span class="sxs-lookup"><span data-stu-id="ed4cf-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="ed4cf-127">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="ed4cf-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="ed4cf-128">エンドポイント DLP との違い</span><span class="sxs-lookup"><span data-stu-id="ed4cf-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="ed4cf-129">エンドポイント DLP を掘り下げる前に知っておく必要がある追加の概念がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="ed4cf-130">デバイス管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="ed4cf-130">Enabling Device management</span></span>

<span data-ttu-id="ed4cf-p105">デバイス管理は、デバイスからテレメトリを収集できる機能です。これは、エンドポイント DLP や [インサイダー リスク管理](insider-risk-management.md)などの Microsoft 365 のコンプライアンス ソリューションに導入する機能です。DLP ポリシーの場所として使用するすべてのデバイスをオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ed4cf-133">![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="ed4cf-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="ed4cf-p106">オンボーディングとオフボーディングは、デバイス管理センターからダウンロードしたスクリプトを介して処理されます。 センターには、これらの展開方法ごとに次のようなカスタムスクリプトがあります。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="ed4cf-136">ローカルスクリプト (最大10台のマシン)</span><span class="sxs-lookup"><span data-stu-id="ed4cf-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="ed4cf-137">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="ed4cf-137">Group policy</span></span>
- <span data-ttu-id="ed4cf-138">System Center Configuration Manager （ バージョン 1610以降 ）</span><span class="sxs-lookup"><span data-stu-id="ed4cf-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="ed4cf-139">Mobile Device Management/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ed4cf-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="ed4cf-140">非永続的コンピューター用の VDI オンボード スクリプト</span><span class="sxs-lookup"><span data-stu-id="ed4cf-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ed4cf-141">![デバイス オンボード ページ](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="ed4cf-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="ed4cf-142">デバイスをオンボードするには、「[Microsoft 365 エンドポイント DLP の使用を開始する](endpoint-dlp-getting-started.md)」の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="ed4cf-143">[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) を介してデバイスをオンボードした場合、それらのデバイスは自動的にデバイスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ed4cf-144">![管理対象デバイスの一覧](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="ed4cf-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="ed4cf-145">エンドポイント DLP データの表示</span><span class="sxs-lookup"><span data-stu-id="ed4cf-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="ed4cf-p107">エンドポイント DLP は、MIME タイプに基づいてアクティビティを監視するため、ファイル拡張子が変更された場合でもアクティビティがキャプチャされます。 公開プレビューでは、以下のすべてを監視します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="ed4cf-148">Word ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-148">Word files</span></span>
- <span data-ttu-id="ed4cf-149">PowerPoint ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-149">PowerPoint files</span></span>
- <span data-ttu-id="ed4cf-150">Excel ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-150">Excel files</span></span>
- <span data-ttu-id="ed4cf-151">PDF ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-151">PDF files</span></span>
- <span data-ttu-id="ed4cf-152">.csv ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-152">.csv files</span></span>
- <span data-ttu-id="ed4cf-153">.tsv ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-153">.tsv files</span></span>
- <span data-ttu-id="ed4cf-154">.txt ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-154">.txt files</span></span>
- <span data-ttu-id="ed4cf-155">.rtf ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-155">.rtf files</span></span>
- <span data-ttu-id="ed4cf-156">.c ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-156">.c files</span></span>
- <span data-ttu-id="ed4cf-157">.class ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-157">.class files</span></span>
- <span data-ttu-id="ed4cf-158">.cpp ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-158">.cpp files</span></span>
- <span data-ttu-id="ed4cf-159">.cs ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-159">.cs files</span></span>
- <span data-ttu-id="ed4cf-160">.h ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-160">.h files</span></span>
- <span data-ttu-id="ed4cf-161">.java ファイル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="ed4cf-p108">エンドポイント DLP は、上記すべての種類のファイルを DLP ポリシーに対して評価し、それに応じた保護アクションを適用します。DLP ポリシーに一致するすべてのファイルは、たとえブロックされていなくても、サポートされているすべてのアクションについて監査されます。さらに、Word、PowerPoint、Excel、PDF、.csv ファイルに対して実行されたファイル アクティビティについては、DLP ポリシーの存在やこれらのファイルとの一致に関係なく、既定で監査されます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="ed4cf-165">[DLP 警告管理ダッシュボード](dlp-configure-view-alerts-policies.md)に移動すると、エンドポイント デバイスに適用されている DLP ポリシーに関連する警告を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-165">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![警告情報](../media/Alert-info-1.png)

<span data-ttu-id="ed4cf-167">同じダッシュボードで、リッチ メタデータに関連付けられたイベントの詳細を表示することもできます</span><span class="sxs-lookup"><span data-stu-id="ed4cf-167">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![イベント情報](../media/Event-info-1.png)

<span data-ttu-id="ed4cf-169">デバイスを場所として持つ DLP ポリシーを構成して展開する前であっても、デバイスがオンボードされると、監査済みのアクティビティに関する情報がアクティビティ エクスプローラーに流入します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-169">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ed4cf-170">![アクティビティ エクスプローラーでのエンドポイント DLP イベント](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="ed4cf-170">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="ed4cf-171">エンドポイント DLP は、監査済みアクティビティに関する広範な情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-171">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="ed4cf-172">たとえば、ファイルがリムーバブル USB メディアにコピーされた場合、アクティビティの詳細に次の属性が表示されます：</span><span class="sxs-lookup"><span data-stu-id="ed4cf-172">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="ed4cf-173">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="ed4cf-173">activity type</span></span>
- <span data-ttu-id="ed4cf-174">クライアント IP</span><span class="sxs-lookup"><span data-stu-id="ed4cf-174">client IP</span></span>
- <span data-ttu-id="ed4cf-175">対象ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="ed4cf-175">target file path</span></span>
- <span data-ttu-id="ed4cf-176">発生したタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="ed4cf-176">happened timestamp</span></span>
- <span data-ttu-id="ed4cf-177">ファイル名</span><span class="sxs-lookup"><span data-stu-id="ed4cf-177">file name</span></span>
- <span data-ttu-id="ed4cf-178">ユーザー</span><span class="sxs-lookup"><span data-stu-id="ed4cf-178">user</span></span>
- <span data-ttu-id="ed4cf-179">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="ed4cf-179">file extension</span></span>
- <span data-ttu-id="ed4cf-180">ファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="ed4cf-180">file size</span></span>
- <span data-ttu-id="ed4cf-181">機密情報の種類（該当する場合）</span><span class="sxs-lookup"><span data-stu-id="ed4cf-181">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="ed4cf-182">sha1 値</span><span class="sxs-lookup"><span data-stu-id="ed4cf-182">sha1 value</span></span>
- <span data-ttu-id="ed4cf-183">sha256 値</span><span class="sxs-lookup"><span data-stu-id="ed4cf-183">sha256 value</span></span>
- <span data-ttu-id="ed4cf-184">以前のファイル名</span><span class="sxs-lookup"><span data-stu-id="ed4cf-184">previous file name</span></span>
- <span data-ttu-id="ed4cf-185">場所</span><span class="sxs-lookup"><span data-stu-id="ed4cf-185">location</span></span>
- <span data-ttu-id="ed4cf-186">親</span><span class="sxs-lookup"><span data-stu-id="ed4cf-186">parent</span></span>
- <span data-ttu-id="ed4cf-187">FilePath</span><span class="sxs-lookup"><span data-stu-id="ed4cf-187">filepath</span></span>
- <span data-ttu-id="ed4cf-188">ソースの場所の種類</span><span class="sxs-lookup"><span data-stu-id="ed4cf-188">source location type</span></span>
- <span data-ttu-id="ed4cf-189">platform</span><span class="sxs-lookup"><span data-stu-id="ed4cf-189">platform</span></span>
- <span data-ttu-id="ed4cf-190">デバイス名</span><span class="sxs-lookup"><span data-stu-id="ed4cf-190">device name</span></span>
- <span data-ttu-id="ed4cf-191">場所の宛先の種類</span><span class="sxs-lookup"><span data-stu-id="ed4cf-191">destination location type</span></span>
- <span data-ttu-id="ed4cf-192">コピーを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="ed4cf-192">application that performed the copy</span></span>
- <span data-ttu-id="ed4cf-193">Microsoft Defender for Endpoint デバイス ID (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="ed4cf-193">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="ed4cf-194">リムーバブルメディアデバイスの製造元</span><span class="sxs-lookup"><span data-stu-id="ed4cf-194">removable media device manufacturer</span></span>
- <span data-ttu-id="ed4cf-195">リムーバブルメディアデバイスのモデル</span><span class="sxs-lookup"><span data-stu-id="ed4cf-195">removable media device model</span></span>
- <span data-ttu-id="ed4cf-196">リムーバブル メディア デバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="ed4cf-196">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ed4cf-197">![USB アクティビティ属性へのコピー](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="ed4cf-197">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed4cf-198">次の手順</span><span class="sxs-lookup"><span data-stu-id="ed4cf-198">Next steps</span></span>

<span data-ttu-id="ed4cf-199">エンドポイント DLP の概要を説明しました。次のステップは以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ed4cf-199">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="ed4cf-200">Microsoft エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="ed4cf-200">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="ed4cf-201">Microsoft エンドポイント データ損失防止を使用する</span><span class="sxs-lookup"><span data-stu-id="ed4cf-201">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="ed4cf-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed4cf-202">See also</span></span>

- [<span data-ttu-id="ed4cf-203">Microsoft エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="ed4cf-203">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="ed4cf-204">Microsoft エンドポイント データ損失防止を使用する</span><span class="sxs-lookup"><span data-stu-id="ed4cf-204">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="ed4cf-205">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="ed4cf-205">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="ed4cf-206">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="ed4cf-206">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="ed4cf-207">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="ed4cf-207">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="ed4cf-208">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ed4cf-208">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="ed4cf-209">インサイダー リスク管理</span><span class="sxs-lookup"><span data-stu-id="ed4cf-209">Insider Risk management</span></span>](insider-risk-management.md)
