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
ms.openlocfilehash: 6787add3ef8b2d6ded22bd05c0ff9658c4b7fbfc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922083"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="d771a-103">Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d771a-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="d771a-104">Microsoft 以外のクラウド アプリに対するデータ損失防止 (DLP) ポリシーは、Microsoft 365 DLP スイートの機能の一部です。これらの機能を使用すると、Microsoft 365 サービス全体で機密性の高いアイテムを検出して保護できます。</span><span class="sxs-lookup"><span data-stu-id="d771a-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="d771a-105">すべての Microsoft DLP 製品の詳細については、「データ損失防止の [概要」を参照してください](./data-loss-prevention-policies.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="d771a-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](./data-loss-prevention-policies.md?view=o365-worldwide).</span></span>

<span data-ttu-id="d771a-106">DLP ポリシーを Microsoft 以外のクラウド アプリに使用して、機密アイテムが Microsoft 以外のクラウド アプリを介して使用および共有される場合の監視と検出を行います。</span><span class="sxs-lookup"><span data-stu-id="d771a-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="d771a-107">これらのポリシーを使用すると、それらのポリシーが正しく使用され保護されていることを確認するために必要な可視性と制御が提供され、危険な動作が危険にさらされるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d771a-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d771a-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="d771a-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="d771a-109">SKU /サブスクリプションライセンス</span><span class="sxs-lookup"><span data-stu-id="d771a-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="d771a-110">DLP ポリシーを Microsoft 以外のクラウド アプリに使用する前に [、Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) サブスクリプションとアドオンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d771a-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="d771a-111">この機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンが必要です。</span><span class="sxs-lookup"><span data-stu-id="d771a-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="d771a-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="d771a-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="d771a-113">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="d771a-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="d771a-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="d771a-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="d771a-115">クラウド アプリのセキュリティ環境を準備する</span><span class="sxs-lookup"><span data-stu-id="d771a-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="d771a-116">Microsoft 以外のクラウド アプリに対する DLP ポリシーでは、Cloud App Security DLP 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="d771a-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="d771a-117">それを使用するには、Cloud App Security 環境を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d771a-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="d771a-118">手順については、「アプリの即時表示、保護、ガバナンスアクションの設定 [」を参照してください](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)。</span><span class="sxs-lookup"><span data-stu-id="d771a-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="d771a-119">Microsoft 以外のクラウド アプリを接続する</span><span class="sxs-lookup"><span data-stu-id="d771a-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="d771a-120">特定の Microsoft 以外のクラウド アプリに DLP ポリシーを使用するには、アプリを Cloud App Security に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d771a-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="d771a-121">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d771a-121">For information, see:</span></span>

- [<span data-ttu-id="d771a-122">Connect Box</span><span class="sxs-lookup"><span data-stu-id="d771a-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d771a-123">Dropbox の接続</span><span class="sxs-lookup"><span data-stu-id="d771a-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d771a-124">Connect G-Suite</span><span class="sxs-lookup"><span data-stu-id="d771a-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d771a-125">Salesforce の接続</span><span class="sxs-lookup"><span data-stu-id="d771a-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="d771a-126">Cisco Webex の接続</span><span class="sxs-lookup"><span data-stu-id="d771a-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="d771a-127">クラウド アプリを Cloud App Security に接続した後、Microsoft 365 DLP ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d771a-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="d771a-128">Microsoft Cloud App Security を使用して、Microsoft クラウド アプリに DLP ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d771a-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="d771a-129">ただし、Microsoft 365 を使用して、Microsoft クラウド アプリに対する DLP ポリシーを作成および管理する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d771a-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="d771a-130">Microsoft 以外のクラウド アプリに DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d771a-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="d771a-131">DLP ポリシーの場所を選択する場合は **、Microsoft Cloud App Security の場所をオン** にしてください。</span><span class="sxs-lookup"><span data-stu-id="d771a-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="d771a-132">特定のアプリまたはインスタンスを選択するには、[インスタンスの選択] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d771a-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="d771a-133">インスタンスを選択しない場合、ポリシーは Microsoft Cloud App Security テナント内のすべての接続アプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="d771a-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![ポリシーを適用する場所](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US と Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="d771a-136">サポートされている Microsoft 以外のクラウド アプリごとにさまざまなアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d771a-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="d771a-137">アプリごとに異なるアクションがあります (クラウド アプリ API によって異なります)。</span><span class="sxs-lookup"><span data-stu-id="d771a-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![ルールを作成する](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="d771a-139">DLP ポリシーでルールを作成する場合は、Microsoft 以外のクラウド アプリのアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d771a-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="d771a-140">サード パーティ製アプリを制限するには、[サードパーティ 製アプリの **制限] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d771a-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![サード パーティ製アプリの制限](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="d771a-142">DLP ポリシーの作成と構成の詳細については、「テストの作成と DLP ポリシー [の調整」を参照してください](./create-test-tune-dlp-policy.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="d771a-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="d771a-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="d771a-143">See Also</span></span>

- [<span data-ttu-id="d771a-144">DLP ポリシーのテストと調整を作成する</span><span class="sxs-lookup"><span data-stu-id="d771a-144">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="d771a-145">DLP の既定ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="d771a-145">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="d771a-146">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="d771a-146">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)