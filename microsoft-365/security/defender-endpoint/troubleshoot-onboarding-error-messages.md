---
title: オンボーディングの問題とエラー メッセージのトラブルシューティング
description: Microsoft Defender for Endpoint のセットアップを完了する際にオンボーディングの問題とエラー メッセージのトラブルシューティングを行います。
keywords: トラブルシューティング, トラブルシューティング, Azure Active Directory, オンボーディング, エラー メッセージ, エラー メッセージ, エンドポイント用 microsoft Defender
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
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 63981d985140858cbbda54a10dc94b30f28131e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064852"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="526b1-104">サブスクリプションとポータル アクセスの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="526b1-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="526b1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="526b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="526b1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="526b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="526b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="526b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="526b1-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="526b1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="526b1-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="526b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="526b1-110">このページでは、Microsoft Defender for Endpoint サービスのセットアップ時に発生する可能性がある問題をトラブルシューティングするための詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="526b1-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="526b1-111">エラー メッセージが表示された場合、Microsoft Defender セキュリティ センターは、問題の内容と関連するリンクが提供される詳細な説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="526b1-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="526b1-112">サブスクリプションが見つかりません</span><span class="sxs-lookup"><span data-stu-id="526b1-112">No subscriptions found</span></span>

<span data-ttu-id="526b1-113">Microsoft Defender Security Center にアクセスしている間にサブスクリプションが見つからないというメッセージが表示される場合は、ユーザーのポータルへのログインに使用される Azure Active Directory (Azure AD) には、Microsoft Defender for Endpoint ライセンスが存在しないという意味です。</span><span class="sxs-lookup"><span data-stu-id="526b1-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="526b1-114">潜在的な理由:</span><span class="sxs-lookup"><span data-stu-id="526b1-114">Potential reasons:</span></span>
- <span data-ttu-id="526b1-115">Windows E5 ライセンスと Office E5 ライセンスは、別のライセンスです。</span><span class="sxs-lookup"><span data-stu-id="526b1-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="526b1-116">ライセンスは購入されましたが、この Azure サーバー インスタンスADされません。</span><span class="sxs-lookup"><span data-stu-id="526b1-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="526b1-117">ライセンス プロビジョニングの問題である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="526b1-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="526b1-118">サービスへの認証に使用されるライセンスとは異なる Microsoft Azure ADにライセンスを誤ってプロビジョニングした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="526b1-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="526b1-119">どちらの場合も、Microsoft Defender for [Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) または Volume ライセンス のサポートで Microsoft サポートに問い [合わせるべきです](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)。</span><span class="sxs-lookup"><span data-stu-id="526b1-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![サブスクリプションが見つからないイメージ](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="526b1-121">サブスクリプションの有効期限が切れています</span><span class="sxs-lookup"><span data-stu-id="526b1-121">Your subscription has expired</span></span>

<span data-ttu-id="526b1-122">Microsoft Defender Security Center へのアクセス中にサブスクリプションの有効期限が切れているというメッセージが表示される場合は、オンライン サービス サブスクリプションの有効期限が切れています。</span><span class="sxs-lookup"><span data-stu-id="526b1-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="526b1-123">Microsoft Defender for Endpoint サブスクリプションは、他のオンライン サービス サブスクリプションと同様に有効期限があります。</span><span class="sxs-lookup"><span data-stu-id="526b1-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="526b1-124">ライセンスの更新または延長は、任意の時点で選択できます。</span><span class="sxs-lookup"><span data-stu-id="526b1-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="526b1-125">有効期限が切れた後にポータルにアクセスすると、サブスクリプションの有効期限が切れたメッセージが表示され、ライセンスを更新しない場合は、デバイスのオフボード パッケージをダウンロードするオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="526b1-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="526b1-126">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="526b1-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="526b1-127">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="526b1-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="526b1-128">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="526b1-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![サブスクリプションの有効期限が切れているイメージ](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="526b1-130">ポータルへのアクセスが承認されていない</span><span class="sxs-lookup"><span data-stu-id="526b1-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="526b1-131">ポータルへのアクセスが承認されていない場合、Microsoft Defender for Endpoint はセキュリティ監視、インシデント調査、応答製品であり、アクセスはユーザーによって制限および制御されます。</span><span class="sxs-lookup"><span data-stu-id="526b1-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="526b1-132">詳細については、「ユーザー アクセスをポータルに [**割り当てる」を参照してください**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="526b1-132">For more information, see, [**Assign user access to the portal**](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![ポータルへのアクセスが承認されていないイメージ](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="526b1-134">現在、ポータルの一部のセクションでデータを使用できない</span><span class="sxs-lookup"><span data-stu-id="526b1-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="526b1-135">ポータル ダッシュボードや他のセクションに「現在データが使用できない」などのエラー メッセージが表示される場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="526b1-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![現在使用できないデータの画像](images/atp-data-not-available.png)

<span data-ttu-id="526b1-137">その下のすべてのサブドメインを許可 `securitycenter.windows.com` する必要があります。</span><span class="sxs-lookup"><span data-stu-id="526b1-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="526b1-138">たとえば、`*.securitycenter.windows.com` などです。</span><span class="sxs-lookup"><span data-stu-id="526b1-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="526b1-139">ポータル通信の問題</span><span class="sxs-lookup"><span data-stu-id="526b1-139">Portal communication issues</span></span>
<span data-ttu-id="526b1-140">ポータルへのアクセス、不足しているデータ、またはポータルの一部へのアクセス制限に関する問題が発生した場合は、次の URL が許可され、通信のために開いているか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="526b1-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



