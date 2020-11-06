---
title: 準備評価ツールによって検出された問題を修正します。
description: ツールによって検出された各問題に対して実行する詳細なアクション
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c28353698dd372e14d5ec51b92eb4c0c051c92a4
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931914"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="8ea0c-104">準備評価ツールによって検出された問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="8ea0c-105">チェックが行われるたびに、ツールは次の4つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="8ea0c-106">結果</span><span class="sxs-lookup"><span data-stu-id="8ea0c-106">Result</span></span>  |<span data-ttu-id="8ea0c-107">意味</span><span class="sxs-lookup"><span data-stu-id="8ea0c-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="8ea0c-108">準備完了</span><span class="sxs-lookup"><span data-stu-id="8ea0c-108">Ready</span></span>     | <span data-ttu-id="8ea0c-109">登録を完了する前にアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="8ea0c-110">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="8ea0c-110">Advisory</span></span>    | <span data-ttu-id="8ea0c-111">このツールまたはこの記事の手順に従って、登録とユーザーのための最適な操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="8ea0c-112">登録は完了 *でき* ますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="8ea0c-113">使用不可能</span><span class="sxs-lookup"><span data-stu-id="8ea0c-113">Not ready</span></span> | <span data-ttu-id="8ea0c-114">*これらの問題を修正しない場合、登録は失敗します。*</span><span class="sxs-lookup"><span data-stu-id="8ea0c-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="8ea0c-115">このツールまたはこの記事に記載されている手順に従って解決してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="8ea0c-116">Error</span><span class="sxs-lookup"><span data-stu-id="8ea0c-116">Error</span></span> | <span data-ttu-id="8ea0c-117">使用している Azure Active Director (AD) の役割には、このチェックを実行するための十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="8ea0c-118">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="8ea0c-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="8ea0c-119">自動操縦展開プロファイル</span><span class="sxs-lookup"><span data-stu-id="8ea0c-119">Autopilot deployment profile</span></span>

<span data-ttu-id="8ea0c-120">Microsoft マネージドデスクトップによって使用される、割り当てられたグループまたは動的なグループを対象とした既存の自動操縦プロファイルはありません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ea0c-121">Microsoft Managed Desktop は、自動操縦を使用して新しいデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="8ea0c-122">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-122">**Not ready**</span></span>

<span data-ttu-id="8ea0c-123">すべてのデバイスに割り当てられている自動操縦プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="8ea0c-124">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="8ea0c-125">Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="8ea0c-126">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-126">**Advisory**</span></span>

<span data-ttu-id="8ea0c-127">自動操縦プロファイルが、登録時に作成される Microsoft マネージドデスクトップデバイスを含まない、割り当てられた、または動的な Azure AD グループを対象としていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="8ea0c-128">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="8ea0c-129">Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="8ea0c-130">証明書コネクタ</span><span class="sxs-lookup"><span data-stu-id="8ea0c-130">Certificate connectors</span></span>

<span data-ttu-id="8ea0c-131">Microsoft マネージドデスクトップに登録するデバイスで使用されている証明書コネクタがある場合、コネクタにエラーはありません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="8ea0c-132">状況に応じて、次のいずれかのアドバイザリが適用されますので、慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="8ea0c-133">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-133">**Advisory**</span></span>

<span data-ttu-id="8ea0c-134">証明書コネクタが存在しません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-134">No certificate connectors are present.</span></span> <span data-ttu-id="8ea0c-135">コネクタは必要ありませんが、Microsoft マネージドデスクトップデバイスへのネットワーク接続について必要な場合があるかどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-136">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="8ea0c-137">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-137">**Advisory**</span></span>

<span data-ttu-id="8ea0c-138">少なくとも1つの証明書コネクタにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="8ea0c-139">このコネクタを Microsoft マネージドデスクトップデバイスに接続するために必要な場合は、このエラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="8ea0c-140">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="8ea0c-141">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-141">**Advisory**</span></span>

<span data-ttu-id="8ea0c-142">少なくとも1つの証明書コネクタがあり、エラーは報告されていません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="8ea0c-143">ただし、Microsoft マネージドデスクトップデバイスでコネクタを再利用するには、プロファイルを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-144">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="8ea0c-145">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="8ea0c-145">Conditional access policies</span></span>

<span data-ttu-id="8ea0c-146">Azure AD 組織の条件付きアクセスポリシーで、Microsoft 管理デスクトップユーザーを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="8ea0c-147">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-147">**Not ready**</span></span>

