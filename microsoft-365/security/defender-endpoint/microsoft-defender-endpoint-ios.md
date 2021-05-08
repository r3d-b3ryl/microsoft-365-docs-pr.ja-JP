---
title: iOS 用 Microsoft Defender for Endpoint API
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
ms.openlocfilehash: 3d9dd871edba29ec6119329f98ada990abad6e8d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246418"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="98ab5-104">iOS 用 Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="98ab5-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="98ab5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="98ab5-105">**Applies to:**</span></span>
- [<span data-ttu-id="98ab5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="98ab5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98ab5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98ab5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="98ab5-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="98ab5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="98ab5-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="98ab5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="98ab5-110">**Microsoft Defender for Endpoint on iOS** では、Web サイト、電子メール、アプリからのフィッシングや安全でないネットワーク接続に対する保護が提供されます。</span><span class="sxs-lookup"><span data-stu-id="98ab5-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="98ab5-111">すべてのアラートは、ウィンドウ内の 1 つのウィンドウからMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="98ab5-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="98ab5-112">このポータルにより、セキュリティ チームは、他のプラットフォームと共に、iOS デバイス上の脅威の一元的なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="98ab5-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="98ab5-113">iOS で Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98ab5-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="98ab5-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="98ab5-114">Pre-requisites</span></span>

<span data-ttu-id="98ab5-115">**エンド ユーザー向け**</span><span class="sxs-lookup"><span data-stu-id="98ab5-115">**For End Users**</span></span>

- <span data-ttu-id="98ab5-116">アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。</span><span class="sxs-lookup"><span data-stu-id="98ab5-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="98ab5-117">「Microsoft [Defender for Endpoint ライセンス要件」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="98ab5-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="98ab5-118">デバイスは、Intune[デバイス](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios)コンプライアンス ポリシーを適用Intune ポータル サイトアプリを介して登録されます。</span><span class="sxs-lookup"><span data-stu-id="98ab5-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="98ab5-119">これには、エンド ユーザーにライセンスを割り当てるMicrosoft Intune必要があります。</span><span class="sxs-lookup"><span data-stu-id="98ab5-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="98ab5-120">Intune ポータル サイト Apple App Store から[ダウンロードできます](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="98ab5-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="98ab5-121">Apple では、リダイレクトユーザーがアプリ ストアから他のアプリをダウンロードすることを許可していないので、この手順は、Microsoft Defender for Endpoint アプリにオンボーディングする前にユーザーが行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="98ab5-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="98ab5-122">ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="98ab5-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="98ab5-123">**管理者向け**</span><span class="sxs-lookup"><span data-stu-id="98ab5-123">**For Administrators**</span></span>

- <span data-ttu-id="98ab5-124">ポータルへのアクセスMicrosoft Defender セキュリティ センターします。</span><span class="sxs-lookup"><span data-stu-id="98ab5-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98ab5-125">Microsoft Intuneは、iOS に Microsoft Defender for Endpoint を展開する場合にサポートされている唯一のモバイル デバイス管理 (MDM) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="98ab5-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="98ab5-126">現在、Intune で iOS 関連のデバイス コンプライアンス ポリシーで Defender for Endpoint を適用する場合は、現在登録されているデバイスだけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="98ab5-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint on iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="98ab5-127">管理センター [Microsoft エンドポイント マネージャーアクセスして](https://go.microsoft.com/fwlink/?linkid=2109431)、組織の登録済みユーザー グループにアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="98ab5-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="98ab5-128">**ネットワーク要件**</span><span class="sxs-lookup"><span data-stu-id="98ab5-128">**Network Requirements**</span></span>
- <span data-ttu-id="98ab5-129">Microsoft Defender for Endpoint on iOS がネットワークに接続されている場合に機能するには[、Microsoft Defender for Endpoint](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)サービス URL へのアクセスを有効にするようにファイアウォール/プロキシを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98ab5-129">For Microsoft Defender for Endpoint on iOS to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span></span>

<span data-ttu-id="98ab5-130">**システム要件**</span><span class="sxs-lookup"><span data-stu-id="98ab5-130">**System Requirements**</span></span>

- <span data-ttu-id="98ab5-131">iOS 11.0 以上を実行している iOS デバイス。</span><span class="sxs-lookup"><span data-stu-id="98ab5-131">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="98ab5-132">iPadは、バージョン 1.1.15010101 以降で正式にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="98ab5-132">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="98ab5-133">デバイスは、アプリに登録[Intune ポータル サイトされます](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="98ab5-133">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="98ab5-134">**Microsoft Defender ATP (Microsoft Defender for Endpoint) on iOS は [、Apple App Store で利用できます](https://aka.ms/mdatpiosappstore)。**</span><span class="sxs-lookup"><span data-stu-id="98ab5-134">**Microsoft Defender ATP (Microsoft Defender for Endpoint) on iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="98ab5-135">インストール手順</span><span class="sxs-lookup"><span data-stu-id="98ab5-135">Installation instructions</span></span>

<span data-ttu-id="98ab5-136">iOS での Microsoft Defender for Endpoint の展開は、Microsoft Intune (MDM) 経由であり、監視対象デバイスと教師付きデバイスの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="98ab5-136">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="98ab5-137">詳細については [、「Deploy Microsoft Defender for Endpoint on iOS」を参照してください](ios-install.md)。</span><span class="sxs-lookup"><span data-stu-id="98ab5-137">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="98ab5-138">リソース</span><span class="sxs-lookup"><span data-stu-id="98ab5-138">Resources</span></span>

- <span data-ttu-id="98ab5-139">iOS またはブログの Microsoft Defender [for Endpoint](ios-whatsnew.md) の新機能にアクセスして、今後のリリースについて情報を得 [る](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="98ab5-139">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="98ab5-140">アプリ内フィードバック システムまたは SecOps ポータルを通じて [フィードバックを提供する](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="98ab5-140">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="98ab5-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="98ab5-141">Next steps</span></span>

- [<span data-ttu-id="98ab5-142">iOS での Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="98ab5-142">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="98ab5-143">iOS の機能で Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="98ab5-143">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
