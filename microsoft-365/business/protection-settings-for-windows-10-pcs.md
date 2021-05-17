---
title: PC のデバイス保護設定を編集またはWindows 10する
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: ビジネス向けアプリで使用できるMicrosoft 365デバイスをセキュリティで保護するWindows 10します。
ms.openlocfilehash: acfb27b2e4592d4ed1e446a63c9495ae07d916de
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578229"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="f1754-103">PC のデバイス保護設定を編集またはWindows 10する</span><span class="sxs-lookup"><span data-stu-id="f1754-103">Edit or create device protection settings for Windows 10 PCs</span></span>

<span data-ttu-id="f1754-104">この記事は、このMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="f1754-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="f1754-105">[セットアップ] ページで既定の Windows保護設定を設定した後、すべてのユーザーまたは一連のユーザーに適用される新しい保護設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f1754-105">After you have set set up default Windows protection settings on the Setup page, you can add new ones that apply to either all users, or a set of users.</span></span> <span data-ttu-id="f1754-106">作成した任意のファイルを編集できます。</span><span class="sxs-lookup"><span data-stu-id="f1754-106">You can also edit any of the ones you have created.</span></span>

## <a name="create-protection-settings-for-windows-10-devices"></a><span data-ttu-id="f1754-107">デバイスの保護設定をWindows 10する</span><span class="sxs-lookup"><span data-stu-id="f1754-107">Create protection settings for Windows 10 devices</span></span>

