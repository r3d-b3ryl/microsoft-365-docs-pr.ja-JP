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
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656141"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="65cbb-104">準備評価ツールによって検出された問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="65cbb-105">チェックが行われるたびに、ツールは次の3つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="65cbb-106">結果</span><span class="sxs-lookup"><span data-stu-id="65cbb-106">Result</span></span>  |<span data-ttu-id="65cbb-107">意味</span><span class="sxs-lookup"><span data-stu-id="65cbb-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="65cbb-108">準備完了</span><span class="sxs-lookup"><span data-stu-id="65cbb-108">Ready</span></span>     | <span data-ttu-id="65cbb-109">登録を完了する前にアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="65cbb-110">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="65cbb-110">Advisory</span></span>    | <span data-ttu-id="65cbb-111">このツールまたはこの記事の手順に従って、登録とユーザーのための最適な操作を行います。</span><span class="sxs-lookup"><span data-stu-id="65cbb-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="65cbb-112">登録は完了 *でき* ますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="65cbb-113">使用不可能</span><span class="sxs-lookup"><span data-stu-id="65cbb-113">Not ready</span></span> | <span data-ttu-id="65cbb-114">*これらの問題を修正しない場合、登録は失敗します。*</span><span class="sxs-lookup"><span data-stu-id="65cbb-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="65cbb-115">このツールまたはこの記事に記載されている手順に従って解決してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="65cbb-116">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="65cbb-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="65cbb-117">自動操縦展開プロファイル</span><span class="sxs-lookup"><span data-stu-id="65cbb-117">Autopilot deployment profile</span></span>

<span data-ttu-id="65cbb-118">Microsoft マネージドデスクトップによって使用される、割り当てられたグループまたは動的なグループを対象とした既存の自動操縦プロファイルはありません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="65cbb-119">Microsoft Managed Desktop は、自動操縦を使用して新しいデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="65cbb-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="65cbb-120">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-120">**Not ready**</span></span>

<span data-ttu-id="65cbb-121">すべてのデバイスに割り当てられている自動操縦プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="65cbb-122">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="65cbb-123">Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="65cbb-124">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-124">**Advisory**</span></span>

<span data-ttu-id="65cbb-125">自動操縦プロファイルが、登録時に作成される Microsoft マネージドデスクトップデバイスを含まない、割り当てられた、または動的な Azure AD グループを対象としていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="65cbb-126">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="65cbb-127">Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="65cbb-128">証明書コネクタ</span><span class="sxs-lookup"><span data-stu-id="65cbb-128">Certificate connectors</span></span>

<span data-ttu-id="65cbb-129">Microsoft マネージドデスクトップに登録するデバイスで使用されている証明書コネクタがある場合、コネクタにエラーはありません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="65cbb-130">状況に応じて、次のいずれかのアドバイザリが適用されますので、慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="65cbb-131">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-131">**Advisory**</span></span>

<span data-ttu-id="65cbb-132">証明書コネクタが存在しません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-132">No certificate connectors are present.</span></span> <span data-ttu-id="65cbb-133">コネクタは必要ありませんが、Microsoft マネージドデスクトップデバイスへのネットワーク接続について必要な場合があるかどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="65cbb-134">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="65cbb-135">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-135">**Advisory**</span></span>

<span data-ttu-id="65cbb-136">少なくとも1つの証明書コネクタにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="65cbb-137">このコネクタを Microsoft マネージドデスクトップデバイスに接続するために必要な場合は、このエラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="65cbb-138">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="65cbb-139">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-139">**Advisory**</span></span>

<span data-ttu-id="65cbb-140">少なくとも1つの証明書コネクタがあり、エラーは報告されていません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="65cbb-141">ただし、Microsoft マネージドデスクトップデバイスでコネクタを再利用するには、プロファイルを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="65cbb-142">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="65cbb-143">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="65cbb-143">Conditional access policies</span></span>

<span data-ttu-id="65cbb-144">Azure AD 組織の条件付きアクセスポリシーで、Microsoft 管理デスクトップユーザーを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="65cbb-145">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-145">**Not ready**</span></span>

