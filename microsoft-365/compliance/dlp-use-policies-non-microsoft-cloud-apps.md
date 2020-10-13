---
title: Microsoft 以外のクラウドアプリのデータ損失防止ポリシーを使用する (プレビュー)
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
description: Microsoft 以外のクラウドアプリで dlp ポリシーを使用する方法について説明します。
ms.openlocfilehash: dd5a7a4bc0725d0785daec6b7635047cd91f20a2
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422759"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="f3c9b-103">Microsoft 以外のクラウドアプリのデータ損失防止ポリシーを使用する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f3c9b-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="f3c9b-104">Microsoft 以外のクラウドアプリに対するデータ損失防止 (DLP) ポリシーは、Microsoft 365 DLP スイートの機能の一部です。これらの機能を使用すると、Microsoft 365 サービス全体の機密アイテムを検出して保護することができます。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="f3c9b-105">すべての Microsoft DLP オファーリングの詳細については、「 [データ損失防止の概要](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="f3c9b-106">Microsoft 以外のクラウドアプリで DLP ポリシーを使用すると、機密性の高いアイテムが使用されているときを監視および検出したり、Microsoft 以外のクラウドアプリで共有したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="f3c9b-107">これらのポリシーを使用すると、それらが適切に使用および保護されていることを確認するために必要な可視性と制御が提供されます。また、それらのポリシーを侵害する可能性のある動作を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f3c9b-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="f3c9b-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="f3c9b-109">SKU /サブスクリプションライセンス</span><span class="sxs-lookup"><span data-stu-id="f3c9b-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="f3c9b-110">Microsoft 以外のクラウドアプリへの DLP ポリシーの使用を開始する前に、 [microsoft 365 のサブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) とアドオンを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="f3c9b-111">この機能にアクセスして使用するには、次のいずれかのサブスクリプションまたはアドオンを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="f3c9b-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="f3c9b-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="f3c9b-113">Microsoft 365 E5 Compliance </span><span class="sxs-lookup"><span data-stu-id="f3c9b-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="f3c9b-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="f3c9b-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="f3c9b-115">クラウドアプリのセキュリティ環境を準備する</span><span class="sxs-lookup"><span data-stu-id="f3c9b-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="f3c9b-116">Microsoft 以外のクラウドアプリへの DLP ポリシーは、Cloud App Security DLP 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="f3c9b-117">これを使用するには、Cloud App Security 環境を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="f3c9b-118">手順については、「 [Set isntant visibility, protection, and ガバナンスの操作](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-118">For instructions, see [Set isntant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="f3c9b-119">Microsoft 以外のクラウドアプリを接続する</span><span class="sxs-lookup"><span data-stu-id="f3c9b-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="f3c9b-120">特定の Microsoft 以外のクラウドアプリに DLP ポリシーを使用するには、アプリが Cloud App Security に接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="f3c9b-121">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-121">For information, see:</span></span>

- <span data-ttu-id="f3c9b-122">[[接続] ボックス](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="f3c9b-122">[Connect Box](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)</span></span>
- [<span data-ttu-id="f3c9b-123">接続ドロップボックス</span><span class="sxs-lookup"><span data-stu-id="f3c9b-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="f3c9b-124">Connect G スイート</span><span class="sxs-lookup"><span data-stu-id="f3c9b-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="f3c9b-125">Salesforce の接続</span><span class="sxs-lookup"><span data-stu-id="f3c9b-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="f3c9b-126">Cisco Webex との接続</span><span class="sxs-lookup"><span data-stu-id="f3c9b-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="f3c9b-127">クラウドアプリを Cloud App Security に接続した後、それらに対して Microsoft 365 DLP ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="f3c9b-128">Microsoft Cloud App Security を使用して、Microsoft クラウドアプリに DLP ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="f3c9b-129">ただし、microsoft 365 を使用して、Microsoft クラウドアプリに DLP ポリシーを作成して管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="f3c9b-130">Microsoft 以外のクラウドアプリに DLP ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f3c9b-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="f3c9b-131">DLP ポリシーの場所を選択する場合は、 **Microsoft Cloud App Security** の場所を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="f3c9b-132">特定のアプリまたはインスタンスを選択するには、[ **インスタンスの選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="f3c9b-133">インスタンスを選択しない場合、ポリシーは Microsoft Cloud App Security テナント内の接続されているすべてのアプリを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![ポリシーを適用する場所](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![ボックス-US および Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="f3c9b-136">Microsoft 以外のサポートされているすべてのクラウドアプリに対してさまざまなアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="f3c9b-137">すべてのアプリに対して、さまざまなアクションがあります (クラウドアプリ API によって異なります)。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![ルールを作成する](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="f3c9b-139">DLP ポリシーでルールを作成するときは、Microsoft 以外のクラウドアプリ用のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="f3c9b-140">サードパーティ製アプリを制限するには、[ **サードパーティ製アプリを制限**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![サードパーティ製アプリを制限する](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="f3c9b-142">DLP ポリシーの作成および構成の詳細については、「 [Create test and チューン a dlp policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3c9b-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3c9b-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3c9b-143">See Also</span></span>

- [<span data-ttu-id="f3c9b-144">DLP ポリシーをテストして調整する</span><span class="sxs-lookup"><span data-stu-id="f3c9b-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="f3c9b-145">DLP の既定ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="f3c9b-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="f3c9b-146">テンプレートからの DLP ポリシーの作成</span><span class="sxs-lookup"><span data-stu-id="f3c9b-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
