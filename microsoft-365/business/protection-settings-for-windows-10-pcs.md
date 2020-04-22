---
title: Windows 10 の PC のデバイス保護設定を設定する
f1.keywords:
- NOCSH
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Windows 10 デバイスをセキュリティで保護するために Microsoft 365 for business で利用可能な既定の設定とその他の設定について説明します。
ms.openlocfilehash: a3b7f0a8572a215491b32101a30c306b54571b6f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633019"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="a9eda-103">Windows 10 の PC のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="a9eda-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="a9eda-104">Windows 10 デバイスをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="a9eda-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="a9eda-105">Microsoft 365 for business を使用して Windows 10 デバイスをセキュリティで保護する方法に関するビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9eda-105">View a video on how to secure Windows 10 devices with Microsoft 365 for business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="a9eda-106"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a9eda-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="a9eda-107">左側のナビゲーションで、[**デバイス** \> **ポリシー** \>の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9eda-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="a9eda-108">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a9eda-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="a9eda-109">[ **ポリシーの種類**] で、[ **Windows 10 デバイスの構成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="a9eda-110">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="a9eda-110">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="a9eda-111">詳細については、「[使用可能な設定](#available-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9eda-111">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="a9eda-112">[ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-112">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="a9eda-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="a9eda-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="a9eda-116">最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="a9eda-117">利用可能な設定</span><span class="sxs-lookup"><span data-stu-id="a9eda-117">Available settings</span></span>

<span data-ttu-id="a9eda-118">既定では、すべての設定が **オン**になっています。</span><span class="sxs-lookup"><span data-stu-id="a9eda-118">By default all settings are **On**.</span></span> <span data-ttu-id="a9eda-119">次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-119">The following settings are available.</span></span>
  
<span data-ttu-id="a9eda-120">詳細については、「 [Microsoft 365 Premium の保護機能を Intune 設定にマップする方法](map-protection-features-to-intune-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9eda-120">For more information, see [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a9eda-121">設定</span><span class="sxs-lookup"><span data-stu-id="a9eda-121">Setting</span></span>  <br/> |<span data-ttu-id="a9eda-122">説明</span><span class="sxs-lookup"><span data-stu-id="a9eda-122">Description</span></span>  <br/> |
|<span data-ttu-id="a9eda-123">Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="a9eda-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="a9eda-124">インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9eda-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="a9eda-125">Microsoft Edge で PC を Web ベースの脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="a9eda-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="a9eda-126">ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="a9eda-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="a9eda-127">デバイスに対する攻撃を回避するルールを使用する</span><span class="sxs-lookup"><span data-stu-id="a9eda-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="a9eda-p104">オンにすると、攻撃の回避により、デバイス感染のためにマルウェアが通常使用するアクションやアプリをブロックすることができます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[攻撃の回避](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="a9eda-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) to learn more.  </span></span><br/> |
|<span data-ttu-id="a9eda-131">ランサムウェアなどの脅威からフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="a9eda-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="a9eda-132">この設定は、フォルダーへのアクセスを制御することによって、ランサムウェアなどの不審なまたは悪意のあるアプリケーションによる書き換えから会社のデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="a9eda-132">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware.</span></span> <span data-ttu-id="a9eda-133">こうした種類のアプリケーションは、保護されているフォルダーで変更を行うことができないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-133">These types of apps are blocked from making changes in protected folders.</span></span> <span data-ttu-id="a9eda-134">Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-134">This setting is only available if Windows Defender Antivirus is set to On.</span></span> <span data-ttu-id="a9eda-135">詳細については、「[フォルダーを制限付きフォルダーアクセスで保護](https://docs.microsoft.com/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9eda-135">See [Protect folders with Controlled folder access](https://docs.microsoft.com/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) to learn more.</span></span>  <br/> |
|<span data-ttu-id="a9eda-136">インターネット上の悪意がある可能性のあるコンテンツに対するネットワーク アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="a9eda-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="a9eda-137">この設定を使用して、フィッシング詐欺、悪用、またはその他の悪意のあるコンテンツをホストする可能性がある低評価のインターネット上の場所への送信ユーザー接続をブロックします。</span><span class="sxs-lookup"><span data-stu-id="a9eda-137">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits, or other malicious content.</span></span> <span data-ttu-id="a9eda-138">この設定は、Windows Defender ウイルス対策が **[オン**] に設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-138">This setting is only available if Windows Defender Antivirus is set to **On**.</span></span> <span data-ttu-id="a9eda-139">詳細については、「[ネットワークを保護する](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9eda-139">For more information, see [Protect your network](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).</span></span>  <br/> |
|<span data-ttu-id="a9eda-140">不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する</span><span class="sxs-lookup"><span data-stu-id="a9eda-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="a9eda-141">BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-141">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="a9eda-142">詳細については、「Bitlocker に関する[FAQ](https://go.microsoft.com/fwlink/?linkid=871000)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9eda-142">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="a9eda-143">ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する</span><span class="sxs-lookup"><span data-stu-id="a9eda-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="a9eda-p108">ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン**のままにしていますが、セキュリティを強化するためにオフにすることもできます。  </span><span class="sxs-lookup"><span data-stu-id="a9eda-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="a9eda-146">ユーザーが Cortana にアクセスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="a9eda-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="a9eda-147">Cortana は非常に役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9eda-147">Cortana can be very helpful!</span></span> <span data-ttu-id="a9eda-148">Cortana では、設定を有効または無効にしたり、案内を表示したり、予定に時間があるかどうかを確認したりすることができます。**この設定は既定でオンに**しておきます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-148">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="a9eda-149">ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する</span><span class="sxs-lookup"><span data-stu-id="a9eda-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="a9eda-150">Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="a9eda-151">Windows 10 デバイスを自動的に最新の状態に維持する</span><span class="sxs-lookup"><span data-stu-id="a9eda-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="a9eda-152">Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="a9eda-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="a9eda-153">この時間アイドル状態になったときにデバイスの画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="a9eda-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="a9eda-p110">ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a9eda-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
