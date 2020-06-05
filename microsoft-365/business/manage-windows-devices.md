---
title: Microsoft 365 for business で管理されるドメインに参加している Windows 10 デバイスを有効にする
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: いくつかの手順で、Microsoft 365 を有効にして、ローカルの Active Directory に参加している Windows 10 デバイスを保護する方法について説明します。
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564950"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="9fbc5-103">Microsoft 365 Business Premium によって管理されるドメインに参加している Windows 10 デバイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="9fbc5-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="9fbc5-104">組織でオンプレミスの Windows Server Active Directory を使用している場合は、Microsoft 365 Business Premium をセットアップして Windows 10 デバイスを保護することができます。ただし、ローカル認証を必要とするオンプレミスのリソースへのアクセスは維持されます。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="9fbc5-105">この保護をセットアップするには、**ハイブリッド AZURE AD に参加**しているデバイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="9fbc5-106">これらのデバイスは、オンプレミスの Active Directory と Azure Active Directory の両方に参加します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="9fbc5-107">このビデオでは、最も一般的なシナリオに対してこれを設定する手順について説明します。これについては、以下の手順でも詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="9fbc5-108">作業を開始する前に、以下の手順を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="9fbc5-109">Azure AD Connect を使用してユーザーを Azure AD に同期します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="9fbc5-110">完全な Azure AD Connect 組織単位 (OU) 同期。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="9fbc5-111">同期するすべてのドメインユーザーが Microsoft 365 Business Premium のライセンスを持っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="9fbc5-112">手順については、「[ドメインユーザーを Microsoft に同期させる](manage-domain-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="9fbc5-113">1. Intune で MDM 機関を確認する</span><span class="sxs-lookup"><span data-stu-id="9fbc5-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="9fbc5-114">Portal.azure.com に移動し、Intune のページ検索の上部に移動します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="9fbc5-115">[Microsoft Intune] ページで、[**デバイスの登録**] を選択し、[**概要**] ページで**MDM authority**が**Intune**であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="9fbc5-116">**Mdm 機関**が**なし**の場合は、 **mdm 機関**をクリックして**Intune**に設定します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="9fbc5-117">**MDM 機関**が**Microsoft office 365**の場合は、[**デバイス**を  >  **登録**する] を選択し、 **Intune mdm**機関を追加する権限の [ **mdm 機関の追加**] ダイアログを使用します (mdm 機関を追加するに**は、mdm**機関が microsoft Office 365 に設定**され**ている場合にのみ使用できます)。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="9fbc5-118">2. Azure AD が参加しているコンピューターに対して有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9fbc5-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="9fbc5-119">管理センターに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> して、[**管理**センター] の一覧にある [azure **active** directory が表示されていない場合はすべて表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="9fbc5-120">**Azure Active directory 管理センター**で、[ **azure active directory** ] に移動し、[**デバイス**]、[**デバイスの設定**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="9fbc5-121">**ユーザーがデバイスを AZURE AD に参加させる**ことが可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="9fbc5-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="9fbc5-122">すべてのユーザーを有効にするには、 **all**に設定します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="9fbc5-123">特定のユーザーを有効にするには、[**オン**] に設定して特定のユーザーグループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="9fbc5-124">Azure AD で同期されている目的のドメインユーザーを[セキュリティグループ](../admin/create-groups/create-groups.md)に追加します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="9fbc5-125">**[グループの選択**] を選択して、そのセキュリティグループの MDM ユーザースコープを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="9fbc5-126">3. MDM に対して Azure AD が有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9fbc5-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="9fbc5-127">管理センターに移動し、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **エンドポイント Managemen**の選択] を選択します (**エンドポイントマネージャー**が表示されない場合は [**すべて表示**] を選択します)</span><span class="sxs-lookup"><span data-stu-id="9fbc5-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="9fbc5-128">**Microsoft エンドポイントマネージャー管理センター**で、[**デバイス**  >  **windows**  >  **windows 登録**の  >  **自動登録**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="9fbc5-129">MDM ユーザースコープが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="9fbc5-130">すべてのコンピューターを登録するには、[**すべて**] に設定して、ユーザーが Windows に作業アカウントを追加するときに、Azure AD と新しいコンピューターに参加するすべてのユーザーコンピューターを自動的に登録します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="9fbc5-131">特定のユーザーグループのコンピューターを登録するには、[**一部**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="9fbc5-132">Azure AD で同期されている目的のドメインユーザーを[セキュリティグループ](../admin/create-groups/create-groups.md)に追加します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="9fbc5-133">**[グループの選択**] を選択して、そのセキュリティグループの MDM ユーザースコープを有効にします。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="9fbc5-134">4. サービス接続ポイント (SCP) を設定する</span><span class="sxs-lookup"><span data-stu-id="9fbc5-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="9fbc5-135">これらの手順は、[ハイブリッド AZURE AD join の構成](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)によって簡略化されています。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="9fbc5-136">Azure AD Connect と Microsoft 365 Business Premium のグローバル管理者および Active Directory 管理者パスワードを使用するために必要な手順を完了するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="9fbc5-137">Azure AD Connect を起動し、[**構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="9fbc5-138">[**追加のタスク**] ページで、[**デバイスオプションの構成**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="9fbc5-139">[**概要**] ページで、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="9fbc5-140">[ **AZURE AD に接続**] ページで、Microsoft 365 Business Premium のグローバル管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="9fbc5-141">[**デバイスオプション**] ページで、[**ハイブリッド Azure AD join の構成**] を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="9fbc5-142">**Scp**ページで、Azure AD CONNECT が scp を構成する各フォレストに対して、以下の手順を完了し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="9fbc5-143">フォレスト名の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-143">Check the box beside the forest name.</span></span> <span data-ttu-id="9fbc5-144">フォレストは、AD ドメイン名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="9fbc5-145">[**認証サービス**] 列で、ドロップダウンを開き、[一致するドメイン名] を選択します (1 つのみを指定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="9fbc5-146">[**追加**] を選択して、ドメイン管理者の資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="9fbc5-147">[**デバイスオペレーティングシステム**] ページで、[Windows 10 以降のドメイン参加デバイスのみ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="9fbc5-148">[**構成の準備完了**] ページで、[**構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="9fbc5-149">[**構成の完了**] ページで、[**終了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="9fbc5-150">5. Intune 登録の GPO を作成する-ADMX メソッド</span><span class="sxs-lookup"><span data-stu-id="9fbc5-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="9fbc5-151">使え.ADMX テンプレートファイル。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="9fbc5-152">AD サーバーにログオンし、[**サーバーマネージャー**ツールを検索して開く  >  **Tools**  >  **] グループポリシーの管理**を開きます。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="9fbc5-153">[ **Domains** ] の下にあるドメイン名を選択し、[**グループポリシーオブジェクト**] を右クリックして [**新規**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="9fbc5-154">新しい GPO に名前 ("*Cloud_Enrollment*" など) を指定し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="9fbc5-155">[**グループポリシーオブジェクト**] の下で新しい GPO を右クリックし、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="9fbc5-156">**グループポリシー管理エディター**で、[**コンピューター構成**ポリシー] の [  >  **Policies**  >  **管理用テンプレート**  >  **Windows コンポーネント**  >  **MDM**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="9fbc5-157">[既定の**Azure AD 資格情報を使用して MDM の自動登録を有効にする**] を右クリックし、[**有効に**する] を選択し  >  **OK**ます。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="9fbc5-158">エディターウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fbc5-159">**既定の AZURE AD 資格情報を使用した自動 MDM 登録を有効に**するポリシーが表示されない場合は、「[最新の管理用テンプレートを取得](#get-the-latest-administrative-templates)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="9fbc5-160">6. グループポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="9fbc5-161">サーバーマネージャーの [**ドメイン**> グループポリシーオブジェクト] で、上記の手順3の GPO (例: "Cloud_Enrollment") を選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="9fbc5-162">GPO の [**スコープ**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="9fbc5-163">GPO の [スコープ] タブで、[ **Links**] の下にあるドメインへのリンクを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="9fbc5-164">[**強制**] を選択して GPO を展開し、確認画面で [ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="9fbc5-165">最新の管理用テンプレートを取得する</span><span class="sxs-lookup"><span data-stu-id="9fbc5-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="9fbc5-166">**既定の AZURE AD 資格情報を使用した自動 MDM 登録を有効に**するポリシーが表示されない場合は、Windows 10、バージョン1803、バージョン1809、またはバージョン1903用の ADMX がインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="9fbc5-167">この問題を解決するには、次の手順を実行します (注: 最新の MDM は下位互換性があります)。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="9fbc5-168">ダウンロード: [Windows 10 の管理用テンプレート (admx) は2019更新プログラム (1903) の場合があり](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)ます。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="9fbc5-169">プライマリドメインコントローラー (PDC) にパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="9fbc5-170">フォルダーのバージョンに応じて、次の操作を行います。 **C:\Program files (x86) \Microsoft Group Policy\Windows 10 5 月 2019 Update (1903) v3**。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="9fbc5-171">上記のパスの**ポリシー定義**フォルダーの名前を**policydefinitions**に変更します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="9fbc5-172">**Policydefinitions**フォルダーを**C:\Windows\SYSVOL\domain\Policies**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="9fbc5-173">ドメイン全体に対して中央ポリシーストアを使用することを計画している場合は、そこに PolicyDefinitions の内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="9fbc5-174">ポリシーを使用可能にするには、プライマリドメインコントローラーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="9fbc5-175">この手順は、将来のバージョンでも同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="9fbc5-176">この時点で、[**既定の AZURE AD 資格情報を使用して MDM の自動登録を有効に**する] ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9fbc5-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