<span data-ttu-id="8ea0c-148">すべてのユーザーを対象とする条件付きアクセスポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="8ea0c-149">登録時に作成される Microsoft マネージドデスクトップサービスアカウントの Azure AD グループが含まれていない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="8ea0c-150">手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="8ea0c-151">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-151">**Advisory**</span></span>

<span data-ttu-id="8ea0c-152">**モダンワークプレースサービスアカウント** の Azure AD グループを除外している条件付きアクセスポリシーがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="8ea0c-153">手順については、「 [条件付きアクセスを調整](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="8ea0c-154">**モダン Workplace Service Accounts** Azure AD group は、登録時にサービスに対して作成する動的なグループです。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="8ea0c-155">登録後にこのグループを除外するには、戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="8ea0c-156">これらのサービスアカウントの詳細については、「 [標準の運用手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="8ea0c-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-157">**Error**</span></span>

<span data-ttu-id="8ea0c-158">Intune 管理者の役割には、このチェックに十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="8ea0c-159">このチェックを実行するには、次のいずれかの Azure AD 役割が割り当てられている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="8ea0c-160">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-160">Security Reader</span></span>
- <span data-ttu-id="8ea0c-161">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-161">Security Administrator</span></span>
- <span data-ttu-id="8ea0c-162">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="8ea0c-163">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-163">Global Reader</span></span>
- <span data-ttu-id="8ea0c-164">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="8ea0c-165">デバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="8ea0c-165">Device Compliance policies</span></span>

<span data-ttu-id="8ea0c-166">Azure AD 組織の Intune デバイスコンプライアンスポリシーでは、Microsoft Managed Desktop ユーザーを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="8ea0c-167">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-167">**Not ready**</span></span>

<span data-ttu-id="8ea0c-168">すべてのユーザーを対象とするコンプライアンスポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="8ea0c-169">Microsoft Managed Desktop ユーザーを含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="8ea0c-170">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="8ea0c-171">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-171">**Advisory**</span></span>

<span data-ttu-id="8ea0c-172">コンプライアンスポリシーに Microsoft Managed Desktop のユーザーが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="8ea0c-173">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="8ea0c-174">デバイス構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="8ea0c-174">Device Configuration policies</span></span>

<span data-ttu-id="8ea0c-175">Azure AD 組織の Intune デバイス構成ポリシーでは、Microsoft 管理デスクトップデバイスまたはユーザーを対象としてはなりません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="8ea0c-176">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-176">**Not ready**</span></span>

<span data-ttu-id="8ea0c-177">すべてのユーザー、すべてのデバイス、またはその両方を対象とする構成ポリシーが、少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="8ea0c-178">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-179">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="8ea0c-180">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-180">**Advisory**</span></span>

<span data-ttu-id="8ea0c-181">コンプライアンスポリシーに、Microsoft マネージドデスクトップデバイスやユーザーが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="8ea0c-182">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="8ea0c-183">デバイスの種類の制限</span><span class="sxs-lookup"><span data-stu-id="8ea0c-183">Device type restrictions</span></span>

<span data-ttu-id="8ea0c-184">Microsoft マネージドデスクトップデバイスでは、Intune への登録が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="8ea0c-185">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-185">**Not ready**</span></span>

<span data-ttu-id="8ea0c-186">「 [登録の制限を設定](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) する」の手順に従って、設定を [ **許可** ] に変更します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="8ea0c-187">登録の状態ページ</span><span class="sxs-lookup"><span data-stu-id="8ea0c-187">Enrollment Status Page</span></span>

<span data-ttu-id="8ea0c-188">現在、登録状態ページ (ESP) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="8ea0c-189">この機能のパブリックプレビューに参加している場合は、この項目を無視できます。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="8ea0c-190">詳細については、「 [自動操縦による初回実行時の動作」および「登録の状態」ページ](../get-started/esp-first-run.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="8ea0c-191">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-191">**Not ready**</span></span>

<span data-ttu-id="8ea0c-192">**アプリケーションとプロファイルの構成の進行状況を示す** ように、ESP の既定のプロファイルが設定されている。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="8ea0c-193">この設定を無効にするか、[ [登録状態の設定] ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)の手順に従って、Azure AD グループへの割り当てに Microsoft Managed Desktop デバイスが含まれないようにします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="8ea0c-194">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-194">**Advisory**</span></span>

<span data-ttu-id="8ea0c-195">[ **アプリとプロファイルの構成の進行状況]** の設定を含むすべてのプロファイルが、Microsoft Managed Desktop デバイスを含む Azure AD グループに割り当てられていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-196">詳細については、「 [登録の状態を設定する」ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="8ea0c-197">Intune の登録</span><span class="sxs-lookup"><span data-stu-id="8ea0c-197">Intune enrollment</span></span>

<span data-ttu-id="8ea0c-198">Azure AD 組織の Windows 10 デバイスは、自動的に Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="8ea0c-199">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-199">**Advisory**</span></span>

<span data-ttu-id="8ea0c-200">MDM ユーザースコープが **一部** または **すべて** に設定されていることを確認し、 **[なし** ] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="8ea0c-201">**一部** を選択した場合は、登録した後に戻って、 **グループ** の **モダンワークプレースすべて** の Azure AD グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="8ea0c-202">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8ea0c-202">Microsoft Store for Business</span></span>

<span data-ttu-id="8ea0c-203">Microsoft Store for Business を使用して、会社のポータルをダウンロードして Microsoft Project や Microsoft Visio などの一部のアプリを展開できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="8ea0c-204">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-204">**Not ready**</span></span>

<span data-ttu-id="8ea0c-205">Microsoft Store for Business が有効になっていないか、Intune と同期されていません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="8ea0c-206">詳細については、「microsoft [Store For Business For Business With Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 」と「 [デバイス上に intune ポータルサイトをインストール](../get-started/company-portal.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="8ea0c-207">多要素認証</span><span class="sxs-lookup"><span data-stu-id="8ea0c-207">Multi-factor authentication</span></span>

<span data-ttu-id="8ea0c-208">多要素認証は、誤って Microsoft Managed Desktop service アカウントに適用されてはなりません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="8ea0c-209">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-209">**Not ready**</span></span>

<span data-ttu-id="8ea0c-210">すべてのユーザーに割り当てられている条件付きアクセスポリシーについて、"required" として設定されている多要素認証 (MFA) ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="8ea0c-211">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-212">詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="8ea0c-213">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-213">**Advisory**</span></span>

<span data-ttu-id="8ea0c-214">MFA を必要とする条件付きアクセスポリシーが、 **モダンワークプレースすべて** の Azure AD グループを除外していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="8ea0c-215">詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="8ea0c-216">**モダンワークプレースすべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的なグループです。そのため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="8ea0c-217">**Error**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-217">**Error**</span></span>

<span data-ttu-id="8ea0c-218">Intune 管理者の役割には、このチェックに十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="8ea0c-219">このチェックを実行するには、次のいずれかの Azure AD 役割が割り当てられている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="8ea0c-220">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-220">Security Reader</span></span>
- <span data-ttu-id="8ea0c-221">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-221">Security Administrator</span></span>
- <span data-ttu-id="8ea0c-222">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="8ea0c-223">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-223">Global Reader</span></span>
- <span data-ttu-id="8ea0c-224">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="8ea0c-225">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="8ea0c-225">PowerShell scripts</span></span>

<span data-ttu-id="8ea0c-226">Windows PowerShell スクリプトは、Microsoft マネージドデスクトップデバイスを対象とする方法では割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="8ea0c-227">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-227">**Advisory**</span></span>

<span data-ttu-id="8ea0c-228">Azure AD 組織の Windows PowerShell スクリプトが、Microsoft 管理デスクトップデバイスまたはユーザーを対象としないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="8ea0c-229">PowerShell スクリプトを割り当てないでください。すべてのユーザー、すべてのデバイス、またはその両方を対象とします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="8ea0c-230">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-231">詳細については、「 [Windows 10 デバイスでの Intune での PowerShell スクリプトの使用](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="8ea0c-232">地域</span><span class="sxs-lookup"><span data-stu-id="8ea0c-232">Region</span></span>

<span data-ttu-id="8ea0c-233">お客様の地域は、Microsoft マネージドデスクトップでサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8ea0c-234">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-234">**Not ready**</span></span>

<span data-ttu-id="8ea0c-235">Azure AD 組織の地域は、Microsoft マネージドデスクトップで現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ea0c-236">詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="8ea0c-237">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-237">**Advisory**</span></span>

<span data-ttu-id="8ea0c-238">Azure AD 組織が配置されている1つ以上の国が Microsoft マネージドデスクトップでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ea0c-239">詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="8ea0c-240">セキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="8ea0c-240">Security baselines</span></span>

<span data-ttu-id="8ea0c-241">セキュリティベースラインポリシーでは、Microsoft マネージドデスクトップデバイスを対象としてはなりません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="8ea0c-242">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-242">**Not ready**</span></span>

<span data-ttu-id="8ea0c-243">すべてのユーザー、すべてのデバイス、またはその両方を対象とするセキュリティ基準プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="8ea0c-244">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-245">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="8ea0c-246">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-246">**Advisory**</span></span>

<span data-ttu-id="8ea0c-247">Microsoft マネージドデスクトップデバイスを除外しているセキュリティベースラインポリシーがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-248">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="8ea0c-249">**モダン Workplace Devices-すべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的グループであるため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="8ea0c-250">Windows アプリ</span><span class="sxs-lookup"><span data-stu-id="8ea0c-250">Windows apps</span></span>

<span data-ttu-id="8ea0c-251">Microsoft Managed Desktop users が所有しているアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="8ea0c-252">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-252">**Advisory**</span></span>

<span data-ttu-id="8ea0c-253">Microsoft Managed Desktop ユーザーに割り当てるアプリのインベントリを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="8ea0c-254">これらのアプリが Intune によって展開可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-254">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="8ea0c-255">詳細については、「 [Microsoft マネージドデスクトップのアプリ](apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-255">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="8ea0c-256">Microsoft エンドポイント構成マネージャーのクエリを Microsoft アカウント担当者に依頼して、Intune に移行する準備ができているアプリや調整が必要なアプリを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-256">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="8ea0c-257">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="8ea0c-257">Windows Hello for Business</span></span>

<span data-ttu-id="8ea0c-258">Microsoft マネージドデスクトップでは、Windows Hello for Business を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-258">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="8ea0c-259">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-259">**Not ready**</span></span>

<span data-ttu-id="8ea0c-260">Windows Hello for Business は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-260">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="8ea0c-261">「 [Create a Windows Hello For Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 」の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-261">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="8ea0c-262">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-262">**Advisory**</span></span>

<span data-ttu-id="8ea0c-263">Windows Hello for Business がセットアップされていません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-263">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="8ea0c-264">「 [Create a Windows Hello For business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)」の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="8ea0c-265">Windows 10 の更新リング</span><span class="sxs-lookup"><span data-stu-id="8ea0c-265">Windows 10 update rings</span></span>

<span data-ttu-id="8ea0c-266">Intune の "Windows 10 update ring" ポリシーで、Microsoft マネージドデスクトップデバイスを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-266">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="8ea0c-267">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-267">**Not ready**</span></span>

<span data-ttu-id="8ea0c-268">すべてのデバイス、すべてのユーザー、またはその両方を対象とする "更新リング" ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-268">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="8ea0c-269">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-269">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="8ea0c-270">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-270">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="8ea0c-271">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-271">**Advisory**</span></span>

<span data-ttu-id="8ea0c-272">**モダンワークプレースのすべて** の Azure AD グループを除外しているすべての更新リングポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-272">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="8ea0c-273">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-273">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="8ea0c-274">**モダン Workplace Devices-すべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的グループであるため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-274">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="8ea0c-275">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="8ea0c-275">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="8ea0c-276">アドホックサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="8ea0c-276">Ad hoc subscriptions</span></span>

<span data-ttu-id="8ea0c-277">"False" に設定されている設定をチェックする方法を確認する方法を説明します。エンタープライズ状態の移動が正常に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-277">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="8ea0c-278">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-278">**Advisory**</span></span>

<span data-ttu-id="8ea0c-279">**AllowAdHocSubscriptions** が **True** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-279">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="8ea0c-280">それ以外の場合、エンタープライズ状態ローミングは機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-280">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="8ea0c-281">詳細については、「 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-281">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="8ea0c-282">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="8ea0c-282">Enterprise State Roaming</span></span>

<span data-ttu-id="8ea0c-283">エンタープライズ状態ローミングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-283">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="8ea0c-284">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-284">**Advisory**</span></span>

<span data-ttu-id="8ea0c-285">エンタープライズ状態の移動が、 **すべて** のグループまたは **選択した** グループに対して有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-285">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="8ea0c-286">詳細については、「 [Azure Active Directory でエンタープライズ状態のローミングを有効にする](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-286">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="8ea0c-287">ライセンス</span><span class="sxs-lookup"><span data-stu-id="8ea0c-287">Licenses</span></span>

<span data-ttu-id="8ea0c-288">Microsoft マネージドデスクトップを使用するには、いくつかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-288">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8ea0c-289">**準備ができていない**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-289">**Not Ready**</span></span>

<span data-ttu-id="8ea0c-290">Microsoft マネージドデスクトップを使用するために必要なすべてのライセンスがありません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-290">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ea0c-291">詳細については、「 [Microsoft Managed Desktop technologies](../intro/technologies.md) 」および「 [ライセンスについ](prerequisites.md#more-about-licenses)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-291">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="8ea0c-292">セキュリティアカウント名</span><span class="sxs-lookup"><span data-stu-id="8ea0c-292">Security account names</span></span>

<span data-ttu-id="8ea0c-293">一部のセキュリティアカウント名は、Microsoft マネージドデスクトップによって作成されたものと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-293">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8ea0c-294">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-294">**Not ready**</span></span>

<span data-ttu-id="8ea0c-295">Microsoft マネージドデスクトップによって作成されたアカウントと競合する、少なくとも1つのアカウント名がある。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-295">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ea0c-296">Microsoft アカウントの担当者と協力して、これらのアカウント名を除外します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-296">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="8ea0c-297">セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="8ea0c-297">Security administrator roles</span></span>

<span data-ttu-id="8ea0c-298">特定のセキュリティロールを持つユーザーは、エンドポイントの Microsoft Defender で割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-298">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8ea0c-299">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-299">**Advisory**</span></span>

<span data-ttu-id="8ea0c-300">これらの役割のいずれかが Azure AD 組織に割り当てられている場合は、エンドポイントの Microsoft Defender にこれらの役割が割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-300">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8ea0c-301">そうしないと、これらの役割を持つ管理者は管理ポータルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-301">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="8ea0c-302">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-302">Security Reader</span></span>
- <span data-ttu-id="8ea0c-303">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="8ea0c-303">Security Operator</span></span>
- <span data-ttu-id="8ea0c-304">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="8ea0c-304">Global Reader</span></span>

<span data-ttu-id="8ea0c-305">詳細については、「 [役割ベースのアクセス制御の役割を作成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-305">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="8ea0c-306">既定のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8ea0c-306">Security default</span></span>

<span data-ttu-id="8ea0c-307">Azure Active Directory のセキュリティの既定値を使用すると、Microsoft Managed Desktop がデバイスを管理できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-307">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="8ea0c-308">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-308">**Not ready**</span></span>

<span data-ttu-id="8ea0c-309">セキュリティの既定値がオンになっている。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-309">You have Security defaults turned on.</span></span> <span data-ttu-id="8ea0c-310">セキュリティの既定値をオフにして、条件付きアクセスポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-310">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="8ea0c-311">詳細については、「 [一般的な条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-311">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="8ea0c-312">セルフサービスによるパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="8ea0c-312">Self-service Password Reset</span></span>

<span data-ttu-id="8ea0c-313">セルフサービスのパスワードのリセット (SSPR) がすべてのユーザーに対して有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-313">Self-service Password Reset (SSPR) must be enabled for all users.</span></span> <span data-ttu-id="8ea0c-314">そうでない場合、Microsoft マネージドデスクトップサービスアカウントは動作しません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-314">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="8ea0c-315">詳細については、「 [チュートリアル: ユーザーがアカウントのロックを解除するか、Azure Active Directory のセルフサービスによるパスワードのリセットを使用してパスワードをリセットする](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-315">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="8ea0c-316">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-316">**Advisory**</span></span>

<span data-ttu-id="8ea0c-317">[SSPR] **選択** した設定に、Microsoft Managed Desktop デバイスが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-317">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>


### <a name="standard-user-role"></a><span data-ttu-id="8ea0c-318">標準ユーザーの役割</span><span class="sxs-lookup"><span data-stu-id="8ea0c-318">Standard user role</span></span>

<span data-ttu-id="8ea0c-319">Microsoft Managed Desktop ユーザーは、ローカル管理者権限を持たない標準ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-319">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="8ea0c-320">これらのユーザーには、Microsoft マネージドデスクトップデバイスを開始するときに、標準のユーザー役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-320">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="8ea0c-321">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-321">**Advisory**</span></span>

<span data-ttu-id="8ea0c-322">Microsoft マネージドデスクトップユーザーには、登録する前にローカル管理者の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-322">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="8ea0c-323">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="8ea0c-323">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="8ea0c-324">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="8ea0c-324">OneDrive for Business</span></span>

<span data-ttu-id="8ea0c-325">[ **特定のドメインに参加している pc でのみ同期を許可** する] の設定は、Microsoft マネージドデスクトップと競合します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-325">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="8ea0c-326">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="8ea0c-326">**Advisory**</span></span>

<span data-ttu-id="8ea0c-327">[ **特定のドメインに参加している pc でのみ同期を許可** する] 設定を使用している。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-327">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="8ea0c-328">この設定は、Microsoft マネージドデスクトップでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-328">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="8ea0c-329">この設定を無効にし、代わりに、条件付きアクセスポリシーを使用するように OneDrive for Business を設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-329">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="8ea0c-330">ヘルプについて [は、「Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea0c-330">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

