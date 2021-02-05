---
title: 準備評価ツールで見つかった問題を修正する
description: ツールが見つけた問題ごとに実行する詳細なアクション
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22b5a6353720f8fbee218c138a3c9d0dee444db9
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114921"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="c5cff-104">準備評価ツールで見つかった問題を修正する</span><span class="sxs-lookup"><span data-stu-id="c5cff-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="c5cff-105">チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="c5cff-106">結果</span><span class="sxs-lookup"><span data-stu-id="c5cff-106">Result</span></span>  |<span data-ttu-id="c5cff-107">意味</span><span class="sxs-lookup"><span data-stu-id="c5cff-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="c5cff-108">準備完了</span><span class="sxs-lookup"><span data-stu-id="c5cff-108">Ready</span></span>     | <span data-ttu-id="c5cff-109">登録を完了する前に、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="c5cff-110">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="c5cff-110">Advisory</span></span>    | <span data-ttu-id="c5cff-111">登録とユーザーの最適なエクスペリエンスを得る場合は、ツールまたはこの記事の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="c5cff-112">登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="c5cff-113">使用不可能</span><span class="sxs-lookup"><span data-stu-id="c5cff-113">Not ready</span></span> | <span data-ttu-id="c5cff-114">*これらの問題を解決しない場合、登録は失敗します。*</span><span class="sxs-lookup"><span data-stu-id="c5cff-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="c5cff-115">ツールまたはこの記事の手順に従って解決します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="c5cff-116">Error</span><span class="sxs-lookup"><span data-stu-id="c5cff-116">Error</span></span> | <span data-ttu-id="c5cff-117">使用している Azure Active Directory (AD) ロールに、このチェックを実行するための十分なアクセス許可がない。</span><span class="sxs-lookup"><span data-stu-id="c5cff-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="c5cff-118">このツールによって報告される結果には、設定を実行した特定の時点での設定の状態だけが反映されます。</span><span class="sxs-lookup"><span data-stu-id="c5cff-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="c5cff-119">後で Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに変更を加えた場合、"準備完了" だったアイテムは "準備ができていない" 状態になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="c5cff-120">Microsoft マネージド デスクトップの操作で問題が発生しないようにするには、ポリシーを変更する前に、この記事で説明されている特定の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="c5cff-121">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="c5cff-121">Microsoft Intune settings</span></span>

