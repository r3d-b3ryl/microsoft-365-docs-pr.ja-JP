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
ms.openlocfilehash: f23209568fcfc2db4a22dbb034890c5a25e21bf7
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527735"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="4a8da-104">準備評価ツールによって検出された問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="4a8da-105">チェックが行われるたびに、ツールは次の4つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="4a8da-106">結果</span><span class="sxs-lookup"><span data-stu-id="4a8da-106">Result</span></span>  |<span data-ttu-id="4a8da-107">意味</span><span class="sxs-lookup"><span data-stu-id="4a8da-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="4a8da-108">準備完了</span><span class="sxs-lookup"><span data-stu-id="4a8da-108">Ready</span></span>     | <span data-ttu-id="4a8da-109">登録を完了する前にアクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="4a8da-110">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="4a8da-110">Advisory</span></span>    | <span data-ttu-id="4a8da-111">このツールまたはこの記事の手順に従って、登録とユーザーのための最適な操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4a8da-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="4a8da-112">登録は完了 *でき* ますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="4a8da-113">使用不可能</span><span class="sxs-lookup"><span data-stu-id="4a8da-113">Not ready</span></span> | <span data-ttu-id="4a8da-114">*これらの問題を修正しない場合、登録は失敗します。*</span><span class="sxs-lookup"><span data-stu-id="4a8da-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="4a8da-115">このツールまたはこの記事に記載されている手順に従って解決してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="4a8da-116">Error</span><span class="sxs-lookup"><span data-stu-id="4a8da-116">Error</span></span> | <span data-ttu-id="4a8da-117">使用している Azure Active Director (AD) の役割には、このチェックを実行するための十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="4a8da-118">Microsoft Intune の設定</span><span class="sxs-lookup"><span data-stu-id="4a8da-118">Microsoft Intune settings</span></span>

