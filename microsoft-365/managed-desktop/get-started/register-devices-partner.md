---
title: デバイスを登録するためのパートナー向け手順
description: パートナーが Microsoft マネージドデスクトップで管理できるようにデバイスを登録する方法
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071445"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="67f00-103">デバイスを登録するためのパートナー向け手順</span><span class="sxs-lookup"><span data-stu-id="67f00-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="67f00-104">このトピックでは、パートナーがデバイスを登録するために従う必要のある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="67f00-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="67f00-105">自分でデバイスを登録するプロセスについては、「 [Microsoft マネージドデスクトップの登録デバイス](register-devices-self.md)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="67f00-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="67f00-106">登録の準備</span><span class="sxs-lookup"><span data-stu-id="67f00-106">Prepare for registration</span></span> 
<span data-ttu-id="67f00-107">お客様の登録を完了する前に、 [パートナーセンター](https://partner.microsoft.com/dashboard)で、お客様との関係を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67f00-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="67f00-108">そのプロセスの詳細については、 [同意書](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f00-108">See the [consent documentation](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="67f00-109">すべての CSP パートナーは、お客様が同意する限り、お客様の代わりにデバイスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="67f00-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="67f00-110">パートナー関係および自動操縦のアクセス許可の詳細については、 [パートナーセンターのヘルプ](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f00-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="67f00-111">このドキュメントは、パートナーと Oem のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="67f00-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="67f00-112">自己登録のプロセスについては、「 [Microsoft マネージドデスクトップの登録デバイス](register-devices-self.md)」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="67f00-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="67f00-113">パートナーセンターを使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="67f00-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="67f00-114">お客様との関係を確立したら、次の手順に従って、パートナーセンターを活用して、関係のあるお客様のためにデバイスを自動操縦に追加できます。</span><span class="sxs-lookup"><span data-stu-id="67f00-114">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="67f00-115">[パートナーセンター](https://partner.microsoft.com/dashboard)への移動</span><span class="sxs-lookup"><span data-stu-id="67f00-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="67f00-116">パートナーセンターメニューから [ **顧客** ] を選択し、管理するデバイスのお客様を選択します。</span><span class="sxs-lookup"><span data-stu-id="67f00-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="67f00-117">お客様の詳細ページで、[ **デバイス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67f00-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="67f00-118">[デバイスへの **プロファイルの適用** ] で、[ **デバイスの追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67f00-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="67f00-119">グループ名の **Microsoft365Managed_Autopilot** を入力し、[ **参照** ] を選択して、顧客のリスト (.csv ファイル形式) をパートナーセンターにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="67f00-119">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="67f00-120">グループ名は、大文字と小文字を区別し **Microsoft365Managed_Autopilot** 正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67f00-120">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="67f00-121">これにより、新しく登録されたデバイスを Microsoft Managed Desktop 自動操縦プロファイルに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="67f00-121">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="67f00-122">この .csv ファイルは、デバイスの購入時に入手する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67f00-122">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="67f00-123">.Csv ファイルを受け取っていない場合は、「 [Windows 自動操縦にデバイスを追加する](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)」の手順に従って作成します。</span><span class="sxs-lookup"><span data-stu-id="67f00-123">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="67f00-124">Windows PowerShell スクリプトは、 [Microsoft Managed Desktop 管理ポータル](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)で使用されているものとは異なります。</span><span class="sxs-lookup"><span data-stu-id="67f00-124">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="67f00-125">パートナーは [、g-et-windowsautopilotinfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) を使用してパートナーセンターの Microsoft マネージドデスクトップデバイスにデバイスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67f00-125">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="67f00-126">.Csv ファイルのアップロード中にエラーメッセージが表示される場合は、ファイルの形式を確認してください。</span><span class="sxs-lookup"><span data-stu-id="67f00-126">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="67f00-127">「 [新しいデバイスで Windows 自動操縦プロファイルを使用する](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)」で説明されている内容と一致していることを確認して、お客様の標準外の環境をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="67f00-127">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="67f00-128">次のリンクから提供されているサンプル .csv ファイルを使用して、[デバイスの **追加** ] リストを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="67f00-128">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="67f00-129">パートナーシナリオでの自動操縦の詳細については、「 [顧客のアカウントにデバイスを追加する](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f00-129">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="67f00-130">OEM API を使用してデバイスを登録する</span><span class="sxs-lookup"><span data-stu-id="67f00-130">Register devices by using the OEM API</span></span>

<span data-ttu-id="67f00-131">顧客の登録を完了する前に、顧客との関係を確立する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67f00-131">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="67f00-132">それぞれの顧客に提供する固有のリンクを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67f00-132">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="67f00-133">「 [OEM の関係を確立する方法」を](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)参照してください。</span><span class="sxs-lookup"><span data-stu-id="67f00-133">See [How to establish OEM relationship](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="67f00-134">関係を確立したら、グループタグ **Microsoft365Managed_Autopilot** を使用して、顧客用のデバイスの登録を開始できます。</span><span class="sxs-lookup"><span data-stu-id="67f00-134">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67f00-135">グループ名は、大文字と小文字を区別し **Microsoft365Managed_Autopilot** 正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67f00-135">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="67f00-136">これにより、新しく登録されたデバイスを Microsoft Managed Desktop 自動操縦プロファイルに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="67f00-136">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>
