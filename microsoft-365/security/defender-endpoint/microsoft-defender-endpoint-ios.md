---
title: Microsoft Defender ATP for iOS の概要
ms.reviewer: ''
description: Microsoft Defender ATP for iOS をインストールして使用する方法について説明します。
keywords: microsoft、Defender、atp、ios、概要、インストール、展開、アンインストール、Intune
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
ms.openlocfilehash: 72c3cfd51e472bbbda61f0084e131c4298633193
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186991"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="30cd0-104">iOS 用 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="30cd0-104">Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="30cd0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="30cd0-105">**Applies to:**</span></span>
- [<span data-ttu-id="30cd0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="30cd0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="30cd0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30cd0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="30cd0-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="30cd0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="30cd0-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="30cd0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="30cd0-110">**Microsoft Defender for Endpoint for iOS** は、Web サイト、電子メール、アプリからのフィッシングや安全でないネットワーク接続に対する保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="30cd0-110">**Microsoft Defender for Endpoint for iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="30cd0-111">すべてのアラートは、Microsoft Defender セキュリティ センターの 1 つのウィンドウから利用できます。</span><span class="sxs-lookup"><span data-stu-id="30cd0-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="30cd0-112">このポータルにより、セキュリティ チームは、他のプラットフォームと共に、iOS デバイス上の脅威の一元的なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="30cd0-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="30cd0-113">IOS 用 Defender for Endpoint と共に他のサード パーティ製のエンドポイント保護製品を実行すると、パフォーマンスの問題や予期しないシステム エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="30cd0-113">Running other third-party endpoint protection products alongside Defender for Endpoint for iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="30cd0-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="30cd0-114">Pre-requisites</span></span>

<span data-ttu-id="30cd0-115">**エンド ユーザー向け**</span><span class="sxs-lookup"><span data-stu-id="30cd0-115">**For End Users**</span></span>

- <span data-ttu-id="30cd0-116">アプリのエンド ユーザーに割り当てられた Microsoft Defender for Endpoint ライセンス。</span><span class="sxs-lookup"><span data-stu-id="30cd0-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="30cd0-117">「Microsoft [Defender for Endpoint ライセンス要件」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="30cd0-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="30cd0-118">デバイスは Intune [ポータル](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) サイト アプリを介して登録され、Intune デバイス コンプライアンス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="30cd0-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="30cd0-119">これには、エンド ユーザーに Microsoft Intune ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="30cd0-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="30cd0-120">Intune ポータル サイト アプリは [、Apple App Store からダウンロードできます](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="30cd0-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="30cd0-121">Apple では、リダイレクトユーザーがアプリ ストアから他のアプリをダウンロードすることを許可していないので、この手順は、Microsoft Defender for Endpoint アプリにオンボーディングする前にユーザーが行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="30cd0-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="30cd0-122">ライセンスを割り当てる方法の詳細については、「ユーザーにライセンスを割り当 [てる」を参照してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。</span><span class="sxs-lookup"><span data-stu-id="30cd0-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="30cd0-123">**管理者向け**</span><span class="sxs-lookup"><span data-stu-id="30cd0-123">**For Administrators**</span></span>

- <span data-ttu-id="30cd0-124">Microsoft Defender セキュリティ センター ポータルへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="30cd0-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="30cd0-125">Microsoft Intune は、Microsoft Defender for Endpoint for iOS を展開する唯一のサポートされるモバイル デバイス管理 (MDM) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="30cd0-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for iOS.</span></span> <span data-ttu-id="30cd0-126">現在、Intune で Defender for Endpoint for iOS 関連のデバイス コンプライアンス ポリシーを適用するには、現在登録されているデバイスだけがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="30cd0-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint for iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="30cd0-127">組織の [登録済みユーザー](https://go.microsoft.com/fwlink/?linkid=2109431)グループにアプリを展開するには、Microsoft Endpoint Manager 管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="30cd0-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="30cd0-128">**システム要件**</span><span class="sxs-lookup"><span data-stu-id="30cd0-128">**System Requirements**</span></span>

- <span data-ttu-id="30cd0-129">iOS 11.0 以上を実行している iOS デバイス。</span><span class="sxs-lookup"><span data-stu-id="30cd0-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="30cd0-130">iPad デバイスは、バージョン 1.1.15010101 以降で正式にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="30cd0-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="30cd0-131">デバイスは Intune ポータル サイト アプリ [に登録されています](https://apps.apple.com/us/app/intune-company-portal/id719171358)。</span><span class="sxs-lookup"><span data-stu-id="30cd0-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="30cd0-132">**iOS 用 Microsoft Defender ATP (Microsoft Defender for Endpoint) が [Apple App Store で利用可能になります](https://aka.ms/mdatpiosappstore)。**</span><span class="sxs-lookup"><span data-stu-id="30cd0-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="30cd0-133">インストール手順</span><span class="sxs-lookup"><span data-stu-id="30cd0-133">Installation instructions</span></span>

<span data-ttu-id="30cd0-134">Microsoft Defender for Endpoint for iOS の展開は Microsoft Intune (MDM) 経由であり、監視対象デバイスと教師付きデバイスの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="30cd0-134">Deployment of Microsoft Defender for Endpoint for iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="30cd0-135">詳細については [、「Deploy Microsoft Defender for Endpoint for iOS」を参照してください](ios-install.md)。</span><span class="sxs-lookup"><span data-stu-id="30cd0-135">For more information, see [Deploy Microsoft Defender for Endpoint for iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="30cd0-136">リソース</span><span class="sxs-lookup"><span data-stu-id="30cd0-136">Resources</span></span>

- <span data-ttu-id="30cd0-137">ブログにアクセスして、今後のリリースについて情報を得 [る](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="30cd0-137">Stay informed about upcoming releases by visiting our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="30cd0-138">アプリ内フィードバック システムまたは SecOps ポータルを通じて [フィードバックを提供する](https://securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="30cd0-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="30cd0-139">次の手順</span><span class="sxs-lookup"><span data-stu-id="30cd0-139">Next steps</span></span>

- [<span data-ttu-id="30cd0-140">Microsoft Defender for Endpoint for iOS の展開</span><span class="sxs-lookup"><span data-stu-id="30cd0-140">Deploy Microsoft Defender for Endpoint for iOS</span></span>](ios-install.md)
- [<span data-ttu-id="30cd0-141">iOS 機能用に Microsoft Defender for Endpoint を構成する</span><span class="sxs-lookup"><span data-stu-id="30cd0-141">Configure Microsoft Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)