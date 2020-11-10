---
title: 準備評価ツールで見つかった問題を修正する
description: ツールによって検出された各問題に対して実行する詳細なアクション
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c342ea9f662d883883755d2f67e5c25ffabddf83
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948411"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="eefaa-104">準備評価ツールで見つかった問題を修正する</span><span class="sxs-lookup"><span data-stu-id="eefaa-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="eefaa-105">チェックが行われるたびに、ツールは次の4つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="eefaa-106">結果</span><span class="sxs-lookup"><span data-stu-id="eefaa-106">Result</span></span>  |<span data-ttu-id="eefaa-107">意味</span><span class="sxs-lookup"><span data-stu-id="eefaa-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="eefaa-108">準備完了</span><span class="sxs-lookup"><span data-stu-id="eefaa-108">Ready</span></span>     | <span data-ttu-id="eefaa-109">登録を完了する前にアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="eefaa-110">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="eefaa-110">Advisory</span></span>    | <span data-ttu-id="eefaa-111">このツールまたはこの記事の手順に従って、登録とユーザーのための最適な操作を行います。</span><span class="sxs-lookup"><span data-stu-id="eefaa-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="eefaa-112">登録は完了 *でき* ますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="eefaa-113">使用不可能</span><span class="sxs-lookup"><span data-stu-id="eefaa-113">Not ready</span></span> | <span data-ttu-id="eefaa-114">*これらの問題を修正しない場合、登録は失敗します。*</span><span class="sxs-lookup"><span data-stu-id="eefaa-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="eefaa-115">このツールまたはこの記事に記載されている手順に従って解決してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="eefaa-116">Error</span><span class="sxs-lookup"><span data-stu-id="eefaa-116">Error</span></span> | <span data-ttu-id="eefaa-117">使用している Azure Active Director (AD) の役割には、このチェックを実行するための十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="eefaa-118">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="eefaa-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="eefaa-119">自動操縦展開プロファイル</span><span class="sxs-lookup"><span data-stu-id="eefaa-119">Autopilot deployment profile</span></span>

<span data-ttu-id="eefaa-120">Microsoft マネージドデスクトップによって使用される、割り当てられたグループまたは動的なグループを対象とした既存の自動操縦プロファイルはありません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="eefaa-121">Microsoft Managed Desktop は、自動操縦を使用して新しいデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="eefaa-122">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-122">**Not ready**</span></span>

<span data-ttu-id="eefaa-123">すべてのデバイスに割り当てられている自動操縦プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="eefaa-124">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="eefaa-125">Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="eefaa-126">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-126">**Advisory**</span></span>

<span data-ttu-id="eefaa-127">自動操縦プロファイルが、登録時に作成される Microsoft マネージドデスクトップデバイスを含まない、割り当てられた、または動的な Azure AD グループを対象としていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="eefaa-128">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="eefaa-129">Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="eefaa-130">証明書コネクタ</span><span class="sxs-lookup"><span data-stu-id="eefaa-130">Certificate connectors</span></span>

<span data-ttu-id="eefaa-131">Microsoft マネージドデスクトップに登録するデバイスで使用されている証明書コネクタがある場合、コネクタにエラーはありません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="eefaa-132">状況に応じて、次のいずれかのアドバイザリが適用されますので、慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="eefaa-133">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-133">**Advisory**</span></span>

<span data-ttu-id="eefaa-134">証明書コネクタが存在しません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-134">No certificate connectors are present.</span></span> <span data-ttu-id="eefaa-135">コネクタは必要ありませんが、Microsoft マネージドデスクトップデバイスへのネットワーク接続について必要な場合があるかどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-136">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="eefaa-137">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-137">**Advisory**</span></span>

<span data-ttu-id="eefaa-138">少なくとも1つの証明書コネクタにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="eefaa-139">このコネクタを Microsoft マネージドデスクトップデバイスに接続するために必要な場合は、このエラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="eefaa-140">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="eefaa-141">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-141">**Advisory**</span></span>

