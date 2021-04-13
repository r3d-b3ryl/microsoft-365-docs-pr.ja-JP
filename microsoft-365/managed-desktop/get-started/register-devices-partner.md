---
title: デバイスを登録するためのパートナー向け手順
description: Microsoft Managed Desktop でデバイスを管理できるよう、パートナーがデバイスを登録する方法
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689235"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="40ffd-103">デバイスを登録するためのパートナー向け手順</span><span class="sxs-lookup"><span data-stu-id="40ffd-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="40ffd-104">この記事では、パートナーがデバイスを登録するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="40ffd-104">This article describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="40ffd-105">デバイスを自分で登録するプロセスについては、「Microsoft Managed Desktop のデバイスを自分で登録する [」に記載されています](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="40ffd-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="40ffd-106">登録の準備</span><span class="sxs-lookup"><span data-stu-id="40ffd-106">Prepare for registration</span></span> 
<span data-ttu-id="40ffd-107">顧客の登録を完了する前に、まずパートナー センターで顧客との関係を [確立する必要があります](https://partner.microsoft.com/dashboard)。</span><span class="sxs-lookup"><span data-stu-id="40ffd-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="40ffd-108">そのプロセスの [詳細については、](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 同意のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40ffd-108">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="40ffd-109">CSP パートナーは、お客様の同意がある限り、任意の顧客に代わってデバイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="40ffd-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="40ffd-110">パートナーの関係と自動操縦のアクセス許可の詳細については、「パートナー センター [のヘルプ」を参照してください](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="40ffd-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="40ffd-111">このドキュメントは、パートナーと OEM 専用です。</span><span class="sxs-lookup"><span data-stu-id="40ffd-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="40ffd-112">自己登録のプロセスについては、「Microsoft Managed Desktop のデバイスを自分で登録 [する」に記載されています](register-devices-self.md)。</span><span class="sxs-lookup"><span data-stu-id="40ffd-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="40ffd-113">パートナー センターを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="40ffd-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="40ffd-114">顧客との関係を確立したら、パートナー センターを使用して、次の手順に従って、関係のある顧客のデバイスを Autopilot に追加できます。</span><span class="sxs-lookup"><span data-stu-id="40ffd-114">Once you have established the relationship with your customers, you can use Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="40ffd-115">パートナー センター [に移動する](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="40ffd-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="40ffd-116">[ **パートナー センター** ] メニューから [顧客] を選択し、管理するデバイスを持つ顧客を選択します。</span><span class="sxs-lookup"><span data-stu-id="40ffd-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="40ffd-117">顧客の詳細ページで、[デバイス] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="40ffd-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="40ffd-118">[デバイス **にプロファイルを適用する]** で、[デバイスの追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="40ffd-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="40ffd-119">次の表に示すように、選択したデバイス プロファイルに適切なグループ タグを入力し、[参照]を選択して顧客のリスト (.csv ファイル形式) をパートナー センターにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="40ffd-119">Enter the appropriate Group Tag for the device profile you've selected (as shown in the following table) and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>

|[<span data-ttu-id="40ffd-120">デバイス プロファイル</span><span class="sxs-lookup"><span data-stu-id="40ffd-120">Device profile</span></span>](../service-description/profiles.md)  |<span data-ttu-id="40ffd-121">グループ タグ</span><span class="sxs-lookup"><span data-stu-id="40ffd-121">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="40ffd-122">機密性の高いデータ</span><span class="sxs-lookup"><span data-stu-id="40ffd-122">Sensitive data</span></span>     |<span data-ttu-id="40ffd-123">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="40ffd-123">**Microsoft365Managed\_SensitiveData**</span></span>    |
|<span data-ttu-id="40ffd-124">Power User</span><span class="sxs-lookup"><span data-stu-id="40ffd-124">Power user</span></span>     | <span data-ttu-id="40ffd-125">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="40ffd-125">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="40ffd-126">標準</span><span class="sxs-lookup"><span data-stu-id="40ffd-126">Standard</span></span>     | <span data-ttu-id="40ffd-127">**Microsoft365Managed \_ Standard**</span><span class="sxs-lookup"><span data-stu-id="40ffd-127">**Microsoft365Managed\_Standard**</span></span>        |

> [!IMPORTANT]
> <span data-ttu-id="40ffd-128">グループ名は、大文字と特殊文字を含む、表に記載されている名前と完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40ffd-128">The Group Name must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="40ffd-129">これにより、新しく登録されたデバイスに Microsoft Managed Desktop Autopilot プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="40ffd-129">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="40ffd-130">デバイスの購入でこの .csv ファイルを受け取っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="40ffd-130">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="40ffd-131">.csv ファイルを受信しなかった場合は [、「Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)へのデバイスの追加」の手順に従って、自分で作成できます。</span><span class="sxs-lookup"><span data-stu-id="40ffd-131">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="40ffd-132">このWindows PowerShellは [、Microsoft Managed Desktop Admin](./register-devices-self.md#obtain-the-hardware-hash)ポータルで使用されるスクリプトとは異なります。</span><span class="sxs-lookup"><span data-stu-id="40ffd-132">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md#obtain-the-hardware-hash).</span></span> <span data-ttu-id="40ffd-133">パートナーは [、Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) を使用して、Microsoft マネージ デスクトップ デバイスのデバイスをパートナー センターに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40ffd-133">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="40ffd-134">.csv ファイルのアップロード中にエラー メッセージが表示される場合は、ファイルの形式を確認します。</span><span class="sxs-lookup"><span data-stu-id="40ffd-134">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="40ffd-135">列の順序が「新しいデバイスで [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)プロファイルを使用して顧客のアウトボックス エクスペリエンスをカスタマイズする」で説明されている順序と一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="40ffd-135">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="40ffd-136">[デバイスの追加] の横にあるリンクから提供されるサンプルの .csv ファイルを使用 **して、デバイス** リストを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="40ffd-136">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="40ffd-137">パートナー シナリオでの自動パイロットの詳細については、「デバイスを [顧客のアカウントに追加する」を参照してください](/partner-center/autopilot#add-devices-to-a-customers-account)。</span><span class="sxs-lookup"><span data-stu-id="40ffd-137">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="40ffd-138">OEM API を使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="40ffd-138">Register devices by using the OEM API</span></span>

<span data-ttu-id="40ffd-139">顧客の登録を完了する前に、まず顧客との関係を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40ffd-139">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="40ffd-140">それぞれの顧客に提供する一意のリンクが必要です。</span><span class="sxs-lookup"><span data-stu-id="40ffd-140">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="40ffd-141">「OEM [リレーションシップを確立する方法」を参照してください](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。</span><span class="sxs-lookup"><span data-stu-id="40ffd-141">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="40ffd-142">リレーションシップを確立したら、選択したデバイス プロファイルごとに適切なグループ タグを使用して、顧客のデバイスの登録を開始できます。</span><span class="sxs-lookup"><span data-stu-id="40ffd-142">Once you've established the relationship, you can start registering devices for customers using the appropriate Group Tag for each device profile they've selected:</span></span>


|<span data-ttu-id="40ffd-143">デバイス プロファイル</span><span class="sxs-lookup"><span data-stu-id="40ffd-143">Device profile</span></span>  |<span data-ttu-id="40ffd-144">グループ タグ</span><span class="sxs-lookup"><span data-stu-id="40ffd-144">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="40ffd-145">機密性の高いデータ</span><span class="sxs-lookup"><span data-stu-id="40ffd-145">Sensitive data</span></span>     | <span data-ttu-id="40ffd-146">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="40ffd-146">**Microsoft365Managed\_SensitiveData**</span></span>     |
|<span data-ttu-id="40ffd-147">Power User</span><span class="sxs-lookup"><span data-stu-id="40ffd-147">Power user</span></span>     | <span data-ttu-id="40ffd-148">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="40ffd-148">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="40ffd-149">標準</span><span class="sxs-lookup"><span data-stu-id="40ffd-149">Standard</span></span>     | <span data-ttu-id="40ffd-150">**Microsoft365Managed \_ Standard**</span><span class="sxs-lookup"><span data-stu-id="40ffd-150">**Microsoft365Managed\_Standard**</span></span>      |

> [!IMPORTANT]
> <span data-ttu-id="40ffd-151">グループ タグは、大文字と特殊文字を含む、表に記載されているタグと完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40ffd-151">The Group Tags must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="40ffd-152">これにより、新しく登録されたデバイスに Microsoft Managed Desktop Autopilot プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="40ffd-152">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>