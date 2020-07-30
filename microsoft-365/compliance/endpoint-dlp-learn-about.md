---
title: 'Microsoft 365 のエンドポイントのデータ損失防止について学ぶ (プレビュー) '
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
- SPO_Content
search.appverid:
- MET150
description: 'Microsoft 365 エンドポイントのデータ損失防止は、、ファイルアクティビティを監視し、それらのファイルの保護アクションをエンドポイントに拡張します。 Microsoft 365 のコンプライアンスソリューションでファイルが表示されます '
ms.openlocfilehash: 2423f45fefe994fbaf5704074c49ce862a59340e
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517498"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="2e449-104">Microsoft 365 のエンドポイントのデータ損失防止について学ぶ (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="2e449-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="2e449-105">Microsoft 365 のデータ損失防止 (DLP) を使用すると、機密があると判断されたアイテムに対して、発生しているアクションを監視し、それらのアイテムの意図しない共有を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="2e449-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="2e449-106">DLP の詳細については、「[データ損失防止ポリシーの概要](data-loss-prevention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e449-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="2e449-107">**エンドポイントデータ損失防止** (エンドポイント DLP) は、Windows 10 デバイスにある機密アイテムについて、DLP のアクティビティの監視と保護機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="2e449-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="2e449-108">デバイスが、 Microsoft 365 コンプライアンス ソリューションに オンボードすると、機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="2e449-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="2e449-109">監視と対処が必要なエンドポイントのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="2e449-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="2e449-110">Microsoft エンドポイント DLP を使用すると、Windows 10 を実行しているデバイスでユーザーが機密アイテムに行っている次のようなアクティビティを監査および管理できます。　　　</span><span class="sxs-lookup"><span data-stu-id="2e449-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="2e449-111">保持されるデータには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e449-111">This includes:</span></span>


|<span data-ttu-id="2e449-112">アイテムのアクティビティ</span><span class="sxs-lookup"><span data-stu-id="2e449-112">activity on item</span></span> |<span data-ttu-id="2e449-113">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="2e449-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="2e449-114">作成済み</span><span class="sxs-lookup"><span data-stu-id="2e449-114">created</span></span>    | <span data-ttu-id="2e449-115">監査可能</span><span class="sxs-lookup"><span data-stu-id="2e449-115">auditable</span></span>      |
|<span data-ttu-id="2e449-116">名前の変更</span><span class="sxs-lookup"><span data-stu-id="2e449-116">renamed</span></span>    |  <span data-ttu-id="2e449-117">監査可能</span><span class="sxs-lookup"><span data-stu-id="2e449-117">auditable</span></span>       |
|<span data-ttu-id="2e449-118">リムーバブルメディアへのコピーと作成</span><span class="sxs-lookup"><span data-stu-id="2e449-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="2e449-119">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="2e449-119">auditable and restrictable</span></span>|
|<span data-ttu-id="2e449-120">\\my-server\fileshare などのネットワーク共有にコピーされます</span><span class="sxs-lookup"><span data-stu-id="2e449-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="2e449-121">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="2e449-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="2e449-122">印刷済み</span><span class="sxs-lookup"><span data-stu-id="2e449-122">printed</span></span> |    <span data-ttu-id="2e449-123">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="2e449-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="2e449-124">Chromium Edge 経由でクラウドにコピー</span><span class="sxs-lookup"><span data-stu-id="2e449-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="2e449-125">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="2e449-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="2e449-126">許可されていないアプリによってアクセスされました</span><span class="sxs-lookup"><span data-stu-id="2e449-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="2e449-127">監査可能/制限可能</span><span class="sxs-lookup"><span data-stu-id="2e449-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="2e449-128">エンドポイント DLP との違い</span><span class="sxs-lookup"><span data-stu-id="2e449-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="2e449-129">エンドポイント DLP を掘り下げる前に知っておく必要がある追加の概念がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="2e449-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="2e449-130">デバイス管理を有効にする</span><span class="sxs-lookup"><span data-stu-id="2e449-130">Enabling Device management</span></span>

