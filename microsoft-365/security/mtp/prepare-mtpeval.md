---
title: Microsoft の脅威保護のテスト環境を準備する
description: Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップするときに、ステークホルダーのサインアップ、タイムライン、環境に関する考慮事項、導入の順序を準備する
keywords: Mtp 試用準備、MTP パイロット準備、mtp パイロットプロジェクトを実行するための準備、パイロット MTP プロジェクトの実行、展開、準備、ステークホルダー、タイムライン、環境、エンドポイント、サーバー、管理、導入
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a684f49ab8c70a19a17ff43195197677bccbf95b
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816771"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="b825a-104">Microsoft の脅威保護の試用ラボまたはパイロット環境の準備</span><span class="sxs-lookup"><span data-stu-id="b825a-104">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>

<span data-ttu-id="b825a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b825a-105">**Applies to:**</span></span>
- <span data-ttu-id="b825a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b825a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b825a-107">Microsoft の脅威保護の試用ラボまたはパイロット環境を作成して展開するには、3つのフェーズがあります。</span><span class="sxs-lookup"><span data-stu-id="b825a-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境の準備" />
      <br/><span data-ttu-id="b825a-109">フェーズ 1: 準備 </a></span><span class="sxs-lookup"><span data-stu-id="b825a-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップする" />
      <br/><span data-ttu-id="b825a-111">フェーズ 2: セットアップ </a></span><span class="sxs-lookup"><span data-stu-id="b825a-111">Phase 2: Setup </a></span></span><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="各 Microsoft 脅威保護の柱とエンドポイントの構成" />
      <br/><span data-ttu-id="b825a-113">フェーズ 3: 構成 & オンボード</a></span><span class="sxs-lookup"><span data-stu-id="b825a-113">Phase 3: Configure & Onboard</a></span></span><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

<span data-ttu-id="b825a-114">現在、準備段階になっています。</span><span class="sxs-lookup"><span data-stu-id="b825a-114">You're currently in the preparation phase.</span></span>


<span data-ttu-id="b825a-115">正常な展開には、準備が重要です。</span><span class="sxs-lookup"><span data-stu-id="b825a-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="b825a-116">このセクションでは、Microsoft の脅威保護の展開のための試用ラボまたはパイロット環境を作成するための準備として考慮する必要のある内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="b825a-116">This section will guide you through what you need to consider as you prepare to create a trial lab or pilot environment for your Microsoft Threat Protection deployment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b825a-117">前提条件</span><span class="sxs-lookup"><span data-stu-id="b825a-117">Prerequisites</span></span>
<span data-ttu-id="b825a-118">Microsoft の脅威保護をプロビジョニングおよび使用するためのライセンス、ハードウェア要件、ソフトウェア要件、およびその他の構成設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="b825a-118">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span> <span data-ttu-id="b825a-119">[Microsoft の脅威保護](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide)、 [microsoft Defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)、 [OFFICE 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)、 [Azure atp](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)、 [microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)の最小要件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b825a-119">See the minimum requirements for [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide), [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).</span></span>

## <a name="stakeholders-and-sign-off"></a><span data-ttu-id="b825a-120">関係者と承認</span><span class="sxs-lookup"><span data-stu-id="b825a-120">Stakeholders and sign-off</span></span>
<span data-ttu-id="b825a-121">次のセクションでは、プロジェクトに関係するすべての関係者を特定し、評価のために、またはパイロットを実行しているかどうかにかかわらず、サインオフ、レビュー、または通知を受ける必要がある可能性があるすべての関係者を識別します。</span><span class="sxs-lookup"><span data-stu-id="b825a-121">The following section serves to identify all the stakeholders that are involved in the project and who may need to sign-off, review, or stay informed, whether for evaluation or running a pilot.</span></span>

