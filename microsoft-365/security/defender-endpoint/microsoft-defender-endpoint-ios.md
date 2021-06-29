---
title: iOS 用 Microsoft Defender for Endpoint API
ms.reviewer: ''
description: iOS に Microsoft Defender for Endpoint をインストールして使用する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, overview, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cbe2fb39221bd9907a3d690503a392edb019d61b
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194855"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="19511-104">iOS 用 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="19511-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19511-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="19511-105">**Applies to:**</span></span>
- [<span data-ttu-id="19511-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="19511-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19511-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19511-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19511-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="19511-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19511-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="19511-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="19511-110">**Microsoft Defender for Endpoint on iOS** では、Web サイト、電子メール、アプリからのフィッシングや安全でないネットワーク接続に対する保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="19511-110">**Microsoft Defender for Endpoint on iOS** offers protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="19511-111">すべてのアラートは、ウィンドウ内の 1 つのウィンドウからMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="19511-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="19511-112">このポータルにより、セキュリティ チームは、他のプラットフォームと共に、iOS デバイス上の脅威の一元的なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="19511-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="19511-113">iOS で Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19511-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="19511-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="19511-114">Pre-requisites</span></span>

<span data-ttu-id="19511-115">**エンド ユーザー向け**</span><span class="sxs-lookup"><span data-stu-id="19511-115">**For End Users**</span></span>

- <span data-ttu-id="19511-116">アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。</span><span class="sxs-lookup"><span data-stu-id="19511-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="19511-117">「Microsoft [Defender for Endpoint ライセンス要件」を参照してください](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="19511-117">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="19511-118">**登録済みデバイスの場合**: デバイスは、Intune デバイスコンプライアンス ポリシーを適用Intune ポータル サイトアプリを介して登録されます。 [](/mem/intune/user-help/enroll-your-device-in-intune-ios)</span><span class="sxs-lookup"><span data-stu-id="19511-118">**For enrolled devices**: Device(s) are [enrolled](/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="19511-119">これには、エンド ユーザーにライセンスを割り当てるMicrosoft Intune必要があります。</span><span class="sxs-lookup"><span data-stu-id="19511-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="19511-120">Intune ポータル サイト Apple App Store から[ダウンロードできます](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="19511-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="19511-121">Apple では、リダイレクトユーザーがアプリ ストアから他のアプリをダウンロードすることを許可していないので、この手順は、Microsoft Defender for Endpoint アプリにオンボーディングする前にユーザーが行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="19511-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="19511-122">**登録されていないデバイスの場合**: デバイスは、デバイスに登録Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="19511-122">**For unenrolled devices**: Device(s) are registered with Azure Active Directory.</span></span> <span data-ttu-id="19511-123">これには、エンド ユーザーがアプリを介して[サインインMicrosoft Authenticator必要です](https://apps.apple.com/app/microsoft-authenticator/id983156458)。</span><span class="sxs-lookup"><span data-stu-id="19511-123">This requires end user to be signed in through [Microsoft Authenticator app](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

- <span data-ttu-id="19511-124">ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="19511-124">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="19511-125">**管理者向け**</span><span class="sxs-lookup"><span data-stu-id="19511-125">**For Administrators**</span></span>

- <span data-ttu-id="19511-126">ポータルへのアクセスMicrosoft Defender セキュリティ センターします。</span><span class="sxs-lookup"><span data-stu-id="19511-126">Access to the Microsoft Defender Security Center portal.</span></span>

- <span data-ttu-id="19511-127">管理センター [Microsoft エンドポイント マネージャーアクセスして](https://go.microsoft.com/fwlink/?linkid=2109431)、組織の登録済みユーザー グループにアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="19511-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19511-128">Microsoft Intuneは、Microsoft Defender for Endpoint を展開し、Intune で Defender for Endpoint 関連のデバイス コンプライアンス ポリシーを適用する、サポートされている唯一の統合エンドポイント管理 (UEM) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="19511-128">Microsoft Intune is the only supported Unified Endpoint Management (UEM) solution for deploying Microsoft Defender for Endpoint and enforcing Defender for Endpoint related device compliance policies in Intune.</span></span>

<span data-ttu-id="19511-129">**システム要件**</span><span class="sxs-lookup"><span data-stu-id="19511-129">**System Requirements**</span></span>

- <span data-ttu-id="19511-130">iOS 11.0 以上を実行している iOS デバイス。</span><span class="sxs-lookup"><span data-stu-id="19511-130">iOS device running iOS 11.0 and above.</span></span> <span data-ttu-id="19511-131">iPadは、バージョン 1.1.15010101 以降で正式にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="19511-131">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="19511-132">デバイスは、アプリに登録するか、Intune ポータル サイト[を](https://apps.apple.com/us/app/intune-company-portal/id719171358)介して Azure Active Directoryに[Microsoft Authenticator。](https://apps.apple.com/app/microsoft-authenticator/id983156458)</span><span class="sxs-lookup"><span data-stu-id="19511-132">Device is either enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358) or registered with Azure Active Directory through [Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458).</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="19511-133">インストール手順</span><span class="sxs-lookup"><span data-stu-id="19511-133">Installation instructions</span></span>

<span data-ttu-id="19511-134">iOS での Microsoft Defender for Endpoint の展開は、MICROSOFT エンドポイント マネージャー (MEM) を介して行え、監視対象デバイスと教師付きデバイスの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="19511-134">Deployment of Microsoft Defender for Endpoint on iOS can be done via Microsoft Endpoint Manager (MEM) and both supervised and unsupervised devices are supported.</span></span> <span data-ttu-id="19511-135">エンドユーザーは、Apple アプリ ストアからアプリを直接 [インストールすることもできます](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="19511-135">End-users can also directly install the app from the [Apple app store](https://aka.ms/mdatpiosappstore).</span></span>
<span data-ttu-id="19511-136">詳細については [、「Deploy Microsoft Defender for Endpoint on iOS」を参照してください](ios-install.md)。</span><span class="sxs-lookup"><span data-stu-id="19511-136">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="19511-137">リソース</span><span class="sxs-lookup"><span data-stu-id="19511-137">Resources</span></span>

- <span data-ttu-id="19511-138">iOS またはブログの Microsoft Defender [for Endpoint](ios-whatsnew.md) の新機能にアクセスして、今後のリリースについて情報を得 [る](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="19511-138">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="19511-139">アプリ内フィードバック システムまたは SecOps ポータルを通じて [フィードバックを提供する](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="19511-139">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="19511-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="19511-140">Next steps</span></span>

- [<span data-ttu-id="19511-141">iOS での Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="19511-141">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="19511-142">iOS の機能で Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="19511-142">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
