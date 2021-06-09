---
title: Microsoft Compliance Extension の詳細情報
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Microsoft Compliance Extension は、ファイル アクティビティの監視と制御、および保護措置を Google Chrome ブラウザーに拡張します。
ms.openlocfilehash: cf7a3cd2e26f2e7d7a116e4a609f98aeea78be19
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843808"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a><span data-ttu-id="e184c-103">Microsoft Compliance Extension の詳細情報</span><span class="sxs-lookup"><span data-stu-id="e184c-103">Learn about the Microsoft Compliance Extension</span></span>

<span data-ttu-id="e184c-104">[エンドポイントデータ損失防止 (エンドポイント DLP)](endpoint-dlp-learn-about.md) は、Windows 10 デバイスにある機密アイテムについて、[Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) のアクティビティの監視と保護機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="e184c-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="e184c-105">デバイスが、 Microsoft 365 コンプライアンス ソリューションに オンボードすると、機密アイテムを使用してユーザーが行っていることに関する情報が[Activity Explorer](data-classification-activity-explorer.md)に表示され、[DLPポリシー](create-test-tune-dlp-policy.md)を通して、それらのアイテムに保護アクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="e184c-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="e184c-106">Microsoft Compliance Extension を Windows 10 デバイスにインストールすると、ユーザーが Google Chrome を使用して機密アイテムにアクセスしようとしたり、クラウド サービスにアップロードしようとしたりするのを監視し、DLP によって保護措置を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="e184c-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="e184c-107">監視と対処が必要なアクティビティ</span><span class="sxs-lookup"><span data-stu-id="e184c-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="e184c-108">Microsoft Compliance Extension を使用すると、Windows 10 を実行しているデバイスでユーザーが機密アイテムに行っている次のようなアクティビティを監査および管理できます。</span><span class="sxs-lookup"><span data-stu-id="e184c-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="e184c-109">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="e184c-109">activity</span></span> |<span data-ttu-id="e184c-110">説明</span><span class="sxs-lookup"><span data-stu-id="e184c-110">description</span></span>  | <span data-ttu-id="e184c-111">サポート対象のポリシー アクション</span><span class="sxs-lookup"><span data-stu-id="e184c-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="e184c-112">ファイルがクラウドにコピーされました</span><span class="sxs-lookup"><span data-stu-id="e184c-112">file copied to cloud</span></span>  | <span data-ttu-id="e184c-113">ユーザーが制限されたサービス ドメインに機密アイテムをアップロードしようとした場合、Chrome ブラウザーを介してアイテムにアクセスしようとした場合に検出します</span><span class="sxs-lookup"><span data-stu-id="e184c-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="e184c-114">監査、ブロック</span><span class="sxs-lookup"><span data-stu-id="e184c-114">audit, block</span></span>|
|<span data-ttu-id="e184c-115">ファイルが印刷されました</span><span class="sxs-lookup"><span data-stu-id="e184c-115">file printed</span></span>  |<span data-ttu-id="e184c-116">ユーザーが Chrome ブラウザーで開いている機密性の高いアイテムをローカルまたはネットワークプリンタに印刷しようとした場合に検出します</span><span class="sxs-lookup"><span data-stu-id="e184c-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="e184c-117">上書き、ブロックの監査、ブロック</span><span class="sxs-lookup"><span data-stu-id="e184c-117">audit, block with override, block</span></span>|
|<span data-ttu-id="e184c-118">ファイルがクリップボードにコピーされました</span><span class="sxs-lookup"><span data-stu-id="e184c-118">file copied to clipboard</span></span> |<span data-ttu-id="e184c-119">ユーザーが Chrome ブラウザーで表示中の機密アイテムから情報をコピーし、他のアプリ、プロセス、またはアイテムに貼り付けようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="e184c-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="e184c-120">上書き、ブロックの監査、ブロック</span><span class="sxs-lookup"><span data-stu-id="e184c-120">audit, block with override, block</span></span>|
|<span data-ttu-id="e184c-121">ファイルがリムーバブル ストレージにコピーされました</span><span class="sxs-lookup"><span data-stu-id="e184c-121">file copied to removable storage</span></span>    | <span data-ttu-id="e184c-122">ユーザーが、機密アイテムや Chrome ブラウザーで開いている機密アイテムの情報をリムーバブルメディアや USB デバイスにコピーしようとした場合に検出します</span><span class="sxs-lookup"><span data-stu-id="e184c-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="e184c-123">上書き、ブロックの監査、ブロック</span><span class="sxs-lookup"><span data-stu-id="e184c-123">audit, block with override, block</span></span>|
|<span data-ttu-id="e184c-124">ファイルがネットワーク共有にコピーされました</span><span class="sxs-lookup"><span data-stu-id="e184c-124">file copied to network share</span></span>  |<span data-ttu-id="e184c-125">ユーザーが、機密アイテムやその情報をネットワーク共有やマッピングされたネットワーク ドライブにコピーしようとした場合に検出します。</span><span class="sxs-lookup"><span data-stu-id="e184c-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="e184c-126">上書き、ブロックの監査、ブロック</span><span class="sxs-lookup"><span data-stu-id="e184c-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="e184c-127">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="e184c-127">Deployment process</span></span>
1. [<span data-ttu-id="e184c-128">エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="e184c-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="e184c-129">Windows 10 デバイスのオンボード ツールと各種方法</span><span class="sxs-lookup"><span data-stu-id="e184c-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="e184c-130">Windows 10 デバイスに拡張機能をインストール</span><span class="sxs-lookup"><span data-stu-id="e184c-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="e184c-131">クラウド サービスへのアップロードや許可されていないブラウザーからのアクセスを制限する [DLP ポリシーを作成または編集](create-test-tune-dlp-policy.md)し、Windows 10 デバイスに適用します。</span><span class="sxs-lookup"><span data-stu-id="e184c-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="e184c-132">次の手順</span><span class="sxs-lookup"><span data-stu-id="e184c-132">Next steps</span></span>

<span data-ttu-id="e184c-133">導入手順とシナリオの詳細については、「[Microsoft Compliance Extension を開始する](dlp-chrome-get-started.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e184c-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="e184c-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="e184c-134">See also</span></span>

- [<span data-ttu-id="e184c-135">Microsoft Compliance Extension を開始する</span><span class="sxs-lookup"><span data-stu-id="e184c-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="e184c-136">Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報</span><span class="sxs-lookup"><span data-stu-id="e184c-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="e184c-137">Microsoft エンドポイント データ損失防止を開始する</span><span class="sxs-lookup"><span data-stu-id="e184c-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="e184c-138">Microsoft エンドポイント データ損失防止を使用する</span><span class="sxs-lookup"><span data-stu-id="e184c-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="e184c-139">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="e184c-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="e184c-140">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="e184c-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="e184c-141">Activity Explorer を使い始める</span><span class="sxs-lookup"><span data-stu-id="e184c-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="e184c-142">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e184c-142">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="e184c-143">インサイダー リスク管理</span><span class="sxs-lookup"><span data-stu-id="e184c-143">Insider Risk management</span></span>](insider-risk-management.md)
