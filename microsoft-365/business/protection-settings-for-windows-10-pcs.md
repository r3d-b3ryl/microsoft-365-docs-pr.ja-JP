---
title: Windows 10 の PC のデバイス保護設定を設定する
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: デフォルトおよびその他の設定を Windows 10 デバイスをセキュリティで保護する Microsoft 365 のビジネスで使用できるについて説明します。
ms.openlocfilehash: ebfe5f59e544b67e5a4f2ecd990031e9221ff8e5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868995"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="2cefd-103">Windows 10 の PC のデバイス保護設定を設定する</span><span class="sxs-lookup"><span data-stu-id="2cefd-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="2cefd-104">Windows 10 デバイスをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="2cefd-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="2cefd-105">Microsoft 365 Business で Windows 10 デバイスをセキュリティで保護する方法のビデオを表示します。</span><span class="sxs-lookup"><span data-stu-id="2cefd-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="2cefd-106">グローバル管理者の資格情報を使用して、[Microsoft 365 Business](https://portal.office.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2cefd-106">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="2cefd-107">管理センターの [ **デバイス ポリシー**] カードで、[ **ポリシーの追加**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2cefd-107">in the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="2cefd-109">[ **ポリシーの追加**] ウィンドウで、このポリシーの一意の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2cefd-109">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="2cefd-110">[ **ポリシーの種類**] で、[ **Windows 10 デバイスの構成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2cefd-110">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="2cefd-p101">**セキュリティで保護された Windows の 10 のデバイス**を展開し\>どのようにしたい設定を構成します。詳細については、[利用可能な設定](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cefd-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](protection-settings-for-windows-10-pcs.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="2cefd-113">[ **既定の設定に戻す**] リンクを使用すれば、既定の設定にいつでも戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="2cefd-113">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="2cefd-p102">次に**にこれらの設定が表示されますか?** 既定**のすべてのユーザー**セキュリティ グループの選択の**変更**を使用したくない場合は、これらの設定が表示されますユーザー セキュリティ グループの検索\>**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="2cefd-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="2cefd-117">最後に、[ **完了**] を選択してポリシーを保存し、それをデバイスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2cefd-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="2cefd-118">利用可能な設定</span><span class="sxs-lookup"><span data-stu-id="2cefd-118">Available settings</span></span>

<span data-ttu-id="2cefd-p103">既定では、すべての設定が **オン**になっています。次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2cefd-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="2cefd-121">詳細については、「[Microsoft 365 Business の保護機能を Intune の設定に対応付ける方法](map-protection-features-to-intune-settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2cefd-121">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2cefd-122">設定</span><span class="sxs-lookup"><span data-stu-id="2cefd-122">Setting</span></span>  <br/> |<span data-ttu-id="2cefd-123">説明</span><span class="sxs-lookup"><span data-stu-id="2cefd-123">Description</span></span>  <br/> |
|<span data-ttu-id="2cefd-124">Windows Defender ウイルス対策を使用してウイルスなどの脅威から PC を保護する</span><span class="sxs-lookup"><span data-stu-id="2cefd-124">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="2cefd-125">インターネットに接続されている危険から PC を保護するには、ウイルス対策をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cefd-125">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="2cefd-126">Microsoft Edge で Web ベースの脅威から PC を保護する</span><span class="sxs-lookup"><span data-stu-id="2cefd-126">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="2cefd-127">ユーザーを悪意のあるサイトやダウンロードから保護するために役立つ、Microsoft Edge の設定をオンにします。</span><span class="sxs-lookup"><span data-stu-id="2cefd-127">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="2cefd-128">デバイスに対する攻撃を回避するルールを使用する</span><span class="sxs-lookup"><span data-stu-id="2cefd-128">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="2cefd-p104">オンにすると、攻撃の回避により、デバイス感染のためにマルウェアが通常使用するアクションやアプリをブロックすることができます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[攻撃の回避](https://go.microsoft.com/fwlink/?linkid=870417)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="2cefd-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="2cefd-132">ランサムウェアなどの脅威からフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="2cefd-132">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="2cefd-p105">この設定は、フォルダーへのアクセスを制御することによって、ランサムウェアなどの不審なまたは悪意のあるアプリケーションによる書き換えから会社のデータを保護します。こうした種類のアプリケーションは、保護されているフォルダーで変更を行うことができないようにブロックされます。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[フォルダーへのアクセス制御でフォルダーを保護する](https://go.microsoft.com/fwlink/?linkid=870418)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="2cefd-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="2cefd-137">インターネット上の悪意がある可能性のあるコンテンツに対するネットワーク アクセスを防止する</span><span class="sxs-lookup"><span data-stu-id="2cefd-137">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="2cefd-p106">この設定を使用すると、フィッシング詐欺、攻撃、またはその他の悪意のあるコンテンツをホストしている可能性がある低評価のインターネット上の場所へのユーザーの外部接続をブロックします。Windows Defender ウイルス対策がオンに設定されている場合にのみこの設定を利用できます。詳細については、「[ネットワークを保護する](https://go.microsoft.com/fwlink/?linkid=870419)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="2cefd-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="2cefd-141">不正なアクセスから PC のファイルとフォルダーを保護するために BitLocker を使用する</span><span class="sxs-lookup"><span data-stu-id="2cefd-141">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="2cefd-p107">BitLocker は、コンピューターのハード ドライブを暗号化することによってデータを保護し、コンピューターの紛失や盗難時にデータの漏えいを防ぎます。詳細については、「[Bitlocker についてよく寄せられる質問](https://go.microsoft.com/fwlink/?linkid=871000)」を参照してください。  </span><span class="sxs-lookup"><span data-stu-id="2cefd-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="2cefd-144">ユーザーが Microsoft Storeからアプリをダウンロードすることを許可する</span><span class="sxs-lookup"><span data-stu-id="2cefd-144">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="2cefd-p108">ユーザーが Microsoft Storeからアプリをダウンロードしてインストールできるようにします。アプリにはゲームから生産性向上ツールまであらゆるものが含まれるため、この設定を **オン**のままにしていますが、セキュリティを強化するためにオフにすることもできます。  </span><span class="sxs-lookup"><span data-stu-id="2cefd-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="2cefd-147">ユーザーが Cortana にアクセスすることを許可する</span><span class="sxs-lookup"><span data-stu-id="2cefd-147">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="2cefd-p109">Cortana は非常に役に立つ場合があります。Cortana によって設定をオンまたはオフにしたり、手順を示したり、ユーザーが予定に間に合うようにしたりすることができるため、既定では、Microsoft はこの設定を **オン**にしています。  </span><span class="sxs-lookup"><span data-stu-id="2cefd-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="2cefd-150">ユーザーが Microsoft から Windows のヒントと広告を受け取ることを許可する</span><span class="sxs-lookup"><span data-stu-id="2cefd-150">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="2cefd-151">Windows のヒントは役に立つ場合があり、新機能がリリースされたときにユーザーが適応するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2cefd-151">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="2cefd-152">Windows 10 デバイスを自動的に最新の状態に維持する</span><span class="sxs-lookup"><span data-stu-id="2cefd-152">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="2cefd-153">Windows 10 デバイスが、最新の更新プログラムを自動的に受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="2cefd-153">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="2cefd-154">この時間アイドル状態になったときにデバイスの画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="2cefd-154">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="2cefd-p110">ユーザーがアイドル状態になった場合に、会社のデータが保護されるようにします。ユーザーが、喫茶店などの公共の場所で作業を行っていて、その場から離れたり、一瞬気を取られたりすると、デバイスを無作為な視線に向けて無防備な状態にしてしまう可能性があります。この設定では、画面の電源をオフにする前にユーザーがアイドル状態になる可能性のある時間を管理できます。</span><span class="sxs-lookup"><span data-stu-id="2cefd-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

