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
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560845"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="39c15-103">Microsoft 365 Business Premium によって管理されるドメインに参加している Windows 10 デバイスを有効にする</span><span class="sxs-lookup"><span data-stu-id="39c15-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="39c15-104">組織でオンプレミスの Windows Server Active Directory を使用している場合は、Microsoft 365 Business Premium をセットアップして Windows 10 デバイスを保護することができます。ただし、ローカル認証を必要とするオンプレミスのリソースへのアクセスは維持されます。</span><span class="sxs-lookup"><span data-stu-id="39c15-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="39c15-105">この保護をセットアップするには、**ハイブリッド AZURE AD に参加**しているデバイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="39c15-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="39c15-106">これらのデバイスは、オンプレミスの Active Directory と Azure Active Directory の両方に参加します。</span><span class="sxs-lookup"><span data-stu-id="39c15-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="39c15-107">このビデオでは、最も一般的なシナリオに対してこれを設定する手順について説明します。これについては、以下の手順でも詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="39c15-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="39c15-108">作業を開始する前に、以下の手順を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="39c15-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="39c15-109">Azure AD Connect を使用してユーザーを Azure AD に同期します。</span><span class="sxs-lookup"><span data-stu-id="39c15-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="39c15-110">完全な Azure AD Connect 組織単位 (OU) 同期。</span><span class="sxs-lookup"><span data-stu-id="39c15-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="39c15-111">同期するすべてのドメインユーザーが Microsoft 365 Business Premium のライセンスを持っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="39c15-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="39c15-112">手順については、「[ドメインユーザーを Microsoft に同期させる](manage-domain-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39c15-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="39c15-113">1. Intune で MDM 機関を確認する</span><span class="sxs-lookup"><span data-stu-id="39c15-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="39c15-114">[エンドポイントマネージャー](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)に移動し、[Microsoft Intune] ページで [ **Device enrollment**] を選択して、[**概要**] ページで**MDM authority**が**Intune**であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39c15-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="39c15-115">**Mdm 機関**が**なし**の場合は、 **mdm 機関**をクリックして**Intune**に設定します。</span><span class="sxs-lookup"><span data-stu-id="39c15-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="39c15-116">**MDM 機関**が**Microsoft office 365**の場合は、[**デバイス**を  >  **登録**する] を選択し、 **Intune mdm**機関を追加する権限の [ **mdm 機関の追加**] ダイアログを使用します (mdm 機関を追加するに**は、mdm**機関が microsoft Office 365 に設定**され**ている場合にのみ使用できます)。</span><span class="sxs-lookup"><span data-stu-id="39c15-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="39c15-117">2. Azure AD が参加しているコンピューターに対して有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="39c15-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="39c15-118">管理センターに移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> して、[**管理**センター] の一覧にある [azure **active** directory が表示されていない場合はすべて表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39c15-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="39c15-119">**Azure Active directory 管理センター**で、[ **azure active directory** ] に移動し、[**デバイス**]、[**デバイスの設定**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="39c15-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="39c15-120">**ユーザーがデバイスを AZURE AD に参加させる**ことが可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="39c15-120">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="39c15-121">すべてのユーザーを有効にするには、 **all**に設定します。</span><span class="sxs-lookup"><span data-stu-id="39c15-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="39c15-122">特定のユーザーを有効にするには、[**オン**] に設定して特定のユーザーグループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="39c15-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="39c15-123">Azure AD で同期されている目的のドメインユーザーを[セキュリティグループ](../admin/create-groups/create-groups.md)に追加します。</span><span class="sxs-lookup"><span data-stu-id="39c15-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="39c15-124">**[グループの選択**] を選択して、そのセキュリティグループの MDM ユーザースコープを有効にします。</span><span class="sxs-lookup"><span data-stu-id="39c15-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="39c15-125">3. MDM に対して Azure AD が有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="39c15-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="39c15-126">管理センターに移動し、[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **エンドポイント Managemen**の選択] を選択します (**エンドポイントマネージャー**が表示されない場合は [**すべて表示**] を選択します)</span><span class="sxs-lookup"><span data-stu-id="39c15-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="39c15-127">**Microsoft エンドポイントマネージャー管理センター**で、[**デバイス**  >  **windows**  >  **windows 登録**の  >  **自動登録**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="39c15-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="39c15-128">MDM ユーザースコープが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="39c15-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="39c15-129">すべてのコンピューターを登録するには、[**すべて**] に設定して、ユーザーが Windows に作業アカウントを追加するときに、Azure AD と新しいコンピューターに参加するすべてのユーザーコンピューターを自動的に登録します。</span><span class="sxs-lookup"><span data-stu-id="39c15-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="39c15-130">特定のユーザーグループのコンピューターを登録するには、[**一部**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="39c15-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="39c15-131">Azure AD で同期されている目的のドメインユーザーを[セキュリティグループ](../admin/create-groups/create-groups.md)に追加します。</span><span class="sxs-lookup"><span data-stu-id="39c15-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="39c15-132">**[グループの選択**] を選択して、そのセキュリティグループの MDM ユーザースコープを有効にします。</span><span class="sxs-lookup"><span data-stu-id="39c15-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="39c15-133">4. 必要なリソースを作成する</span><span class="sxs-lookup"><span data-stu-id="39c15-133">4. Create the required resources</span></span> 

<span data-ttu-id="39c15-134">[ハイブリッド AZURE AD join の構成](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)に必要なタスクを実行することは、 [secmgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell モジュールにある[SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)コマンドレットを使用することによって簡略化されました。</span><span class="sxs-lookup"><span data-stu-id="39c15-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="39c15-135">このコマンドレットを呼び出すと、必要なサービス接続ポイントとグループポリシーが作成および構成されます。</span><span class="sxs-lookup"><span data-stu-id="39c15-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="39c15-136">このモジュールは、PowerShell のインスタンスから次を呼び出してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="39c15-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="39c15-137">このモジュールは、Azure AD Connect を実行している Windows サーバーにインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39c15-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="39c15-138">必要なサービス接続ポイントとグループポリシーを作成するには、 [SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)コマンドレットを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="39c15-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="39c15-139">このタスクを実行するときには、Microsoft 365 Business Premium グローバル管理者の資格情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="39c15-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="39c15-140">リソースを作成する準備ができたら、次のように呼び出します。</span><span class="sxs-lookup"><span data-stu-id="39c15-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="39c15-141">最初のコマンドは、Microsoft クラウドとの接続を確立し、メッセージが表示されたら、Microsoft 365 Business Premium グローバル管理者の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="39c15-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="39c15-142">5. グループポリシーをリンクする</span><span class="sxs-lookup"><span data-stu-id="39c15-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="39c15-143">グループポリシー管理コンソール (GPMC) で、ポリシーをリンクする場所を右クリックし、コンテキストメニューから [既存の*GPO のリンク*] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39c15-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="39c15-144">上記の手順で作成したポリシーを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39c15-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="39c15-145">最新の管理用テンプレートを取得する</span><span class="sxs-lookup"><span data-stu-id="39c15-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="39c15-146">**既定の AZURE AD 資格情報を使用した自動 MDM 登録を有効に**するポリシーが表示されない場合は、Windows 10、バージョン1803、バージョン1809、またはバージョン1903用の ADMX がインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39c15-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="39c15-147">この問題を解決するには、次の手順を実行します (注: 最新の MDM は下位互換性があります)。</span><span class="sxs-lookup"><span data-stu-id="39c15-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="39c15-148">ダウンロード: [Windows 10 の管理用テンプレート (admx) は2019更新プログラム (1903) の場合があり](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all)ます。</span><span class="sxs-lookup"><span data-stu-id="39c15-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="39c15-149">プライマリドメインコントローラー (PDC) にパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="39c15-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="39c15-150">フォルダーのバージョンに応じて、次の操作を行います。 **C:\Program files (x86) \Microsoft Group Policy\Windows 10 5 月 2019 Update (1903) v3**。</span><span class="sxs-lookup"><span data-stu-id="39c15-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="39c15-151">上記のパスの**ポリシー定義**フォルダーの名前を**policydefinitions**に変更します。</span><span class="sxs-lookup"><span data-stu-id="39c15-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="39c15-152">**Policydefinitions**フォルダーを**C:\Windows\SYSVOL\domain\Policies**にコピーします。</span><span class="sxs-lookup"><span data-stu-id="39c15-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="39c15-153">ドメイン全体に対して中央ポリシーストアを使用することを計画している場合は、そこに PolicyDefinitions の内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="39c15-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="39c15-154">ポリシーを使用可能にするには、プライマリドメインコントローラーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="39c15-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="39c15-155">この手順は、将来のバージョンでも同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="39c15-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="39c15-156">この時点で、[**既定の AZURE AD 資格情報を使用して MDM の自動登録を有効に**する] ポリシーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39c15-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
