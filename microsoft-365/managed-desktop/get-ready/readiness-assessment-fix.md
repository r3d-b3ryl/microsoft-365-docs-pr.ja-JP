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
audience: Admin
ms.openlocfilehash: 9d2f9a95b3d5d90b79122d55477284083ea8332e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286887"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="16fd3-104">準備評価ツールで見つかった問題を修正する</span><span class="sxs-lookup"><span data-stu-id="16fd3-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="16fd3-105">チェックごとに、ツールは次の 4 つの結果のいずれかを報告します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="16fd3-106">結果</span><span class="sxs-lookup"><span data-stu-id="16fd3-106">Result</span></span>  |<span data-ttu-id="16fd3-107">意味</span><span class="sxs-lookup"><span data-stu-id="16fd3-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="16fd3-108">準備完了</span><span class="sxs-lookup"><span data-stu-id="16fd3-108">Ready</span></span>     | <span data-ttu-id="16fd3-109">登録を完了する前に、アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="16fd3-110">アドバイザリ</span><span class="sxs-lookup"><span data-stu-id="16fd3-110">Advisory</span></span>    | <span data-ttu-id="16fd3-111">登録とユーザーの最適なエクスペリエンスについては、ツールまたはこの記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="16fd3-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="16fd3-112">登録 *は* 完了できますが、最初のデバイスを展開する前に、これらの問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="16fd3-113">使用不可能</span><span class="sxs-lookup"><span data-stu-id="16fd3-113">Not ready</span></span> | <span data-ttu-id="16fd3-114">*これらの問題を解決しない場合、登録は失敗します。*</span><span class="sxs-lookup"><span data-stu-id="16fd3-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="16fd3-115">ツールまたはこの記事の手順に従って解決します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="16fd3-116">Error</span><span class="sxs-lookup"><span data-stu-id="16fd3-116">Error</span></span> | <span data-ttu-id="16fd3-117">使用Azure Active Directory (AD) ロールには、このチェックを実行するための十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="16fd3-118">このツールによって報告された結果は、設定を実行した特定の時点でのみ設定の状態を反映します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="16fd3-119">後で Microsoft Intune、Azure Active Directory、または Microsoft 365 のポリシーに変更を加えた場合、"準備完了" だったアイテムは "準備完了" になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="16fd3-120">ポリシーを変更する前Microsoft マネージド デスクトップ、この記事で説明されている特定の設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="16fd3-121">Microsoft Intune設定</span><span class="sxs-lookup"><span data-stu-id="16fd3-121">Microsoft Intune settings</span></span>

