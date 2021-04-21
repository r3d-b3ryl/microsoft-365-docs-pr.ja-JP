---
title: Microsoft Defender ウイルス対策を使用して望ましくない可能性のあるアプリケーションをブロックする
description: 不要と思われるアプリケーション (PUA) ウイルス対策機能を有効にして、アドウェアなどの不要なソフトウェアをブロックします。
keywords: pua, enable, unwanted software, 望ましくないアプリ, アドウェア, ブラウザー ツールバー, 検出, ブロック, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 808eff2074dfe1573708264590b401f3d38db982
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904012"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="9e867-104">望ましくない可能性のあるアプリケーションの検出とブロック</span><span class="sxs-lookup"><span data-stu-id="9e867-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9e867-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9e867-105">**Applies to:**</span></span>

- [<span data-ttu-id="9e867-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9e867-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="9e867-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9e867-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="9e867-108">望ましくない可能性のあるアプリケーション (PUA) は、コンピューターの動作が遅くなる、予期しない広告を表示する、または最悪の場合は予期しないソフトウェアや望ましくない可能性のある他のソフトウェアをインストールするソフトウェアのカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="9e867-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="9e867-109">PUA はウイルス、マルウェア、その他の種類の脅威とは見なされませんが、エンドポイントのパフォーマンスや使用に悪影響を及ぼすエンドポイントに対してアクションを実行する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9e867-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="9e867-110">PUA *という用語は* 、特定の種類の望ましくない動作が原因で、Microsoft Defender for Endpoint によって評価される、評判の悪いアプリケーションを参照できます。</span><span class="sxs-lookup"><span data-stu-id="9e867-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="9e867-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9e867-111">Here are some examples:</span></span>

- <span data-ttu-id="9e867-112">**広告または** プロモーションを表示する広告ソフトウェア(Web ページに広告を挿入するソフトウェアを含む)。</span><span class="sxs-lookup"><span data-stu-id="9e867-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="9e867-113">**同じエンティティによって** デジタル署名されていない他のソフトウェアのインストールを提供するソフトウェアのバンドル。</span><span class="sxs-lookup"><span data-stu-id="9e867-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="9e867-114">また、PUA と見なす他のソフトウェアをインストールするソフトウェアも提供しています。</span><span class="sxs-lookup"><span data-stu-id="9e867-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="9e867-115">**セキュリティ製品の存在** で動作が異なるソフトウェアを含む、セキュリティ製品による検出を積極的に回避しようとする Evasion ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="9e867-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="9e867-116">セキュリティ機能による特別な注意のためにアプリケーションにラベルを付けするために使用する条件の詳細と条件については、「Microsoft がマルウェアと望ましくない可能性のあるアプリケーションを識別する方法」を [参照してください](/windows/security/threat-protection/intelligence/criteria)。</span><span class="sxs-lookup"><span data-stu-id="9e867-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="9e867-117">望ましくない可能性のあるアプリケーションは、ネットワークが実際のマルウェアに感染するリスクを高め、マルウェア感染を特定しにくくしたり、IT リソースを無駄にしたりします。</span><span class="sxs-lookup"><span data-stu-id="9e867-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="9e867-118">PUA 保護は、Windows 10、Windows Server 2019、および Windows Server 2016 でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9e867-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="9e867-119">Windows 10 (バージョン 2004 以降) では、既定で PUA for Enterprise (E5) デバイスと見なされるアプリがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="9e867-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="9e867-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9e867-120">Microsoft Edge</span></span>

<span data-ttu-id="9e867-121">クロム [ベースの新](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)しい Microsoft Edge は、望ましくない可能性のあるアプリケーションのダウンロードと関連するリソース URL をブロックします。</span><span class="sxs-lookup"><span data-stu-id="9e867-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="9e867-122">この機能は [、Microsoft Defender SmartScreen を介して提供されます](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)。</span><span class="sxs-lookup"><span data-stu-id="9e867-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="9e867-123">クロム ベースの Microsoft Edge で PUA 保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="9e867-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="9e867-124">Microsoft Edge (クロム ベースのバージョン 80.0.361.50) で望ましくない可能性があるアプリケーション保護は既定で無効になっていますが、ブラウザー内から簡単にオンにできます。</span><span class="sxs-lookup"><span data-stu-id="9e867-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="9e867-125">エッジ ブラウザーで省略記号を選択し、[設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9e867-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="9e867-126">[プライバシー **、検索、サービス] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9e867-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="9e867-127">[セキュリティ **] セクションで** 、[望ましくない可能性のあるアプリ **をブロックする] をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="9e867-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="9e867-128">Microsoft Edge (クロムベース) を実行している場合は [、Microsoft Defender SmartScreen](https://demo.smartscreen.msft.net/)デモ ページの 1 つでテストすることで、PUA 保護の URL ブロック機能を安全に確認できます。</span><span class="sxs-lookup"><span data-stu-id="9e867-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="9e867-129">Microsoft Defender SmartScreen で URL をブロックする</span><span class="sxs-lookup"><span data-stu-id="9e867-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="9e867-130">PUA 保護が有効になっているクロム ベースのエッジでは、Microsoft Defender SmartScreen は PUA に関連付けられた URL から保護します。</span><span class="sxs-lookup"><span data-stu-id="9e867-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="9e867-131">セキュリティ管理者 [は、Microsoft](/DeployEdge/configure-microsoft-edge) Edge と Microsoft Defender SmartScreen を組み合わせて PUA に関連付けられた URL からユーザーのグループを保護する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9e867-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="9e867-132">Microsoft Defender SmartScreen [には、PUA](/DeployEdge/microsoft-edge-policies#smartscreen-settings) をブロックするためのグループ ポリシー設定など、いくつかのグループ ポリシー [設定が明示的に用意されています](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)。</span><span class="sxs-lookup"><span data-stu-id="9e867-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="9e867-133">さらに、管理者はグループ ポリシー設定を使用して [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) をオンまたはオフにし、Microsoft Defender SmartScreen 全体を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9e867-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="9e867-134">Microsoft Defender for Endpoint には、Microsoft が管理するデータ セットに基づいて独自のブロックリストが含まれるが、独自の脅威インテリジェンスに基づいてこのリストをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9e867-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="9e867-135">Microsoft Defender for Endpoint ポータル [で](manage-indicators.md) インジケーターを作成および管理する場合、Microsoft Defender SmartScreen は新しい設定を尊重します。</span><span class="sxs-lookup"><span data-stu-id="9e867-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="9e867-136">Microsoft Defender ウイルス対策と PUA 保護</span><span class="sxs-lookup"><span data-stu-id="9e867-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="9e867-137">Microsoft Defender Antivirus の望ましくない可能性のあるアプリケーション (PUA) 保護機能は、ネットワーク内のエンドポイントで PUA を検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="9e867-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="9e867-138">この機能は、Windows 10、Windows Server 2019、および Windows Server 2016 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9e867-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="9e867-139">Microsoft Defender Antivirus は、PUA ファイルと、PUA ファイルのダウンロード、移動、実行、またはインストールを試みる試みをブロックします。</span><span class="sxs-lookup"><span data-stu-id="9e867-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="9e867-140">ブロックされた PUA ファイルは検疫に移動されます。</span><span class="sxs-lookup"><span data-stu-id="9e867-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="9e867-141">エンドポイントで PUA ファイルが検出されると、Microsoft Defender ウイルス対策は、他の脅威検出と同じ形式で[ユーザーに通知](configure-notifications-microsoft-defender-antivirus.md)を送信します (通知が無効になっている場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="9e867-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="9e867-142">通知は、その内容を示 `PUA:` すために前置きされます。</span><span class="sxs-lookup"><span data-stu-id="9e867-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="9e867-143">通知は、Windows セキュリティ アプリ内の通常 [の検疫リストに表示されます](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9e867-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="9e867-144">Microsoft Defender ウイルス対策で PUA 保護を構成する</span><span class="sxs-lookup"><span data-stu-id="9e867-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="9e867-145">[Microsoft Intune、Microsoft Endpoint](/mem/intune/protect/device-protect)Configuration [Manager、グループ](/mem/configmgr/protect/deploy-use/endpoint-protection)ポリシー [](/azure/active-directory-domain-services/manage-group-policy)、または PowerShell コマンドレットを使用して[PUA 保護を有効にできます](/powershell/module/defender/?preserve-view=true&view=win10-ps)。</span><span class="sxs-lookup"><span data-stu-id="9e867-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="9e867-146">また、監査モードで PUA 保護を使用して、望ましくない可能性のあるアプリケーションをブロックせずに検出することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e867-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="9e867-147">検出は Windows イベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="9e867-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="9e867-148">Microsoft Defender for Endpoint のデモ web サイトを demo.wd.microsoft.com [機能が](https://demo.wd.microsoft.com/Page/UrlRep) 動作しているのを確認し、実際に動作しているのを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9e867-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="9e867-149">監査モードでの PUA 保護は、社内のソフトウェア セキュリティ コンプライアンス チェックを実施し、誤検知を回避する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9e867-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="9e867-150">Intune を使用して PUA 保護を構成する</span><span class="sxs-lookup"><span data-stu-id="9e867-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="9e867-151">詳細 [については、「Configure device Restriction settings in Microsoft Intune」](/intune/device-restrictions-configure) および [「Microsoft Defender Antivirus device Restriction settings for Windows 10 in Intune」](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e867-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="9e867-152">Configuration Manager を使用して PUA 保護を構成する</span><span class="sxs-lookup"><span data-stu-id="9e867-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="9e867-153">PUA 保護は、Microsoft エンドポイント マネージャー (現在のブランチ) で既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9e867-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="9e867-154">Microsoft Endpoint Manager (Current Branch) の構成の詳細については、「マルウェア対策ポリシーを作成して展開する方法 [:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) スケジュールされたスキャン設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e867-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="9e867-155">System Center 2012 Configuration Manager の場合は、「Configuration Manager でエンドポイント保護に望ましくない可能性のあるアプリケーション保護ポリシーを展開する方法」 [を参照してください](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)。</span><span class="sxs-lookup"><span data-stu-id="9e867-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="9e867-156">Microsoft Defender ウイルス対策によってブロックされた PUA イベントは、Microsoft エンドポイント構成マネージャーではなく、Windows イベント ビューアーで報告されます。</span><span class="sxs-lookup"><span data-stu-id="9e867-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="9e867-157">グループ ポリシーを使用して PUA 保護を構成する</span><span class="sxs-lookup"><span data-stu-id="9e867-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="9e867-158">[Windows 10 2020 年 10 月更新プログラム (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)用の管理用テンプレート (.admx) をダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="9e867-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="9e867-159">グループ ポリシー管理コンピューターで、グループ ポリシー管理 [コンソールを開きます](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="9e867-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="9e867-160">構成するグループ ポリシー オブジェクトを選択し、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9e867-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="9e867-161">グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9e867-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="9e867-162">ツリーを Windows コンポーネント Microsoft Defender ウイルス **対策**  >  **に展開します**。</span><span class="sxs-lookup"><span data-stu-id="9e867-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="9e867-163">[望ましくない **可能性があるアプリケーションの検出を構成する] をダブルクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9e867-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="9e867-164">[有効 **] を** 選択して PUA 保護を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9e867-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="9e867-165">[**オプション]** で、[**ブロック]** を選択して望ましくない可能性のあるアプリケーションをブロックするか、[監査モード] を選択して環境での設定の動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="9e867-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="9e867-166">[**OK**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9e867-166">Select **OK**.</span></span>

9. <span data-ttu-id="9e867-167">グループ ポリシー オブジェクトは、通常と同じ方法で展開します。</span><span class="sxs-lookup"><span data-stu-id="9e867-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="9e867-168">PowerShell コマンドレットを使用して PUA 保護を構成する</span><span class="sxs-lookup"><span data-stu-id="9e867-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="9e867-169">PUA 保護を有効にするには</span><span class="sxs-lookup"><span data-stu-id="9e867-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="9e867-170">無効になっている場合、このコマンドレットの値 `Enabled` を設定して機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9e867-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="9e867-171">PUA 保護を監査モードに設定するには</span><span class="sxs-lookup"><span data-stu-id="9e867-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="9e867-172">設定は `AuditMode` 、PUA をブロックせずに検出します。</span><span class="sxs-lookup"><span data-stu-id="9e867-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="9e867-173">PUA 保護を無効にするには</span><span class="sxs-lookup"><span data-stu-id="9e867-173">To disable PUA protection</span></span>

<span data-ttu-id="9e867-174">PUA 保護を有効に保つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9e867-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="9e867-175">ただし、次のコマンドレットを使用してオフにできます。</span><span class="sxs-lookup"><span data-stu-id="9e867-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="9e867-176">このコマンドレットの値を設定して `Disabled` 、機能が有効になっている場合は無効にします。</span><span class="sxs-lookup"><span data-stu-id="9e867-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="9e867-177">詳細については [、「PowerShell コマンドレット](use-powershell-cmdlets-microsoft-defender-antivirus.md) を使用して Microsoft Defender ウイルス対策コマンドレットと Defender コマンドレットを構成および実行する」 [を参照してください](/powershell/module/defender/index)。</span><span class="sxs-lookup"><span data-stu-id="9e867-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="9e867-178">PowerShell を使用して PUA イベントを表示する</span><span class="sxs-lookup"><span data-stu-id="9e867-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="9e867-179">PUA イベントは Windows イベント ビューアーで報告されますが、Microsoft エンドポイント マネージャーや Intune では報告されません。</span><span class="sxs-lookup"><span data-stu-id="9e867-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="9e867-180">コマンドレットを使用して `Get-MpThreat` 、Microsoft Defender ウイルス対策が処理した脅威を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="9e867-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="9e867-181">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="9e867-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="9e867-182">PUA 検出に関する電子メール通知を取得する</span><span class="sxs-lookup"><span data-stu-id="9e867-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="9e867-183">電子メール通知を有効にし、PUA 検出に関するメールを受信できます。</span><span class="sxs-lookup"><span data-stu-id="9e867-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="9e867-184">Microsoft Defender [ウイルス対策イベントの表示の詳細](troubleshoot-microsoft-defender-antivirus.md) については、「トラブルシューティング イベントの IDS」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e867-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="9e867-185">PUA イベントは、イベント ID **1160 の下に記録されます**。</span><span class="sxs-lookup"><span data-stu-id="9e867-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="9e867-186">高度な検索を使用して PUA イベントを表示する</span><span class="sxs-lookup"><span data-stu-id="9e867-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="9e867-187">[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)を使用している場合は、高度な検索クエリを使用して PUA イベントを表示できます。</span><span class="sxs-lookup"><span data-stu-id="9e867-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="9e867-188">クエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9e867-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="9e867-189">高度な狩猟の詳細については、「高度な狩猟 [を使用して脅威を事前に検索する」を参照してください](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9e867-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="9e867-190">PUA 保護からファイルを除外する</span><span class="sxs-lookup"><span data-stu-id="9e867-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="9e867-191">PUA 保護によってファイルが誤ってブロックされた場合や、タスクを完了するために PUA の機能が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9e867-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="9e867-192">このような場合、ファイルを除外リストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="9e867-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="9e867-193">詳細については、「ファイル拡張子とフォルダー [の場所に基づいて除外を構成および検証する」を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="9e867-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9e867-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e867-194">See also</span></span>

- [<span data-ttu-id="9e867-195">次世代の保護</span><span class="sxs-lookup"><span data-stu-id="9e867-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9e867-196">行動、ヒューリスティック、リアルタイム保護を構成する</span><span class="sxs-lookup"><span data-stu-id="9e867-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)