---
title: Microsoft Defender Antivirus によるモバイル デバイスの更新方法を定義する
description: Microsoft Defender ウイルス対策保護の更新プログラムを使用して、ラップトップなどのモバイル デバイスを更新する方法を管理します。
keywords: 更新プログラム、保護、スケジュールの更新、バッテリー、モバイル デバイス、ノート PC、ノートブック、オプトイン、microsoft update、wsus、override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 143b0cb4bac1d3307e440f98fa4278f38e07c7f2
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269542"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="f7c87-104">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="f7c87-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f7c87-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f7c87-105">**Applies to:**</span></span>

- [<span data-ttu-id="f7c87-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f7c87-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f7c87-107">モバイル デバイスと VM では、更新プログラムによるパフォーマンスの影響を受けずに、より多くの構成が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7c87-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="f7c87-108">これらのデバイスに役立つ 2 つの設定があります。</span><span class="sxs-lookup"><span data-stu-id="f7c87-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="f7c87-109">WSUS 接続のないモバイル コンピューターで Microsoft Update にオプトインする</span><span class="sxs-lookup"><span data-stu-id="f7c87-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="f7c87-110">バッテリーの電源で実行するときにセキュリティ インテリジェンスの更新を防止する</span><span class="sxs-lookup"><span data-stu-id="f7c87-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="f7c87-111">次の記事は、次の状況でも役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7c87-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="f7c87-112">スケジュールされたスキャンとキャッチアップ スキャンの構成</span><span class="sxs-lookup"><span data-stu-id="f7c87-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f7c87-113">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="f7c87-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f7c87-114">仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド</span><span class="sxs-lookup"><span data-stu-id="f7c87-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="f7c87-115">WSUS 接続のないモバイル コンピューターで Microsoft Update にオプトインする</span><span class="sxs-lookup"><span data-stu-id="f7c87-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="f7c87-116">Microsoft Update を使用すると、Microsoft Defender ウイルス対策を実行しているモバイル デバイスが企業ネットワークに接続されていない場合や、WSUS 接続がない場合にセキュリティ インテリジェンスを最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7c87-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="f7c87-117">つまり、Microsoft Update を上書きする WSUS を設定している場合でも、保護更新プログラムを (Microsoft Update 経由で) デバイスに配信できます。</span><span class="sxs-lookup"><span data-stu-id="f7c87-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="f7c87-118">モバイル デバイスで Microsoft Update をオプトインするには、次のいずれかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f7c87-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="f7c87-119">グループ ポリシーで設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="f7c87-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="f7c87-120">VBScript を使用してスクリプトを作成し、ネットワーク内の各コンピューターで実行します。</span><span class="sxs-lookup"><span data-stu-id="f7c87-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="f7c87-121">[設定] メニューを使用して、ネットワーク上のすべてのコンピューターを手動 **でオプトイン** します。</span><span class="sxs-lookup"><span data-stu-id="f7c87-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="f7c87-122">グループ ポリシーを使用して Microsoft Update にオプトインする</span><span class="sxs-lookup"><span data-stu-id="f7c87-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="f7c87-123">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="f7c87-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="f7c87-124">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f7c87-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="f7c87-125">[ポリシー **] を選択し** 、[ **管理用テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f7c87-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="f7c87-126">ツリーを Windows コンポーネント **の Microsoft** Defender ウイルス対策  >  **署名更新プログラム**  >  **に展開します**。</span><span class="sxs-lookup"><span data-stu-id="f7c87-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="f7c87-127">[Microsoft **Update からのセキュリティ インテリジェンス更新プログラムを許可** する] を **[有効] に設定** し  **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f7c87-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="f7c87-128">VBScript を使用して Microsoft Update にオプトインする</span><span class="sxs-lookup"><span data-stu-id="f7c87-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="f7c87-129">MSDN の記事 [「Opt-In to Microsoft Update」](/windows/win32/wua_sdk/opt-in-to-microsoft-update) の手順を使用して、VBScript を作成します。</span><span class="sxs-lookup"><span data-stu-id="f7c87-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="f7c87-130">ネットワーク内の各コンピューターで作成した VBScript を実行します。</span><span class="sxs-lookup"><span data-stu-id="f7c87-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="f7c87-131">Microsoft Update に手動でオプトインする</span><span class="sxs-lookup"><span data-stu-id="f7c87-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="f7c87-132">[ **更新プログラム] で** **Windows Update &する** コンピューターのセキュリティ設定を開きます。</span><span class="sxs-lookup"><span data-stu-id="f7c87-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="f7c87-133">[詳細設定 **] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="f7c87-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="f7c87-134">[Windows の更新時に他の Microsoft 製品の更新 **プログラムを提供する] のチェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="f7c87-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="f7c87-135">バッテリーの電源で実行するときにセキュリティ インテリジェンスの更新を防止する</span><span class="sxs-lookup"><span data-stu-id="f7c87-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="f7c87-136">Pc が有線電源に接続されている場合にのみ保護更新プログラムをダウンロードする Microsoft Defender ウイルス対策を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f7c87-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="f7c87-137">グループ ポリシーを使用してバッテリーの電源に関するセキュリティ インテリジェンスの更新を防止する</span><span class="sxs-lookup"><span data-stu-id="f7c87-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="f7c87-138">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを選択し、編集用に開きます。</span><span class="sxs-lookup"><span data-stu-id="f7c87-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="f7c87-139">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f7c87-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="f7c87-140">[ポリシー **] を選択し** 、[ **管理用テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f7c87-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="f7c87-141">ツリーを Windows コンポーネント **の Microsoft** Defender ウイルス対策署名更新プログラムに展開し、[バッテリ電源で実行する場合にセキュリティ インテリジェンス更新プログラムを許可する] を [無効]  >    >  に **設定します**。 </span><span class="sxs-lookup"><span data-stu-id="f7c87-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="f7c87-142">次に **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7c87-142">Then select **OK**.</span></span> 

<span data-ttu-id="f7c87-143">この操作により、PC がバッテリ電源をオンにしている場合に保護更新プログラムがダウンロードされなかから保護されます。</span><span class="sxs-lookup"><span data-stu-id="f7c87-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f7c87-144">関連記事</span><span class="sxs-lookup"><span data-stu-id="f7c87-144">Related articles</span></span>

- [<span data-ttu-id="f7c87-145">Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する</span><span class="sxs-lookup"><span data-stu-id="f7c87-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f7c87-146">Windows 10 で Microsoft Defender ウイルス対策を更新および管理する</span><span class="sxs-lookup"><span data-stu-id="f7c87-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)