<span data-ttu-id="eefaa-142">少なくとも1つの証明書コネクタがあり、エラーは報告されていません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="eefaa-143">ただし、Microsoft マネージドデスクトップデバイスでコネクタを再利用するには、プロファイルを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-144">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="eefaa-145">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="eefaa-145">Conditional access policies</span></span>

<span data-ttu-id="eefaa-146">Azure AD 組織の条件付きアクセスポリシーで、Microsoft 管理デスクトップユーザーを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="eefaa-147">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-147">**Not ready**</span></span>

<span data-ttu-id="eefaa-148">すべてのユーザーを対象とする条件付きアクセスポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="eefaa-149">登録時に作成される Microsoft マネージドデスクトップサービスアカウントの Azure AD グループが含まれていない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="eefaa-150">手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="eefaa-151">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-151">**Advisory**</span></span>

<span data-ttu-id="eefaa-152">**モダンワークプレースサービスアカウント** の Azure AD グループを除外している条件付きアクセスポリシーがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="eefaa-153">手順については、「 [条件付きアクセスを調整](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="eefaa-154">**モダン Workplace Service Accounts** Azure AD group は、登録時にサービスに対して作成する動的なグループです。</span><span class="sxs-lookup"><span data-stu-id="eefaa-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="eefaa-155">登録後にこのグループを除外するには、戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="eefaa-156">これらのサービスアカウントの詳細については、「 [標準の運用手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="eefaa-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="eefaa-157">**Error**</span></span>

<span data-ttu-id="eefaa-158">Intune 管理者の役割には、このチェックに十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="eefaa-159">このチェックを実行するには、次のいずれかの Azure AD 役割が割り当てられている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="eefaa-160">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="eefaa-160">Security Reader</span></span>
- <span data-ttu-id="eefaa-161">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="eefaa-161">Security Administrator</span></span>
- <span data-ttu-id="eefaa-162">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="eefaa-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="eefaa-163">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="eefaa-163">Global Reader</span></span>
- <span data-ttu-id="eefaa-164">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="eefaa-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="eefaa-165">デバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="eefaa-165">Device Compliance policies</span></span>

<span data-ttu-id="eefaa-166">Azure AD 組織の Intune デバイスコンプライアンスポリシーでは、Microsoft Managed Desktop ユーザーを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="eefaa-167">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-167">**Not ready**</span></span>

<span data-ttu-id="eefaa-168">すべてのユーザーを対象とするコンプライアンスポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="eefaa-169">Microsoft Managed Desktop ユーザーを含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="eefaa-170">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="eefaa-171">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-171">**Advisory**</span></span>

<span data-ttu-id="eefaa-172">コンプライアンスポリシーに Microsoft Managed Desktop のユーザーが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="eefaa-173">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="eefaa-174">デバイス構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="eefaa-174">Device Configuration policies</span></span>

<span data-ttu-id="eefaa-175">Azure AD 組織の Intune デバイス構成ポリシーでは、Microsoft 管理デスクトップデバイスまたはユーザーを対象としてはなりません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="eefaa-176">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-176">**Not ready**</span></span>

<span data-ttu-id="eefaa-177">すべてのユーザー、すべてのデバイス、またはその両方を対象とする構成ポリシーが、少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="eefaa-178">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-179">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="eefaa-180">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-180">**Advisory**</span></span>

<span data-ttu-id="eefaa-181">コンプライアンスポリシーに、Microsoft マネージドデスクトップデバイスやユーザーが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="eefaa-182">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="eefaa-183">デバイスの種類の制限</span><span class="sxs-lookup"><span data-stu-id="eefaa-183">Device type restrictions</span></span>

<span data-ttu-id="eefaa-184">Microsoft マネージドデスクトップデバイスでは、Intune への登録が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="eefaa-185">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-185">**Not ready**</span></span>

<span data-ttu-id="eefaa-186">「 [登録の制限を設定](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) する」の手順に従って、設定を [ **許可** ] に変更します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="eefaa-187">登録の状態ページ</span><span class="sxs-lookup"><span data-stu-id="eefaa-187">Enrollment Status Page</span></span>

<span data-ttu-id="eefaa-188">現在、登録状態ページ (ESP) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="eefaa-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="eefaa-189">この機能のパブリックプレビューに参加している場合は、この項目を無視できます。</span><span class="sxs-lookup"><span data-stu-id="eefaa-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="eefaa-190">詳細については、「 [自動操縦による初回実行時の動作」および「登録の状態」ページ](../get-started/esp-first-run.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="eefaa-191">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-191">**Not ready**</span></span>

<span data-ttu-id="eefaa-192">**アプリケーションとプロファイルの構成の進行状況を示す** ように、ESP の既定のプロファイルが設定されている。</span><span class="sxs-lookup"><span data-stu-id="eefaa-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="eefaa-193">この設定を無効にするか、[ [登録状態の設定] ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)の手順に従って、Azure AD グループへの割り当てに Microsoft Managed Desktop デバイスが含まれないようにします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="eefaa-194">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-194">**Advisory**</span></span>

<span data-ttu-id="eefaa-195">[ **アプリとプロファイルの構成の進行状況]** の設定を含むすべてのプロファイルが、Microsoft Managed Desktop デバイスを含む Azure AD グループに割り当てられていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-196">詳細については、「 [登録の状態を設定する」ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="eefaa-197">Intune の登録</span><span class="sxs-lookup"><span data-stu-id="eefaa-197">Intune enrollment</span></span>

<span data-ttu-id="eefaa-198">Azure AD 組織の Windows 10 デバイスは、自動的に Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="eefaa-199">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-199">**Advisory**</span></span>

<span data-ttu-id="eefaa-200">MDM ユーザースコープが **一部** または **すべて** に設定されていることを確認し、 **[なし** ] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="eefaa-201">**一部** を選択した場合は、登録した後に戻って、 **グループ** の **モダンワークプレースすべて** の Azure AD グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="eefaa-202">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="eefaa-202">Microsoft Store for Business</span></span>

<span data-ttu-id="eefaa-203">Microsoft Store for Business を使用して、会社のポータルをダウンロードして Microsoft Project や Microsoft Visio などの一部のアプリを展開できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="eefaa-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="eefaa-204">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-204">**Not ready**</span></span>

<span data-ttu-id="eefaa-205">Microsoft Store for Business が有効になっていないか、Intune と同期されていません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="eefaa-206">詳細については、「microsoft [Store For Business For Business With Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 」と「 [デバイス上に intune ポータルサイトをインストール](../get-started/company-portal.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="eefaa-207">多要素認証</span><span class="sxs-lookup"><span data-stu-id="eefaa-207">Multi-factor authentication</span></span>

<span data-ttu-id="eefaa-208">多要素認証は、誤って Microsoft Managed Desktop service アカウントに適用されてはなりません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="eefaa-209">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-209">**Not ready**</span></span>

<span data-ttu-id="eefaa-210">すべてのユーザーに割り当てられている条件付きアクセスポリシーについて、"required" として設定されている多要素認証 (MFA) ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="eefaa-211">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-212">詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="eefaa-213">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-213">**Advisory**</span></span>

<span data-ttu-id="eefaa-214">MFA を必要とする条件付きアクセスポリシーが、 **モダンワークプレースすべて** の Azure AD グループを除外していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="eefaa-215">詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="eefaa-216">**モダンワークプレースすべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的なグループです。そのため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="eefaa-217">**Error**</span><span class="sxs-lookup"><span data-stu-id="eefaa-217">**Error**</span></span>

<span data-ttu-id="eefaa-218">Intune 管理者の役割には、このチェックに十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="eefaa-219">このチェックを実行するには、次のいずれかの Azure AD 役割が割り当てられている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="eefaa-220">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="eefaa-220">Security Reader</span></span>
- <span data-ttu-id="eefaa-221">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="eefaa-221">Security Administrator</span></span>
- <span data-ttu-id="eefaa-222">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="eefaa-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="eefaa-223">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="eefaa-223">Global Reader</span></span>
- <span data-ttu-id="eefaa-224">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="eefaa-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="eefaa-225">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="eefaa-225">PowerShell scripts</span></span>

<span data-ttu-id="eefaa-226">Windows PowerShell スクリプトは、Microsoft マネージドデスクトップデバイスを対象とする方法では割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="eefaa-227">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-227">**Advisory**</span></span>

<span data-ttu-id="eefaa-228">Azure AD 組織の Windows PowerShell スクリプトが、Microsoft 管理デスクトップデバイスまたはユーザーを対象としないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="eefaa-229">PowerShell スクリプトを割り当てないでください。すべてのユーザー、すべてのデバイス、またはその両方を対象とします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="eefaa-230">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-231">詳細については、「 [Windows 10 デバイスでの Intune での PowerShell スクリプトの使用](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="eefaa-232">地域</span><span class="sxs-lookup"><span data-stu-id="eefaa-232">Region</span></span>

<span data-ttu-id="eefaa-233">お客様の地域は、Microsoft マネージドデスクトップでサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="eefaa-234">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-234">**Not ready**</span></span>

<span data-ttu-id="eefaa-235">Azure AD 組織の地域は、Microsoft マネージドデスクトップで現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="eefaa-236">詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="eefaa-237">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-237">**Advisory**</span></span>

<span data-ttu-id="eefaa-238">Azure AD 組織が配置されている1つ以上の国が Microsoft マネージドデスクトップでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="eefaa-239">詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="eefaa-240">セキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="eefaa-240">Security baselines</span></span>

<span data-ttu-id="eefaa-241">セキュリティベースラインポリシーでは、Microsoft マネージドデスクトップデバイスを対象としてはなりません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="eefaa-242">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-242">**Not ready**</span></span>

<span data-ttu-id="eefaa-243">すべてのユーザー、すべてのデバイス、またはその両方を対象とするセキュリティ基準プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="eefaa-244">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-245">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="eefaa-246">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-246">**Advisory**</span></span>

<span data-ttu-id="eefaa-247">Microsoft マネージドデスクトップデバイスを除外しているセキュリティベースラインポリシーがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-248">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="eefaa-249">**モダン Workplace Devices-すべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的グループであるため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="eefaa-250">Windows アプリ</span><span class="sxs-lookup"><span data-stu-id="eefaa-250">Windows apps</span></span>

<span data-ttu-id="eefaa-251">Microsoft Managed Desktop users が所有しているアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="eefaa-252">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-252">**Advisory**</span></span>

<span data-ttu-id="eefaa-253">Microsoft Managed Desktop ユーザーに割り当てるアプリのインベントリを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="eefaa-254">これらのアプリが Intune によって展開可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-254">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="eefaa-255">詳細については、「 [Microsoft マネージドデスクトップのアプリ](apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-255">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="eefaa-256">Microsoft エンドポイント構成マネージャーのクエリを Microsoft アカウント担当者に依頼して、Intune に移行する準備ができているアプリや調整が必要なアプリを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="eefaa-256">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="eefaa-257">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="eefaa-257">Windows Hello for Business</span></span>

<span data-ttu-id="eefaa-258">Microsoft マネージドデスクトップでは、Windows Hello for Business を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-258">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="eefaa-259">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-259">**Not ready**</span></span>

<span data-ttu-id="eefaa-260">Windows Hello for Business は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="eefaa-260">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="eefaa-261">「 [Create a Windows Hello For Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 」の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-261">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="eefaa-262">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-262">**Advisory**</span></span>

<span data-ttu-id="eefaa-263">Windows Hello for Business がセットアップされていません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-263">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="eefaa-264">「 [Create a Windows Hello For business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)」の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="eefaa-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="eefaa-265">Windows 10 の更新リング</span><span class="sxs-lookup"><span data-stu-id="eefaa-265">Windows 10 update rings</span></span>

<span data-ttu-id="eefaa-266">Intune の "Windows 10 update ring" ポリシーで、Microsoft マネージドデスクトップデバイスを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-266">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="eefaa-267">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-267">**Not ready**</span></span>

<span data-ttu-id="eefaa-268">すべてのデバイス、すべてのユーザー、またはその両方を対象とする "更新リング" ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-268">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="eefaa-269">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-269">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="eefaa-270">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-270">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="eefaa-271">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-271">**Advisory**</span></span>

<span data-ttu-id="eefaa-272">すべての更新リングポリシーで、 **モダン Workplace Devices** を除外していることを確認してください。すべての Azure AD グループ。</span><span class="sxs-lookup"><span data-stu-id="eefaa-272">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="eefaa-273">これらのポリシーに Azure AD ユーザーグループを割り当てている場合は、すべての更新リングポリシーで、Microsoft Managed Desktop ユーザーが含まれる、 **モダンワークプレースすべて** の azure ad グループも除外していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-273">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="eefaa-274">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-274">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="eefaa-275">**モダン Workplace Devices-all** および **モダン workplace-** すべての Azure AD グループには、Microsoft マネージドデスクトップに登録したときに作成したグループが割り当てられます。そのため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-275">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="eefaa-276">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="eefaa-276">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="eefaa-277">アドホックサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="eefaa-277">Ad hoc subscriptions</span></span>

<span data-ttu-id="eefaa-278">"False" に設定されている設定をチェックする方法を確認する方法を説明します。エンタープライズ状態の移動が正常に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-278">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="eefaa-279">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-279">**Advisory**</span></span>

<span data-ttu-id="eefaa-280">**AllowAdHocSubscriptions** が **True** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-280">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="eefaa-281">それ以外の場合、エンタープライズ状態ローミングは機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-281">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="eefaa-282">詳細については、「 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-282">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="eefaa-283">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="eefaa-283">Enterprise State Roaming</span></span>

<span data-ttu-id="eefaa-284">エンタープライズ状態ローミングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-284">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="eefaa-285">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-285">**Advisory**</span></span>

<span data-ttu-id="eefaa-286">エンタープライズ状態の移動が、 **すべて** のグループまたは **選択した** グループに対して有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-286">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="eefaa-287">詳細については、「 [Azure Active Directory でエンタープライズ状態のローミングを有効にする](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-287">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="eefaa-288">ライセンス</span><span class="sxs-lookup"><span data-stu-id="eefaa-288">Licenses</span></span>

<span data-ttu-id="eefaa-289">Microsoft マネージドデスクトップを使用するには、いくつかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="eefaa-289">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="eefaa-290">**準備ができていない**</span><span class="sxs-lookup"><span data-stu-id="eefaa-290">**Not Ready**</span></span>

<span data-ttu-id="eefaa-291">Microsoft マネージドデスクトップを使用するために必要なすべてのライセンスがありません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-291">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="eefaa-292">詳細については、「 [Microsoft Managed Desktop technologies](../intro/technologies.md) 」および「 [ライセンスについ](prerequisites.md#more-about-licenses)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-292">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="eefaa-293">セキュリティアカウント名</span><span class="sxs-lookup"><span data-stu-id="eefaa-293">Security account names</span></span>

<span data-ttu-id="eefaa-294">一部のセキュリティアカウント名は、Microsoft マネージドデスクトップによって作成されたものと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-294">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="eefaa-295">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-295">**Not ready**</span></span>

<span data-ttu-id="eefaa-296">Microsoft マネージドデスクトップによって作成されたアカウントと競合する、少なくとも1つのアカウント名がある。</span><span class="sxs-lookup"><span data-stu-id="eefaa-296">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="eefaa-297">Microsoft アカウントの担当者と協力して、これらのアカウント名を除外します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-297">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="eefaa-298">セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="eefaa-298">Security administrator roles</span></span>

<span data-ttu-id="eefaa-299">特定のセキュリティロールを持つユーザーは、エンドポイントの Microsoft Defender で割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-299">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="eefaa-300">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-300">**Advisory**</span></span>

<span data-ttu-id="eefaa-301">これらの役割のいずれかが Azure AD 組織に割り当てられている場合は、エンドポイントの Microsoft Defender にこれらの役割が割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-301">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="eefaa-302">そうしないと、これらの役割を持つ管理者は管理ポータルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-302">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="eefaa-303">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="eefaa-303">Security Reader</span></span>
- <span data-ttu-id="eefaa-304">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="eefaa-304">Security Operator</span></span>
- <span data-ttu-id="eefaa-305">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="eefaa-305">Global Reader</span></span>

<span data-ttu-id="eefaa-306">詳細については、「 [役割ベースのアクセス制御の役割を作成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-306">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="eefaa-307">既定のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="eefaa-307">Security default</span></span>

<span data-ttu-id="eefaa-308">Azure Active Directory のセキュリティの既定値を使用すると、Microsoft Managed Desktop がデバイスを管理できなくなります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-308">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="eefaa-309">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="eefaa-309">**Not ready**</span></span>

<span data-ttu-id="eefaa-310">セキュリティの既定値がオンになっている。</span><span class="sxs-lookup"><span data-stu-id="eefaa-310">You have Security defaults turned on.</span></span> <span data-ttu-id="eefaa-311">セキュリティの既定値をオフにして、条件付きアクセスポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-311">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="eefaa-312">詳細については、「 [一般的な条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-312">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="eefaa-313">セルフサービスによるパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="eefaa-313">Self-service Password Reset</span></span>

<span data-ttu-id="eefaa-314">Microsoft Managed Desktop service アカウントを除くすべてのユーザーに対して、セルフサービスのパスワードのリセット (SSPR) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-314">Self-service Password Reset (SSPR) should be enabled for all users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="eefaa-315">詳細については、「 [チュートリアル: ユーザーがアカウントのロックを解除するか、Azure Active Directory のセルフサービスによるパスワードのリセットを使用してパスワードをリセットする](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-315">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="eefaa-316">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-316">**Advisory**</span></span>

<span data-ttu-id="eefaa-317">SSPR が **選択** した設定に、Microsoft managed desktop デバイスは含まれていますが、Microsoft managed desktop service アカウントを除外していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-317">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="eefaa-318">SSPR が有効になっている場合、Microsoft マネージドデスクトップサービスアカウントは期待どおりに機能しません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-318">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="eefaa-319">標準ユーザーの役割</span><span class="sxs-lookup"><span data-stu-id="eefaa-319">Standard user role</span></span>

<span data-ttu-id="eefaa-320">グローバル管理者およびデバイス管理者の Azure AD ロールを割り当てられているユーザー以外は、Microsoft Managed Desktop ユーザーは、ローカル管理者特権を持たない標準ユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="eefaa-320">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="eefaa-321">他のすべてのユーザーには、Microsoft マネージドデスクトップデバイスを起動するときに、標準のユーザー役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="eefaa-321">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="eefaa-322">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-322">**Advisory**</span></span>

<span data-ttu-id="eefaa-323">Microsoft マネージドデスクトップのユーザーには、登録後の Microsoft マネージドデスクトップデバイスに対するローカル管理者権限がありません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-323">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="eefaa-324">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="eefaa-324">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="eefaa-325">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="eefaa-325">OneDrive for Business</span></span>

<span data-ttu-id="eefaa-326">[ **特定のドメインに参加している pc でのみ同期を許可** する] の設定は、Microsoft マネージドデスクトップと競合します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-326">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="eefaa-327">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="eefaa-327">**Advisory**</span></span>

<span data-ttu-id="eefaa-328">[ **特定のドメインに参加している pc でのみ同期を許可** する] 設定を使用している。</span><span class="sxs-lookup"><span data-stu-id="eefaa-328">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="eefaa-329">この設定は、Microsoft マネージドデスクトップでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="eefaa-329">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="eefaa-330">この設定を無効にし、代わりに、条件付きアクセスポリシーを使用するように OneDrive for Business を設定します。</span><span class="sxs-lookup"><span data-stu-id="eefaa-330">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="eefaa-331">ヘルプについて [は、「Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eefaa-331">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