<span data-ttu-id="2e449-131">デバイス管理は、デバイスからテレメトリを収集できる機能です。これは、エンドポイント DLP や [インサイダー リスク管理](insider-risk-management.md)などの 365 Microsoft のコンプライアンスソリューションに導入する機能です。</span><span class="sxs-lookup"><span data-stu-id="2e449-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="2e449-132">DLP ポリシーの場所として使用するすべてのデバイスをオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e449-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![デバイス管理を有効にする](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="2e449-134">オンボードとオフボードは、デバイス管理センターからダウンロードするスクリプトを通して処理されます。</span><span class="sxs-lookup"><span data-stu-id="2e449-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="2e449-135">センターには、次の展開方法ごとにカスタムスクリプトがあります：</span><span class="sxs-lookup"><span data-stu-id="2e449-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="2e449-136">ローカルスクリプト (最大10台のマシン)</span><span class="sxs-lookup"><span data-stu-id="2e449-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="2e449-137">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="2e449-137">Group policy</span></span>
- <span data-ttu-id="2e449-138">System Center Configuration Manager （ バージョン 1610以降 ）</span><span class="sxs-lookup"><span data-stu-id="2e449-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="2e449-139">Mobile Device Management/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2e449-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="2e449-140">非永続的マシン用の VDI のオンボードスクリプト</span><span class="sxs-lookup"><span data-stu-id="2e449-140">VDI onboarding scripts for non-persistent machines</span></span>