<span data-ttu-id="f1754-108">次の方法でデバイスをセキュリティで保護するWindows 10ビデオをMicrosoft 365 Business Premium。</span><span class="sxs-lookup"><span data-stu-id="f1754-108">View a video on how to secure Windows 10 devices with Microsoft 365 Business Premium:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="f1754-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f1754-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="f1754-110">左側のナビゲーションで、[デバイス ポリシー **の** \> **追加] を** \> **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f1754-110">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="f1754-111">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f1754-111">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="f1754-112">[ **ポリシーの種類**] で、[ **Windows 10 デバイスの構成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f1754-112">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
5. <span data-ttu-id="f1754-113">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="f1754-113">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="f1754-114">詳細については、「使用可能な設定 [」を参照してください](#available-settings)。</span><span class="sxs-lookup"><span data-stu-id="f1754-114">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="f1754-115">[ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="f1754-115">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="f1754-p103">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="f1754-p103">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
7. <span data-ttu-id="f1754-119">最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f1754-119">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 

## <a name="edit-windows-10-protection-settings"></a><span data-ttu-id="f1754-120">保護Windows 10の編集</span><span class="sxs-lookup"><span data-stu-id="f1754-120">Edit Windows 10 protection settings</span></span>
 
1. <span data-ttu-id="f1754-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f1754-121">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="f1754-122">左側のナビゲーションで、[デバイス ポリシー **]** \> **を選択します** 。</span><span class="sxs-lookup"><span data-stu-id="f1754-122">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="f1754-123">既存のデバイス ポリシーをWindowsし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="f1754-123">Choose an existing Windows device policy and then **Edit**.</span></span>
1. <span data-ttu-id="f1754-124">変更 **する設定** の横にある [編集] を選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f1754-124">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="available-settings"></a><span data-ttu-id="f1754-125">利用可能な設定</span><span class="sxs-lookup"><span data-stu-id="f1754-125">Available settings</span></span>

<span data-ttu-id="f1754-p104">既定では、すべての設定が **オン** になっています。次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1754-p104">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="f1754-128">詳細については、「Intune の設定[にマップする方法Microsoft 365 プレミアム保護機能」を参照してください](map-protection-features-to-intune-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="f1754-128">For more information, see [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f1754-129">Setting</span><span class="sxs-lookup"><span data-stu-id="f1754-129">Setting</span></span>  <br/> |<span data-ttu-id="f1754-130">説明</span><span class="sxs-lookup"><span data-stu-id="f1754-130">Description</span></span>  <br/> |
|<span data-ttu-id="f1754-131">Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="f1754-131">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="f1754-132">インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1754-132">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="f1754-133">Microsoft Edge で PC を Web ベースの脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="f1754-133">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="f1754-134">ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="f1754-134">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="f1754-135">デバイスに対する攻撃を回避するルールを使用する</span><span class="sxs-lookup"><span data-stu-id="f1754-135">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="f1754-p105">オンにすると、攻撃の回避により、デバイス感染のためにマルウェアが通常使用するアクションやアプリをブロックすることができます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[攻撃の回避](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="f1754-p105">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) to learn more.  </span></span><br/> |
|<span data-ttu-id="f1754-139">ランサムウェアなどの脅威からフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="f1754-139">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="f1754-140">この設定は、フォルダーへのアクセスを制御することによって、ランサムウェアなどの不審なまたは悪意のあるアプリケーションによる書き換えから会社のデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="f1754-140">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware.</span></span> <span data-ttu-id="f1754-141">こうした種類のアプリケーションは、保護されているフォルダーで変更を行うことができないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f1754-141">These types of apps are blocked from making changes in protected folders.</span></span> <span data-ttu-id="f1754-142">Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。</span><span class="sxs-lookup"><span data-stu-id="f1754-142">This setting is only available if Windows Defender Antivirus is set to On.</span></span> <span data-ttu-id="f1754-143">詳細 [については、「フォルダー アクセスの制御を使用してフォルダーを保護する」](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1754-143">See [Protect folders with Controlled folder access](/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) to learn more.</span></span>  <br/> |
|<span data-ttu-id="f1754-144">インターネット上の悪意がある可能性のあるコンテンツに対するネットワーク アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="f1754-144">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="f1754-145">この設定を使用して、フィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある低評価のインターネットの場所への送信ユーザー接続をブロックします。</span><span class="sxs-lookup"><span data-stu-id="f1754-145">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits, or other malicious content.</span></span> <span data-ttu-id="f1754-146">この設定は、[オン] に設定Windows Defender ウイルス対策場合にのみ使用 **できます**。</span><span class="sxs-lookup"><span data-stu-id="f1754-146">This setting is only available if Windows Defender Antivirus is set to **On**.</span></span> <span data-ttu-id="f1754-147">詳細については、「ネットワークを [保護する」を参照してください](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="f1754-147">For more information, see [Protect your network](/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).</span></span>  <br/> |
|<span data-ttu-id="f1754-148">不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する</span><span class="sxs-lookup"><span data-stu-id="f1754-148">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="f1754-149">BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="f1754-149">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="f1754-150">詳細については [、「Bitlocker FAQ」を参照してください](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)。</span><span class="sxs-lookup"><span data-stu-id="f1754-150">For more information, see [Bitlocker FAQ](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions).</span></span>  <br/> |
|<span data-ttu-id="f1754-151">ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する</span><span class="sxs-lookup"><span data-stu-id="f1754-151">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="f1754-p109">ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン** のままにしていますが、セキュリティを強化するためにオフにすることもできます。  </span><span class="sxs-lookup"><span data-stu-id="f1754-p109">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="f1754-154">ユーザーが Cortana にアクセスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="f1754-154">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="f1754-155">Cortana は非常に役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1754-155">Cortana can be very helpful!</span></span> <span data-ttu-id="f1754-156">Cortana では、設定のオンとオフを切り替え、指示を出し、予定に間に合っている必要がある場合は、この設定を **既定でオンのままに** します。</span><span class="sxs-lookup"><span data-stu-id="f1754-156">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="f1754-157">ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する</span><span class="sxs-lookup"><span data-stu-id="f1754-157">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="f1754-158">Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f1754-158">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="f1754-159">Windows 10 デバイスを自動的に最新の状態に維持する</span><span class="sxs-lookup"><span data-stu-id="f1754-159">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="f1754-160">Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="f1754-160">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="f1754-161">この時間アイドル状態になったときにデバイスの画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="f1754-161">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="f1754-p111">ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。</span><span class="sxs-lookup"><span data-stu-id="f1754-p111">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |