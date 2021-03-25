---
title: MacOS デバイスの Microsoft Defender ATP を Jamf Pro に登録する
description: MacOS デバイスの Microsoft Defender ATP を Jamf Pro に登録する
keywords: microsoft、 defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4dcaa8063ea11ab2ca43330a761783fead829d3e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067651"
---
# <a name="enroll-microsoft-defender-for-endpoint-for-macos-devices-into-jamf-pro"></a><span data-ttu-id="d17cb-104">MacOS デバイスの Microsoft Defender for Endpoint を Jamf Pro に登録する</span><span class="sxs-lookup"><span data-stu-id="d17cb-104">Enroll Microsoft Defender for Endpoint for macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d17cb-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d17cb-105">**Applies to:**</span></span>
- [<span data-ttu-id="d17cb-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d17cb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="d17cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d17cb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d17cb-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d17cb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d17cb-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d17cb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="d17cb-110">macOS デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="d17cb-110">Enroll macOS devices</span></span>

<span data-ttu-id="d17cb-111">JamF に登録するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="d17cb-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="d17cb-112">この記事では、次の 2 つの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d17cb-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="d17cb-113">方法 1: 登録の招待</span><span class="sxs-lookup"><span data-stu-id="d17cb-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="d17cb-114">方法 2: 事前登録</span><span class="sxs-lookup"><span data-stu-id="d17cb-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="d17cb-115">完全な一覧については、「コンピューターの登録 [について」を参照してください](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)。</span><span class="sxs-lookup"><span data-stu-id="d17cb-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="d17cb-116">登録方法 1: 登録の招待</span><span class="sxs-lookup"><span data-stu-id="d17cb-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="d17cb-117">Jamf Pro ダッシュボードで、[登録の招待] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d17cb-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![構成設定のイメージ1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="d17cb-119">[+ **新規] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d17cb-119">Select **+ New**.</span></span>

    ![ロゴの説明が自動的に生成される](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="d17cb-121">[ **招待の受信者の指定] >** **[** 電子メール アドレス] の下に、受信者の電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d17cb-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![構成設定のイメージ2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![構成設定のイメージ 3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="d17cb-124">たとえば、次の janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d17cb-124">For example: janedoe@contoso.com</span></span>

    ![構成設定のイメージ 4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="d17cb-126">招待のメッセージを構成します。</span><span class="sxs-lookup"><span data-stu-id="d17cb-126">Configure the message for the invitation.</span></span>

    ![構成設定のイメージ5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![構成設定のイメージ6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![構成設定のイメージ 7](images/3ced5383a6be788486d89d407d042f28.png)

    ![構成設定のイメージ8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="d17cb-131">登録方法 2: 事前登録</span><span class="sxs-lookup"><span data-stu-id="d17cb-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="d17cb-132">Jamf Pro ダッシュボードで、[Prestage 登録 **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d17cb-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![構成設定のイメージ 9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="d17cb-134">「Computer [PreStage 登録」の手順に従います](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)。</span><span class="sxs-lookup"><span data-stu-id="d17cb-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="d17cb-135">macOS デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="d17cb-135">Enroll macOS device</span></span>

1. <span data-ttu-id="d17cb-136">[ **続行] を** 選択し、[システムの基本設定] ウィンドウから **CA 証明書をインストール** します。</span><span class="sxs-lookup"><span data-stu-id="d17cb-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Jamf Pro 登録のイメージ1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="d17cb-138">CA 証明書がインストールされた後、ブラウザー ウィンドウに戻り、[続行] を **選択して** MDM プロファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d17cb-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Jamf Pro 登録のイメージ2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="d17cb-140">[JAMF **からの** ダウンロードを許可する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d17cb-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Jamf Pro 登録のイメージ3](images/jamfpro-download.png)

4. <span data-ttu-id="d17cb-142">[続行 **] を** 選択して MDM プロファイルのインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="d17cb-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Jamf Pro 登録のイメージ 4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="d17cb-144">[続行 **] を** 選択して MDM プロファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d17cb-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Jamf Pro 登録のイメージ5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="d17cb-146">[続行 **] を**  選択して構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="d17cb-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Jamf Pro 登録のイメージ6](images/jamfpro-mdm-profile.png)
