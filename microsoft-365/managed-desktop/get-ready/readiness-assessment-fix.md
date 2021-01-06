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
ms.openlocfilehash: 3c3c0d21ca93c0d93d17cefbc6ce630d00a16d09
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760126"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="dbd78-104">準備評価ツールで見つかった問題を修正する</span><span class="sxs-lookup"><span data-stu-id="dbd78-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="dbd78-105">チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="dbd78-106">結果</span><span class="sxs-lookup"><span data-stu-id="dbd78-106">Result</span></span>  |<span data-ttu-id="dbd78-107">意味</span><span class="sxs-lookup"><span data-stu-id="dbd78-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="dbd78-108">準備完了</span><span class="sxs-lookup"><span data-stu-id="dbd78-108">Ready</span></span>     | <span data-ttu-id="dbd78-109">登録を完了する前に、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="dbd78-110">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="dbd78-110">Advisory</span></span>    | <span data-ttu-id="dbd78-111">登録とユーザーの最適なエクスペリエンスを得る場合は、ツールまたはこの記事の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="dbd78-112">登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="dbd78-113">使用不可能</span><span class="sxs-lookup"><span data-stu-id="dbd78-113">Not ready</span></span> | <span data-ttu-id="dbd78-114">*これらの問題を解決しない場合、登録は失敗します。*</span><span class="sxs-lookup"><span data-stu-id="dbd78-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="dbd78-115">ツールまたはこの記事の手順に従って解決します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="dbd78-116">Error</span><span class="sxs-lookup"><span data-stu-id="dbd78-116">Error</span></span> | <span data-ttu-id="dbd78-117">使用している Azure Active Director (AD) ロールに、このチェックを実行するための十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="dbd78-118">このツールによって報告される結果には、設定を実行した特定の時点での設定の状態だけが反映されます。</span><span class="sxs-lookup"><span data-stu-id="dbd78-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="dbd78-119">後で Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに変更を加えた場合、"準備完了" だったアイテムは "準備ができていない" 状態になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="dbd78-120">Microsoft マネージド デスクトップの操作で問題が発生しないようにするには、ポリシーを変更する前に、この記事で説明されている特定の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="dbd78-121">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="dbd78-121">Microsoft Intune settings</span></span>