<span data-ttu-id="65cbb-146">すべてのユーザーを対象とする条件付きアクセスポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="65cbb-147">登録時に作成される Microsoft マネージドデスクトップサービスアカウントの Azure AD グループが含まれていない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="65cbb-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="65cbb-148">手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="65cbb-149">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-149">**Advisory**</span></span>

<span data-ttu-id="65cbb-150">**モダンワークプレースサービスアカウント**の Azure AD グループを除外している条件付きアクセスポリシーがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="65cbb-151">手順については、「 [条件付きアクセスを調整](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="65cbb-152">**モダン Workplace Service Accounts** Azure AD group は、登録時にサービスに対して作成する動的なグループです。</span><span class="sxs-lookup"><span data-stu-id="65cbb-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="65cbb-153">登録後にこのグループを除外するには、戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="65cbb-154">これらのサービスアカウントの詳細については、「 [標準の運用手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="65cbb-155">デバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="65cbb-155">Device Compliance policies</span></span>

<span data-ttu-id="65cbb-156">Azure AD 組織の Intune デバイスコンプライアンスポリシーでは、Microsoft Managed Desktop ユーザーを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="65cbb-157">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-157">**Not ready**</span></span>

<span data-ttu-id="65cbb-158">すべてのユーザーを対象とするコンプライアンスポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="65cbb-159">Microsoft Managed Desktop ユーザーを含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="65cbb-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="65cbb-160">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="65cbb-161">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-161">**Advisory**</span></span>

<span data-ttu-id="65cbb-162">コンプライアンスポリシーに Microsoft Managed Desktop のユーザーが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="65cbb-163">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="65cbb-164">デバイス構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="65cbb-164">Device Configuration policies</span></span>

<span data-ttu-id="65cbb-165">Azure AD 組織の Intune デバイス構成ポリシーでは、Microsoft 管理デスクトップデバイスまたはユーザーを対象としてはなりません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="65cbb-166">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-166">**Not ready**</span></span>

<span data-ttu-id="65cbb-167">すべてのユーザー、すべてのデバイス、またはその両方を対象とする構成ポリシーが、少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="65cbb-168">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="65cbb-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="65cbb-169">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="65cbb-170">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-170">**Advisory**</span></span>

<span data-ttu-id="65cbb-171">コンプライアンスポリシーに、Microsoft マネージドデスクトップデバイスやユーザーが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="65cbb-172">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="65cbb-173">デバイスの種類の制限</span><span class="sxs-lookup"><span data-stu-id="65cbb-173">Device type restrictions</span></span>

<span data-ttu-id="65cbb-174">Microsoft マネージドデスクトップデバイスでは、Intune への登録が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="65cbb-175">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-175">**Not ready**</span></span>

<span data-ttu-id="65cbb-176">「 [登録の制限を設定](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) する」の手順に従って、設定を [ **許可**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="65cbb-177">登録の状態ページ</span><span class="sxs-lookup"><span data-stu-id="65cbb-177">Enrollment Status Page</span></span>

<span data-ttu-id="65cbb-178">現在、登録状態ページ (ESP) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="65cbb-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="65cbb-179">この機能のパブリックプレビューに参加している場合は、この項目を無視できます。</span><span class="sxs-lookup"><span data-stu-id="65cbb-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="65cbb-180">詳細については、「 [自動操縦による初回実行時の動作」および「登録の状態」ページ](../get-started/esp-first-run.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="65cbb-181">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-181">**Not ready**</span></span>

<span data-ttu-id="65cbb-182">**アプリケーションとプロファイルの構成の進行状況を示す**ように、ESP の既定のプロファイルが設定されている。</span><span class="sxs-lookup"><span data-stu-id="65cbb-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="65cbb-183">[ [登録の状態の設定] ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)の手順に従って、この設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="65cbb-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="65cbb-184">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-184">**Advisory**</span></span>

<span data-ttu-id="65cbb-185">[ **アプリとプロファイルの構成の進行状況]** の設定を含むすべてのプロファイルが、Microsoft Managed Desktop デバイスを含む Azure AD グループに割り当てられていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="65cbb-186">詳細については、「 [登録の状態を設定する」ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="65cbb-187">Intune の登録</span><span class="sxs-lookup"><span data-stu-id="65cbb-187">Intune enrollment</span></span>

<span data-ttu-id="65cbb-188">Azure AD 組織の Windows 10 デバイスは、自動的に Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="65cbb-189">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-189">**Not ready**</span></span>

<span data-ttu-id="65cbb-190">Azure AD 組織のユーザーは、Microsoft Intune に自動的に登録されません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="65cbb-191">MDM ユーザースコープを **一部** または **すべて**に変更します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="65cbb-192">を選びます。</span><span class="sxs-lookup"><span data-stu-id="65cbb-192">If you choose.</span></span> <span data-ttu-id="65cbb-193">何らかの \* \* 登録後に戻ってきて、**グループ**の**モダンワークプレースすべて**の Azure AD グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="65cbb-194">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="65cbb-194">Microsoft Store for Business</span></span>

<span data-ttu-id="65cbb-195">Microsoft Store for Business を使用して、会社のポータルをダウンロードして Microsoft Project や Microsoft Visio などの一部のアプリを展開できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="65cbb-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="65cbb-196">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-196">**Not ready**</span></span>

<span data-ttu-id="65cbb-197">Microsoft Store for Business が有効になっていないか、Intune と同期されていません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="65cbb-198">詳細については、「microsoft [Store For Business For Business With Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 」と「 [デバイス上に intune ポータルサイトをインストール](../get-started/company-portal.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="65cbb-199">多要素認証</span><span class="sxs-lookup"><span data-stu-id="65cbb-199">Multi-factor authentication</span></span>

<span data-ttu-id="65cbb-200">多要素認証は、誤って Microsoft Managed Desktop service アカウントに適用されてはなりません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="65cbb-201">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-201">**Not ready**</span></span>

<span data-ttu-id="65cbb-202">すべてのユーザーに割り当てられている条件付きアクセスポリシーについて、"required" として設定されている多要素認証 (MFA) ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="65cbb-203">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="65cbb-204">詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="65cbb-205">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-205">**Advisory**</span></span>

<span data-ttu-id="65cbb-206">MFA を必要とする条件付きアクセスポリシーが、 **モダンワークプレースすべて** の Azure AD グループを除外していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="65cbb-207">詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="65cbb-208">**モダンワークプレースすべて**の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的なグループです。そのため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="65cbb-209">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="65cbb-209">PowerShell scripts</span></span>

<span data-ttu-id="65cbb-210">Windows PowerShell スクリプトは、Microsoft マネージドデスクトップデバイスを対象とする方法では割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="65cbb-211">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-211">**Advisory**</span></span>

<span data-ttu-id="65cbb-212">Azure AD 組織の Windows PowerShell スクリプトが、Microsoft 管理デスクトップデバイスまたはユーザーを対象としないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="65cbb-213">詳細については、「 [Windows 10 デバイスでの Intune での PowerShell スクリプトの使用](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="65cbb-214">地域</span><span class="sxs-lookup"><span data-stu-id="65cbb-214">Region</span></span>

<span data-ttu-id="65cbb-215">お客様の地域は、Microsoft マネージドデスクトップでサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="65cbb-216">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-216">**Not ready**</span></span>

<span data-ttu-id="65cbb-217">Azure AD 組織の地域は、Microsoft マネージドデスクトップで現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="65cbb-218">詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="65cbb-219">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-219">**Advisory**</span></span>

<span data-ttu-id="65cbb-220">Azure AD 組織が配置されている1つ以上の国が Microsoft マネージドデスクトップでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="65cbb-221">詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="65cbb-222">セキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="65cbb-222">Security baselines</span></span>

<span data-ttu-id="65cbb-223">セキュリティベースラインポリシーでは、Microsoft マネージドデスクトップデバイスを対象としてはなりません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="65cbb-224">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-224">**Not ready**</span></span>

<span data-ttu-id="65cbb-225">すべてのユーザー、すべてのデバイス、またはその両方を対象とするセキュリティ基準プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="65cbb-226">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="65cbb-227">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="65cbb-228">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-228">**Advisory**</span></span>

<span data-ttu-id="65cbb-229">Microsoft マネージドデスクトップデバイスを除外しているセキュリティベースラインポリシーがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="65cbb-230">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="65cbb-231">**モダン Workplace Devices-すべて**の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的グループであるため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="65cbb-232">Windows アプリ</span><span class="sxs-lookup"><span data-stu-id="65cbb-232">Windows apps</span></span>

<span data-ttu-id="65cbb-233">Microsoft Managed Desktop users が所有しているアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="65cbb-234">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-234">**Advisory**</span></span>

<span data-ttu-id="65cbb-235">Microsoft Managed Desktop ユーザーに割り当てるアプリのインベントリを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="65cbb-236">これらのアプリが Intune によって展開可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="65cbb-237">詳細については、「 [Microsoft マネージドデスクトップのアプリ](apps.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="65cbb-238">Microsoft エンドポイント構成マネージャーのクエリを Microsoft アカウント担当者に依頼して、Intune に移行する準備ができているアプリや調整が必要なアプリを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="65cbb-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="65cbb-239">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="65cbb-239">Windows Hello for Business</span></span>

<span data-ttu-id="65cbb-240">Microsoft マネージドデスクトップでは、Windows Hello for Business を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="65cbb-241">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-241">**Not ready**</span></span>

<span data-ttu-id="65cbb-242">Windows Hello for Business は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="65cbb-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="65cbb-243">「 [Create a Windows Hello For Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 」の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65cbb-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="65cbb-244">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-244">**Advisory**</span></span>

<span data-ttu-id="65cbb-245">Windows Hello for Business がセットアップされていません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="65cbb-246">「 [Create a Windows Hello For business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)」の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65cbb-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="65cbb-247">Windows 10 の更新リング</span><span class="sxs-lookup"><span data-stu-id="65cbb-247">Windows 10 update rings</span></span>

<span data-ttu-id="65cbb-248">Intune の "Windows 10 update ring" ポリシーで、Microsoft マネージドデスクトップデバイスを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="65cbb-249">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-249">**Not ready**</span></span>

<span data-ttu-id="65cbb-250">すべてのデバイス、すべてのユーザー、またはその両方を対象とする "更新リング" ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="65cbb-251">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="65cbb-252">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="65cbb-253">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-253">**Advisory**</span></span>

<span data-ttu-id="65cbb-254">**モダンワークプレースのすべて**の Azure AD グループを除外しているすべての更新リングポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="65cbb-255">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="65cbb-256">**モダン Workplace Devices-すべて**の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的グループであるため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="65cbb-257">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="65cbb-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="65cbb-258">アドホックサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="65cbb-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="65cbb-259">"False" に設定されている設定をチェックする方法を確認する方法を説明します。エンタープライズ状態の移動が正常に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="65cbb-260">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-260">**Advisory**</span></span>

<span data-ttu-id="65cbb-261">**AllowAdHocSubscriptions**が**True**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="65cbb-262">それ以外の場合、エンタープライズ状態ローミングは機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="65cbb-263">詳細については、「 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="65cbb-264">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="65cbb-264">Enterprise State Roaming</span></span>

<span data-ttu-id="65cbb-265">エンタープライズ状態ローミングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="65cbb-266">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-266">**Advisory**</span></span>

<span data-ttu-id="65cbb-267">エンタープライズ状態の移動が、 **すべて** のグループまたは **選択した** グループに対して有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="65cbb-268">詳細については、「 [Azure Active Directory でエンタープライズ状態のローミングを有効にする](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="65cbb-269">ライセンス</span><span class="sxs-lookup"><span data-stu-id="65cbb-269">Licenses</span></span>

<span data-ttu-id="65cbb-270">Microsoft マネージドデスクトップを使用するには、いくつかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="65cbb-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="65cbb-271">**準備ができていない**</span><span class="sxs-lookup"><span data-stu-id="65cbb-271">**Not Ready**</span></span>

<span data-ttu-id="65cbb-272">Microsoft マネージドデスクトップを使用するために必要なすべてのライセンスがありません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="65cbb-273">詳細については、「 [Microsoft Managed Desktop technologies](../intro/technologies.md) 」および「 [ライセンスについ](prerequisites.md#more-about-licenses)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="65cbb-274">セキュリティアカウント名</span><span class="sxs-lookup"><span data-stu-id="65cbb-274">Security account names</span></span>

<span data-ttu-id="65cbb-275">一部のセキュリティアカウント名は、Microsoft マネージドデスクトップによって作成されたものと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="65cbb-276">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-276">**Not ready**</span></span>

<span data-ttu-id="65cbb-277">Microsoft マネージドデスクトップによって作成されたアカウントと競合する、少なくとも1つのアカウント名がある。</span><span class="sxs-lookup"><span data-stu-id="65cbb-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="65cbb-278">Microsoft アカウントの担当者と協力して、これらのアカウント名を除外します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="65cbb-279">セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="65cbb-279">Security administrator roles</span></span>

<span data-ttu-id="65cbb-280">特定のセキュリティロールを持つユーザーは、エンドポイントの Microsoft Defender で割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="65cbb-281">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-281">**Advisory**</span></span>

<span data-ttu-id="65cbb-282">これらの役割のいずれかが Azure AD 組織に割り当てられている場合は、エンドポイントの Microsoft Defender にこれらの役割が割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="65cbb-283">そうしないと、これらの役割を持つ管理者は管理ポータルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="65cbb-284">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="65cbb-284">Security Reader</span></span>
- <span data-ttu-id="65cbb-285">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="65cbb-285">Security Operator</span></span>
- <span data-ttu-id="65cbb-286">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="65cbb-286">Global Reader</span></span>

<span data-ttu-id="65cbb-287">詳細については、「 [役割ベースのアクセス制御の役割を作成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="65cbb-288">既定のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="65cbb-288">Security default</span></span>

<span data-ttu-id="65cbb-289">Azure Active Directory のセキュリティの既定値を使用すると、Microsoft Managed Desktop がデバイスを管理できなくなります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="65cbb-290">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-290">**Not ready**</span></span>

<span data-ttu-id="65cbb-291">セキュリティの既定値がオンになっている。</span><span class="sxs-lookup"><span data-stu-id="65cbb-291">You have Security defaults turned on.</span></span> <span data-ttu-id="65cbb-292">セキュリティの既定値をオフにして、条件付きアクセスポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="65cbb-293">詳細については、「 [一般的な条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="65cbb-294">セルフサービスによるパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="65cbb-294">Self-service Password Reset</span></span>

<span data-ttu-id="65cbb-295">セルフサービスのパスワードのリセット (SSPR) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="65cbb-296">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="65cbb-296">**Not ready**</span></span>

<span data-ttu-id="65cbb-297">すべてのユーザーに対して SSPR を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="65cbb-298">そうでない場合、Microsoft マネージドデスクトップサービスアカウントは動作しません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="65cbb-299">詳細については、「 [チュートリアル: ユーザーがアカウントのロックを解除するか、Azure Active Directory のセルフサービスによるパスワードのリセットを使用してパスワードをリセットする](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="65cbb-300">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-300">**Advisory**</span></span>

<span data-ttu-id="65cbb-301">[SSPR] **選択** した設定に、Microsoft Managed Desktop デバイスが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="65cbb-302">標準ユーザーの役割</span><span class="sxs-lookup"><span data-stu-id="65cbb-302">Standard user role</span></span>

<span data-ttu-id="65cbb-303">Microsoft Managed Desktop ユーザーは、ローカル管理者権限を持たない標準ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="65cbb-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="65cbb-304">これらのユーザーには、Microsoft マネージドデスクトップデバイスを開始するときに、標準のユーザー役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="65cbb-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="65cbb-305">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-305">**Advisory**</span></span>

<span data-ttu-id="65cbb-306">Microsoft マネージドデスクトップユーザーには、登録する前にローカル管理者の権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="65cbb-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="65cbb-307">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="65cbb-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="65cbb-308">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="65cbb-308">OneDrive for Business</span></span>

<span data-ttu-id="65cbb-309">[ **特定のドメインに参加している pc でのみ同期を許可** する] の設定は、Microsoft マネージドデスクトップと競合します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="65cbb-310">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="65cbb-310">**Advisory**</span></span>

<span data-ttu-id="65cbb-311">[ **特定のドメインに参加している pc でのみ同期を許可** する] 設定を使用している。</span><span class="sxs-lookup"><span data-stu-id="65cbb-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="65cbb-312">この設定は、Microsoft マネージドデスクトップでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="65cbb-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="65cbb-313">この設定を無効にし、代わりに、条件付きアクセスポリシーを使用するように OneDrive for Business を設定します。</span><span class="sxs-lookup"><span data-stu-id="65cbb-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="65cbb-314">ヘルプについて [は、「Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65cbb-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

