---
title: 準備評価ツールで見つかった問題を修正する
description: ツールが見つけた各問題に対して実行する詳細なアクション
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75c2967037ae83abca2aaa3cd02d1f6b2ae14caa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925918"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="fcf79-104">準備評価ツールで見つかった問題を修正する</span><span class="sxs-lookup"><span data-stu-id="fcf79-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="fcf79-105">チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="fcf79-106">結果</span><span class="sxs-lookup"><span data-stu-id="fcf79-106">Result</span></span>  |<span data-ttu-id="fcf79-107">意味</span><span class="sxs-lookup"><span data-stu-id="fcf79-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="fcf79-108">準備完了</span><span class="sxs-lookup"><span data-stu-id="fcf79-108">Ready</span></span>     | <span data-ttu-id="fcf79-109">登録を完了する前に、アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="fcf79-110">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="fcf79-110">Advisory</span></span>    | <span data-ttu-id="fcf79-111">登録とユーザーの最適なエクスペリエンスについては、ツールまたはこの記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fcf79-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="fcf79-112">登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="fcf79-113">使用不可能</span><span class="sxs-lookup"><span data-stu-id="fcf79-113">Not ready</span></span> | <span data-ttu-id="fcf79-114">*これらの問題を解決しない場合、登録は失敗します。*</span><span class="sxs-lookup"><span data-stu-id="fcf79-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="fcf79-115">ツールまたはこの記事の手順に従って解決します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="fcf79-116">Error</span><span class="sxs-lookup"><span data-stu-id="fcf79-116">Error</span></span> | <span data-ttu-id="fcf79-117">使用している Azure Active Directory (AD) ロールには、このチェックを実行するための十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="fcf79-118">このツールによって報告された結果は、設定を実行した特定の時点でのみ設定の状態を反映します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="fcf79-119">後で Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに変更を加えた場合、"準備完了" だったアイテムは "準備ができていない" 状態になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="fcf79-120">Microsoft Managed Desktop 操作の問題を回避するには、ポリシーを変更する前に、この記事で説明されている特定の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcf79-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="fcf79-121">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="fcf79-121">Microsoft Intune settings</span></span>

