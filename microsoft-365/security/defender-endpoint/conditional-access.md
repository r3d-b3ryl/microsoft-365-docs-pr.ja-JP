---
title: 条件付きアクセスを有効にして、ユーザー、デバイス、およびデータをより良く保護する
description: 条件付きアクセスを有効にして、デバイスが危険にさらされているとみなされ、アプリケーションが非準拠であると判断された場合にアプリケーションが実行されるのを防ぐ。
keywords: 条件付きアクセス、ブロック アプリケーション、セキュリティ レベル、Intune、
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166199"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a><span data-ttu-id="e93a4-104">条件付きアクセスを有効にして、ユーザー、デバイス、およびデータをより良く保護する</span><span class="sxs-lookup"><span data-stu-id="e93a4-104">Enable Conditional Access to better protect users, devices, and data</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e93a4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e93a4-105">**Applies to:**</span></span>
- [<span data-ttu-id="e93a4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e93a4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e93a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e93a4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e93a4-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e93a4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e93a4-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="e93a4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

<span data-ttu-id="e93a4-110">条件付きアクセスは、セキュリティで保護されたデバイスだけがアプリケーションにアクセスし、ユーザーとエンタープライズ情報をより適切に保護するのに役立つ機能です。</span><span class="sxs-lookup"><span data-stu-id="e93a4-110">Conditional Access is a capability that helps you better protect your users and enterprise information by making sure that only secure devices have access to applications.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

<span data-ttu-id="e93a4-111">条件付きアクセスを使用すると、デバイスのリスク レベルに基づいてエンタープライズ情報へのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-111">With Conditional Access, you can control access to enterprise information based on the risk level of a device.</span></span> <span data-ttu-id="e93a4-112">これにより、信頼できるアプリケーションを使用して信頼できるデバイス上の信頼できるユーザーを維持できます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-112">This helps keep trusted users on trusted devices using trusted applications.</span></span>

<span data-ttu-id="e93a4-113">ポリシーを適用して、デバイスが準拠状態に戻るまでアプリケーションの実行を停止することで、デバイスとアプリケーションがネットワークから情報を実行およびアクセスできるセキュリティ条件を定義できます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-113">You can define security conditions under which devices and applications can run and access information from your network by enforcing policies to stop applications from running until a device returns to a compliant state.</span></span> 

<span data-ttu-id="e93a4-114">Defender for Endpoint での条件付きアクセスの実装は、Microsoft Intune (Intune) デバイス コンプライアンス ポリシーと Azure Active Directory (Azure Active Directory AD) 条件付きアクセス ポリシーに基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="e93a4-114">The implementation of Conditional Access in Defender for Endpoint is based on Microsoft Intune (Intune) device compliance policies and Azure Active Directory (Azure AD) conditional access policies.</span></span> 

<span data-ttu-id="e93a4-115">コンプライアンス ポリシーは、条件付きアクセスと一緒に使用して、1 つ以上のデバイス コンプライアンス ポリシー ルールを満たすデバイスだけがアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-115">The compliance policy is used with Conditional Access to allow only devices that fulfill one or more device compliance policy rules to access applications.</span></span> 

## <a name="understand-the-conditional-access-flow"></a><span data-ttu-id="e93a4-116">条件付きアクセス フローについて</span><span class="sxs-lookup"><span data-stu-id="e93a4-116">Understand the Conditional Access flow</span></span>
<span data-ttu-id="e93a4-117">条件付きアクセスが実行され、デバイスで脅威が見られると、脅威が修復されるまで機密コンテンツへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-117">Conditional Access is put in place so that when a threat is seen on a device, access to sensitive content is blocked until the threat is remediated.</span></span> 

<span data-ttu-id="e93a4-118">フローは、デバイスのリスクが低、中、または高く見られるから始まります。</span><span class="sxs-lookup"><span data-stu-id="e93a4-118">The flow begins with devices being seen to have a low, medium, or high risk.</span></span> <span data-ttu-id="e93a4-119">その後、これらのリスク判定が Intune に送信されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-119">These risk determinations are then sent to Intune.</span></span> 

<span data-ttu-id="e93a4-120">Intune でポリシーを構成する方法に応じて、条件付きアクセスを設定して、特定の条件が満たされるとポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-120">Depending on how you configure policies in Intune, Conditional Access can be set up so that when certain conditions are met, the policy is applied.</span></span>

<span data-ttu-id="e93a4-121">たとえば、リスクが高いデバイスに条件付きアクセスを適用する Intune を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-121">For example, you can configure Intune to apply Conditional Access on devices that have a high risk.</span></span>

<span data-ttu-id="e93a4-122">Intune では、デバイス コンプライアンス ポリシーが Azure AD条件付きアクセスと組み合わせて使用して、アプリケーションへのアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="e93a4-122">In Intune, a device compliance policy is used in conjunction with Azure AD Conditional Access to block access to applications.</span></span> <span data-ttu-id="e93a4-123">並行して、自動調査と修復プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-123">In parallel, an automated investigation and remediation process is launched.</span></span>

 <span data-ttu-id="e93a4-124">自動調査と修復が行なっている間も、ユーザーはデバイスを使用できますが、脅威が完全に修復されるまでエンタープライズ データへのアクセスはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-124">A user can still use the device while the automated investigation and remediation is taking place, but access to enterprise data is blocked until the threat is fully remediated.</span></span> 

<span data-ttu-id="e93a4-125">デバイスで見つかったリスクを解決するには、デバイスを準拠した状態に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e93a4-125">To resolve the risk found on a device, you'll need to return the device to a compliant state.</span></span> <span data-ttu-id="e93a4-126">デバイスにリスクが見られない場合、デバイスは準拠状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e93a4-126">A device returns to a compliant state when there is no risk seen on it.</span></span> 

<span data-ttu-id="e93a4-127">リスクに対処するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e93a4-127">There are three ways to address a risk:</span></span>
1. <span data-ttu-id="e93a4-128">手動または自動修復を使用します。</span><span class="sxs-lookup"><span data-stu-id="e93a4-128">Use Manual or automated remediation.</span></span>
2. <span data-ttu-id="e93a4-129">デバイスでアクティブなアラートを解決します。</span><span class="sxs-lookup"><span data-stu-id="e93a4-129">Resolve active alerts on the device.</span></span> <span data-ttu-id="e93a4-130">これにより、デバイスからリスクが削除されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-130">This will remove the risk from the device.</span></span>
3. <span data-ttu-id="e93a4-131">アクティブ なポリシーからデバイスを削除できます。そのため、条件付きアクセスはデバイスに適用されません。</span><span class="sxs-lookup"><span data-stu-id="e93a4-131">You can remove the device from the active policies and consequently, Conditional Access will not be applied on the device.</span></span> 

<span data-ttu-id="e93a4-132">手動による修復では、secops 管理者がアラートを調査し、デバイスで見られるリスクに対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e93a4-132">Manual remediation requires a secops admin to investigate an alert and address the risk seen on the device.</span></span> <span data-ttu-id="e93a4-133">自動修復は、次のセクション「条件付きアクセスの構成」で提供される構成 [設定によって構成されます](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e93a4-133">The automated remediation is configured through configuration settings provided in the following section, [Configure Conditional Access](configure-conditional-access.md).</span></span>

<span data-ttu-id="e93a4-134">手動または自動修復によってリスクが削除されると、デバイスは準拠した状態に戻り、アプリケーションへのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-134">When the risk is removed either through manual or automated remediation, the device returns to a compliant state and access to applications is granted.</span></span>

<span data-ttu-id="e93a4-135">次の一連のイベントの例では、条件付きアクセスの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="e93a4-135">The following example sequence of events explains Conditional Access in action:</span></span>

1. <span data-ttu-id="e93a4-136">ユーザーが悪意のあるファイルを開き、Defender for Endpoint はデバイスにリスクの高いフラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="e93a4-136">A user opens a malicious file and Defender for Endpoint flags the device as high risk.</span></span>
2. <span data-ttu-id="e93a4-137">高リスク評価は Intune に渡されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-137">The high risk assessment is passed along to Intune.</span></span> <span data-ttu-id="e93a4-138">並行して、特定された脅威を修復するために自動調査が開始されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-138">In parallel, an automated investigation is initiated to remediate the identified threat.</span></span> <span data-ttu-id="e93a4-139">また、特定された脅威を修復するために手動で修復することもできます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-139">A manual remediation can also be done to remediate the identified threat.</span></span>
3. <span data-ttu-id="e93a4-140">Intune で作成されたポリシーに基づいて、デバイスは準拠していないとマークされます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-140">Based on the policy created in Intune, the device is marked as not compliant.</span></span> <span data-ttu-id="e93a4-141">その後、評価は Intune 条件付きアクセス ADによって Azure サーバーに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-141">The assessment is then communicated to Azure AD by the Intune Conditional Access policy.</span></span> <span data-ttu-id="e93a4-142">Azure ADでは、対応するポリシーが適用され、アプリケーションへのアクセスがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-142">In Azure AD, the corresponding policy is applied to block access to applications.</span></span>
4. <span data-ttu-id="e93a4-143">手動または自動化された調査と修復が完了し、脅威が削除されます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-143">The manual or automated investigation and remediation is completed and the threat is removed.</span></span> <span data-ttu-id="e93a4-144">Defender for Endpoint では、デバイスにリスクがないと見なされ、Intune はデバイスが準拠状態にあると評価します。</span><span class="sxs-lookup"><span data-stu-id="e93a4-144">Defender for Endpoint sees that there is no risk on the device and Intune assesses the device to be in a compliant state.</span></span> <span data-ttu-id="e93a4-145">Azure ADアプリケーションへのアクセスを許可するポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="e93a4-145">Azure AD applies the policy which allows access to applications.</span></span>
5. <span data-ttu-id="e93a4-146">これで、ユーザーはアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e93a4-146">Users can now access applications.</span></span>

 
## <a name="related-topic"></a><span data-ttu-id="e93a4-147">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e93a4-147">Related topic</span></span>
- [<span data-ttu-id="e93a4-148">Microsoft Defender for Endpoint で条件付きアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="e93a4-148">Configure Conditional Access in Microsoft Defender for Endpoint</span></span>](configure-conditional-access.md)