<span data-ttu-id="4a8da-119">Intune の設定には、Microsoft エンドポイントマネージャー [管理センター](https://endpoint.microsoft.com)でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4a8da-119">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="4a8da-120">自動操縦展開プロファイル</span><span class="sxs-lookup"><span data-stu-id="4a8da-120">Autopilot deployment profile</span></span>

<span data-ttu-id="4a8da-121">Microsoft マネージドデスクトップによって使用される、割り当てられたグループまたは動的なグループを対象とした既存の自動操縦プロファイルはありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-121">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a8da-122">Microsoft Managed Desktop は、自動操縦を使用して新しいデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-122">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="4a8da-123">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-123">**Not ready**</span></span>

<span data-ttu-id="4a8da-124">すべてのデバイスに割り当てられている自動操縦プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-124">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="4a8da-125">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-125">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="4a8da-126">Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-126">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="4a8da-127">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-127">**Advisory**</span></span>

<span data-ttu-id="4a8da-128">自動操縦プロファイルが、登録時に作成される Microsoft マネージドデスクトップデバイスを含まない、割り当てられた、または動的な Azure AD グループを対象としていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-128">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="4a8da-129">手順については、「 [Windows 自動操縦を使用した Intune での windows デバイスの登録](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-129">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="4a8da-130">Microsoft Managed Desktop enrollment の後、自動操縦ポリシーを設定して、 **モダン Workplace Devices-All** Azure AD グループを除外します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-130">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="4a8da-131">証明書コネクタ</span><span class="sxs-lookup"><span data-stu-id="4a8da-131">Certificate connectors</span></span>

<span data-ttu-id="4a8da-132">Microsoft マネージドデスクトップに登録するデバイスで使用されている証明書コネクタがある場合、コネクタにエラーはありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-132">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="4a8da-133">状況に応じて、次のいずれかのアドバイザリが適用されますので、慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-133">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="4a8da-134">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-134">**Advisory**</span></span>

<span data-ttu-id="4a8da-135">証明書コネクタが存在しません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-135">No certificate connectors are present.</span></span> <span data-ttu-id="4a8da-136">コネクタは必要ありませんが、Microsoft マネージドデスクトップデバイスへのネットワーク接続について必要な場合があるかどうかを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-136">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-137">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-137">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="4a8da-138">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-138">**Advisory**</span></span>

<span data-ttu-id="4a8da-139">少なくとも1つの証明書コネクタにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-139">At least one certificate connector has an error.</span></span> <span data-ttu-id="4a8da-140">このコネクタを Microsoft マネージドデスクトップデバイスに接続するために必要な場合は、このエラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-140">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="4a8da-141">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-141">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="4a8da-142">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-142">**Advisory**</span></span>

<span data-ttu-id="4a8da-143">少なくとも1つの証明書コネクタがあり、エラーは報告されていません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-143">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="4a8da-144">ただし、Microsoft マネージドデスクトップデバイスでコネクタを再利用するには、プロファイルを作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-144">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-145">詳細については、「 [Microsoft マネージドデスクトップの証明書とネットワークプロファイルを準備する](certs-wifi-lan.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-145">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="4a8da-146">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="4a8da-146">Conditional access policies</span></span>

<span data-ttu-id="4a8da-147">Azure AD 組織の条件付きアクセスポリシーで、Microsoft 管理デスクトップユーザーを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-147">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="4a8da-148">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-148">**Not ready**</span></span>

<span data-ttu-id="4a8da-149">すべてのユーザーを対象とする条件付きアクセスポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-149">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="4a8da-150">登録時に作成される Microsoft マネージドデスクトップサービスアカウントの Azure AD グループが含まれていない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-150">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="4a8da-151">手順については、「 [条件付きアクセス: ユーザーとグループ](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-151">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="4a8da-152">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-152">**Advisory**</span></span>

<span data-ttu-id="4a8da-153">**モダンワークプレースサービスアカウント** の Azure AD グループを除外している条件付きアクセスポリシーがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-153">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="4a8da-154">手順については、「 [条件付きアクセスを調整](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-154">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="4a8da-155">**モダン Workplace Service Accounts** Azure AD group は、登録時にサービスに対して作成する動的なグループです。</span><span class="sxs-lookup"><span data-stu-id="4a8da-155">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="4a8da-156">登録後にこのグループを除外するには、戻る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-156">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="4a8da-157">これらのサービスアカウントの詳細については、「 [標準の運用手順](../service-description/operations-and-monitoring.md#standard-operating-procedures)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-157">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="4a8da-158">**Error**</span><span class="sxs-lookup"><span data-stu-id="4a8da-158">**Error**</span></span>

<span data-ttu-id="4a8da-159">Intune 管理者の役割には、このチェックに十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-159">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="4a8da-160">このチェックを実行するには、次のいずれかの Azure AD 役割が割り当てられている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-160">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="4a8da-161">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="4a8da-161">Security Reader</span></span>
- <span data-ttu-id="4a8da-162">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="4a8da-162">Security Administrator</span></span>
- <span data-ttu-id="4a8da-163">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="4a8da-163">Conditional Access Administrator</span></span>
- <span data-ttu-id="4a8da-164">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="4a8da-164">Global Reader</span></span>
- <span data-ttu-id="4a8da-165">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="4a8da-165">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="4a8da-166">デバイスコンプライアンスポリシー</span><span class="sxs-lookup"><span data-stu-id="4a8da-166">Device Compliance policies</span></span>

<span data-ttu-id="4a8da-167">Azure AD 組織の Intune デバイスコンプライアンスポリシーでは、Microsoft Managed Desktop ユーザーを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-167">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="4a8da-168">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-168">**Not ready**</span></span>

<span data-ttu-id="4a8da-169">すべてのユーザーを対象とするコンプライアンスポリシーが少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-169">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="4a8da-170">Microsoft Managed Desktop ユーザーを含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-170">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="4a8da-171">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-171">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="4a8da-172">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-172">**Advisory**</span></span>

<span data-ttu-id="4a8da-173">コンプライアンスポリシーに Microsoft Managed Desktop のユーザーが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-173">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="4a8da-174">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="4a8da-175">デバイス構成ポリシー</span><span class="sxs-lookup"><span data-stu-id="4a8da-175">Device Configuration policies</span></span>

<span data-ttu-id="4a8da-176">Azure AD 組織の Intune デバイス構成ポリシーでは、Microsoft 管理デスクトップデバイスまたはユーザーを対象としてはなりません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-176">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="4a8da-177">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-177">**Not ready**</span></span>

<span data-ttu-id="4a8da-178">すべてのユーザー、すべてのデバイス、またはその両方を対象とする構成ポリシーが、少なくとも1つあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-178">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="4a8da-179">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とするようにポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-179">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-180">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-180">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="4a8da-181">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-181">**Advisory**</span></span>

<span data-ttu-id="4a8da-182">コンプライアンスポリシーに、Microsoft マネージドデスクトップデバイスやユーザーが含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-182">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="4a8da-183">手順については、「 [Microsoft Intune でコンプライアンスポリシーを作成する](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-183">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="4a8da-184">デバイスの種類の制限</span><span class="sxs-lookup"><span data-stu-id="4a8da-184">Device type restrictions</span></span>

<span data-ttu-id="4a8da-185">Microsoft マネージドデスクトップデバイスでは、Intune への登録が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-185">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="4a8da-186">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-186">**Not ready**</span></span>

<span data-ttu-id="4a8da-187">「 [登録の制限を設定](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) する」の手順に従って、設定を [ **許可**] に変更します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-187">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="4a8da-188">登録の状態ページ</span><span class="sxs-lookup"><span data-stu-id="4a8da-188">Enrollment Status Page</span></span>

<span data-ttu-id="4a8da-189">現在、登録状態ページ (ESP) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4a8da-189">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="4a8da-190">この機能のパブリックプレビューに参加している場合は、この項目を無視できます。</span><span class="sxs-lookup"><span data-stu-id="4a8da-190">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="4a8da-191">詳細については、「 [自動操縦による初回実行時の動作」および「登録の状態」ページ](../get-started/esp-first-run.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-191">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="4a8da-192">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-192">**Not ready**</span></span>

<span data-ttu-id="4a8da-193">**アプリケーションとプロファイルの構成の進行状況を示す** ように、ESP の既定のプロファイルが設定されている。</span><span class="sxs-lookup"><span data-stu-id="4a8da-193">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="4a8da-194">この設定を無効にするか、[ [登録状態の設定] ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)の手順に従って、Azure AD グループへの割り当てに Microsoft Managed Desktop デバイスが含まれないようにします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-194">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="4a8da-195">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-195">**Advisory**</span></span>

<span data-ttu-id="4a8da-196">[ **アプリとプロファイルの構成の進行状況]** の設定を含むすべてのプロファイルが、Microsoft Managed Desktop デバイスを含む Azure AD グループに割り当てられていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-196">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-197">詳細については、「 [登録の状態を設定する」ページ](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-197">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="4a8da-198">Intune の登録</span><span class="sxs-lookup"><span data-stu-id="4a8da-198">Intune enrollment</span></span>

<span data-ttu-id="4a8da-199">Azure AD 組織の Windows 10 デバイスは、自動的に Intune に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-199">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="4a8da-200">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-200">**Advisory**</span></span>

<span data-ttu-id="4a8da-201">MDM ユーザースコープが **一部** または **すべて** に設定されていることを確認し、 **[なし**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-201">Make sure the MDM User scope is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="4a8da-202">**一部** を選択した場合は、登録した後に戻って、**グループ** の **モダンワークプレースすべて** の Azure AD グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-202">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="4a8da-203">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="4a8da-203">Microsoft Store for Business</span></span>

<span data-ttu-id="4a8da-204">Microsoft Store for Business を使用して、会社のポータルをダウンロードして Microsoft Project や Microsoft Visio などの一部のアプリを展開できるようにしています。</span><span class="sxs-lookup"><span data-stu-id="4a8da-204">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="4a8da-205">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-205">**Not ready**</span></span>

<span data-ttu-id="4a8da-206">Microsoft Store for Business が有効になっていないか、Intune と同期されていません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="4a8da-207">詳細については、「microsoft [Store For Business For Business With Microsoft intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 」と「 [デバイス上に intune ポータルサイトをインストール](../get-started/company-portal.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="4a8da-208">多要素認証</span><span class="sxs-lookup"><span data-stu-id="4a8da-208">Multifactor authentication</span></span>

<span data-ttu-id="4a8da-209">多元的認証は、Microsoft マネージドデスクトップサービスアカウントに誤って適用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-209">Multifactor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="4a8da-210">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-210">**Not ready**</span></span>

<span data-ttu-id="4a8da-211">すべてのユーザーに割り当てられている条件付きアクセスポリシーについては、いくつかの多元的な認証 (MFA) ポリシーを "必須" として設定しています。</span><span class="sxs-lookup"><span data-stu-id="4a8da-211">You have some multifactor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="4a8da-212">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-212">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-213">詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-213">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="4a8da-214">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-214">**Advisory**</span></span>

<span data-ttu-id="4a8da-215">MFA を必要とする条件付きアクセスポリシーが、 **モダンワークプレースすべて** の Azure AD グループを除外していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-215">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="4a8da-216">詳細については、「 [条件付きアクセスポリシー](#conditional-access-policies) と [条件付きアクセス: すべてのユーザーに MFA を必須にする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="4a8da-217">**モダンワークプレースすべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的なグループです。そのため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-217">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="4a8da-218">**Error**</span><span class="sxs-lookup"><span data-stu-id="4a8da-218">**Error**</span></span>

<span data-ttu-id="4a8da-219">Intune 管理者の役割には、このチェックに十分な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="4a8da-220">このチェックを実行するには、次のいずれかの Azure AD 役割が割り当てられている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="4a8da-221">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="4a8da-221">Security Reader</span></span>
- <span data-ttu-id="4a8da-222">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="4a8da-222">Security Administrator</span></span>
- <span data-ttu-id="4a8da-223">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="4a8da-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="4a8da-224">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="4a8da-224">Global Reader</span></span>
- <span data-ttu-id="4a8da-225">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="4a8da-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="4a8da-226">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="4a8da-226">PowerShell scripts</span></span>

<span data-ttu-id="4a8da-227">Windows PowerShell スクリプトは、Microsoft マネージドデスクトップデバイスを対象とする方法では割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="4a8da-228">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-228">**Advisory**</span></span>

<span data-ttu-id="4a8da-229">Azure AD 組織の Windows PowerShell スクリプトが、Microsoft 管理デスクトップデバイスまたはユーザーを対象としないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="4a8da-230">PowerShell スクリプトを割り当てないでください。すべてのユーザー、すべてのデバイス、またはその両方を対象とします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-230">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="4a8da-231">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-231">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-232">詳細については、「 [Windows 10 デバイスでの Intune での PowerShell スクリプトの使用](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-232">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="4a8da-233">地域</span><span class="sxs-lookup"><span data-stu-id="4a8da-233">Region</span></span>

<span data-ttu-id="4a8da-234">お客様の地域は、Microsoft マネージドデスクトップでサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-234">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4a8da-235">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-235">**Not ready**</span></span>

<span data-ttu-id="4a8da-236">Azure AD 組織の地域は、Microsoft マネージドデスクトップで現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-236">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a8da-237">詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-237">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="4a8da-238">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-238">**Advisory**</span></span>

<span data-ttu-id="4a8da-239">Azure AD 組織が配置されている1つ以上の国が Microsoft マネージドデスクトップでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-239">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a8da-240">詳細については、「 [Microsoft Managed Desktop supported の地域と言語](../service-description/regions-languages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="4a8da-241">セキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="4a8da-241">Security baselines</span></span>

<span data-ttu-id="4a8da-242">セキュリティベースラインポリシーでは、Microsoft マネージドデスクトップデバイスを対象としてはなりません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-242">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="4a8da-243">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-243">**Not ready**</span></span>

<span data-ttu-id="4a8da-244">すべてのユーザー、すべてのデバイス、またはその両方を対象とするセキュリティ基準プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-244">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="4a8da-245">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-245">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-246">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-246">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="4a8da-247">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-247">**Advisory**</span></span>

<span data-ttu-id="4a8da-248">Microsoft マネージドデスクトップデバイスを除外しているセキュリティベースラインポリシーがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-248">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-249">手順については、「 [セキュリティ基準を使用して Intune で Windows 10 デバイスを構成する](https://docs.microsoft.com/mem/intune/protect/security-baselines)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="4a8da-250">**モダン Workplace Devices-すべて** の Azure AD グループは、Microsoft マネージドデスクトップに登録するときに作成する動的グループであるため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-250">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="4a8da-251">Windows アプリ</span><span class="sxs-lookup"><span data-stu-id="4a8da-251">Windows apps</span></span>

<span data-ttu-id="4a8da-252">Microsoft Managed Desktop users が所有しているアプリを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-252">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="4a8da-253">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-253">**Advisory**</span></span>

<span data-ttu-id="4a8da-254">Microsoft Managed Desktop ユーザーに割り当てるアプリのインベントリを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-254">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="4a8da-255">これらのアプリは Intune によって展開される必要があるため、既存の Intune アプリを再利用することを評価してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-255">Since these apps must be deployed by Intune, evaluate re-using existing Intune apps.</span></span> <span data-ttu-id="4a8da-256">企業ポータルの使用を検討してください (「デバイスおよび登録状態ページ (ESP) [に Intune ポータルサイトをインストール](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) する」を参照し、ユーザーにアプリを配布してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-256">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="4a8da-257">詳細については、「 [Microsoft マネージドデスクトップのアプリ](apps.md) 」および「 [自動操縦の状態」ページにある初回実行時の環境](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-257">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="4a8da-258">Microsoft エンドポイント構成マネージャーのクエリを Microsoft アカウント担当者に依頼して、Intune に移行する準備ができているアプリや調整が必要なアプリを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="4a8da-258">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="4a8da-259">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="4a8da-259">Windows Hello for Business</span></span>

<span data-ttu-id="4a8da-260">Microsoft マネージドデスクトップでは、Windows Hello for Business を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-260">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="4a8da-261">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-261">**Not ready**</span></span>

<span data-ttu-id="4a8da-262">Windows Hello for Business は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4a8da-262">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="4a8da-263">「 [Create a Windows Hello For Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 」の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="4a8da-264">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-264">**Advisory**</span></span>

<span data-ttu-id="4a8da-265">Windows Hello for Business がセットアップされていません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-265">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="4a8da-266">「 [Create a Windows Hello For business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)」の手順に従って、これを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4a8da-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="4a8da-267">Windows 10 の更新リング</span><span class="sxs-lookup"><span data-stu-id="4a8da-267">Windows 10 update rings</span></span>

<span data-ttu-id="4a8da-268">Intune の "Windows 10 update ring" ポリシーで、Microsoft マネージドデスクトップデバイスを対象としないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-268">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="4a8da-269">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-269">**Not ready**</span></span>

<span data-ttu-id="4a8da-270">すべてのデバイス、すべてのユーザー、またはその両方を対象とする "更新リング" ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-270">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="4a8da-271">Microsoft マネージドデスクトップデバイスを一切含まない特定の Azure AD グループを対象とする割り当てを使用するようにポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-271">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="4a8da-272">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="4a8da-273">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-273">**Advisory**</span></span>

<span data-ttu-id="4a8da-274">すべての更新リングポリシーで、 **モダン Workplace Devices** を除外していることを確認してください。すべての Azure AD グループ。</span><span class="sxs-lookup"><span data-stu-id="4a8da-274">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="4a8da-275">これらのポリシーに Azure AD ユーザーグループを割り当てている場合は、すべての更新リングポリシーで、Microsoft Managed Desktop ユーザーが含まれる、 **モダンワークプレースすべて** の azure ad グループも除外していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-275">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="4a8da-276">手順については、「 [Intune で Windows 10 ソフトウェアの更新プログラムを管理](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-276">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="4a8da-277">**モダン Workplace Devices-all** および **モダン workplace-** すべての Azure AD グループには、Microsoft マネージドデスクトップに登録したときに作成したグループが割り当てられます。そのため、登録後にこのグループを除外する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-277">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="4a8da-278">Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="4a8da-278">Azure Active Directory settings</span></span>

<span data-ttu-id="4a8da-279">Azure [portal](https://portal.azure.com)で Azure Active Directory の設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4a8da-279">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="4a8da-280">アドホックサブスクリプション</span><span class="sxs-lookup"><span data-stu-id="4a8da-280">Ad hoc subscriptions</span></span>

<span data-ttu-id="4a8da-281">"False" に設定されている設定をチェックする方法を確認する方法を説明します。エンタープライズ状態の移動が正常に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-281">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="4a8da-282">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-282">**Advisory**</span></span>

<span data-ttu-id="4a8da-283">**AllowAdHocSubscriptions** が **True** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-283">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="4a8da-284">それ以外の場合、エンタープライズ状態ローミングは機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-284">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="4a8da-285">詳細については、「 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-285">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="4a8da-286">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="4a8da-286">Enterprise State Roaming</span></span>

<span data-ttu-id="4a8da-287">エンタープライズ状態ローミングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-287">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="4a8da-288">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-288">**Advisory**</span></span>

<span data-ttu-id="4a8da-289">エンタープライズ状態の移動が、 **すべて** のグループまたは **選択した** グループに対して有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-289">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="4a8da-290">詳細については、「 [Azure Active Directory でエンタープライズ状態のローミングを有効にする](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-290">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="4a8da-291">ライセンス</span><span class="sxs-lookup"><span data-stu-id="4a8da-291">Licenses</span></span>

<span data-ttu-id="4a8da-292">Microsoft マネージドデスクトップを使用するには、いくつかのライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4a8da-292">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4a8da-293">**準備ができていない**</span><span class="sxs-lookup"><span data-stu-id="4a8da-293">**Not Ready**</span></span>

<span data-ttu-id="4a8da-294">Microsoft マネージドデスクトップを使用するために必要なすべてのライセンスがありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-294">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a8da-295">詳細については、「 [Microsoft Managed Desktop technologies](../intro/technologies.md) 」および「 [ライセンスについ](prerequisites.md#more-about-licenses)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-295">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="4a8da-296">セキュリティアカウント名</span><span class="sxs-lookup"><span data-stu-id="4a8da-296">Security account names</span></span>

<span data-ttu-id="4a8da-297">一部のセキュリティアカウント名は、Microsoft マネージドデスクトップによって作成されたものと競合する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-297">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="4a8da-298">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-298">**Not ready**</span></span>

<span data-ttu-id="4a8da-299">Microsoft マネージドデスクトップによって作成されたアカウントと競合する、少なくとも1つのアカウント名がある。</span><span class="sxs-lookup"><span data-stu-id="4a8da-299">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a8da-300">Microsoft アカウントの担当者と協力して、これらのアカウント名を除外します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-300">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="4a8da-301">セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="4a8da-301">Security administrator roles</span></span>

<span data-ttu-id="4a8da-302">特定のセキュリティロールを持つユーザーは、エンドポイントの Microsoft Defender で割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-302">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="4a8da-303">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-303">**Advisory**</span></span>

<span data-ttu-id="4a8da-304">ユーザーが Azure AD 組織でこれらの役割のいずれかに割り当てられている場合は、エンドポイントの Microsoft Defender でもこれらの役割が割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-304">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4a8da-305">そうしないと、これらの役割を持つ管理者は管理ポータルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-305">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="4a8da-306">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="4a8da-306">Security Operator</span></span>
- <span data-ttu-id="4a8da-307">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="4a8da-307">Global Reader</span></span>

<span data-ttu-id="4a8da-308">詳細については、「 [役割ベースのアクセス制御の役割を作成および管理する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-308">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="4a8da-309">既定のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4a8da-309">Security default</span></span>

<span data-ttu-id="4a8da-310">Azure Active Directory のセキュリティの既定値を使用すると、Microsoft Managed Desktop がデバイスを管理できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-310">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="4a8da-311">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="4a8da-311">**Not ready**</span></span>

<span data-ttu-id="4a8da-312">セキュリティの既定値がオンになっている。</span><span class="sxs-lookup"><span data-stu-id="4a8da-312">You have Security defaults turned on.</span></span> <span data-ttu-id="4a8da-313">セキュリティの既定値をオフにして、条件付きアクセスポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-313">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="4a8da-314">詳細については、「 [一般的な条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-314">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="4a8da-315">セルフサービスによるパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="4a8da-315">Self-service Password Reset</span></span>

<span data-ttu-id="4a8da-316">Microsoft Managed Desktop service アカウントを除いたすべての Microsoft Managed Desktop users に対して、セルフサービスのパスワードのリセット (SSPR) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-316">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="4a8da-317">詳細については、「 [チュートリアル: ユーザーがアカウントのロックを解除するか、Azure Active Directory のセルフサービスによるパスワードのリセットを使用してパスワードをリセットする](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-317">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="4a8da-318">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-318">**Advisory**</span></span>

<span data-ttu-id="4a8da-319">SSPR が **選択** した設定に、Microsoft managed desktop デバイスは含まれていますが、Microsoft managed desktop service アカウントを除外していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-319">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="4a8da-320">SSPR が有効になっている場合、Microsoft マネージドデスクトップサービスアカウントは期待どおりに機能しません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-320">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="4a8da-321">標準ユーザーの役割</span><span class="sxs-lookup"><span data-stu-id="4a8da-321">Standard user role</span></span>

<span data-ttu-id="4a8da-322">グローバル管理者およびデバイス管理者の Azure AD ロールを割り当てられているユーザー以外は、Microsoft Managed Desktop ユーザーは、ローカル管理者特権を持たない標準ユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="4a8da-322">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="4a8da-323">他のすべてのユーザーには、Microsoft マネージドデスクトップデバイスを起動するときに、標準のユーザー役割が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="4a8da-323">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="4a8da-324">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-324">**Advisory**</span></span>

<span data-ttu-id="4a8da-325">Microsoft マネージドデスクトップのユーザーには、登録後の Microsoft マネージドデスクトップデバイスに対するローカル管理者権限がありません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-325">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="4a8da-326">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="4a8da-326">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="4a8da-327">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4a8da-327">OneDrive</span></span>

<span data-ttu-id="4a8da-328">[ **特定のドメインに参加している pc でのみ同期を許可** する] の設定は、Microsoft マネージドデスクトップと競合します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-328">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a8da-329">Onedrive [管理センター](https://admin.onedrive.com)で onedrive 設定にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4a8da-329">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="4a8da-330">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="4a8da-330">**Advisory**</span></span>

<span data-ttu-id="4a8da-331">[ **特定のドメインに参加している pc でのみ同期を許可** する] 設定を使用している。</span><span class="sxs-lookup"><span data-stu-id="4a8da-331">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="4a8da-332">この設定は、Microsoft マネージドデスクトップでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4a8da-332">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="4a8da-333">この設定を無効にして、代わりに、条件付きアクセスポリシーを使用するように OneDrive を設定します。</span><span class="sxs-lookup"><span data-stu-id="4a8da-333">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="4a8da-334">ヘルプについて [は、「Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a8da-334">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

