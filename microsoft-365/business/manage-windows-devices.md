---
title: ドメインに参加している Windows 10 デバイスをビジネス向け Microsoft 365 で管理可能にする
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Microsoft 365 がローカルの Active-Directory に参加している Windows 10 デバイスをわずか数ステップで保護する方法について説明します。
ms.openlocfilehash: 8a45c6959bee368491c5c6424e3713300c443779
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580136"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="ab17a-103">ドメインに参加している Windows 10 デバイスを Microsoft 365 Business Premium によって管理可能にする</span><span class="sxs-lookup"><span data-stu-id="ab17a-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="ab17a-104">組織で Windows Server Active Directory をオンプレミスで使用している場合は、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持しながら、Windows 10 デバイスを保護するために Microsoft 365 Business Premium をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="ab17a-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="ab17a-105">この保護を設定するには、参加しているデバイスに **ハイブリッド Azure AD実装できます**。</span><span class="sxs-lookup"><span data-stu-id="ab17a-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="ab17a-106">これらのデバイスは、オンプレミスの Active Directory と Azure Active Directory の両方に参加しています。</span><span class="sxs-lookup"><span data-stu-id="ab17a-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="ab17a-107">このビデオでは、最も一般的なシナリオでこれを設定する手順について説明します。この手順については、以下の手順でも説明します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="ab17a-108">開始する前に、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="ab17a-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="ab17a-109">Azure AD Connect とユーザーを Azure AD同期します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="ab17a-110">Azure AD組織単位 (OU) の同期を完了します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="ab17a-111">同期するドメイン ユーザー全員が Microsoft 365 Business Premium にライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab17a-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="ab17a-112">手順については [、「ドメイン ユーザーを Microsoft に同期する](manage-domain-users.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab17a-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="ab17a-113">1. Intune で MDM 機関を確認する</span><span class="sxs-lookup"><span data-stu-id="ab17a-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="ab17a-114">[エンドポイント マネージャー][に移動](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview)し、[Microsoft Intune] ページで[デバイスの登録] を選択し、[概要] ページで **、MDM 機関** が Intune である必要 **があります**。</span><span class="sxs-lookup"><span data-stu-id="ab17a-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="ab17a-115">**MDM 機関が** **None の場合は\*\*\*\*、MDM 機関** をクリックして Intune に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="ab17a-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="ab17a-116">**MDM** 機関が **Microsoft Office 365** の場合は、[デバイスの登録] に移動し、右側の [MDM 機関の追加] ダイアログを使用して Intune MDM 機関を追加します (MDM 機関の追加ダイアログは、MDM Authority が Microsoft Office  >   365に設定されている場合にのみ使用できます)。</span><span class="sxs-lookup"><span data-stu-id="ab17a-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="ab17a-117">2. Azure AD参加が有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="ab17a-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="ab17a-118">管理センターに移動し、[管理センター] リストで <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **[Azure Active Directory]** ([Azure Active Directory が表示されない場合はすべて表示する] **を選択) を選択** します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="ab17a-119">Azure **Active Directory 管理センターで\*\*\*\*、[Azure Active Directory]** に移動し、[デバイス] を選択し、[**デバイス** の設定]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ab17a-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="ab17a-120">ユーザー **がデバイスを Azure に参加する可能性AD** 確認する</span><span class="sxs-lookup"><span data-stu-id="ab17a-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="ab17a-121">すべてのユーザーを有効にするには、[すべて] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="ab17a-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="ab17a-122">特定のユーザーを有効にするには、[選択] **に** 設定して、特定のユーザー グループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ab17a-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="ab17a-123">Azure で同期された目的のドメイン ユーザーをセキュリティ ADに [追加します](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="ab17a-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="ab17a-124">[グループ **の選択]** を選択して、そのセキュリティ グループの MDM ユーザー スコープを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ab17a-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="ab17a-125">3. MDM で Azure ADが有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="ab17a-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="ab17a-126">管理センターに移動し、[エンドポイント管理] t を選択します ([エンドポイント マネージャーが表示されない場合は、[すべて表示 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **]** を選択) </span><span class="sxs-lookup"><span data-stu-id="ab17a-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="ab17a-127">Microsoft **Endpoint Manager 管理センターで、[** デバイス]   >  **[Windows Windows** 登録自動登録  >    >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ab17a-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="ab17a-128">MDM ユーザー スコープが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="ab17a-129">すべてのコンピューターを登録するには、[すべて] に設定して、ユーザーが Windows に作業用アカウントを追加するときに、Azure AD に参加しているすべてのユーザー コンピューターと新しいコンピューターを自動的に登録します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="ab17a-130">特定の **ユーザー グループ** のコンピューターを登録するには、[一部] に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="ab17a-131">Azure で同期された目的のドメイン ユーザーをセキュリティ ADに [追加します](../admin/create-groups/create-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="ab17a-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="ab17a-132">[グループ **の選択]** を選択して、そのセキュリティ グループの MDM ユーザー スコープを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ab17a-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="ab17a-133">4. 必要なリソースを作成する</span><span class="sxs-lookup"><span data-stu-id="ab17a-133">4. Create the required resources</span></span> 

<span data-ttu-id="ab17a-134">ハイブリッド[Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)参加を構成するために必要なタスクを実行すると[、SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell モジュールにある[Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)コマンドレットを使用して簡略化されました。</span><span class="sxs-lookup"><span data-stu-id="ab17a-134">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="ab17a-135">このコマンドレットを呼び出すと、必要なサービス接続ポイントとグループ ポリシーが作成および構成されます。</span><span class="sxs-lookup"><span data-stu-id="ab17a-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="ab17a-136">このモジュールは、PowerShell のインスタンスから次のコマンドを呼び出してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ab17a-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="ab17a-137">このモジュールは、Azure サーバー接続を実行している Windows Server にインストールAD勧めします。</span><span class="sxs-lookup"><span data-stu-id="ab17a-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="ab17a-138">必要なサービス接続ポイントとグループ ポリシーを作成するには  [、Initialize-SecMgmtHybirdDeviceEnrollment コマンドレットを呼び出](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="ab17a-139">このタスクを実行するには、Microsoft 365 Business Premium のグローバル管理者資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="ab17a-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="ab17a-140">リソースを作成する準備ができたら、次のコマンドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="ab17a-141">最初のコマンドは、Microsoft クラウドとの接続を確立し、メッセージが表示されたら、Microsoft 365 Business Premium のグローバル管理者資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="ab17a-142">5. グループ ポリシーのリンク</span><span class="sxs-lookup"><span data-stu-id="ab17a-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="ab17a-143">グループ ポリシー管理コンソール (GPMC) で、ポリシーをリンクする場所を右クリックし、コンテキスト メニューから [既存 *の GPO...* をリンクする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="ab17a-144">上記の手順で作成したポリシーを選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ab17a-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="ab17a-145">最新の管理用テンプレートを取得する</span><span class="sxs-lookup"><span data-stu-id="ab17a-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="ab17a-146">[既定の Azure AD 資格情報を使用して **自動 MDM** 登録を有効にする] ポリシーが表示されない場合は、Windows 10 バージョン 1803 以降に ADMX がインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab17a-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="ab17a-147">問題を解決するには、次の手順に従います (注: 最新の MDM.admx は下位互換性があります)。</span><span class="sxs-lookup"><span data-stu-id="ab17a-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="ab17a-148">ダウンロード: [Windows 10 2020 年 10 月更新プログラム (20H2)](https://www.microsoft.com/download/102157)用の管理用テンプレート (.admx) 。</span><span class="sxs-lookup"><span data-stu-id="ab17a-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="ab17a-149">ドメイン コントローラーにパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ab17a-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="ab17a-150">管理用テンプレートのバージョンに応じて、フォルダーに移動します **。C:\Program Files (x86)\Microsoft グループ ポリシー\Windows 10 2020 Update (20H2)**</span><span class="sxs-lookup"><span data-stu-id="ab17a-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="ab17a-151">上記の **パスの [ポリシー定義]** フォルダーの名前を **PolicyDefinitions に変更します**。</span><span class="sxs-lookup"><span data-stu-id="ab17a-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="ab17a-152">**PolicyDefinitions フォルダー** を SYSVOL 共有にコピーします。既定では **C:\Windows\SYSVOL\domain\Policies** にあります。</span><span class="sxs-lookup"><span data-stu-id="ab17a-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="ab17a-153">ドメイン全体で中央ポリシー ストアを使用する場合は、PolicyDefinitions のコンテンツをそこに追加します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="ab17a-154">複数のドメイン コントローラーがある場合は、ポリシーが使用可能になるまで SYSVOL がレプリケートされるのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="ab17a-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="ab17a-155">この手順は、将来のバージョンの管理用テンプレートでも機能します。</span><span class="sxs-lookup"><span data-stu-id="ab17a-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="ab17a-156">この時点で、既定の Azure アカウント資格情報を使用して **自動 MDM** 登録を有効にするポリシー AD確認できます。</span><span class="sxs-lookup"><span data-stu-id="ab17a-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>