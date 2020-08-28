---
title: Windows 10 Pc のデバイス保護設定を編集または作成する
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Windows 10 デバイスをセキュリティで保護するために Microsoft 365 for business で使用可能な設定について説明します。
ms.openlocfilehash: bd992113403c7134fb32bc6cced5bf216843241b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289157"
---
# <a name="edit-or-create-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="495e1-103">Windows 10 Pc のデバイス保護設定を編集または作成する</span><span class="sxs-lookup"><span data-stu-id="495e1-103">Edit or create device protection settings for Windows 10 PCs</span></span>

<span data-ttu-id="495e1-104">この記事は、Microsoft 365 Business Premium に適用されます。</span><span class="sxs-lookup"><span data-stu-id="495e1-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="495e1-105">[セットアップ] ページで、既定の Windows 保護設定を設定した後、すべてのユーザーまたはユーザーのセットに適用する新しいものを追加できます。</span><span class="sxs-lookup"><span data-stu-id="495e1-105">After you have set set up default Windows protection settings on the Setup page, you can add new ones that apply to either all users, or a set of users.</span></span> <span data-ttu-id="495e1-106">作成したものを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="495e1-106">You can also edit any of the ones you have created.</span></span>

## <a name="create-protection-settings-for-windows-10-devices"></a><span data-ttu-id="495e1-107">Windows 10 デバイスの保護設定を作成する</span><span class="sxs-lookup"><span data-stu-id="495e1-107">Create protection settings for Windows 10 devices</span></span>

