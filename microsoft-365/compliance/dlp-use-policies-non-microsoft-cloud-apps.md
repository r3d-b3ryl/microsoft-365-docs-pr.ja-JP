---
title: Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する (プレビュー)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 以外のクラウド アプリで dlp ポリシーを使用する方法について説明します。
ms.openlocfilehash: d4c5170cab01b1ca22701b13c7afbf4f2e0ba7da
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114135"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="1605c-103">Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1605c-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="1605c-104">Microsoft 以外のクラウド アプリに対するデータ損失防止 (DLP) ポリシーは、DLP Microsoft 365機能の一部です。これらの機能を使用すると、セキュリティ サービス全体で機密アイテムをMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="1605c-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="1605c-105">すべての Microsoft DLP 製品の詳細については、「データ損失防止について」 [を参照してください](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="1605c-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="1605c-106">DLP ポリシーを Microsoft 以外のクラウド アプリに使用して、機密アイテムが Microsoft 以外のクラウド アプリを介して使用および共有される場合の監視と検出を行います。</span><span class="sxs-lookup"><span data-stu-id="1605c-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="1605c-107">これらのポリシーを使用すると、それらのポリシーが正しく使用され保護されていることを確認するために必要な可視性と制御が提供され、危険な動作が危険にさらされるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1605c-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1605c-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="1605c-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="1605c-109">SKU /サブスクリプションライセンス</span><span class="sxs-lookup"><span data-stu-id="1605c-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="1605c-110">DLP ポリシーを Microsoft 以外のクラウド アプリに使用する前に、サブスクリプションMicrosoft 365[アドオン](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1605c-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="1605c-111">この機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="1605c-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="1605c-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1605c-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="1605c-113">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="1605c-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="1605c-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="1605c-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="1605c-115">環境をCloud App Securityする</span><span class="sxs-lookup"><span data-stu-id="1605c-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="1605c-116">Microsoft 以外のクラウド アプリに対する DLP ポリシーでは、DLP Cloud App Securityを使用します。</span><span class="sxs-lookup"><span data-stu-id="1605c-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="1605c-117">この環境を使用するには、環境を準備Cloud App Security必要があります。</span><span class="sxs-lookup"><span data-stu-id="1605c-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="1605c-118">手順については、「アプリの即時表示、保護、ガバナンスアクションの設定 [」を参照してください](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。</span><span class="sxs-lookup"><span data-stu-id="1605c-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="1605c-119">Connect Microsoft 以外のクラウド アプリを使用する</span><span class="sxs-lookup"><span data-stu-id="1605c-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="1605c-120">DLP ポリシーを Microsoft 以外の特定のクラウド アプリに使用するには、アプリをアプリに接続する必要Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="1605c-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="1605c-121">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1605c-121">For information, see:</span></span>

- [<span data-ttu-id="1605c-122">ConnectBox</span><span class="sxs-lookup"><span data-stu-id="1605c-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1605c-123">Connect Dropbox</span><span class="sxs-lookup"><span data-stu-id="1605c-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1605c-124">ConnectG-Suite</span><span class="sxs-lookup"><span data-stu-id="1605c-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1605c-125">ConnectSalesforce</span><span class="sxs-lookup"><span data-stu-id="1605c-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1605c-126">ConnectCisco Webex</span><span class="sxs-lookup"><span data-stu-id="1605c-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="1605c-127">クラウド アプリをクラウド アプリに接続Cloud App Security、クラウド アプリMicrosoft 365 DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1605c-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="1605c-128">また、Microsoft クラウド アプリに DLP Microsoft Cloud App Securityを作成するために、このポリシーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1605c-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="1605c-129">ただし、Microsoft クラウド アプリに対して DLP Microsoft 365を作成および管理するには、このポリシーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1605c-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="1605c-130">Microsoft 以外のクラウド アプリに DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="1605c-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="1605c-131">DLP ポリシーの場所を選択する場合は、その場所 **Microsoft Cloud App Securityします**。</span><span class="sxs-lookup"><span data-stu-id="1605c-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="1605c-132">特定のアプリまたはインスタンスを選択するには、[インスタンスの選択] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1605c-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="1605c-133">インスタンスを選択しない場合、ポリシーは、テナント内のすべての接続アプリMicrosoft Cloud App Securityします。</span><span class="sxs-lookup"><span data-stu-id="1605c-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![ポリシーを適用する場所](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US と Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="1605c-136">サポートされている Microsoft 以外のクラウド アプリごとにさまざまなアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1605c-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="1605c-137">アプリごとに異なるアクションがあります (クラウド アプリ API によって異なります)。</span><span class="sxs-lookup"><span data-stu-id="1605c-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![ルールを作成する](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="1605c-139">DLP ポリシーでルールを作成する場合は、Microsoft 以外のクラウド アプリのアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1605c-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="1605c-140">サード パーティ製アプリを制限するには、[サードパーティ 製アプリの **制限] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="1605c-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![サード パーティ製アプリの制限](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="1605c-142">DLP ポリシーの作成と構成の詳細については、「テストの作成と DLP ポリシー [の調整」を参照してください](./create-test-tune-dlp-policy.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="1605c-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="1605c-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="1605c-143">See Also</span></span>

- [<span data-ttu-id="1605c-144">DLP ポリシーのテストと調整を作成する</span><span class="sxs-lookup"><span data-stu-id="1605c-144">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="1605c-145">DLP の既定ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="1605c-145">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="1605c-146">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="1605c-146">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)