<span data-ttu-id="c5cff-122">Intune の設定には、Microsoft Endpoint Manager 管理センターから [アクセスできます](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="c5cff-123">Autopilot 展開プロファイル</span><span class="sxs-lookup"><span data-stu-id="c5cff-123">Autopilot deployment profile</span></span>

<span data-ttu-id="c5cff-124">Microsoft マネージド デスクトップ デバイスを使用して、割り当てられたグループや動的なグループを対象とする既存の Autopilot プロファイルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-125">Microsoft マネージド デスクトップでは、Autopilot を使用して新しいデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="c5cff-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="c5cff-126">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-126">**Not ready**</span></span>

<span data-ttu-id="c5cff-127">すべてのデバイスに割り当てられている Autopilot プロファイルがある。</span><span class="sxs-lookup"><span data-stu-id="c5cff-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="c5cff-128">手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="c5cff-129">Microsoft マネージド デスクトップの登録後、Autopilot ポリシーを設定して **、Modern Workplace Devices -All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="c5cff-130">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-130">**Advisory**</span></span>

<span data-ttu-id="c5cff-131">Autopilot プロファイルが、Microsoft マネージド デスクトップ デバイスを含AD、割り当てられた、または動的な Azure AD グループを対象とするようにします。</span><span class="sxs-lookup"><span data-stu-id="c5cff-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-132">手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="c5cff-133">Microsoft マネージド デスクトップの登録後、Autopilot プロファイルを設定して **、Modern Workplace Devices -All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="c5cff-134">証明書コネクタ</span><span class="sxs-lookup"><span data-stu-id="c5cff-134">Certificate connectors</span></span>

<span data-ttu-id="c5cff-135">Microsoft マネージド デスクトップに登録するデバイスで使用される証明書コネクタがある場合、コネクタにエラーが発生しません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="c5cff-136">次の勧告の 1 つだけが状況に適用されます。そのため、慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="c5cff-137">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-137">**Advisory**</span></span>

<span data-ttu-id="c5cff-138">証明書コネクタは存在しない。</span><span class="sxs-lookup"><span data-stu-id="c5cff-138">No certificate connectors are present.</span></span> <span data-ttu-id="c5cff-139">コネクタは必要ない可能性がありますが、Microsoft マネージド デスクトップ デバイスのネットワーク接続に必要かどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-140">詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="c5cff-141">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-141">**Advisory**</span></span>

<span data-ttu-id="c5cff-142">少なくとも 1 つの証明書コネクタにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="c5cff-143">Microsoft マネージド デスクトップ デバイスに証明書を提供するためにこのコネクタが必要な場合は、エラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="c5cff-144">詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="c5cff-145">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-145">**Advisory**</span></span>

<span data-ttu-id="c5cff-146">証明書コネクタが 1 つ以上あるので、エラーは報告されません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="c5cff-147">ただし、展開の準備として、Microsoft マネージド デスクトップ デバイス用のコネクタを再利用するプロファイルを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-148">詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="c5cff-149">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="c5cff-149">Conditional access policies</span></span>

<span data-ttu-id="c5cff-150">条件付きアクセス ポリシーによって、Microsoft マネージド デスクトップが Intune と Azure AD で Azure AD 組織 (テナント) を管理AD。</span><span class="sxs-lookup"><span data-stu-id="c5cff-150">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="c5cff-151">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-151">**Not ready**</span></span>

<span data-ttu-id="c5cff-152">すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="c5cff-153">登録時に、Microsoft マネージド デスクトップ サービス アカウントを関連する条件付きアクセス ポリシーから除外し、新しい条件付きアクセス ポリシーを適用してこれらのアカウントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-153">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="c5cff-154">登録後、Microsoft Endpoint Manager で Microsoft マネージド デスクトップの条件付きアクセス ポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c5cff-154">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="c5cff-155">これらのサービス アカウントの詳細については、「標準の運用手順 [」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-155">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="c5cff-156">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-156">**Advisory**</span></span>

<span data-ttu-id="c5cff-157">条件付きアクセス ポリシーを使用すると、Microsoft マネージド デスクトップが Microsoft マネージド デスクトップ サービスを管理しなくる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-157">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="c5cff-158">登録時に、Microsoft マネージド デスクトップ サービス アカウントを関連する条件付きアクセス ポリシーから除外し、新しい条件付きアクセス ポリシーを適用してこれらのアカウントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-158">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="c5cff-159">これらのサービス アカウントの詳細については、「標準の運用手順 [」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-159">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="c5cff-160">**エラー**</span><span class="sxs-lookup"><span data-stu-id="c5cff-160">**Error**</span></span>

<span data-ttu-id="c5cff-161">Intune 管理者ロールには、このチェックのための十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-161">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="c5cff-162">このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-162">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="c5cff-163">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="c5cff-163">Security Reader</span></span>
- <span data-ttu-id="c5cff-164">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="c5cff-164">Security Administrator</span></span>
- <span data-ttu-id="c5cff-165">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="c5cff-165">Conditional Access Administrator</span></span>
- <span data-ttu-id="c5cff-166">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="c5cff-166">Global Reader</span></span>
- <span data-ttu-id="c5cff-167">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="c5cff-167">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="c5cff-168">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="c5cff-168">Device Compliance policies</span></span>

<span data-ttu-id="c5cff-169">Azure 組織の Intune デバイス コンプライアンス ポリシー AD Microsoft マネージド デスクトップ デバイスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-169">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="c5cff-170">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-170">**Not ready**</span></span>

<span data-ttu-id="c5cff-171">すべてのユーザーを対象とするコンプライアンス ポリシーが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-171">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="c5cff-172">Microsoft マネージド デスクトップには、Microsoft マネージド デスクトップ デバイスを対象とするコンプライアンス ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5cff-172">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="c5cff-173">Microsoft マネージド デスクトップのユーザーまたはデバイスを含AD特定の Azure AD グループを対象にするようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-173">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="c5cff-174">手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="c5cff-175">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-175">**Advisory**</span></span>

<span data-ttu-id="c5cff-176">Microsoft マネージド デスクトップ ユーザーを対象としないコンプライアンス ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-176">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="c5cff-177">手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="c5cff-178">デバイス構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="c5cff-178">Device Configuration profiles</span></span>

<span data-ttu-id="c5cff-179">Azure 組織の Intune デバイス構成プロファイルAD Microsoft Manage Desktop デバイスまたはユーザーを対象にしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-179">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="c5cff-180">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-180">**Not ready**</span></span>

<span data-ttu-id="c5cff-181">すべてのユーザー、すべてのデバイス、または両方を対象とする構成プロファイルが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-181">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="c5cff-182">Microsoft マネージド デスクトップ デバイスを含AD特定の Azure AD グループをターゲットにするようにプロファイルをリセットします。</span><span class="sxs-lookup"><span data-stu-id="c5cff-182">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-183">手順については [、「Microsoft Intune でカスタム設定を使用してプロファイルを作成する」を参照してください](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-183">For steps, see [Create a profile with custom settings in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="c5cff-184">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-184">**Advisory**</span></span>

<span data-ttu-id="c5cff-185">Microsoft マネージド デスクトップ デバイスまたはユーザーが含まれる構成ポリシーを含めなかったか確認します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-185">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="c5cff-186">手順については [、「Microsoft Intune でカスタム設定を使用してプロファイルを作成する」を参照してください](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-186">For steps, see [Create a profile with custom settings in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="c5cff-187">デバイスの種類の制限</span><span class="sxs-lookup"><span data-stu-id="c5cff-187">Device type restrictions</span></span>

<span data-ttu-id="c5cff-188">Microsoft マネージド デスクトップ デバイスは、Intune への登録を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="c5cff-189">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-189">**Not ready**</span></span>

<span data-ttu-id="c5cff-190">現在、Windows デバイスが Intune に登録されるのを防ぐために、少なくとも 1 つの登録制限ポリシーが構成されています。</span><span class="sxs-lookup"><span data-stu-id="c5cff-190">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="c5cff-191">「Microsoft マネージド デスクトップ ユーザー [を](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 対象とする登録制限ポリシーごとに登録制限を設定する」の手順に従い **、Windows (MDM)** の設定を [許可] に変更 **します**。</span><span class="sxs-lookup"><span data-stu-id="c5cff-191">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="c5cff-192">ただし、個人所有の **Windows (MDM)** **デバイス** を [ブロック] に設定 **できます**。</span><span class="sxs-lookup"><span data-stu-id="c5cff-192">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="c5cff-193">[登録の状態] ページ</span><span class="sxs-lookup"><span data-stu-id="c5cff-193">Enrollment Status Page</span></span>

<span data-ttu-id="c5cff-194">現在、登録ステータス ページ (ESP) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c5cff-194">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="c5cff-195">この機能の Microsoft マネージド デスクトップ パブリック プレビューに参加する場合は、この項目を無視できます。</span><span class="sxs-lookup"><span data-stu-id="c5cff-195">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="c5cff-196">詳細については [、「Autopilot での最初の実行エクスペリエンスと [登録の状態] ページ」を参照してください](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-196">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="c5cff-197">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-197">**Not ready**</span></span>

<span data-ttu-id="c5cff-198">ESP の既定のプロファイルは、[アプリとプロファイルの構成 **の進行状況を表示する] に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="c5cff-198">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="c5cff-199">この設定を無効にするか、「登録状態ページのセットアップ」の手順に従って、Azure AD グループへの割り当てに Microsoft マネージド デスクトップ デバイスが含まれるのを確認 [します](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-199">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="c5cff-200">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-200">**Advisory**</span></span>

<span data-ttu-id="c5cff-201">[アプリとプロファイルの構成の進行状況の表示] 設定を持つプロファイルが、Microsoft マネージド デスクトップ デバイスを含む Azure AD グループに割り当てられていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-201">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-202">詳細については、「登録状態 [ページのセットアップ」を参照してください](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-202">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="c5cff-203">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="c5cff-203">Microsoft Store for Business</span></span>

<span data-ttu-id="c5cff-204">ビジネス向け Microsoft Store を使用し、Microsoft マネージド デスクトップにポータル サイト アプリを展開すると、ユーザーは必要に応じて Microsoft Project や Microsoft Visio などの一部のアプリをインストールできます (許可されている場合)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-204">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="c5cff-205">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-205">**Not ready**</span></span>

<span data-ttu-id="c5cff-206">ビジネス向け Microsoft Store が有効になっていないか、Intune と同期されていない。</span><span class="sxs-lookup"><span data-stu-id="c5cff-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="c5cff-207">詳細については、ビジネス向け Microsoft Store からボリューム購入したアプリを [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) で管理し、デバイスに Intune ポータル サイトをインストールする方法を [参照してください](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="c5cff-208">多要素認証</span><span class="sxs-lookup"><span data-stu-id="c5cff-208">Multifactor authentication</span></span>

<span data-ttu-id="c5cff-209">多要素認証では、Microsoft マネージド デスクトップが Intune と Azure AD で Azure AD 組織 (テナント) を管理AD。</span><span class="sxs-lookup"><span data-stu-id="c5cff-209">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="c5cff-210">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-210">**Not ready**</span></span>

<span data-ttu-id="c5cff-211">すべてのユーザーに割り当てられている条件付きアクセスポリシーに対して、いくつかの多要素認証ポリシーを必要に応じて設定します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-211">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="c5cff-212">登録時に、Microsoft マネージド デスクトップ サービス アカウントを関連する条件付きアクセス ポリシーから除外し、新しい条件付きアクセス ポリシーを適用してこれらのアカウントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-212">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="c5cff-213">これらのサービス アカウントの詳細については、「標準の運用手順 [」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-213">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="c5cff-214">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-214">**Advisory**</span></span>

<span data-ttu-id="c5cff-215">条件付きアクセス ポリシーで多要素認証が必要になります。このポリシーにより、Microsoft マネージド デスクトップで Microsoft マネージド デスクトップ サービスが管理されるのを防ぐ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-215">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="c5cff-216">登録時に、Microsoft マネージド デスクトップ サービス アカウントを関連する条件付きアクセス ポリシーから除外し、新しい条件付きアクセス ポリシーを適用してこれらのアカウントへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-216">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="c5cff-217">これらのサービス アカウントの詳細については、「標準の運用手順 [」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-217">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="c5cff-218">**エラー**</span><span class="sxs-lookup"><span data-stu-id="c5cff-218">**Error**</span></span>

<span data-ttu-id="c5cff-219">Intune 管理者ロールには、このチェックのための十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="c5cff-220">このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="c5cff-221">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="c5cff-221">Security Reader</span></span>
- <span data-ttu-id="c5cff-222">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="c5cff-222">Security Administrator</span></span>
- <span data-ttu-id="c5cff-223">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="c5cff-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="c5cff-224">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="c5cff-224">Global Reader</span></span>
- <span data-ttu-id="c5cff-225">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="c5cff-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="c5cff-226">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="c5cff-226">PowerShell scripts</span></span>

<span data-ttu-id="c5cff-227">Windows PowerShellは、Microsoft マネージド デスクトップ デバイスをターゲットとする方法では割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="c5cff-228">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-228">**Advisory**</span></span>

<span data-ttu-id="c5cff-229">Azure Windows PowerShell内のスクリプトAD Microsoft Manage Desktop デバイスやユーザーを対象としなにされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="c5cff-230">PowerShell スクリプトを、すべてのユーザー、すべてのデバイス、または両方を対象に割り当てない。</span><span class="sxs-lookup"><span data-stu-id="c5cff-230">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="c5cff-231">Microsoft マネージド デスクトップ デバイスまたはユーザーを含AD Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-231">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="c5cff-232">詳細については、「Intune で [Windows 10 デバイスで PowerShell](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)スクリプトを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-232">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="c5cff-233">Region</span><span class="sxs-lookup"><span data-stu-id="c5cff-233">Region</span></span>

<span data-ttu-id="c5cff-234">お客様の地域は、Microsoft マネージド デスクトップでサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-234">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="c5cff-235">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-235">**Not ready**</span></span>

<span data-ttu-id="c5cff-236">Azure AD組織の地域は、Microsoft マネージド デスクトップでは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-236">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="c5cff-237">詳細については [、Microsoft マネージド デスクトップでサポートされている地域と言語を参照してください](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-237">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="c5cff-238">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-238">**Advisory**</span></span>

<span data-ttu-id="c5cff-239">Azure 組織が位置する 1 つ以上の国AD Microsoft マネージド デスクトップではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-239">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="c5cff-240">詳細については [、Microsoft マネージド デスクトップでサポートされている地域と言語を参照してください](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="c5cff-241">セキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="c5cff-241">Security baselines</span></span>

<span data-ttu-id="c5cff-242">セキュリティ基本ポリシーは、Microsoft マネージド デスクトップ デバイスを対象にしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-242">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="c5cff-243">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-243">**Not ready**</span></span>

<span data-ttu-id="c5cff-244">すべてのユーザー、すべてのデバイス、または両方を対象とするセキュリティ基本プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-244">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="c5cff-245">Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-245">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-246">手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-246">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="c5cff-247">登録時に、すべての Microsoft マネージド デスクトップ デバイスに新しいセキュリティベースラインを適用します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-247">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-248">登録後、Microsoft Endpoint Manager の構成ポリシー領域で、Microsoftマネージド デスクトップのセキュリティ基本ポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c5cff-248">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="c5cff-249">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-249">**Advisory**</span></span>

<span data-ttu-id="c5cff-250">Microsoft マネージド デスクトップ デバイスを除外したセキュリティ基本ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-250">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-251">手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-251">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="c5cff-252">登録時に、すべての Microsoft マネージド デスクトップ デバイスに新しいセキュリティベースラインを適用します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-252">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-253">**Modern Workplace Devices -All** Azure AD グループは、Microsoft マネージド デスクトップに登録するときに作成される動的なグループです。そのため、登録後にこのグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 


### <a name="windows-apps"></a><span data-ttu-id="c5cff-254">Windows アプリ</span><span class="sxs-lookup"><span data-stu-id="c5cff-254">Windows apps</span></span>

<span data-ttu-id="c5cff-255">Microsoft マネージド デスクトップ ユーザーに必要なアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="c5cff-256">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-256">**Advisory**</span></span>

<span data-ttu-id="c5cff-257">Microsoft マネージド デスクトップ ユーザーが持つアプリのインベントリを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="c5cff-258">これらのアプリは Intune で展開する必要があるから、既存の Intune アプリの再利用を評価します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-258">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="c5cff-259">ポータル サイトの使用を検討します (「デバイスに [Intune ポータル](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) サイトをインストールする」と「登録状態ページ (ESP)」を参照)、ユーザーにアプリを配布します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-259">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="c5cff-260">詳細については [、「Microsoft マネージド](apps.md) デスクトップのアプリ」と [「Autopilot](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)での初回実行時エクスペリエンス」および「登録状態ページ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="c5cff-261">Microsoft Endpoint Configuration Manager で Microsoft アカウントの担当者に、Intune に移行する準備ができているアプリや調整が必要なアプリを特定するクエリを求められます。</span><span class="sxs-lookup"><span data-stu-id="c5cff-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="c5cff-262">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="c5cff-262">Windows Hello for Business</span></span>

<span data-ttu-id="c5cff-263">Microsoft マネージド デスクトップでは、Windows Hello for Business を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="c5cff-264">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-264">**Not ready**</span></span>

<span data-ttu-id="c5cff-265">Windows Hello for Business は無効です。</span><span class="sxs-lookup"><span data-stu-id="c5cff-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="c5cff-266">「Windows Hello for Business ポリシーを作成する」の [手順に従って有効にする](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="c5cff-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="c5cff-267">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-267">**Advisory**</span></span>

<span data-ttu-id="c5cff-268">Windows Hello for Business がセットアップされていない。</span><span class="sxs-lookup"><span data-stu-id="c5cff-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="c5cff-269">「Windows Hello for Business ポリシーを作成する [」の手順に従って有効にしてください](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-269">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="c5cff-270">Windows 10 の更新リング</span><span class="sxs-lookup"><span data-stu-id="c5cff-270">Windows 10 update rings</span></span>

<span data-ttu-id="c5cff-271">Intune の "Windows 10 更新リング" ポリシーは、Microsoft マネージド デスクトップ デバイスをターゲットにしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="c5cff-272">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-272">**Not ready**</span></span>

<span data-ttu-id="c5cff-273">すべてのデバイス、すべてのユーザー、または両方を対象とする "更新リング" ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="c5cff-274">Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="c5cff-275">手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="c5cff-276">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-276">**Advisory**</span></span>

<span data-ttu-id="c5cff-277">モダン Workplace **Devices -All** Azure AD グループから除外した更新リング ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="c5cff-278">Azure AD ユーザー グループをこれらのポリシーに割り当てた場合は、Microsoft マネージド デスクトップ ユーザー (または同等のグループ) に追加する **Modern Workplace -All** Azure AD グループも除外している更新リング ポリシーを必ず除外してください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-278">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="c5cff-279">手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-279">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="c5cff-280">Modern **Workplace Devices -All** グループと **Modern Workplace - すべての** Azure AD グループは、Microsoft マネージド デスクトップに登録するときに作成されるグループなので、登録後にこのグループを除外するために戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="c5cff-281">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="c5cff-281">Azure Active Directory settings</span></span>

<span data-ttu-id="c5cff-282">Azure Active Directory の設定には [、Azure Portal でアクセスできます](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="c5cff-283">Intune 登録</span><span class="sxs-lookup"><span data-stu-id="c5cff-283">Intune enrollment</span></span>

<span data-ttu-id="c5cff-284">Azure 組織の Windows 10 デバイスAD Intune に自動的に登録できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-284">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="c5cff-285">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-285">**Advisory**</span></span>

<span data-ttu-id="c5cff-286">MDM ユーザー スコープ **が [なし] ではなく** [ **一部]** または [ **すべて]** に設定されている必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="c5cff-286">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="c5cff-287">[一部] を選択した場合は、登録後に戻って、グループの Modern Workplace  **-All** Azure AD グループ、またはすべての Microsoft マネージド デスクトップ ユーザーを対象とする同等のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-287">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="c5cff-288">[「Microsoft Intune を使用して Windows デバイスの登録をセットアップする」を参照してください](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-288">See [Set up enrollment for Windows devices by using Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="c5cff-289">アドホック サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="c5cff-289">Ad hoc subscriptions</span></span>

<span data-ttu-id="c5cff-290">("false" に設定されている場合)、エンタープライズ状態ローミングが正しく動作しない可能性がある設定を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-290">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="c5cff-291">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-291">**Advisory**</span></span>

<span data-ttu-id="c5cff-292">**AllowAdHocSubscriptions** が **True** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c5cff-292">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="c5cff-293">それ以外の場合は、Enterprise State Roaming が機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-293">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="c5cff-294">詳細については [、「Set-MsolCompanySettings」を参照してください](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-294">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="c5cff-295">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="c5cff-295">Enterprise State Roaming</span></span>

<span data-ttu-id="c5cff-296">Enterprise State Roaming を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-296">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="c5cff-297">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-297">**Advisory**</span></span>

<span data-ttu-id="c5cff-298">[すべて] または [選択したグループ] に対して Enterprise State Roaming が有効 **になっているか確認** します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-298">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="c5cff-299">詳細については [、「Azure Active Directory でエンタープライズ状態ローミングを有効にする」を参照してください](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-299">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="c5cff-300">ライセンス</span><span class="sxs-lookup"><span data-stu-id="c5cff-300">Licenses</span></span>

<span data-ttu-id="c5cff-301">Microsoft マネージド デスクトップを使用するには、多数のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="c5cff-301">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="c5cff-302">**準備ができていない**</span><span class="sxs-lookup"><span data-stu-id="c5cff-302">**Not Ready**</span></span>

<span data-ttu-id="c5cff-303">Microsoft マネージド デスクトップを使用するために必要なライセンスの一部を持っている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-303">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="c5cff-304">詳細については [、Microsoft マネージド デスクトップテクノロジと](../intro/technologies.md) ライセンスの [詳細を参照してください](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-304">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="c5cff-305">セキュリティ アカウント名</span><span class="sxs-lookup"><span data-stu-id="c5cff-305">Security account names</span></span>

<span data-ttu-id="c5cff-306">一部のセキュリティ アカウント名は、Microsoft マネージド デスクトップで作成された名前と競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-306">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="c5cff-307">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-307">**Not ready**</span></span>

<span data-ttu-id="c5cff-308">Microsoft マネージド デスクトップで作成されたアカウント名と競合するアカウント名が少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-308">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="c5cff-309">Microsoft アカウント担当者と一緒に、これらのアカウント名を除外します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-309">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="c5cff-310">セキュリティ管理者ロール</span><span class="sxs-lookup"><span data-stu-id="c5cff-310">Security administrator roles</span></span>

<span data-ttu-id="c5cff-311">特定のセキュリティ ロールを持つユーザーには、それらの役割が Microsoft Defender for Endpoint に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-311">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="c5cff-312">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-312">**Advisory**</span></span>

<span data-ttu-id="c5cff-313">Azure AD 組織でこれらの役割に割り当てられているユーザーがある場合は、それらのユーザーに、エンドポイント用 Microsoft Defender でこれらの役割も割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-313">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="c5cff-314">そうしないと、これらの役割を持つ管理者は管理ポータルにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-314">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="c5cff-315">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="c5cff-315">Security Operator</span></span>
- <span data-ttu-id="c5cff-316">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="c5cff-316">Global Reader</span></span>

<span data-ttu-id="c5cff-317">詳細については、「役割ベースのアクセス [制御の役割を作成および管理する」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-317">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="c5cff-318">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="c5cff-318">Security default</span></span>

<span data-ttu-id="c5cff-319">Azure Active Directory のセキュリティの既定値により、Microsoft マネージド デスクトップでデバイスを管理できません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-319">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="c5cff-320">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="c5cff-320">**Not ready**</span></span>

<span data-ttu-id="c5cff-321">セキュリティの既定値を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="c5cff-321">You have Security defaults turned on.</span></span> <span data-ttu-id="c5cff-322">セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-322">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="c5cff-323">詳細については、「一般的な条件付 [きアクセス ポリシー」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-323">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="c5cff-324">セルフサービスによるパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="c5cff-324">Self-service Password Reset</span></span>

<span data-ttu-id="c5cff-325">セルフサービスによるパスワードリセット (SSPR) は、Microsoft マネージド デスクトップ サービス アカウントを除くすべての Microsoft マネージド デスクトップ ユーザーに対して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="c5cff-325">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="c5cff-326">詳細については、「チュートリアル: Azure Active Directory のセルフサービス によるパスワードのリセットを使用して、ユーザーが自分のアカウントのロックを解除したり、パスワード [をリセットしたりできる」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-326">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="c5cff-327">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-327">**Advisory**</span></span>

<span data-ttu-id="c5cff-328">[SSPR の **選択]** 設定に Microsoft マネージド デスクトップ ユーザーが含まれていますが、Microsoft マネージド デスクトップ サービス アカウントは除外します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-328">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="c5cff-329">SSPR が有効な場合、Microsoft マネージド デスクトップ サービス アカウントは期待通り動作しません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-329">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="c5cff-330">標準ユーザー ロール</span><span class="sxs-lookup"><span data-stu-id="c5cff-330">Standard user role</span></span>

<span data-ttu-id="c5cff-331">グローバル管理者とデバイス管理者の Azure AD ロールが割り当てられているユーザー以外に、Microsoft マネージド デスクトップ ユーザーはローカル管理者特権のない標準ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="c5cff-331">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="c5cff-332">その他のすべてのユーザーには、Microsoft マネージド デスクトップ デバイスの起動時に標準のユーザー ロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="c5cff-332">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="c5cff-333">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-333">**Advisory**</span></span>

<span data-ttu-id="c5cff-334">Microsoft マネージド デスクトップ ユーザーは、登録後に Microsoft マネージド デスクトップ デバイスに対するローカル管理者特権を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5cff-334">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="c5cff-335">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="c5cff-335">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="c5cff-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="c5cff-336">OneDrive</span></span>

<span data-ttu-id="c5cff-337">特定 **のドメインに参加している PC** でのみ同期を許可する設定は、Microsoft マネージド デスクトップと競合します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-337">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="c5cff-338">OneDrive 管理センターで OneDrive の設定に [アクセスできます](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="c5cff-338">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="c5cff-339">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="c5cff-339">**Advisory**</span></span>

<span data-ttu-id="c5cff-340">特定のドメインに参加している PC でのみ同期を許可 **する設定を使用** している。</span><span class="sxs-lookup"><span data-stu-id="c5cff-340">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="c5cff-341">この設定は、Microsoft マネージド デスクトップでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="c5cff-341">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="c5cff-342">この設定を無効にし、代わりに条件付きアクセス ポリシーを使用する OneDrive を設定します。</span><span class="sxs-lookup"><span data-stu-id="c5cff-342">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="c5cff-343">ヘルプ [については、「条件付きアクセスの展開を計画する](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5cff-343">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>