<span data-ttu-id="16fd3-122">Intune の設定には、管理センターのMicrosoft エンドポイント マネージャー[アクセスできます](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="16fd3-123">自動パイロット展開プロファイル</span><span class="sxs-lookup"><span data-stu-id="16fd3-123">Autopilot deployment profile</span></span>

<span data-ttu-id="16fd3-124">割り当てられたグループまたは動的グループをターゲットとする既存の Autopilot プロファイルを、Microsoft マネージド デスクトップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-125">Microsoft マネージド デスクトップを使用して新しいデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="16fd3-126">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-126">**Not ready**</span></span>

<span data-ttu-id="16fd3-127">すべてのデバイスに割り当てられている自動パイロット プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="16fd3-128">手順については[、「Autopilot を使用Windows Intune にデバイスを登録する」を参照Windowsしてください](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="16fd3-129">登録Microsoft マネージド デスクトップ後、Autopilot ポリシーを設定して、モダン **Workplace デバイス -All** Azure ADグループをADします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="16fd3-130">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-130">**Advisory**</span></span>

<span data-ttu-id="16fd3-131">Autopilot プロファイルが、割り当てられたまたは動的な Azure ADデバイスを含Microsoft マネージド デスクトップしてください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-132">手順については[、「Autopilot を使用Windows Intune にデバイスを登録する」を参照Windowsしてください](/mem/autopilot/enrollment-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="16fd3-133">登録Microsoft マネージド デスクトップ、Autopilot プロファイルを設定して、モダン Workplace **デバイス -All** Azure ADグループを除外します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="16fd3-134">証明書コネクタ</span><span class="sxs-lookup"><span data-stu-id="16fd3-134">Certificate connectors</span></span>

<span data-ttu-id="16fd3-135">Microsoft マネージド デスクトップ に登録するデバイスで使用される証明書コネクタがある場合、コネクタにエラーは発生しません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="16fd3-136">以下のアドバイザリの 1 つだけが状況に適用されますので、注意深く確認してください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="16fd3-137">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-137">**Advisory**</span></span>

<span data-ttu-id="16fd3-138">証明書コネクタはありません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-138">No certificate connectors are present.</span></span> <span data-ttu-id="16fd3-139">コネクタは必要ない可能性がありますが、デバイスのネットワーク接続に必要かどうかを評価Microsoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-140">詳細については、「証明書とネットワーク プロファイルを準備する」[を参照Microsoft マネージド デスクトップ。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="16fd3-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="16fd3-141">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-141">**Advisory**</span></span>

<span data-ttu-id="16fd3-142">少なくとも 1 つの証明書コネクタにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="16fd3-143">デバイスに証明書を提供するためにこのコネクタが必要Microsoft マネージド デスクトップ、エラーを解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="16fd3-144">詳細については、「証明書とネットワーク プロファイルを準備する」[を参照Microsoft マネージド デスクトップ。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="16fd3-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="16fd3-145">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-145">**Advisory**</span></span>

<span data-ttu-id="16fd3-146">証明書コネクタが 1 つ以上あるので、エラーは報告されません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="16fd3-147">ただし、展開の準備として、デバイスのコネクタを再利用するためにプロファイルを作成Microsoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-148">詳細については、「証明書とネットワーク プロファイルを準備する」[を参照Microsoft マネージド デスクトップ。](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="16fd3-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

### <a name="company-portal"></a><span data-ttu-id="16fd3-149">ポータル サイト</span><span class="sxs-lookup"><span data-stu-id="16fd3-149">Company Portal</span></span>

<span data-ttu-id="16fd3-150">Microsoft マネージド デスクトップ IT 管理者は、ユーザーがデバイスを使用Intune ポータル サイトユーザー用にMicrosoft マネージド デスクトップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-150">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="16fd3-151">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-151">**Not ready**</span></span>

<span data-ttu-id="16fd3-152">ユーザーに対ポータル サイトインストールされていない。</span><span class="sxs-lookup"><span data-stu-id="16fd3-152">You do not have Company Portal installed for your users.</span></span> <span data-ttu-id="16fd3-153">Intune ポータル サイト同期を強制的に行い、Intune とデバイス間の同期をビジネス向け Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="16fd3-153">Purchase Company Portal and force a sync between Intune and Microsoft Store for Business.</span></span> <span data-ttu-id="16fd3-154">詳細については、「デバイスにインストール[するIntune ポータル サイト」を参照してください](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-154">For more information, see [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="16fd3-155">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="16fd3-155">Conditional access policies</span></span>

<span data-ttu-id="16fd3-156">条件付きアクセス ポリシーは、Intune Microsoft マネージド デスクトップ Azure AD組織 (テナント) の管理を妨AD。</span><span class="sxs-lookup"><span data-stu-id="16fd3-156">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="16fd3-157">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-157">**Not ready**</span></span>

<span data-ttu-id="16fd3-158">すべてのユーザーを対象とする条件付きアクセス ポリシーが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-158">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="16fd3-159">登録時に、関連する条件付きアクセス Microsoft マネージド デスクトップサービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-159">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="16fd3-160">登録後、条件付きアクセス ポリシー Microsoft マネージド デスクトップを確認Microsoft エンドポイント マネージャー。</span><span class="sxs-lookup"><span data-stu-id="16fd3-160">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="16fd3-161">これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-161">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="16fd3-162">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-162">**Advisory**</span></span>

<span data-ttu-id="16fd3-163">条件付きアクセス ポリシーを使用すると、Microsoft マネージド デスクトップサービスを管理Microsoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-163">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="16fd3-164">登録時に、関連する条件付きアクセス Microsoft マネージド デスクトップサービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-164">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="16fd3-165">これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-165">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="16fd3-166">**Error**</span><span class="sxs-lookup"><span data-stu-id="16fd3-166">**Error**</span></span>

<span data-ttu-id="16fd3-167">Intune 管理者の役割には、このチェックに対する十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-167">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="16fd3-168">このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-168">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="16fd3-169">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="16fd3-169">Security Reader</span></span>
- <span data-ttu-id="16fd3-170">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="16fd3-170">Security Administrator</span></span>
- <span data-ttu-id="16fd3-171">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="16fd3-171">Conditional Access Administrator</span></span>
- <span data-ttu-id="16fd3-172">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="16fd3-172">Global Reader</span></span>
- <span data-ttu-id="16fd3-173">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="16fd3-173">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="16fd3-174">デバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="16fd3-174">Device Compliance policies</span></span>

<span data-ttu-id="16fd3-175">Azure 組織の Intune デバイス コンプライアンス ポリシー ADデバイスにMicrosoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-175">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="16fd3-176">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-176">**Not ready**</span></span>

<span data-ttu-id="16fd3-177">すべてのユーザーを対象とする少なくとも 1 つのコンプライアンス ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-177">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="16fd3-178">Microsoft マネージド デスクトップデバイスを対象とするコンプライアンス ポリシー Microsoft マネージド デスクトップ含まれます。</span><span class="sxs-lookup"><span data-stu-id="16fd3-178">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="16fd3-179">ポリシーを変更して、ユーザーまたはデバイスAD含む特定の Azure Microsoft マネージド デスクトップグループをターゲットにします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-179">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="16fd3-180">手順については、「コンプライアンス ポリシー[を作成する」を参照Microsoft Intune。](/mem/intune/protect/create-compliance-policy)</span><span class="sxs-lookup"><span data-stu-id="16fd3-180">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="16fd3-181">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-181">**Advisory**</span></span>

<span data-ttu-id="16fd3-182">コンプライアンス ポリシーがユーザーを対象とMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-182">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="16fd3-183">手順については、「コンプライアンス ポリシー[を作成する」を参照Microsoft Intune。](/mem/intune/protect/create-compliance-policy)</span><span class="sxs-lookup"><span data-stu-id="16fd3-183">For steps, see [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="16fd3-184">デバイス構成プロファイル</span><span class="sxs-lookup"><span data-stu-id="16fd3-184">Device Configuration profiles</span></span>

<span data-ttu-id="16fd3-185">Azure 組織の Intune デバイス構成プロファイルAD、Microsoft Manage Desktop デバイスまたはユーザーをターゲットにしなける必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-185">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="16fd3-186">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-186">**Not ready**</span></span>

<span data-ttu-id="16fd3-187">すべてのユーザー、すべてのデバイス、または両方を対象とする構成プロファイルが少なくとも 1 つあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-187">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="16fd3-188">プロファイルをリセットして、特定の Azure ADデバイスを含Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-188">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-189">手順については、「カスタム設定[を使用してプロファイルを作成する」を参照Microsoft Intune。](/mem/intune/configuration/custom-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="16fd3-189">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="16fd3-190">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-190">**Advisory**</span></span>

<span data-ttu-id="16fd3-191">構成ポリシーにデバイスまたはユーザーが含Microsoft マネージド デスクトップしてください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-191">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="16fd3-192">手順については、「カスタム設定[を使用してプロファイルを作成する」を参照Microsoft Intune。](/mem/intune/configuration/custom-settings-configure)</span><span class="sxs-lookup"><span data-stu-id="16fd3-192">For steps, see [Create a profile with custom settings in Microsoft Intune](/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="16fd3-193">デバイスの種類の制限</span><span class="sxs-lookup"><span data-stu-id="16fd3-193">Device type restrictions</span></span>

<span data-ttu-id="16fd3-194">Microsoft マネージド デスクトップ Intune への登録を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-194">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="16fd3-195">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-195">**Not ready**</span></span>

<span data-ttu-id="16fd3-196">現在、Intune でのデバイスへの登録を許可Windows、少なくとも 1 つの登録制限ポリシーが構成されています。</span><span class="sxs-lookup"><span data-stu-id="16fd3-196">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="16fd3-197">「ユーザーを対象 [](/mem/intune/enrollment/enrollment-restrictions-set)とする登録制限ポリシーごとに登録制限を設定し、Microsoft マネージド デスクトップ **(MDM)** 設定を [許可] に変更Windows手順に従 **います**。</span><span class="sxs-lookup"><span data-stu-id="16fd3-197">Follow the steps in [Set enrollment restrictions](/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="16fd3-198">ただし、個人所有のデバイス **(MDM)** Windowsを [ブロック] に **設定できます**。</span><span class="sxs-lookup"><span data-stu-id="16fd3-198">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="16fd3-199">[登録の状態] ページ</span><span class="sxs-lookup"><span data-stu-id="16fd3-199">Enrollment Status Page</span></span>

<span data-ttu-id="16fd3-200">現在、登録状態ページ (ESP) が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="16fd3-200">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="16fd3-201">この機能のパブリック プレビュー Microsoft マネージド デスクトップ参加する場合は、このアイテムを無視できます。</span><span class="sxs-lookup"><span data-stu-id="16fd3-201">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="16fd3-202">詳細については [、「First-run experience with Autopilot」および「登録状態ページ」を参照してください](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-202">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="16fd3-203">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-203">**Not ready**</span></span>

<span data-ttu-id="16fd3-204">ESP の既定のプロファイルが [アプリとプロファイルの構成の進行状況 **を表示する] に設定されています**。</span><span class="sxs-lookup"><span data-stu-id="16fd3-204">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="16fd3-205">この設定を無効にするか、Azure AD グループへの割り当てに Microsoft マネージド デスクトップ デバイスが含まれるのを確認するには、「登録状態ページのセットアップ」の手順に[従います](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-205">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="16fd3-206">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-206">**Advisory**</span></span>

<span data-ttu-id="16fd3-207">[アプリとプロファイルの構成の進行状況を表示する] 設定を持つプロファイルが、デバイスを含む Azure AD グループに割りMicrosoft マネージド デスクトップしてください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-207">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-208">詳細については、「登録状態 [ページの設定」を参照してください](/mem/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-208">For more information, see [Set up the Enrollment Status Page](/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="16fd3-209">ビジネス向け Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="16fd3-209">Microsoft Store for Business</span></span>

<span data-ttu-id="16fd3-210">ビジネス向け Microsoft Store ポータル サイト アプリを Microsoft マネージド デスクトップ に展開して、Microsoft Project や Microsoft Visio などの一部のアプリを必要に応じてインストールできます (許可されている場合)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-210">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="16fd3-211">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-211">**Not ready**</span></span>

<span data-ttu-id="16fd3-212">ビジネス向け Microsoft Store有効になっていないか、Intune と同期されていない場合。</span><span class="sxs-lookup"><span data-stu-id="16fd3-212">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="16fd3-213">詳細については、「How [to manage volume purchased](/mem/intune/apps/windows-store-for-business) apps from the ビジネス向け Microsoft Store Microsoft Intune デバイスIntune ポータル サイトインストールする」を[参照してください](../get-started/company-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-213">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="16fd3-214">多要素認証</span><span class="sxs-lookup"><span data-stu-id="16fd3-214">Multifactor authentication</span></span>

<span data-ttu-id="16fd3-215">多要素認証では、Intune Microsoft マネージド デスクトップ Azure AD組織 (テナント) を管理AD。</span><span class="sxs-lookup"><span data-stu-id="16fd3-215">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="16fd3-216">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-216">**Not ready**</span></span>

<span data-ttu-id="16fd3-217">すべてのユーザーに割り当てられている条件付きアクセスポリシーでは、必要に応じていくつかの多要素認証ポリシーが設定されています。</span><span class="sxs-lookup"><span data-stu-id="16fd3-217">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="16fd3-218">登録時に、関連する条件付きアクセス Microsoft マネージド デスクトップサービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-218">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="16fd3-219">これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-219">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="16fd3-220">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-220">**Advisory**</span></span>

<span data-ttu-id="16fd3-221">条件付きアクセス ポリシーでは、複数要素認証が必要になります。この場合、Microsoft マネージド デスクトップサービスを管理Microsoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-221">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="16fd3-222">登録時に、関連する条件付きアクセス Microsoft マネージド デスクトップサービス アカウントを除外し、これらのアカウントへのアクセスを制限する新しい条件付きアクセス ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-222">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="16fd3-223">これらのサービス アカウントの詳細については、「Standard operating [procedures」を参照してください](../service-description/operations-and-monitoring.md#standard-operating-procedures)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-223">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="16fd3-224">**Error**</span><span class="sxs-lookup"><span data-stu-id="16fd3-224">**Error**</span></span>

<span data-ttu-id="16fd3-225">Intune 管理者の役割には、このチェックに対する十分なアクセス許可が付与されません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-225">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="16fd3-226">このチェックを実行するには、次の Azure ADロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-226">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="16fd3-227">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="16fd3-227">Security Reader</span></span>
- <span data-ttu-id="16fd3-228">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="16fd3-228">Security Administrator</span></span>
- <span data-ttu-id="16fd3-229">条件付きアクセス管理者</span><span class="sxs-lookup"><span data-stu-id="16fd3-229">Conditional Access Administrator</span></span>
- <span data-ttu-id="16fd3-230">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="16fd3-230">Global Reader</span></span>
- <span data-ttu-id="16fd3-231">デバイス管理者</span><span class="sxs-lookup"><span data-stu-id="16fd3-231">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="16fd3-232">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="16fd3-232">PowerShell scripts</span></span>

<span data-ttu-id="16fd3-233">Windows PowerShellデバイスをターゲットとする方法では、スクリプトを割りMicrosoft マネージド デスクトップできません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-233">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="16fd3-234">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-234">**Advisory**</span></span>

<span data-ttu-id="16fd3-235">組織の Azure Windows PowerShellスクリプトAD Microsoft Manage Desktop デバイスまたはユーザーを対象とされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-235">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="16fd3-236">すべてのユーザー、すべてのデバイス、または両方を対象とする PowerShell スクリプトを割り当てない。</span><span class="sxs-lookup"><span data-stu-id="16fd3-236">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="16fd3-237">ポリシーを変更して、特定の Azure ADデバイスまたはユーザーを含Microsoft マネージド デスクトップ割り当てを使用します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-237">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="16fd3-238">詳細については、「Intune のデバイスで PowerShell スクリプトを[使用するWindows 10を参照してください](/mem/intune/apps/intune-management-extension)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-238">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="16fd3-239">地域</span><span class="sxs-lookup"><span data-stu-id="16fd3-239">Region</span></span>

<span data-ttu-id="16fd3-240">地域は、地域でサポートされているMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="16fd3-240">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="16fd3-241">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-241">**Not ready**</span></span>

<span data-ttu-id="16fd3-242">Azure AD組織の地域は、現在、ユーザーがサポートMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="16fd3-242">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="16fd3-243">詳細については、「サポートされている[地域Microsoft マネージド デスクトップ言語」を参照してください](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="16fd3-244">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-244">**Advisory**</span></span>

<span data-ttu-id="16fd3-245">Azure 組織が所属する 1 つ以上のADは、ユーザーがサポートMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="16fd3-245">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="16fd3-246">詳細については、「サポートされている[地域Microsoft マネージド デスクトップ言語」を参照してください](../service-description/regions-languages.md)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-246">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="16fd3-247">セキュリティベースライン</span><span class="sxs-lookup"><span data-stu-id="16fd3-247">Security baselines</span></span>

<span data-ttu-id="16fd3-248">セキュリティ ベースライン ポリシーは、すべてのデバイスを対象Microsoft マネージド デスクトップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-248">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="16fd3-249">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-249">**Not ready**</span></span>

<span data-ttu-id="16fd3-250">すべてのユーザー、すべてのデバイス、または両方を対象とするセキュリティ 基準プロファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-250">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="16fd3-251">ポリシーを変更して、特定の Azure ADデバイスを含Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-251">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-252">手順については[、「Use security baselines to configure Windows 10 Intune」を参照してください](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="16fd3-253">登録中に、すべてのデバイスに新しいセキュリティ 基準をMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-253">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-254">登録後、セキュリティ ベースライン ポリシー Microsoft マネージド デスクトップ構成ポリシー領域で確認Microsoft エンドポイント マネージャー。 </span><span class="sxs-lookup"><span data-stu-id="16fd3-254">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="16fd3-255">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-255">**Advisory**</span></span>

<span data-ttu-id="16fd3-256">デバイスから除外するセキュリティ 基準ポリシー Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-256">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-257">手順については[、「Use security baselines to configure Windows 10 Intune」を参照してください](/mem/intune/protect/security-baselines)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-257">For steps, see [Use security baselines to configure Windows 10 devices in Intune](/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="16fd3-258">登録中に、すべてのデバイスに新しいセキュリティ 基準をMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-258">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-259">モダン **ワークプレース デバイス -All** Azure AD グループは、Microsoft マネージド デスクトップ に登録するときに作成する動的グループなので、登録後にこのグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-259">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 


### <a name="windows-apps"></a><span data-ttu-id="16fd3-260">Windowsアプリ</span><span class="sxs-lookup"><span data-stu-id="16fd3-260">Windows apps</span></span>

<span data-ttu-id="16fd3-261">ユーザーに提供するアプリMicrosoft マネージド デスクトップ確認します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-261">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="16fd3-262">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-262">**Advisory**</span></span>

<span data-ttu-id="16fd3-263">ユーザーに提供するアプリのインベントリをMicrosoft マネージド デスクトップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-263">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="16fd3-264">これらのアプリは Intune によって展開する必要があるから、既存の Intune アプリの再利用を評価します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-264">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="16fd3-265">ユーザーにアプリポータル サイトする場合は、「[](../get-started/company-portal.md)デバイスIntune ポータル サイトをインストールする」と「登録状態ページ (ESP)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-265">Consider using Company Portal (see [Install Intune Company Portal on devices](../get-started/company-portal.md) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="16fd3-266">詳細については、「自動パイロット[でのアプリのMicrosoft マネージド デスクトップ](apps.md)実行エクスペリエンス」および「登録状態ページ」[を参照してください](../get-started/esp-first-run.md)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-266">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="16fd3-267">Intune に移行する準備ができているアプリや調整が必要なアプリMicrosoft Endpoint Configuration Manager Microsoft アカウント担当者に問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-267">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="16fd3-268">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="16fd3-268">Windows Hello for Business</span></span>

<span data-ttu-id="16fd3-269">Microsoft マネージド デスクトップビジネスWindows Hello有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-269">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="16fd3-270">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-270">**Not ready**</span></span>

<span data-ttu-id="16fd3-271">Windows Helloは無効です。</span><span class="sxs-lookup"><span data-stu-id="16fd3-271">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="16fd3-272">ビジネス 向けビジネス ポリシーの作成の手順[に従ってWindows Helloを有効にする](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="16fd3-272">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="16fd3-273">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-273">**Advisory**</span></span>

<span data-ttu-id="16fd3-274">Windows Hello for Business は設定されていない。</span><span class="sxs-lookup"><span data-stu-id="16fd3-274">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="16fd3-275">[ビジネス向けビジネス ポリシーの作成] の手順[に従ってWindows Helloを有効にしてください](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-275">Enable it by following the steps in [Create a Windows Hello for Business policy](/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="16fd3-276">Windows 10リング</span><span class="sxs-lookup"><span data-stu-id="16fd3-276">Windows 10 update rings</span></span>

<span data-ttu-id="16fd3-277">Intune の "Windows 10リング" ポリシーは、すべてのデバイスを対象Microsoft マネージド デスクトップできません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-277">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="16fd3-278">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-278">**Not ready**</span></span>

<span data-ttu-id="16fd3-279">すべてのデバイス、すべてのユーザー、または両方を対象とする "更新リング" ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-279">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="16fd3-280">ポリシーを変更して、特定の Azure ADデバイスを含Microsoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-280">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="16fd3-281">手順については[、「Intune でソフトウェアWindows 10更新プログラムを管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-281">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="16fd3-282">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-282">**Advisory**</span></span>

<span data-ttu-id="16fd3-283">最新の Workplace Devices **-All Azure** ADグループを除外している更新リング ポリシーをADしてください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-283">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="16fd3-284">これらのポリシーに Azure AD ユーザー グループを割り当てた場合は、Microsoft マネージド デスクトップ ユーザーを追加するモダン **Workplace -All** Azure AD グループ (または同等のグループ) も除外している更新リング ポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-284">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="16fd3-285">手順については[、「Intune でソフトウェアWindows 10更新プログラムを管理する」を参照してください](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-285">For steps, see [Manage Windows 10 software updates in Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="16fd3-286">モダン ワークプレース デバイス **-All** および **Modern Workplace -All** Azure AD グループは、Microsoft マネージド デスクトップ に登録するときに作成するグループなので、登録後にこのグループを除外するために戻ってくる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-286">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="16fd3-287">Azure Active Directory設定</span><span class="sxs-lookup"><span data-stu-id="16fd3-287">Azure Active Directory settings</span></span>

<span data-ttu-id="16fd3-288">Azure portal でAzure Active Directory設定に[アクセスできます](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-288">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="16fd3-289">Intune の登録</span><span class="sxs-lookup"><span data-stu-id="16fd3-289">Intune enrollment</span></span>

<span data-ttu-id="16fd3-290">Windows 10組織の Azure ADデバイスは、Intune に自動的に登録できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-290">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="16fd3-291">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-291">**Advisory**</span></span>

<span data-ttu-id="16fd3-292">MDM User スコープ **が [一部] または** [すべて] **に設定されているの** に **、None** は設定 **されていないか確認します**。</span><span class="sxs-lookup"><span data-stu-id="16fd3-292">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="16fd3-293">[一部] を **選択** した場合は、登録後に戻り、すべてのユーザーを対象とするグループまたは同等のグループに対してモダン Workplace **-All** Azure AD グループをMicrosoft マネージド デスクトップします。</span><span class="sxs-lookup"><span data-stu-id="16fd3-293">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="16fd3-294">「[デバイスを使用してデバイスの登録Windows設定する」を参照](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="16fd3-294">See [Set up enrollment for Windows devices by using Microsoft Intune](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="16fd3-295">アドホック サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="16fd3-295">Ad hoc subscriptions</span></span>

<span data-ttu-id="16fd3-296">("false" に設定されている場合) 状態ローミングが正しく動作Enterprise設定を確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-296">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="16fd3-297">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-297">**Advisory**</span></span>

<span data-ttu-id="16fd3-298">**AllowAdHocSubscriptions が True** に設定されている必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="16fd3-298">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="16fd3-299">それ以外の場合Enterprise状態ローミングが機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-299">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="16fd3-300">詳細については [、「Set-MsolCompanySettings」を参照してください](/powershell/module/msonline/set-msolcompanysettings)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-300">For more information, see [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="16fd3-301">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="16fd3-301">Enterprise State Roaming</span></span>

<span data-ttu-id="16fd3-302">Enterprise状態ローミングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-302">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="16fd3-303">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-303">**Advisory**</span></span>

<span data-ttu-id="16fd3-304">[すべて] または [選択Enterprise] の **状態ローミングが** 有効 **になっているか確認** します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-304">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="16fd3-305">詳細については、「Enable Enterprise ステート ローミング」[を参照Azure Active Directory。](/azure/active-directory/devices/enterprise-state-roaming-enable)</span><span class="sxs-lookup"><span data-stu-id="16fd3-305">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="16fd3-306">ライセンス</span><span class="sxs-lookup"><span data-stu-id="16fd3-306">Licenses</span></span>

<span data-ttu-id="16fd3-307">ライセンスを使用するには、多数のライセンスMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="16fd3-307">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="16fd3-308">**準備ができていない**</span><span class="sxs-lookup"><span data-stu-id="16fd3-308">**Not Ready**</span></span>

<span data-ttu-id="16fd3-309">ユーザーが使用する必要があるすべてのライセンスを持っているMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="16fd3-309">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="16fd3-310">詳細については[、「Microsoft マネージド デスクトップ」](../intro/technologies.md)および「[ライセンスの詳細」を参照してください](prerequisites.md#more-about-licenses)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-310">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="microsoft-managed-desktop-service-accounts"></a><span data-ttu-id="16fd3-311">Microsoft マネージド デスクトップ サービス アカウント</span><span class="sxs-lookup"><span data-stu-id="16fd3-311">Microsoft Managed Desktop service accounts</span></span>

<span data-ttu-id="16fd3-312">一部のアカウント名は、サービスを管理するためにMicrosoft マネージド デスクトップアカウント名とMicrosoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-312">Certain account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.</span></span>

<span data-ttu-id="16fd3-313">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-313">**Not ready**</span></span>

<span data-ttu-id="16fd3-314">ユーザーが作成したアカウント名と競合するアカウント名が少なくとも 1 つMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="16fd3-314">You have at least one account name that will conflict with account names created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="16fd3-315">これらのアカウント名を除外するには、Microsoft アカウント担当者と一緒に作業します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-315">Work with your Microsoft account representative to exclude these account names.</span></span> <span data-ttu-id="16fd3-316">セキュリティ リスクを最小限に抑えるために、アカウント名を一般に一覧表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-316">We don't list the account names publicly to minimize security risk.</span></span> 


### <a name="security-administrator-roles"></a><span data-ttu-id="16fd3-317">セキュリティ管理者の役割</span><span class="sxs-lookup"><span data-stu-id="16fd3-317">Security administrator roles</span></span>

<span data-ttu-id="16fd3-318">特定のセキュリティ ロールを持つユーザーには、それらの役割が Microsoft Defender for Endpoint に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-318">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="16fd3-319">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-319">**Advisory**</span></span>

<span data-ttu-id="16fd3-320">Azure AD組織でこれらの役割に割り当てられているユーザーがある場合は、それらの役割も Microsoft Defender for Endpoint に割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-320">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="16fd3-321">それ以外の場合、これらの役割を持つ管理者は管理ポータルにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-321">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="16fd3-322">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="16fd3-322">Security Operator</span></span>
- <span data-ttu-id="16fd3-323">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="16fd3-323">Global Reader</span></span>

<span data-ttu-id="16fd3-324">詳細については、「役割ベースの [アクセス制御の役割を作成および管理する」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/user-roles)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-324">For more information, see [Create and manage roles for role-based access control](/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="16fd3-325">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="16fd3-325">Security default</span></span>

<span data-ttu-id="16fd3-326">セキュリティの既定値はAzure Active DirectoryデバイスMicrosoft マネージド デスクトップ管理できません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-326">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="16fd3-327">**使用不可能**</span><span class="sxs-lookup"><span data-stu-id="16fd3-327">**Not ready**</span></span>

<span data-ttu-id="16fd3-328">セキュリティの既定値を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="16fd3-328">You have Security defaults turned on.</span></span> <span data-ttu-id="16fd3-329">セキュリティの既定値をオフにし、条件付きアクセス ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-329">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="16fd3-330">詳細については、「一般的な条件付 [きアクセス ポリシー」を参照してください](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-330">For more information, see [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="16fd3-331">セルフサービス のパスワードのリセット</span><span class="sxs-lookup"><span data-stu-id="16fd3-331">Self-service Password Reset</span></span>

<span data-ttu-id="16fd3-332">セルフサービス パスワード リセット (SSPR) は、サービス アカウントを除くすべてのユーザー Microsoft マネージド デスクトップ有効Microsoft マネージド デスクトップできます。</span><span class="sxs-lookup"><span data-stu-id="16fd3-332">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="16fd3-333">詳細については、「チュートリアル: ユーザーが自分のアカウントのロックを解除したり、セルフサービス パスワードのリセットを使用してパスワードAzure Active Directory[を有効にする」を参照してください](/azure/active-directory/authentication/tutorial-enable-sspr)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-333">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="16fd3-334">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-334">**Advisory**</span></span>

<span data-ttu-id="16fd3-335">SSPR **Selected 設定** にユーザーが含Microsoft マネージド デスクトップサービス アカウントMicrosoft マネージド デスクトップしてください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-335">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="16fd3-336">Microsoft マネージド デスクトップ SSPR が有効な場合、サービス アカウントは期待通り動作しません。</span><span class="sxs-lookup"><span data-stu-id="16fd3-336">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="16fd3-337">標準ユーザー ロール</span><span class="sxs-lookup"><span data-stu-id="16fd3-337">Standard user role</span></span>

<span data-ttu-id="16fd3-338">グローバル管理者とデバイス管理者の Azure ADロールが割り当てられているユーザー以外に、Microsoft マネージド デスクトップユーザーはローカル管理者特権のない標準ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="16fd3-338">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="16fd3-339">他のすべてのユーザーには、デバイスを起動するときに標準のユーザー ロールMicrosoft マネージド デスクトップされます。</span><span class="sxs-lookup"><span data-stu-id="16fd3-339">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="16fd3-340">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-340">**Advisory**</span></span>

<span data-ttu-id="16fd3-341">Microsoft マネージド デスクトップユーザーは、登録後に自分のデバイスに対してローカルMicrosoft マネージド デスクトップ特権を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="16fd3-341">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="16fd3-342">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="16fd3-342">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="16fd3-343">OneDrive</span><span class="sxs-lookup"><span data-stu-id="16fd3-343">OneDrive</span></span>

<span data-ttu-id="16fd3-344">[**特定のドメインに参加** している PC でのみ同期を許可する] の設定は、特定のドメインと競合Microsoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="16fd3-344">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="16fd3-345">管理センターでOneDrive設定OneDrive[アクセスできます](https://admin.onedrive.com)。</span><span class="sxs-lookup"><span data-stu-id="16fd3-345">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="16fd3-346">**アドバイザリ**</span><span class="sxs-lookup"><span data-stu-id="16fd3-346">**Advisory**</span></span>

<span data-ttu-id="16fd3-347">[特定のドメインに参加している PC でのみ同期を許可 **する] 設定を使用** しています。</span><span class="sxs-lookup"><span data-stu-id="16fd3-347">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="16fd3-348">この設定は、この設定ではMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="16fd3-348">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="16fd3-349">この設定を無効にし、代わりに条件付OneDriveポリシーを使用する方法を設定します。</span><span class="sxs-lookup"><span data-stu-id="16fd3-349">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="16fd3-350">ヘルプについては [、「条件付きアクセスの展開を計画する](/azure/active-directory/conditional-access/plan-conditional-access) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16fd3-350">See [Plan a Conditional Access deployment](/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>