>[!NOTE]
><span data-ttu-id="b825a-122">組織によっては、このような役割を持つセキュリティ組織の成熟度を持たない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b825a-122">Not all organizations might have the security organization maturity to have such roles.</span></span> <span data-ttu-id="b825a-123">このような場合は、レビューと承認の責任について指導者チームと相談してください。</span><span class="sxs-lookup"><span data-stu-id="b825a-123">In such case, consult with your leadership team on review and approval accountabilities.</span></span>

<span data-ttu-id="b825a-124">組織に応じて、次の表にステークホルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b825a-124">Add stakeholders to the table below as appropriate for your organization.</span></span>

-   <span data-ttu-id="b825a-125">そのため、このプロジェクトのサインオフ</span><span class="sxs-lookup"><span data-stu-id="b825a-125">SO = Sign-off on this project</span></span>

-   <span data-ttu-id="b825a-126">R = このプロジェクトをレビューし、入力を提供します。</span><span class="sxs-lookup"><span data-stu-id="b825a-126">R = Review this project and provide input</span></span>

-   <span data-ttu-id="b825a-127">I = このプロジェクトの通知を受けた</span><span class="sxs-lookup"><span data-stu-id="b825a-127">I = Informed of this project</span></span>

| <span data-ttu-id="b825a-128">Name</span><span class="sxs-lookup"><span data-stu-id="b825a-128">Name</span></span>                 | <span data-ttu-id="b825a-129">Role</span><span class="sxs-lookup"><span data-stu-id="b825a-129">Role</span></span>                                                                                                                                                                                                          | <span data-ttu-id="b825a-130">Action</span><span class="sxs-lookup"><span data-stu-id="b825a-130">Action</span></span> |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| <span data-ttu-id="b825a-131">名前と電子メールを入力する</span><span class="sxs-lookup"><span data-stu-id="b825a-131">Enter name and email</span></span> | <span data-ttu-id="b825a-132">**最高情報セキュリティ責任者 (CISO)** *新しいテクノロジの展開について組織の内部スポンサーとしての役割を果たすエグゼクティブの代表者。*</span><span class="sxs-lookup"><span data-stu-id="b825a-132">**Chief Information Security Officer (CISO)** *An executive representative who serves as sponsor inside the organization for the new technology deployment.*</span></span>                                                  | <span data-ttu-id="b825a-133">だから</span><span class="sxs-lookup"><span data-stu-id="b825a-133">SO</span></span>     |
| <span data-ttu-id="b825a-134">名前と電子メールを入力する</span><span class="sxs-lookup"><span data-stu-id="b825a-134">Enter name and email</span></span> | <span data-ttu-id="b825a-135">**サイバー防衛運用センター (cdoc) の本社**は、 *この変更がお客様のセキュリティ運用チームのプロセスとどのように連携するかを定義することを担当しています。*</span><span class="sxs-lookup"><span data-stu-id="b825a-135">**Head of Cyber Defense Operations Center (CDOC)** *A representative from the CDOC team in charge of defining how this change is aligned with the processes in the customers security operations team.*</span></span>       | <span data-ttu-id="b825a-136">だから</span><span class="sxs-lookup"><span data-stu-id="b825a-136">SO</span></span>     |
| <span data-ttu-id="b825a-137">名前と電子メールを入力する</span><span class="sxs-lookup"><span data-stu-id="b825a-137">Enter name and email</span></span> | <span data-ttu-id="b825a-138">**セキュリティアーキテクト**セキュリティ *チームは、この変更が組織内のコアセキュリティアーキテクチャとどのように連携するかを定義することを担当しています。*</span><span class="sxs-lookup"><span data-stu-id="b825a-138">**Security Architect** *A representative from the Security team in charge of defining how this change is aligned with the core Security architecture in the organization.*</span></span>                         | <span data-ttu-id="b825a-139">R</span><span class="sxs-lookup"><span data-stu-id="b825a-139">R</span></span>      |
| <span data-ttu-id="b825a-140">名前と電子メールを入力する</span><span class="sxs-lookup"><span data-stu-id="b825a-140">Enter name and email</span></span> | <span data-ttu-id="b825a-141">**Workplace アーキテクト** *IT チームの代表者は、この変更が組織内のコアワークプレースアーキテクチャとどのように連携するかを定義すること*を担当します。</span><span class="sxs-lookup"><span data-stu-id="b825a-141">**Workplace Architect** *A representative from the IT team in charge of defining how this change is aligned with the core workplace architecture in the organization.*</span></span>                             | <span data-ttu-id="b825a-142">R</span><span class="sxs-lookup"><span data-stu-id="b825a-142">R</span></span>      |
| <span data-ttu-id="b825a-143">名前と電子メールを入力する</span><span class="sxs-lookup"><span data-stu-id="b825a-143">Enter name and email</span></span> | <span data-ttu-id="b825a-144">\**セキュリティアナリスト\*\*\*この変更によって、検出機能、ユーザーの操作、およびこの変更の全体的な有用性に関する情報を提供できる、cdoc チームからの担当者は、セキュリティ運用の観点から、この変更に関する情報を提供できます。*</span><span class="sxs-lookup"><span data-stu-id="b825a-144">**Security Analyst** *A representative from the CDOC team who can provide input on the detection capabilities, user experience, and overall usefulness of this change from a security operations perspective.*</span></span> | <span data-ttu-id="b825a-145">I</span><span class="sxs-lookup"><span data-stu-id="b825a-145">I</span></span>      |