<span data-ttu-id="dbd78-122">Intune の設定には、Microsoft Endpoint Manager 管理センターから [アクセスできます](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="dbd78-123">Autopilot 展開プロファイル</span><span class="sxs-lookup"><span data-stu-id="dbd78-123">Autopilot deployment profile</span></span>

<span data-ttu-id="dbd78-124">Microsoft マネージド デスクトップで使用される割り当て済みグループまたは動的グループを対象とする既存の Autopilot プロファイルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbd78-125">Microsoft マネージド デスクトップでは、Autopilot を使用して新しいデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="dbd78-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="dbd78-126">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-126">**Not ready**</span></span>

<span data-ttu-id="dbd78-127">すべてのデバイスに割り当てられている Autopilot プロファイルがある。</span><span class="sxs-lookup"><span data-stu-id="dbd78-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="dbd78-128">手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="dbd78-129">Microsoft マネージド デスクトップの登録後、Autopilot ポリシーを設定して **、Modern Workplace Devices -All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="dbd78-130">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-130">**Advisory**</span></span>

<span data-ttu-id="dbd78-131">Autopilot プロファイルが、登録時に作成される Microsoft マネージド デスクトップ デバイスを含む、割り当て済みまたは動的な Azure AD グループを対象とするようにします。</span><span class="sxs-lookup"><span data-stu-id="dbd78-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="dbd78-132">手順については [、「Windows Autopilot を使用して Intune に Windows デバイスを登録する」を参照してください](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="dbd78-133">Microsoft マネージド デスクトップの登録後、Autopilot ポリシーを設定して **、Modern Workplace Devices -All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-133">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="dbd78-134">証明書コネクタ</span><span class="sxs-lookup"><span data-stu-id="dbd78-134">Certificate connectors</span></span>

<span data-ttu-id="dbd78-135">Microsoft マネージド デスクトップに登録するデバイスで使用されている証明書コネクタがある場合、コネクタにエラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-135">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="dbd78-136">次の勧告の 1 つだけが状況に適用されます。そのため、慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="dbd78-137">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-137">**Advisory**</span></span>

<span data-ttu-id="dbd78-138">証明書コネクタは存在しない。</span><span class="sxs-lookup"><span data-stu-id="dbd78-138">No certificate connectors are present.</span></span> <span data-ttu-id="dbd78-139">コネクタは必要ない可能性がありますが、Microsoft マネージド デスクトップ デバイスへのネットワーク接続に必要かどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-140">詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="dbd78-141">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-141">**Advisory**</span></span>

<span data-ttu-id="dbd78-142">少なくとも 1 つの証明書コネクタにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="dbd78-143">Microsoft マネージド デスクトップ デバイスへの接続にこのコネクタが必要な場合は、エラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-143">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="dbd78-144">詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="dbd78-145">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-145">**Advisory**</span></span>

<span data-ttu-id="dbd78-146">証明書コネクタが 1 つ以上あるので、エラーは報告されません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="dbd78-147">ただし、Microsoft マネージド デスクトップ デバイス用のコネクタを再利用するプロファイルを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-147">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-148">詳細については [、「Microsoft マネージド デスクトップの証明書とネットワーク プロファイルを準備する」を参照してください](certs-wifi-lan.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="dbd78-149">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="dbd78-149">Conditional access policies</span></span>

<span data-ttu-id="dbd78-150">Azure 組織の条件付きアクセス ポリシー AD、Microsoft Manage Desktop ユーザーを対象にしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-150">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="dbd78-151">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-151">**Not ready**</span></span>

<span data-ttu-id="dbd78-152">すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="dbd78-153">登録時に作成される Microsoft マネージド デスクトップ サービス アカウントの Azure AD グループを含む特定の Azure AD グループをターゲットにするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="dbd78-153">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="dbd78-154">手順については、「条件付きアクセス [: ユーザーとグループ」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-154">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="dbd78-155">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-155">**Advisory**</span></span>

<span data-ttu-id="dbd78-156">モダン Workplace Service アカウント **Azure** グループを除外した条件付きアクセス ポリシー ADしてください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-156">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="dbd78-157">手順については、「条件付きアクセス [の調整」を参照してください](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-157">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="dbd78-158">モダン **Workplace Service アカウント** Azure ADグループは、登録時にサービス用に作成される動的なグループです。</span><span class="sxs-lookup"><span data-stu-id="dbd78-158">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="dbd78-159">登録後に、このグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-159">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="dbd78-160">これらのサービス アカウントの詳細については、「標準の運用手順 [」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-160">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="dbd78-161">**エラー**</span><span class="sxs-lookup"><span data-stu-id="dbd78-161">**Error**</span></span>

<span data-ttu-id="dbd78-162">Intune 管理者ロールには、このチェックのための十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-162">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="dbd78-163">このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-163">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="dbd78-164">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="dbd78-164">Security Reader</span></span>
- <span data-ttu-id="dbd78-165">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="dbd78-165">Security Administrator</span></span>
- <span data-ttu-id="dbd78-166">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="dbd78-166">Conditional Access Administrator</span></span>
- <span data-ttu-id="dbd78-167">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="dbd78-167">Global Reader</span></span>
- <span data-ttu-id="dbd78-168">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="dbd78-168">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="dbd78-169">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="dbd78-169">Device Compliance policies</span></span>

<span data-ttu-id="dbd78-170">Azure 組織の Intune デバイス コンプライアンス ポリシー AD Microsoft マネージド デスクトップ ユーザーを対象にしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-170">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="dbd78-171">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-171">**Not ready**</span></span>

<span data-ttu-id="dbd78-172">すべてのユーザーを対象とするコンプライアンス ポリシーが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-172">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="dbd78-173">Microsoft マネージド デスクトップ ユーザーを含AD Azure ADグループを対象にするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="dbd78-173">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="dbd78-174">手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="dbd78-175">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-175">**Advisory**</span></span>

<span data-ttu-id="dbd78-176">Microsoft マネージド デスクトップ ユーザーが含まれるコンプライアンス ポリシーを含めなかったか確認します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-176">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="dbd78-177">手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="dbd78-178">デバイス構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="dbd78-178">Device Configuration policies</span></span>

<span data-ttu-id="dbd78-179">Azure 組織の Intune デバイス構成ポリシー AD Microsoft Manage Desktop デバイスまたはユーザーを対象にしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-179">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="dbd78-180">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-180">**Not ready**</span></span>

<span data-ttu-id="dbd78-181">少なくとも 1 つの構成ポリシーで、すべてのユーザー、すべてのデバイス、または両方を対象とします。</span><span class="sxs-lookup"><span data-stu-id="dbd78-181">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="dbd78-182">Microsoft マネージド デスクトップ デバイスを含AD特定の Azure AD グループをターゲットにするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="dbd78-182">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-183">手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-183">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="dbd78-184">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-184">**Advisory**</span></span>

<span data-ttu-id="dbd78-185">Microsoft マネージド デスクトップ デバイスまたはユーザーが含まれるコンプライアンス ポリシーを含めなかったか確認します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-185">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="dbd78-186">手順については [、「Microsoft Intune でコンプライアンス ポリシーを作成する」を参照してください](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-186">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="dbd78-187">デバイスの種類の制限</span><span class="sxs-lookup"><span data-stu-id="dbd78-187">Device type restrictions</span></span>

<span data-ttu-id="dbd78-188">Microsoft マネージド デスクトップ デバイスは、Intune への登録を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="dbd78-189">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-189">**Not ready**</span></span>

<span data-ttu-id="dbd78-190">「登録の制限 [を設定する」の手順に従って、](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 設定を [許可] に **変更します**。</span><span class="sxs-lookup"><span data-stu-id="dbd78-190">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="dbd78-191">[登録の状態] ページ</span><span class="sxs-lookup"><span data-stu-id="dbd78-191">Enrollment Status Page</span></span>

<span data-ttu-id="dbd78-192">現在、登録ステータス ページ (ESP) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="dbd78-192">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="dbd78-193">この機能のパブリック プレビューに参加している場合は、この項目を無視できます。</span><span class="sxs-lookup"><span data-stu-id="dbd78-193">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="dbd78-194">詳細については [、「Autopilot での最初の実行エクスペリエンスと [登録の状態] ページ」を参照してください](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-194">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="dbd78-195">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-195">**Not ready**</span></span>

<span data-ttu-id="dbd78-196">ESP の既定のプロファイルは、[アプリとプロファイルの構成 **の進行状況を表示する] に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="dbd78-196">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="dbd78-197">この設定を無効にするか、「登録状態の設定」ページの手順に従って、Azure AD グループへの割り当てに Microsoft マネージド デスクトップ デバイスが含まれるのを確認 [します](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-197">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="dbd78-198">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-198">**Advisory**</span></span>

<span data-ttu-id="dbd78-199">[アプリとプロファイルの構成の進行状況の表示] 設定を持つプロファイルが、Microsoft マネージド デスクトップ デバイスを含む Azure AD グループに割り当てられていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-199">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-200">詳細については、「登録状態 [ページのセットアップ」を参照してください](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-200">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="dbd78-201">Intune 登録</span><span class="sxs-lookup"><span data-stu-id="dbd78-201">Intune enrollment</span></span>

<span data-ttu-id="dbd78-202">Azure 組織の Windows 10 デバイスAD Intune に自動的に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-202">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="dbd78-203">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-203">**Advisory**</span></span>

<span data-ttu-id="dbd78-204">MDM ユーザー スコープが [なし] ではなく [ **一部]** または [ **すべて]** に設定されている必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="dbd78-204">Make sure the MDM User scope is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="dbd78-205">[一部] **を選択** した場合は、登録後に戻って、 **モダン Workplace -All** Azure AD グループを選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="dbd78-205">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="dbd78-206">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="dbd78-206">Microsoft Store for Business</span></span>

<span data-ttu-id="dbd78-207">ビジネス向け Microsoft Store を使用して、ポータル サイトをダウンロードして、Microsoft Project や Microsoft Visio などの一部のアプリを展開できます。</span><span class="sxs-lookup"><span data-stu-id="dbd78-207">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="dbd78-208">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-208">**Not ready**</span></span>

<span data-ttu-id="dbd78-209">ビジネス向け Microsoft Store が有効になっていないか、Intune と同期されていない。</span><span class="sxs-lookup"><span data-stu-id="dbd78-209">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="dbd78-210">詳細については、ビジネス向け Microsoft Store からボリューム購入したアプリを [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) で管理し、デバイスに Intune ポータル サイトをインストールする方法を [参照してください](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-210">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="dbd78-211">多要素認証</span><span class="sxs-lookup"><span data-stu-id="dbd78-211">Multifactor authentication</span></span>

<span data-ttu-id="dbd78-212">多要素認証を Microsoft マネージド デスクトップ サービス アカウントに誤って適用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-212">Multifactor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="dbd78-213">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-213">**Not ready**</span></span>

<span data-ttu-id="dbd78-214">すべてのユーザーに割り当てられている条件付きアクセス ポリシーに対して、いくつかの多要素認証 (MFA) ポリシーが "必須" に設定されている。</span><span class="sxs-lookup"><span data-stu-id="dbd78-214">You have some multifactor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="dbd78-215">Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-215">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-216">詳細については、「条件付きアクセス ポリシー [と条件付きアクセス](#conditional-access-policies) : すべてのユーザーに MFA を要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="dbd78-217">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-217">**Advisory**</span></span>

<span data-ttu-id="dbd78-218">MFA を必要とする条件付きアクセス ポリシーで **、Modern Workplace -All** Azure ADしてください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-218">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="dbd78-219">詳細については、「条件付きアクセス ポリシー [と条件付きアクセス](#conditional-access-policies) : すべてのユーザーに MFA を要求する」 [を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-219">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="dbd78-220">**Modern Workplace -All** Azure AD グループは、Microsoft マネージド デスクトップに登録するときに作成される動的なグループです。そのため、登録後にこのグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-220">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="dbd78-221">**エラー**</span><span class="sxs-lookup"><span data-stu-id="dbd78-221">**Error**</span></span>

<span data-ttu-id="dbd78-222">Intune 管理者ロールには、このチェックのための十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-222">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="dbd78-223">このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-223">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="dbd78-224">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="dbd78-224">Security Reader</span></span>
- <span data-ttu-id="dbd78-225">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="dbd78-225">Security Administrator</span></span>
- <span data-ttu-id="dbd78-226">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="dbd78-226">Conditional Access Administrator</span></span>
- <span data-ttu-id="dbd78-227">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="dbd78-227">Global Reader</span></span>
- <span data-ttu-id="dbd78-228">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="dbd78-228">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="dbd78-229">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="dbd78-229">PowerShell scripts</span></span>

<span data-ttu-id="dbd78-230">Windows PowerShellは、Microsoft マネージド デスクトップ デバイスをターゲットとする方法では割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-230">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="dbd78-231">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-231">**Advisory**</span></span>

<span data-ttu-id="dbd78-232">Azure Windows PowerShellのスクリプトが、Microsoft ADデスクトップ デバイスやユーザーを対象としなにされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-232">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="dbd78-233">PowerShell スクリプトを、すべてのユーザー、すべてのデバイス、または両方を対象に割り当てない。</span><span class="sxs-lookup"><span data-stu-id="dbd78-233">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="dbd78-234">Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-234">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-235">詳細については、「Intune で [Windows 10 デバイスで PowerShell](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)スクリプトを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-235">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="dbd78-236">Region</span><span class="sxs-lookup"><span data-stu-id="dbd78-236">Region</span></span>

<span data-ttu-id="dbd78-237">お客様の地域は、Microsoft マネージド デスクトップでサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-237">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="dbd78-238">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-238">**Not ready**</span></span>

<span data-ttu-id="dbd78-239">Azure AD組織の地域は、Microsoft マネージド デスクトップでは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-239">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbd78-240">詳細については [、Microsoft マネージド デスクトップでサポートされている地域と言語を参照してください](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="dbd78-241">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-241">**Advisory**</span></span>

<span data-ttu-id="dbd78-242">組織の Azure ADがある国の 1 つ以上は、Microsoft マネージド デスクトップではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-242">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbd78-243">詳細については [、Microsoft マネージド デスクトップでサポートされている地域と言語を参照してください](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="dbd78-244">セキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="dbd78-244">Security baselines</span></span>

<span data-ttu-id="dbd78-245">セキュリティ基本ポリシーは、Microsoft マネージド デスクトップ デバイスを対象としなにしろ。</span><span class="sxs-lookup"><span data-stu-id="dbd78-245">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="dbd78-246">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-246">**Not ready**</span></span>

<span data-ttu-id="dbd78-247">すべてのユーザー、すべてのデバイス、または両方を対象とするセキュリティベースライン プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-247">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="dbd78-248">Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-248">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-249">手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="dbd78-250">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-250">**Advisory**</span></span>

<span data-ttu-id="dbd78-251">Microsoft マネージド デスクトップ デバイスを除外したセキュリティ基本ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-251">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-252">手順については、「セキュリティベースライン [を使用して Intune で Windows 10 デバイスを構成する」を参照してください](https://docs.microsoft.com/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="dbd78-253">**Modern Workplace Devices -All** Azure AD グループは、Microsoft マネージド デスクトップに登録するときに作成される動的なグループです。そのため、登録後にこのグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="dbd78-254">Windows アプリ</span><span class="sxs-lookup"><span data-stu-id="dbd78-254">Windows apps</span></span>

<span data-ttu-id="dbd78-255">Microsoft マネージド デスクトップ ユーザーに必要なアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="dbd78-256">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-256">**Advisory**</span></span>

<span data-ttu-id="dbd78-257">Microsoft マネージド デスクトップ ユーザーが持つアプリのインベントリを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="dbd78-258">これらのアプリは Intune で展開する必要があるから、既存の Intune アプリの再使用を評価します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-258">Since these apps must be deployed by Intune, evaluate re-using existing Intune apps.</span></span> <span data-ttu-id="dbd78-259">ポータル サイトの使用を検討します (「デバイスへの [Intune ポータル](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) サイトのインストールと登録状態ページ (ESP)」を参照して、ユーザーにアプリを配布します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-259">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="dbd78-260">詳細については [、「Microsoft マネージド](apps.md) デスクトップのアプリ」と [「Autopilot](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)での初回実行時エクスペリエンス」および「登録状態ページ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="dbd78-261">Microsoft Endpoint Configuration Manager で Microsoft アカウント担当者にクエリを求め、Intune に移行する準備ができているアプリや調整が必要なアプリを特定できます。</span><span class="sxs-lookup"><span data-stu-id="dbd78-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="dbd78-262">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="dbd78-262">Windows Hello for Business</span></span>

<span data-ttu-id="dbd78-263">Microsoft マネージド デスクトップでは、Windows Hello for Business を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="dbd78-264">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-264">**Not ready**</span></span>

<span data-ttu-id="dbd78-265">Windows Hello for Business は無効です。</span><span class="sxs-lookup"><span data-stu-id="dbd78-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="dbd78-266">「Windows Hello for Business ポリシーを作成する」の [手順に従って有効にする](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="dbd78-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="dbd78-267">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-267">**Advisory**</span></span>

<span data-ttu-id="dbd78-268">Windows Hello for Business がセットアップされていない。</span><span class="sxs-lookup"><span data-stu-id="dbd78-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="dbd78-269">「Windows Hello for Business ポリシーを作成する」の手順 [に従って有効にしてください](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-269">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="dbd78-270">Windows 10 の更新リング</span><span class="sxs-lookup"><span data-stu-id="dbd78-270">Windows 10 update rings</span></span>

<span data-ttu-id="dbd78-271">Intune の "Windows 10 更新リング" ポリシーは、Microsoft マネージド デスクトップ デバイスをターゲットにしなけずにしてください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="dbd78-272">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-272">**Not ready**</span></span>

<span data-ttu-id="dbd78-273">すべてのデバイス、すべてのユーザー、または両方を対象とする "更新リング" ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="dbd78-274">Microsoft マネージド デスクトップ デバイスを含む特定の Azure AD グループを対象とする Assignment を使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="dbd78-275">手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="dbd78-276">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-276">**Advisory**</span></span>

<span data-ttu-id="dbd78-277">モダン Workplace **Devices -All** Azure AD グループから除外した更新リング ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="dbd78-278">これらのポリシーに Azure AD ユーザー グループを割り当てた場合は、Microsoft マネージド デスクトップ ユーザーを含む **Modern Workplace -All** Azure AD グループも除外している更新リング ポリシーを必ず除外してください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-278">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="dbd78-279">手順については、「Intune での [Windows 10 ソフトウェア更新プログラムの管理」を参照してください](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-279">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="dbd78-280">Modern **Workplace Devices -All** グループと **Modern Workplace -All** Azure AD グループの両方に、Microsoft マネージド デスクトップに登録するときに作成したグループが割り当てられるので、登録後にこのグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="dbd78-281">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="dbd78-281">Azure Active Directory settings</span></span>

<span data-ttu-id="dbd78-282">Azure Portal で Azure Active Directory の設定に [アクセスできます](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="dbd78-283">アドホック サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="dbd78-283">Ad hoc subscriptions</span></span>

<span data-ttu-id="dbd78-284">("false" に設定されている場合)、エンタープライズ状態ローミングが正しく動作しない可能性がある設定を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-284">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="dbd78-285">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-285">**Advisory**</span></span>

<span data-ttu-id="dbd78-286">**AllowAdHocSubscriptions** が **True** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="dbd78-286">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="dbd78-287">それ以外の場合は、Enterprise State Roaming が機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-287">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="dbd78-288">詳細については [、「Set-MsolCompanySettings」を参照してください](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-288">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="dbd78-289">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="dbd78-289">Enterprise State Roaming</span></span>

<span data-ttu-id="dbd78-290">Enterprise State Roaming を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-290">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="dbd78-291">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-291">**Advisory**</span></span>

<span data-ttu-id="dbd78-292">[すべて] または [選択したグループ] に対して Enterprise State Roaming が有効 **になっているか確認** します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-292">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="dbd78-293">詳細については [、「Azure Active Directory でエンタープライズ状態ローミングを有効にする」を参照してください](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-293">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="dbd78-294">ライセンス</span><span class="sxs-lookup"><span data-stu-id="dbd78-294">Licenses</span></span>

<span data-ttu-id="dbd78-295">Microsoft マネージド デスクトップを使用するには、多数のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dbd78-295">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="dbd78-296">**準備ができていない**</span><span class="sxs-lookup"><span data-stu-id="dbd78-296">**Not Ready**</span></span>

<span data-ttu-id="dbd78-297">Microsoft マネージド デスクトップを使用するために必要なライセンスの一部を持っている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-297">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbd78-298">詳細については [、Microsoft マネージド デスクトップテクノロジと](../intro/technologies.md) ライセンスの [詳細を参照してください](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-298">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="dbd78-299">セキュリティ アカウント名</span><span class="sxs-lookup"><span data-stu-id="dbd78-299">Security account names</span></span>

<span data-ttu-id="dbd78-300">一部のセキュリティ アカウント名は、Microsoft マネージド デスクトップで作成された名前と競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-300">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="dbd78-301">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-301">**Not ready**</span></span>

<span data-ttu-id="dbd78-302">Microsoft マネージド デスクトップで作成されたアカウント名と競合するアカウント名が少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-302">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbd78-303">Microsoft アカウント担当者と一緒に、これらのアカウント名を除外します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-303">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="dbd78-304">セキュリティ管理者ロール</span><span class="sxs-lookup"><span data-stu-id="dbd78-304">Security administrator roles</span></span>

<span data-ttu-id="dbd78-305">特定のセキュリティ ロールを持つユーザーには、Microsoft Defender for Endpoint に割り当てられているユーザーが必要です。</span><span class="sxs-lookup"><span data-stu-id="dbd78-305">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="dbd78-306">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-306">**Advisory**</span></span>

<span data-ttu-id="dbd78-307">Azure AD 組織でこれらの役割に割り当てられているユーザーがある場合は、それらのユーザーに、エンドポイント用 Microsoft Defender でこれらの役割も割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-307">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="dbd78-308">そうしないと、これらの役割を持つ管理者は管理ポータルにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-308">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="dbd78-309">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="dbd78-309">Security Operator</span></span>
- <span data-ttu-id="dbd78-310">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="dbd78-310">Global Reader</span></span>

<span data-ttu-id="dbd78-311">詳細については、「役割ベースのアクセス [制御の役割の作成と管理」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-311">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="dbd78-312">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="dbd78-312">Security default</span></span>

<span data-ttu-id="dbd78-313">Azure Active Directory のセキュリティの既定値により、Microsoft マネージド デスクトップでデバイスを管理できません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-313">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="dbd78-314">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="dbd78-314">**Not ready**</span></span>

<span data-ttu-id="dbd78-315">セキュリティの既定値を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="dbd78-315">You have Security defaults turned on.</span></span> <span data-ttu-id="dbd78-316">セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-316">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="dbd78-317">詳細については、「一般的な条件付 [きアクセス ポリシー」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-317">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="dbd78-318">セルフサービスによるパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="dbd78-318">Self-service Password Reset</span></span>

<span data-ttu-id="dbd78-319">セルフサービスによるパスワードリセット (SSPR) は、Microsoft マネージド デスクトップ サービス アカウントを除くすべての Microsoft マネージド デスクトップ ユーザーに対して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-319">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="dbd78-320">詳細については、「チュートリアル: Azure Active Directory のセルフサービス によるパスワードのリセットを使用して、ユーザーが自分のアカウントのロックを解除したり、パスワード [をリセットしたりできる」を参照してください](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-320">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="dbd78-321">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-321">**Advisory**</span></span>

<span data-ttu-id="dbd78-322">SSPR の **選択した** 設定に Microsoft マネージド デスクトップ デバイスが含まれていますが、Microsoft マネージド デスクトップ サービス アカウントは除外します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-322">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="dbd78-323">SSPR が有効な場合、Microsoft マネージド デスクトップ サービス アカウントは期待通り動作しません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-323">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="dbd78-324">標準ユーザー ロール</span><span class="sxs-lookup"><span data-stu-id="dbd78-324">Standard user role</span></span>

<span data-ttu-id="dbd78-325">グローバル管理者とデバイス管理者の Azure AD ロールが割り当てられているユーザー以外に、Microsoft マネージド デスクトップ ユーザーは、ローカル管理者特権のない標準ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="dbd78-325">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="dbd78-326">他のすべてのユーザーには、Microsoft マネージド デスクトップ デバイスの起動時に標準のユーザー ロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dbd78-326">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="dbd78-327">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-327">**Advisory**</span></span>

<span data-ttu-id="dbd78-328">Microsoft マネージド デスクトップ ユーザーは、登録後に Microsoft マネージド デスクトップ デバイスに対するローカル管理者特権を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="dbd78-328">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="dbd78-329">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="dbd78-329">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="dbd78-330">OneDrive</span><span class="sxs-lookup"><span data-stu-id="dbd78-330">OneDrive</span></span>

<span data-ttu-id="dbd78-331">特定 **のドメインに参加している PC** でのみ同期を許可する設定は、Microsoft マネージド デスクトップと競合します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-331">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbd78-332">OneDrive 管理センターで OneDrive の設定に [アクセスできます](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="dbd78-332">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="dbd78-333">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="dbd78-333">**Advisory**</span></span>

<span data-ttu-id="dbd78-334">特定のドメインに **参加している PC でのみ** 同期を許可する設定を使用している。</span><span class="sxs-lookup"><span data-stu-id="dbd78-334">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="dbd78-335">この設定は、Microsoft マネージド デスクトップでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="dbd78-335">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="dbd78-336">この設定を無効にし、代わりに条件付きアクセス ポリシーを使用する OneDrive を設定します。</span><span class="sxs-lookup"><span data-stu-id="dbd78-336">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="dbd78-337">ヘルプ [については、「条件付きアクセスの展開を計画する](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbd78-337">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