<span data-ttu-id="495e1-108">Microsoft 365 Business Premium を使用して Windows 10 デバイスをセキュリティで保護する方法に関するビデオを参照してください。</span><span class="sxs-lookup"><span data-stu-id="495e1-108">View a video on how to secure Windows 10 devices with Microsoft 365 Business Premium:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="495e1-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="495e1-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="495e1-110">左側のナビゲーションで、[**デバイス**ポリシーの追加] を選択し \> **Policies** \> **Add**ます。</span><span class="sxs-lookup"><span data-stu-id="495e1-110">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="495e1-111">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="495e1-111">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="495e1-112">[ **ポリシーの種類**] で、[ **Windows 10 デバイスの構成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="495e1-112">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
5. <span data-ttu-id="495e1-113">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span><span class="sxs-lookup"><span data-stu-id="495e1-113">Expand **Secure Windows 10 Devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="495e1-114">詳細については、「 [使用可能な設定](#available-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495e1-114">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="495e1-115">[ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="495e1-115">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](../media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="495e1-p103">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="495e1-p103">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
7. <span data-ttu-id="495e1-119">最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="495e1-119">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 

## <a name="edit-windows-10-protection-settings"></a><span data-ttu-id="495e1-120">Windows 10 の保護設定を編集する</span><span class="sxs-lookup"><span data-stu-id="495e1-120">Edit Windows 10 protection settings</span></span>
 
1. <span data-ttu-id="495e1-121"><a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> で管理センターにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="495e1-121">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="495e1-122">左側のナビゲーションで、[**デバイス**ポリシー] を選択し \> **Policies**ます。</span><span class="sxs-lookup"><span data-stu-id="495e1-122">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="495e1-123">既存の Windows デバイスポリシーを選択し、[ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="495e1-123">Choose an existing Windows device policy and then **Edit**.</span></span>
1. <span data-ttu-id="495e1-124">変更する設定の横にある [ **編集** ] を選択してから、 **保存**します。</span><span class="sxs-lookup"><span data-stu-id="495e1-124">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="available-settings"></a><span data-ttu-id="495e1-125">利用可能な設定</span><span class="sxs-lookup"><span data-stu-id="495e1-125">Available settings</span></span>

<span data-ttu-id="495e1-126">既定では、すべての設定が **オン**になっています。</span><span class="sxs-lookup"><span data-stu-id="495e1-126">By default all settings are **On**.</span></span> <span data-ttu-id="495e1-127">次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="495e1-127">The following settings are available.</span></span>
  
<span data-ttu-id="495e1-128">詳細については、「 [Microsoft 365 Premium の保護機能を Intune 設定にマップする方法](map-protection-features-to-intune-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495e1-128">For more information, see [How do protection features in Microsoft 365 Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="495e1-129">Setting</span><span class="sxs-lookup"><span data-stu-id="495e1-129">Setting</span></span>  <br/> |<span data-ttu-id="495e1-130">説明</span><span class="sxs-lookup"><span data-stu-id="495e1-130">Description</span></span>  <br/> |
|<span data-ttu-id="495e1-131">Windows Defender ウイルス対策を使用して PC をウイルスとその他の脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="495e1-131">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="495e1-132">インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="495e1-132">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="495e1-133">Microsoft Edge で PC を Web ベースの脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="495e1-133">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="495e1-134">ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="495e1-134">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="495e1-135">デバイスに対する攻撃を回避するルールを使用する</span><span class="sxs-lookup"><span data-stu-id="495e1-135">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="495e1-p105">オンにすると、攻撃の回避により、デバイス感染のためにマルウェアが通常使用するアクションやアプリをブロックすることができます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[攻撃の回避](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="495e1-p105">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) to learn more.  </span></span><br/> |
|<span data-ttu-id="495e1-139">ランサムウェアなどの脅威からフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="495e1-139">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="495e1-140">この設定は、フォルダーへのアクセスを制御することによって、ランサムウェアなどの不審なまたは悪意のあるアプリケーションによる書き換えから会社のデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="495e1-140">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware.</span></span> <span data-ttu-id="495e1-141">こうした種類のアプリケーションは、保護されているフォルダーで変更を行うことができないようにブロックされます。</span><span class="sxs-lookup"><span data-stu-id="495e1-141">These types of apps are blocked from making changes in protected folders.</span></span> <span data-ttu-id="495e1-142">Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。</span><span class="sxs-lookup"><span data-stu-id="495e1-142">This setting is only available if Windows Defender Antivirus is set to On.</span></span> <span data-ttu-id="495e1-143">詳細については、「 [フォルダーを制限付きフォルダーアクセスで保護](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495e1-143">See [Protect folders with Controlled folder access](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/create-deploy-exploit-guard-policy#bkmk_CFA) to learn more.</span></span>  <br/> |
|<span data-ttu-id="495e1-144">インターネット上の悪意がある可能性のあるコンテンツに対するネットワーク アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="495e1-144">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="495e1-145">この設定を使用して、フィッシング詐欺、悪用、またはその他の悪意のあるコンテンツをホストする可能性がある低評価のインターネット上の場所への送信ユーザー接続をブロックします。</span><span class="sxs-lookup"><span data-stu-id="495e1-145">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits, or other malicious content.</span></span> <span data-ttu-id="495e1-146">この設定は、Windows Defender ウイルス対策が **[オン**] に設定されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="495e1-146">This setting is only available if Windows Defender Antivirus is set to **On**.</span></span> <span data-ttu-id="495e1-147">詳細については、「 [ネットワークを保護する](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495e1-147">For more information, see [Protect your network](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-real-time-protection-windows-defender-antivirus).</span></span>  <br/> |
|<span data-ttu-id="495e1-148">不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する</span><span class="sxs-lookup"><span data-stu-id="495e1-148">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="495e1-149">BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="495e1-149">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="495e1-150">詳細については、「Bitlocker に関する [FAQ](https://go.microsoft.com/fwlink/?linkid=871000)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="495e1-150">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="495e1-151">ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する</span><span class="sxs-lookup"><span data-stu-id="495e1-151">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="495e1-p109">ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン**のままにしていますが、セキュリティを強化するためにオフにすることもできます。  </span><span class="sxs-lookup"><span data-stu-id="495e1-p109">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="495e1-154">ユーザーが Cortana にアクセスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="495e1-154">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="495e1-155">Cortana は非常に役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="495e1-155">Cortana can be very helpful!</span></span> <span data-ttu-id="495e1-156">Cortana では、設定を有効または無効にしたり、案内を表示したり、予定に時間があるかどうかを確認したりすることができます。 **この設定は既定でオンに** しておきます。</span><span class="sxs-lookup"><span data-stu-id="495e1-156">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="495e1-157">ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する</span><span class="sxs-lookup"><span data-stu-id="495e1-157">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="495e1-158">Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="495e1-158">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="495e1-159">Windows 10 デバイスを自動的に最新の状態に維持する</span><span class="sxs-lookup"><span data-stu-id="495e1-159">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="495e1-160">Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="495e1-160">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="495e1-161">この時間アイドル状態になったときにデバイスの画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="495e1-161">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="495e1-p111">ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーは、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりして、デバイスが無作為な視線に対して無防備な状態になってしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。</span><span class="sxs-lookup"><span data-stu-id="495e1-p111">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