## <a name="prepare-your-azure-active-directory"></a><span data-ttu-id="b825a-146">Azure Active Directory の準備</span><span class="sxs-lookup"><span data-stu-id="b825a-146">Prepare your Azure Active Directory</span></span>
<span data-ttu-id="b825a-147">オンプレミスの Active Directory と Azure Active Directory との間の同期を既に有効にしている場合は、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="b825a-147">Skip this step if you have already enabled synchronization between Active Directory and Azure Active Directory on premises.</span></span> <span data-ttu-id="b825a-148">Azure Active Directory からの既存のベストプラクティスドキュメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="b825a-148">Review existing best practices documentation from Azure Active Directory.</span></span> <span data-ttu-id="b825a-149">次の手順は、パイロット Microsoft の脅威保護プロジェクトを評価または実行するために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="b825a-149">The following steps are optimized to evaluate or run a pilot Microsoft Threat Protection project.</span></span>

1. <span data-ttu-id="b825a-150">Azure **AD Connect**> [azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade)ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="b825a-150">Go to the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) portal > **Azure AD Connect**.</span></span> 
<span data-ttu-id="b825a-151">![Azure Active Directory ポータルページのイメージ](../../media/mtp-eval-1.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-151">![Image of Azure Active Directory portal page](../../media/mtp-eval-1.png)</span></span> <br> 

2. <span data-ttu-id="b825a-152">[ **Microsoft Azure Active Directory Connect**から**ダウンロード**] をクリックして、ドメインコントローラーに転送します。</span><span class="sxs-lookup"><span data-stu-id="b825a-152">Click **Download** from **Microsoft Azure Active Directory Connect** and transfer it to your Domain Controller.</span></span>
<span data-ttu-id="b825a-153">![Azure Active Directoru Connect ダウンロードページのイメージ](../../media/mtp-eval-2.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-153">![Image of Azure Active Directoru Connect download page](../../media/mtp-eval-2.png)</span></span> <br>

3. <span data-ttu-id="b825a-154">ドメインコントローラーで、Azure Active Directory Connect ウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="b825a-154">On the domain controller, follow the Azure Active Directory Connect wizard.</span></span> <span data-ttu-id="b825a-155">ライセンス条項とプライバシーに関する通知を読んで、同意する場合はチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b825a-155">Read the license terms and privacy notice and select the checkbox if you agree.</span></span> <span data-ttu-id="b825a-156">[**続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b825a-156">Click **Continue**.</span></span>
<span data-ttu-id="b825a-157">![Azure AD Connect ウェルカムページの画像](../../media/mtp-eval-3.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-157">![Image of Azure AD Connect welcome page](../../media/mtp-eval-3.png)</span></span> <br>

4. <span data-ttu-id="b825a-158">[ **エクスプレス設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b825a-158">Navigate to **Express Settings**.</span></span>
<span data-ttu-id="b825a-159">![Express 設定ページのイメージ](../../media/mtp-eval-4.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-159">![Image of Express Settings page](../../media/mtp-eval-4.png)</span></span> <br>

5. <span data-ttu-id="b825a-160">グローバル管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b825a-160">Enter your global administrator credentials.</span></span> <span data-ttu-id="b825a-161">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b825a-161">Click **Next**.</span></span>
<span data-ttu-id="b825a-162">![グローバル管理者の資格情報を入力する必要がある Azure AD に接続するためのページの画像](../../media/mtp-eval-5.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-162">![Image of Connect to Azure AD page where you should enter your global administrator credentials](../../media/mtp-eval-5.png)</span></span> <br>

6. <span data-ttu-id="b825a-163">Active Directory ドメインサービスのエンタープライズ管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b825a-163">Enter your Active Directory Domain Services enterprise administrator credentials.</span></span> <span data-ttu-id="b825a-164">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b825a-164">Click **Next**.</span></span>
<span data-ttu-id="b825a-165">![資格情報を入力する必要がある、AD DS への接続ページの画像](../../media/mtp-eval-6.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-165">![Image of Connect to AD DS page where you should enter your credentials](../../media/mtp-eval-6.png)</span></span> <br>

7. <span data-ttu-id="b825a-166">[ **インストール** ] をクリックして構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="b825a-166">Click **Install** to confirm the configuration.</span></span>
<span data-ttu-id="b825a-167">![構成確認ページのイメージ](../../media/mtp-eval-7.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-167">![Image of configuration confirmation page](../../media/mtp-eval-7.png)</span></span> <br>

8. <span data-ttu-id="b825a-168">これで完了です。 Azure Active Directory Connect が正常に構成されました。</span><span class="sxs-lookup"><span data-stu-id="b825a-168">Congratulations, you have successfully configured Azure Active Directory Connect.</span></span>
<span data-ttu-id="b825a-169">![正常に構成された Azure Active Directory Connect ページのイメージ](../../media/mtp-eval-8.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-169">![Image of a successfully configured Azure Active Directory Connect page](../../media/mtp-eval-8.png)</span></span> <br>

<span data-ttu-id="b825a-170">これで、 [Active Directory にユーザーとグループを追加](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) し、 [SAM-R ポリシーを構成](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b825a-170">You can now [add users and groups to Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) and [configure a SAM-R policy](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).</span></span>  


## <a name="configuration-order"></a><span data-ttu-id="b825a-171">構成の順序</span><span class="sxs-lookup"><span data-stu-id="b825a-171">Configuration order</span></span>
<span data-ttu-id="b825a-172">次の表は、試用ラボまたはパイロット環境の展開に Microsoft の脅威保護コンポーネントを構成するために Microsoft が推奨する順序を示しています。</span><span class="sxs-lookup"><span data-stu-id="b825a-172">The table below indicates the order Microsoft recommends for configuring the Microsoft Threat Protection components for your trial lab or pilot environment deployment.</span></span>

| <span data-ttu-id="b825a-173">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b825a-173">Component</span></span>                               | <span data-ttu-id="b825a-174">説明</span><span class="sxs-lookup"><span data-stu-id="b825a-174">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="b825a-175">構成順序のランク</span><span class="sxs-lookup"><span data-stu-id="b825a-175">Configuration order rank</span></span> |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| <span data-ttu-id="b825a-176">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b825a-176">Office 365 Advanced Threat Protection</span></span>| <span data-ttu-id="b825a-177">Office 365 ATP は、電子メールメッセージ、リンク (Url)、およびコラボレーションツールがもたらす悪意のある脅威から組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="b825a-177">Office 365 ATP safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <br> [<span data-ttu-id="b825a-178">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b825a-178">Learn more.</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)                                                                                                                                                                                                                                             | <span data-ttu-id="b825a-179">1 </span><span class="sxs-lookup"><span data-stu-id="b825a-179">1</span></span>                   |
|<span data-ttu-id="b825a-180">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b825a-180">Azure Advanced Threat Protection</span></span>|<span data-ttu-id="b825a-181">Azure ATP では、Active Directory のシグナルを使用して、高度な脅威、侵害された id、および組織に向けた悪意のある insider 操作を識別、検出、調査します。</span><span class="sxs-lookup"><span data-stu-id="b825a-181">Azure ATP uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <br> <span data-ttu-id="b825a-182">[詳細情報](https://docs.microsoft.com/azure-advanced-threat-protection/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b825a-182">[Learn more](https://docs.microsoft.com/azure-advanced-threat-protection/).</span></span>| <span data-ttu-id="b825a-183">2 </span><span class="sxs-lookup"><span data-stu-id="b825a-183">2</span></span> |
|<span data-ttu-id="b825a-184">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b825a-184">Microsoft Cloud App Security</span></span>| <span data-ttu-id="b825a-185">Microsoft Cloud App Security は、複数のクラウドで稼働するクラウドアクセスセキュリティブローカー (CASB) です。</span><span class="sxs-lookup"><span data-stu-id="b825a-185">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB) that operates on multiple clouds.</span></span> <span data-ttu-id="b825a-186">これにより、豊富な可視性、データ移動の制御、および高度な分析が提供され、すべてのクラウドサービスにわたる脅威を特定し、戦闘することができます。</span><span class="sxs-lookup"><span data-stu-id="b825a-186">It provides rich visibility, control over data travel, and sophisticated analytics to identify and combat cyberthreats across all your cloud services.</span></span> <br> <span data-ttu-id="b825a-187">[詳細情報](https://docs.microsoft.com/cloud-app-security/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b825a-187">[Learn more](https://docs.microsoft.com/cloud-app-security/).</span></span>                                                                                                                                                                                                                                                                                                                                                                       |<span data-ttu-id="b825a-188">3 </span><span class="sxs-lookup"><span data-stu-id="b825a-188">3</span></span>                   |
|<span data-ttu-id="b825a-189">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b825a-189">Microsoft Defender Advanced Threat Protection</span></span> | <span data-ttu-id="b825a-190">Microsoft Defender ATP エンドポイント検出および対応機能により、高度な攻撃のほとんどリアルタイムで実用的な検出が実現されます。</span><span class="sxs-lookup"><span data-stu-id="b825a-190">Microsoft Defender ATP endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="b825a-191">セキュリティ アナリストは、効率的にアラートの優先順位を設定し、違反の全容を可視化して、脅威に対処する対応策を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="b825a-191">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span> <br> [<span data-ttu-id="b825a-192">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b825a-192">Learn more.</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |<span data-ttu-id="b825a-193">4 </span><span class="sxs-lookup"><span data-stu-id="b825a-193">4</span></span>                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a><span data-ttu-id="b825a-194">次の手順</span><span class="sxs-lookup"><span data-stu-id="b825a-194">Next step</span></span>
<span data-ttu-id="b825a-195">![フェーズ 2: セットアップ](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="b825a-195">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="b825a-196">フェーズ 2: セットアップ</span><span class="sxs-lookup"><span data-stu-id="b825a-196">Phase 2: Setup</span></span>](setup-mtpeval.md)<br> <span data-ttu-id="b825a-197">Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b825a-197">Set up your Microsoft Threat Protection trial lab or pilot environment</span></span>