<span data-ttu-id="fcf79-122">Intune の設定には、Microsoft Endpoint Manager 管理センターから [アクセスできます](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="fcf79-123">自動パイロット展開プロファイル</span><span class="sxs-lookup"><span data-stu-id="fcf79-123">Autopilot deployment profile</span></span>

<span data-ttu-id="fcf79-124">Microsoft Managed Desktop デバイスを使用して割り当てられたグループまたは動的グループを対象とする既存の自動パイロット プロファイルを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-125">Microsoft Managed Desktop では、Autopilot を使用して新しいデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="fcf79-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="fcf79-126">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-126">**Not ready**</span></span>

<span data-ttu-id="fcf79-127">すべてのデバイスに割り当てられている自動パイロット プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="fcf79-128">手順については、「Windows Autopilot を使用して Intune に Windows デバイスを登録 [する」を参照してください](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="fcf79-129">Microsoft Managed Desktop の登録後、Autopilot ポリシーを設定して、モダン ワークプレース デバイス **-All** Azure ADグループを除外します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="fcf79-130">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-130">**Advisory**</span></span>

<span data-ttu-id="fcf79-131">Autopilot プロファイルが、Microsoft Managed Desktop デバイスを含AD割り当てられた、または動的な Azure クライアント グループを対象とするようにします。</span><span class="sxs-lookup"><span data-stu-id="fcf79-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-132">手順については、「Windows Autopilot を使用して Intune に Windows デバイスを登録 [する」を参照してください](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="fcf79-133">Microsoft Managed Desktop の登録後、Autopilot プロファイルにモダン ワークプレース デバイス **-All** Azure ADグループをADします。</span><span class="sxs-lookup"><span data-stu-id="fcf79-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="fcf79-134">証明書コネクタ</span><span class="sxs-lookup"><span data-stu-id="fcf79-134">Certificate connectors</span></span>

<span data-ttu-id="fcf79-135">Microsoft Managed Desktop に登録するデバイスで使用される証明書コネクタがある場合、コネクタにエラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="fcf79-136">以下のアドバイザリの 1 つだけが状況に適用されますので、注意深く確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcf79-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="fcf79-137">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-137">**Advisory**</span></span>

<span data-ttu-id="fcf79-138">証明書コネクタはありません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-138">No certificate connectors are present.</span></span> <span data-ttu-id="fcf79-139">コネクタは必要ない可能性がありますが、Microsoft Managed Desktop デバイスのネットワーク接続に必要かどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-140">詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="fcf79-141">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-141">**Advisory**</span></span>

<span data-ttu-id="fcf79-142">少なくとも 1 つの証明書コネクタにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="fcf79-143">Microsoft Managed Desktop デバイスに証明書を提供するためにこのコネクタが必要な場合は、エラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="fcf79-144">詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="fcf79-145">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-145">**Advisory**</span></span>

<span data-ttu-id="fcf79-146">証明書コネクタが 1 つ以上あるので、エラーは報告されません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="fcf79-147">ただし、展開の準備として、Microsoft Managed Desktop デバイス用のコネクタを再利用するプロファイルを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-148">詳細については [、「Prepare certificates and network profiles for Microsoft Managed Desktop」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="fcf79-149">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="fcf79-149">Conditional access policies</span></span>

<span data-ttu-id="fcf79-150">条件付きアクセス ポリシーでは、Microsoft Managed Desktop が Intune と Azure の組織 (テナント) で Azure AD 組織 (テナント) を管理AD。</span><span class="sxs-lookup"><span data-stu-id="fcf79-150">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="fcf79-151">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-151">**Not ready**</span></span>

<span data-ttu-id="fcf79-152">すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="fcf79-153">登録時に、Microsoft Managed Desktop サービス アカウントを関連する条件付きアクセス ポリシーから除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-153">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="fcf79-154">登録後、Microsoft Endpoint Manager で Microsoft Managed Desktop 条件付きアクセス ポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fcf79-154">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="fcf79-155">これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-155">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="fcf79-156">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-156">**Advisory**</span></span>

<span data-ttu-id="fcf79-157">条件付きアクセス ポリシーを使用すると、Microsoft Managed Desktop が Microsoft Managed Desktop サービスを管理しなくる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-157">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="fcf79-158">登録時に、Microsoft Managed Desktop サービス アカウントを関連する条件付きアクセス ポリシーから除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-158">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="fcf79-159">これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-159">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="fcf79-160">**エラー**</span><span class="sxs-lookup"><span data-stu-id="fcf79-160">**Error**</span></span>

<span data-ttu-id="fcf79-161">Intune 管理者の役割には、このチェックに対する十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-161">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="fcf79-162">このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-162">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="fcf79-163">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcf79-163">Security Reader</span></span>
- <span data-ttu-id="fcf79-164">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="fcf79-164">Security Administrator</span></span>
- <span data-ttu-id="fcf79-165">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="fcf79-165">Conditional Access Administrator</span></span>
- <span data-ttu-id="fcf79-166">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcf79-166">Global Reader</span></span>
- <span data-ttu-id="fcf79-167">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="fcf79-167">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="fcf79-168">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="fcf79-168">Device Compliance policies</span></span>

<span data-ttu-id="fcf79-169">Azure 組織の Intune デバイス コンプライアンス ポリシー AD Microsoft Managed Desktop デバイスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-169">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="fcf79-170">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-170">**Not ready**</span></span>

<span data-ttu-id="fcf79-171">すべてのユーザーを対象とする少なくとも 1 つのコンプライアンス ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-171">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="fcf79-172">Microsoft Managed Desktop には、Microsoft 管理デスクトップ デバイスを対象とするコンプライアンス ポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fcf79-172">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="fcf79-173">ポリシーを変更して、Microsoft Managed Desktop ユーザーまたはデバイスAD含む特定の Azure クライアント グループを対象とします。</span><span class="sxs-lookup"><span data-stu-id="fcf79-173">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="fcf79-174">手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-174">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="fcf79-175">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-175">**Advisory**</span></span>

<span data-ttu-id="fcf79-176">Microsoft Managed Desktop ユーザーを対象としないコンプライアンス ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-176">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="fcf79-177">手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-177">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="fcf79-178">デバイス構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="fcf79-178">Device Configuration profiles</span></span>

<span data-ttu-id="fcf79-179">Azure 組織の Intune デバイス構成プロファイルAD、Microsoft Manage Desktop デバイスまたはユーザーをターゲットにしなける必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-179">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="fcf79-180">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-180">**Not ready**</span></span>

<span data-ttu-id="fcf79-181">すべてのユーザー、すべてのデバイス、または両方を対象とする構成プロファイルが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-181">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="fcf79-182">Microsoft Managed Desktop デバイスを含AD特定の Azure サーバー グループをターゲットにするようにプロファイルをリセットします。</span><span class="sxs-lookup"><span data-stu-id="fcf79-182">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-183">手順については [、「Microsoft Intune でカスタム設定を使用してプロファイルを作成する」を参照してください](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-183">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="fcf79-184">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-184">**Advisory**</span></span>

<span data-ttu-id="fcf79-185">Microsoft Managed Desktop デバイスまたはユーザーを含めなかった構成ポリシーが含まれるか確認します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-185">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="fcf79-186">手順については [、「Microsoft Intune でカスタム設定を使用してプロファイルを作成する」を参照してください](/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-186">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="fcf79-187">デバイスの種類の制限</span><span class="sxs-lookup"><span data-stu-id="fcf79-187">Device type restrictions</span></span>

<span data-ttu-id="fcf79-188">Microsoft Managed Desktop デバイスは、Intune への登録を許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="fcf79-189">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-189">**Not ready**</span></span>

<span data-ttu-id="fcf79-190">現在、少なくとも 1 つの登録制限ポリシーが Intune への Windows デバイスの登録を防止するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="fcf79-190">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="fcf79-191">「Microsoft Managed Desktop ユーザーを対象とする登録制限ポリシーごとに登録制限を設定する」の手順に従い **、Windows (MDM)** 設定を [許可] に **変更します**。 [](/mem/intune/enrollment/enrollment-restrictions-set)</span><span class="sxs-lookup"><span data-stu-id="fcf79-191">Follow the steps in [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="fcf79-192">ただし、個人所有の **Windows (MDM)** デバイスを [ブロック] に **設定できます**。</span><span class="sxs-lookup"><span data-stu-id="fcf79-192">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="fcf79-193">[登録の状態] ページ</span><span class="sxs-lookup"><span data-stu-id="fcf79-193">Enrollment Status Page</span></span>

<span data-ttu-id="fcf79-194">現在、登録状態ページ (ESP) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="fcf79-194">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="fcf79-195">この機能の Microsoft Managed Desktop パブリック プレビューに参加する場合は、このアイテムを無視できます。</span><span class="sxs-lookup"><span data-stu-id="fcf79-195">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="fcf79-196">詳細については [、「First-run experience with Autopilot」および「登録状態ページ」を参照してください](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-196">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="fcf79-197">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-197">**Not ready**</span></span>

<span data-ttu-id="fcf79-198">ESP の既定のプロファイルが [アプリとプロファイルの構成の進行状況 **を表示する] に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="fcf79-198">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="fcf79-199">この設定を無効にするか、「登録状態ページの設定」の手順に従って、Azure AD グループへの割り当てに Microsoft Managed Desktop デバイスが含まれるのを [確認します](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-199">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="fcf79-200">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-200">**Advisory**</span></span>

<span data-ttu-id="fcf79-201">[アプリとプロファイルの構成の進行状況を表示する] 設定を持つプロファイルが、Microsoft Managed Desktop デバイスを含む Azure AD グループに割り当てられていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-201">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-202">詳細については、「登録状態 [ページの設定」を参照してください](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-202">For more information, see [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="fcf79-203">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="fcf79-203">Microsoft Store for Business</span></span>

<span data-ttu-id="fcf79-204">Microsoft Store for Business を使用し、Microsoft Managed Desktop にポータル サイト アプリを展開し、ユーザーが Microsoft Project や Microsoft Visio などの一部のアプリを必要に応じてインストールできます (許可されている場合)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-204">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="fcf79-205">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-205">**Not ready**</span></span>

<span data-ttu-id="fcf79-206">Microsoft Store for Business は有効になっていないか、Intune と同期されません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="fcf79-207">詳細については [、「Microsoft Store for Business](/mem/intune/apps/windows-store-for-business) から Microsoft Intune で購入したボリューム アプリを管理する方法」および「デバイスに Intune ポータル をインストールする方法」 [を参照してください](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="fcf79-208">多要素認証</span><span class="sxs-lookup"><span data-stu-id="fcf79-208">Multifactor authentication</span></span>

<span data-ttu-id="fcf79-209">多要素認証では、Microsoft Managed Desktop が Intune および Azure 組織 (テナント) で Azure AD 組織 (テナント) を管理AD。</span><span class="sxs-lookup"><span data-stu-id="fcf79-209">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="fcf79-210">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-210">**Not ready**</span></span>

<span data-ttu-id="fcf79-211">すべてのユーザーに割り当てられている条件付きアクセスポリシーでは、必要に応じていくつかの多要素認証ポリシーが設定されています。</span><span class="sxs-lookup"><span data-stu-id="fcf79-211">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="fcf79-212">登録時に、Microsoft Managed Desktop サービス アカウントを関連する条件付きアクセス ポリシーから除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-212">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="fcf79-213">これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-213">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="fcf79-214">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-214">**Advisory**</span></span>

<span data-ttu-id="fcf79-215">条件付きアクセス ポリシーで多要素認証が必要になります。Microsoft Managed Desktop が Microsoft Managed Desktop サービスを管理する妨げる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-215">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="fcf79-216">登録時に、Microsoft Managed Desktop サービス アカウントを関連する条件付きアクセス ポリシーから除外し、これらのアカウントへのアクセスを制限するために新しい条件付きアクセス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-216">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="fcf79-217">これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-217">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="fcf79-218">**エラー**</span><span class="sxs-lookup"><span data-stu-id="fcf79-218">**Error**</span></span>

<span data-ttu-id="fcf79-219">Intune 管理者の役割には、このチェックに対する十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="fcf79-220">このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="fcf79-221">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcf79-221">Security Reader</span></span>
- <span data-ttu-id="fcf79-222">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="fcf79-222">Security Administrator</span></span>
- <span data-ttu-id="fcf79-223">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="fcf79-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="fcf79-224">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcf79-224">Global Reader</span></span>
- <span data-ttu-id="fcf79-225">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="fcf79-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="fcf79-226">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="fcf79-226">PowerShell scripts</span></span>

<span data-ttu-id="fcf79-227">Windows PowerShellは、Microsoft Managed Desktop デバイスを対象とする方法では割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="fcf79-228">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-228">**Advisory**</span></span>

<span data-ttu-id="fcf79-229">組織の Azure Windows PowerShellスクリプトAD Microsoft Manage Desktop デバイスまたはユーザーを対象とされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="fcf79-230">すべてのユーザー、すべてのデバイス、または両方を対象とする PowerShell スクリプトを割り当てない。</span><span class="sxs-lookup"><span data-stu-id="fcf79-230">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="fcf79-231">ポリシーを変更して、Microsoft Managed Desktop デバイスまたはユーザーを含AD特定の Azure AD グループを対象とする割り当てを使用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-231">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="fcf79-232">詳細については [、「Use PowerShell scripts on Windows 10 devices in Intune」を参照してください](/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-232">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="fcf79-233">Region</span><span class="sxs-lookup"><span data-stu-id="fcf79-233">Region</span></span>

<span data-ttu-id="fcf79-234">地域は Microsoft Managed Desktop でサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-234">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="fcf79-235">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-235">**Not ready**</span></span>

<span data-ttu-id="fcf79-236">現在、Azure AD組織の地域は Microsoft Managed Desktop でサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-236">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="fcf79-237">詳細については [、「Microsoft Managed Desktop でサポートされている地域と言語」を参照してください](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-237">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="fcf79-238">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-238">**Advisory**</span></span>

<span data-ttu-id="fcf79-239">Azure 組織が所属する 1 つ以上のADは、Microsoft Managed Desktop ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-239">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="fcf79-240">詳細については [、「Microsoft Managed Desktop でサポートされている地域と言語」を参照してください](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="fcf79-241">セキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="fcf79-241">Security baselines</span></span>

<span data-ttu-id="fcf79-242">セキュリティ ベースライン ポリシーは、Microsoft 管理デスクトップ デバイスを対象とすべきではありません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-242">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="fcf79-243">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-243">**Not ready**</span></span>

<span data-ttu-id="fcf79-244">すべてのユーザー、すべてのデバイス、または両方を対象とするセキュリティ 基準プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-244">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="fcf79-245">ポリシーを変更して、Microsoft 管理デスクトップ デバイスを含AD特定の Azure サーバー グループを対象とする割り当てを使用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-245">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-246">手順については、「セキュリティ 基準 [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-246">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="fcf79-247">登録時に、Microsoft Managed Desktop のすべてのデバイスに新しいセキュリティ 基準を適用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-247">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-248">登録後、Microsoft Endpoint Manager の [構成ポリシー]領域で Microsoft Managed Desktop セキュリティ 基準ポリシーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fcf79-248">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="fcf79-249">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-249">**Advisory**</span></span>

<span data-ttu-id="fcf79-250">Microsoft Managed Desktop デバイスを除外しているセキュリティ 基準ポリシーを必ず確認します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-250">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-251">手順については、「セキュリティ 基準 [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-251">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="fcf79-252">登録時に、Microsoft Managed Desktop のすべてのデバイスに新しいセキュリティ 基準を適用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-252">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-253">モダン **Workplace Devices -All** Azure AD グループは、Microsoft Managed Desktop に登録するときに作成する動的グループなので、登録後にこのグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 


### <a name="windows-apps"></a><span data-ttu-id="fcf79-254">Windows アプリ</span><span class="sxs-lookup"><span data-stu-id="fcf79-254">Windows apps</span></span>

<span data-ttu-id="fcf79-255">Microsoft Managed Desktop ユーザーに必要なアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="fcf79-256">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-256">**Advisory**</span></span>

<span data-ttu-id="fcf79-257">Microsoft Managed Desktop ユーザーが持つアプリのインベントリを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="fcf79-258">これらのアプリは Intune によって展開する必要があるから、既存の Intune アプリの再利用を評価します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-258">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="fcf79-259">ポータル サイトの使用を検討する (「デバイスに [Intune ポータル](../get-started/company-portal.md) サイトをインストールする」および「登録状態ページ (ESP)」を参照)、ユーザーにアプリを配布します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-259">Consider using Company Portal (see [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="fcf79-260">詳細については [、「Apps in Microsoft Managed Desktop](apps.md) and First-run experience with [Autopilot and the Enrollment Status Page」を参照してください](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="fcf79-261">Microsoft Endpoint Configuration Manager で Microsoft アカウント担当者にクエリを求め、Intune に移行する準備ができているアプリや調整が必要なアプリを特定できます。</span><span class="sxs-lookup"><span data-stu-id="fcf79-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="fcf79-262">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="fcf79-262">Windows Hello for Business</span></span>

<span data-ttu-id="fcf79-263">Microsoft Managed Desktop では、Windows Hello for Business を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="fcf79-264">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-264">**Not ready**</span></span>

<span data-ttu-id="fcf79-265">Windows Hello for Business が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="fcf79-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="fcf79-266">「Windows Hello for Business ポリシーの作成」 [の手順に従って有効にする](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="fcf79-266">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="fcf79-267">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-267">**Advisory**</span></span>

<span data-ttu-id="fcf79-268">Windows Hello for Business は設定されていない。</span><span class="sxs-lookup"><span data-stu-id="fcf79-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="fcf79-269">「ビジネス向け Windows Hello for Business ポリシーの作成 [」の手順に従って有効にしてください](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-269">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="fcf79-270">Windows 10 の更新プログラム リング</span><span class="sxs-lookup"><span data-stu-id="fcf79-270">Windows 10 update rings</span></span>

<span data-ttu-id="fcf79-271">Intune の "Windows 10 更新プログラム リング" ポリシーは、Microsoft マネージ デスクトップ デバイスを対象としなく必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="fcf79-272">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-272">**Not ready**</span></span>

<span data-ttu-id="fcf79-273">すべてのデバイス、すべてのユーザー、または両方を対象とする "更新リング" ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="fcf79-274">ポリシーを変更して、Microsoft 管理デスクトップ デバイスを含AD特定の Azure サーバー グループを対象とする割り当てを使用します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fcf79-275">手順については、「Intune で [Windows 10 ソフトウェア更新プログラムを管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-275">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="fcf79-276">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-276">**Advisory**</span></span>

<span data-ttu-id="fcf79-277">最新の Workplace Devices **-All Azure** ADグループを除外している更新リング ポリシーをADしてください。</span><span class="sxs-lookup"><span data-stu-id="fcf79-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="fcf79-278">これらのポリシーに Azure AD ユーザー グループを割り当てた場合は、Microsoft **Managed Desktop** ユーザーを追加するモダン Workplace -All Azure AD グループ (または同等のグループ) も除外している更新リング ポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcf79-278">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="fcf79-279">手順については、「Intune で [Windows 10 ソフトウェア更新プログラムを管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-279">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="fcf79-280">モダン ワークプレース デバイス **-All** および **Modern Workplace -All** Azure AD グループは、Microsoft Managed Desktop に登録するときに作成するグループなので、登録後にこのグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="fcf79-281">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="fcf79-281">Azure Active Directory settings</span></span>

<span data-ttu-id="fcf79-282">Azure Active Directory の設定には [、Azure](https://portal.azure.com)ポータルからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fcf79-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="fcf79-283">Intune の登録</span><span class="sxs-lookup"><span data-stu-id="fcf79-283">Intune enrollment</span></span>

<span data-ttu-id="fcf79-284">Azure 組織の Windows 10 AD Intune に自動的に登録できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-284">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="fcf79-285">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-285">**Advisory**</span></span>

<span data-ttu-id="fcf79-286">MDM User スコープ **が [一部] または** [すべて] **に設定されているの** に **、None** は設定 **されていないか確認します**。</span><span class="sxs-lookup"><span data-stu-id="fcf79-286">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="fcf79-287">[一部] を **選択** した場合は、登録後に戻って、すべての Microsoft 管理デスクトップユーザーを対象とするグループまたは同等のグループの Modern **Workplace -All** Azure AD グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-287">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="fcf79-288">「Microsoft [Intune を使用して Windows デバイスの登録をセットアップする」を参照してください](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-288">See [Set up enrollment for Windows devices by using Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="fcf79-289">アドホック サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="fcf79-289">Ad hoc subscriptions</span></span>

<span data-ttu-id="fcf79-290">("false" に設定されている場合) エンタープライズ状態ローミングが正常に動作しない可能性がある設定を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-290">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="fcf79-291">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-291">**Advisory**</span></span>

<span data-ttu-id="fcf79-292">**AllowAdHocSubscriptions が True** に設定されている必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="fcf79-292">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="fcf79-293">それ以外の場合、エンタープライズ状態ローミングが機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-293">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="fcf79-294">詳細については [、「Set-MsolCompanySettings」を参照してください](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-294">For more information, see [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="fcf79-295">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="fcf79-295">Enterprise State Roaming</span></span>

<span data-ttu-id="fcf79-296">エンタープライズ状態ローミングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-296">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="fcf79-297">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-297">**Advisory**</span></span>

<span data-ttu-id="fcf79-298">[すべて] または [選択したグループ] に対して **エンタープライズ状態ローミング\*\*\*\*が有効になっているか確認** します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-298">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="fcf79-299">詳細については [、「Enable Enterprise State Roaming in Azure Active Directory」を参照してください](/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-299">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="fcf79-300">ライセンス</span><span class="sxs-lookup"><span data-stu-id="fcf79-300">Licenses</span></span>

<span data-ttu-id="fcf79-301">Microsoft Managed Desktop を使用するには、多数のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="fcf79-301">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="fcf79-302">**準備ができていない**</span><span class="sxs-lookup"><span data-stu-id="fcf79-302">**Not Ready**</span></span>

<span data-ttu-id="fcf79-303">Microsoft Managed Desktop を使用するために必要なすべてのライセンスを持っている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-303">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="fcf79-304">詳細については [、「Microsoft Managed Desktop テクノロジ」および「](../intro/technologies.md) ライセンス [の詳細」を参照してください](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-304">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="microsoft-managed-desktop-service-accounts"></a><span data-ttu-id="fcf79-305">Microsoft Managed Desktop サービス アカウント</span><span class="sxs-lookup"><span data-stu-id="fcf79-305">Microsoft Managed Desktop service accounts</span></span>

<span data-ttu-id="fcf79-306">一部のアカウント名は、Microsoft Managed Desktop サービスを管理するために Microsoft Managed Desktop によって作成されたアカウント名と競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-306">Certain account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.</span></span>

<span data-ttu-id="fcf79-307">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-307">**Not ready**</span></span>

<span data-ttu-id="fcf79-308">Microsoft Managed Desktop によって作成されたアカウント名と競合するアカウント名が少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-308">You have at least one account name that will conflict with account names created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="fcf79-309">これらのアカウント名を除外するには、Microsoft アカウント担当者と一緒に作業します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-309">Work with your Microsoft account representative to exclude these account names.</span></span> <span data-ttu-id="fcf79-310">セキュリティ リスクを最小限に抑えるために、アカウント名を一般に一覧表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-310">We don't list the account names publicly to minimize security risk.</span></span> 


### <a name="security-administrator-roles"></a><span data-ttu-id="fcf79-311">セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="fcf79-311">Security administrator roles</span></span>

<span data-ttu-id="fcf79-312">特定のセキュリティ ロールを持つユーザーには、それらの役割が Microsoft Defender for Endpoint に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-312">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="fcf79-313">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-313">**Advisory**</span></span>

<span data-ttu-id="fcf79-314">Azure AD組織でこれらの役割に割り当てられているユーザーがある場合は、それらの役割も Microsoft Defender for Endpoint に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-314">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="fcf79-315">それ以外の場合、これらの役割を持つ管理者は管理ポータルにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-315">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="fcf79-316">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="fcf79-316">Security Operator</span></span>
- <span data-ttu-id="fcf79-317">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="fcf79-317">Global Reader</span></span>

<span data-ttu-id="fcf79-318">詳細については、「役割ベースの [アクセス制御の役割を作成および管理する」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-318">For more information, see [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="fcf79-319">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="fcf79-319">Security default</span></span>

<span data-ttu-id="fcf79-320">Azure Active Directory のセキュリティの既定値では、Microsoft Managed Desktop がデバイスを管理できません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-320">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="fcf79-321">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="fcf79-321">**Not ready**</span></span>

<span data-ttu-id="fcf79-322">セキュリティの既定値を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="fcf79-322">You have Security defaults turned on.</span></span> <span data-ttu-id="fcf79-323">セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-323">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="fcf79-324">詳細については、「一般的な条件付 [きアクセス ポリシー」を参照してください](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-324">For more information, see [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="fcf79-325">セルフサービス のパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="fcf79-325">Self-service Password Reset</span></span>

<span data-ttu-id="fcf79-326">セルフサービス パスワードリセット (SSPR) は、Microsoft Managed Desktop サービス アカウントを除くすべての Microsoft 管理デスクトップ ユーザーに対して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="fcf79-326">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="fcf79-327">詳細については、「チュートリアル: ユーザーが自分のアカウントのロックを解除したり、Azure Active Directory セルフサービス のパスワードリセットを使用してパスワードをリセットしたりするようにする」 [を参照してください](/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-327">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="fcf79-328">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-328">**Advisory**</span></span>

<span data-ttu-id="fcf79-329">SSPR **Selected 設定** に Microsoft Managed Desktop ユーザーが含まれていますが、Microsoft Managed Desktop サービス アカウントは除外します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-329">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="fcf79-330">SSPR が有効になっている場合、Microsoft Managed Desktop サービス アカウントは期待通り動作しません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-330">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="fcf79-331">標準ユーザー ロール</span><span class="sxs-lookup"><span data-stu-id="fcf79-331">Standard user role</span></span>

<span data-ttu-id="fcf79-332">グローバル管理者とデバイス管理者の Azure ADロールに割り当てられているユーザー以外は、Microsoft Managed Desktop ユーザーは、ローカル管理者特権のない標準ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="fcf79-332">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="fcf79-333">Microsoft Managed Desktop デバイスを起動すると、他のすべてのユーザーに標準のユーザー ロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="fcf79-333">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="fcf79-334">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-334">**Advisory**</span></span>

<span data-ttu-id="fcf79-335">Microsoft Managed Desktop ユーザーは、登録後に Microsoft Managed Desktop デバイスに対するローカル管理者特権を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcf79-335">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="fcf79-336">エンタープライズ向け Microsoft  365 アプリ</span><span class="sxs-lookup"><span data-stu-id="fcf79-336">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="fcf79-337">OneDrive</span><span class="sxs-lookup"><span data-stu-id="fcf79-337">OneDrive</span></span>

<span data-ttu-id="fcf79-338">[ **特定のドメインに参加** している PC でのみ同期を許可する] 設定は、Microsoft マネージ デスクトップと競合します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-338">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="fcf79-339">OneDrive 管理センターで OneDrive の設定に [アクセスできます](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="fcf79-339">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="fcf79-340">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="fcf79-340">**Advisory**</span></span>

<span data-ttu-id="fcf79-341">[特定のドメインに参加している PC でのみ同期を許可 **する] 設定を使用** しています。</span><span class="sxs-lookup"><span data-stu-id="fcf79-341">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="fcf79-342">この設定は、Microsoft Managed Desktop では機能しません。</span><span class="sxs-lookup"><span data-stu-id="fcf79-342">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="fcf79-343">この設定を無効にし、代わりに条件付きアクセス ポリシーを使用する OneDrive を設定します。</span><span class="sxs-lookup"><span data-stu-id="fcf79-343">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="fcf79-344">ヘルプについては [、「条件付きアクセスの展開を計画する](/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcf79-344">See [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>