![デバイスオンボーディングページ](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="2e449-142">デバイスをオンボードにするには、[Microsoft 365 エンドポイント DLPの使用を開始する](endpoint-dlp-getting-started.md)の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e449-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="2e449-143">[Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)を通して、デバイスをオンボーディングしている場合、これらのデバイスは自動的にデバイスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e449-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![デバイスリストを管理する](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="2e449-145">エンドポイント DLP データの表示</span><span class="sxs-lookup"><span data-stu-id="2e449-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="2e449-146">エンドポイント DLP は、MIME タイプに基づいてアクティビティを監視するため、ファイル拡張子が変更された場合でもアクティビティがキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e449-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="2e449-147">パブリックプレビューでは、すべてが監視されます:</span><span class="sxs-lookup"><span data-stu-id="2e449-147">At public preview it watches all:</span></span>

- <span data-ttu-id="2e449-148">Word ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-148">Word files</span></span>
- <span data-ttu-id="2e449-149">PowerPoint ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-149">PowerPoint files</span></span>
- <span data-ttu-id="2e449-150">Excel ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-150">Excel files</span></span>
- <span data-ttu-id="2e449-151">PDF ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-151">PDF files</span></span>
- <span data-ttu-id="2e449-152">.csv ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-152">.csv files</span></span>
- <span data-ttu-id="2e449-153">.tsv ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-153">.tsv files</span></span>
- <span data-ttu-id="2e449-154">c ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-154">c files</span></span>
- <span data-ttu-id="2e449-155">クラス ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-155">class files</span></span>
- <span data-ttu-id="2e449-156">cpp ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-156">cpp files</span></span>
- <span data-ttu-id="2e449-157">cs ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-157">cs files</span></span>
- <span data-ttu-id="2e449-158">h ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-158">h files</span></span>
- <span data-ttu-id="2e449-159">java ファイル</span><span class="sxs-lookup"><span data-stu-id="2e449-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="2e449-160">.txt とソースコードのファイルは既定では監査されません。 DLP は、適用されたポリシーに対して DLP を評価し、それに従って、ユーザーのアクションを監査またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="2e449-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="2e449-161">デバイスがオンボードされると、場所としてデバイスを使用する DLP ポリシーを構成し、展開する前でも、監査されたアクティビティに関する情報がアクティビティエクスプローラーに流れます。</span><span class="sxs-lookup"><span data-stu-id="2e449-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![アクティビティ エクスプローラーでのエンドポイント dlp イベント](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="2e449-163">エンドポイント DLP は、監査済みアクティビティに関する広範囲にわたる情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="2e449-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="2e449-164">たとえば、ファイルがリムーバブル USB メディアにコピーされた場合、アクティビティの詳細に次の属性が表示されます：</span><span class="sxs-lookup"><span data-stu-id="2e449-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="2e449-165">アクティビティの種類</span><span class="sxs-lookup"><span data-stu-id="2e449-165">activity type</span></span>
- <span data-ttu-id="2e449-166">クライアント IP</span><span class="sxs-lookup"><span data-stu-id="2e449-166">client IP</span></span>
- <span data-ttu-id="2e449-167">対象ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="2e449-167">target file path</span></span>
- <span data-ttu-id="2e449-168">発生したタイムスタンプ</span><span class="sxs-lookup"><span data-stu-id="2e449-168">happened timestamp</span></span>
- <span data-ttu-id="2e449-169">ファイル名</span><span class="sxs-lookup"><span data-stu-id="2e449-169">file name</span></span>
- <span data-ttu-id="2e449-170">ユーザー</span><span class="sxs-lookup"><span data-stu-id="2e449-170">user</span></span>
- <span data-ttu-id="2e449-171">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="2e449-171">file extension</span></span>
- <span data-ttu-id="2e449-172">ファイル サイズ</span><span class="sxs-lookup"><span data-stu-id="2e449-172">file size</span></span>
- <span data-ttu-id="2e449-173">機密情報の種類（該当する場合）</span><span class="sxs-lookup"><span data-stu-id="2e449-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="2e449-174">sha1 値</span><span class="sxs-lookup"><span data-stu-id="2e449-174">sha1 value</span></span>
- <span data-ttu-id="2e449-175">sha256 値</span><span class="sxs-lookup"><span data-stu-id="2e449-175">sha256 value</span></span>
- <span data-ttu-id="2e449-176">以前のファイル名</span><span class="sxs-lookup"><span data-stu-id="2e449-176">previous file name</span></span>
- <span data-ttu-id="2e449-177">場所</span><span class="sxs-lookup"><span data-stu-id="2e449-177">location</span></span>
- <span data-ttu-id="2e449-178">親</span><span class="sxs-lookup"><span data-stu-id="2e449-178">parent</span></span>
- <span data-ttu-id="2e449-179">FilePath</span><span class="sxs-lookup"><span data-stu-id="2e449-179">filepath</span></span>
- <span data-ttu-id="2e449-180">ソースの場所の種類</span><span class="sxs-lookup"><span data-stu-id="2e449-180">source location type</span></span>
- <span data-ttu-id="2e449-181">platform</span><span class="sxs-lookup"><span data-stu-id="2e449-181">platform</span></span>
- <span data-ttu-id="2e449-182">デバイス名</span><span class="sxs-lookup"><span data-stu-id="2e449-182">device name</span></span>
- <span data-ttu-id="2e449-183">場所の宛先の種類</span><span class="sxs-lookup"><span data-stu-id="2e449-183">destination location type</span></span>
- <span data-ttu-id="2e449-184">コピーを実行したアプリケーション</span><span class="sxs-lookup"><span data-stu-id="2e449-184">application that performed the copy</span></span>
- <span data-ttu-id="2e449-185">MDATP デバイス ID (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="2e449-185">MDATP device ID (if applicable)</span></span>
- <span data-ttu-id="2e449-186">リムーバブルメディアデバイスの製造元</span><span class="sxs-lookup"><span data-stu-id="2e449-186">removable media device manufacturer</span></span>
- <span data-ttu-id="2e449-187">リムーバブルメディアデバイスのモデル</span><span class="sxs-lookup"><span data-stu-id="2e449-187">removable media device model</span></span>
- <span data-ttu-id="2e449-188">リムーバブルメディアデバイスのシリアル番号</span><span class="sxs-lookup"><span data-stu-id="2e449-188">removable media device serial number</span></span>

![usb アクティビティ属性にコピーする](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="2e449-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="2e449-190">Next steps</span></span>

<span data-ttu-id="2e449-191">ここまでエンドポイント DLP について学びましたので、次のステップの手順は以下になります：</span><span class="sxs-lookup"><span data-stu-id="2e449-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="2e449-192">Microsoft Endpoint データ損失防止 (プレビュー) を開始する</span><span class="sxs-lookup"><span data-stu-id="2e449-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="2e449-193">エンドポイント データ損失防止 (プレビュー) を使用する</span><span class="sxs-lookup"><span data-stu-id="2e449-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="2e449-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e449-194">See also</span></span>

- [<span data-ttu-id="2e449-195">Microsoft Endpoint データ損失防止 (プレビュー) を開始する</span><span class="sxs-lookup"><span data-stu-id="2e449-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="2e449-196">エンドポイント データ損失防止 (プレビュー) を使用する</span><span class="sxs-lookup"><span data-stu-id="2e449-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="2e449-197">データ損失防止の概要</span><span class="sxs-lookup"><span data-stu-id="2e449-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="2e449-198">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="2e449-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="2e449-199">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="2e449-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="2e449-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) </span><span class="sxs-lookup"><span data-stu-id="2e449-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="2e449-201">インサイダー リスク管理</span><span class="sxs-lookup"><span data-stu-id="2e449-201">Insider Risk management</span></span>](insider-risk-management.md)