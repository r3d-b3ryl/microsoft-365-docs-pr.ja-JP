---
title: Microsoft Defender ウイルス対策
description: 組み込みのマルウェア対策とウイルス対策の保護機能である Microsoft Defender ウイルス対策を管理、構成、使用する方法について説明します。
keywords: Microsoft Defender ウイルス対策, windows defender, マルウェア対策, scep, システム センター エンドポイント保護, システム センター構成マネージャー, ウイルス, マルウェア, 脅威, 検出, 保護, セキュリティ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323055"
---
# <a name="microsoft-defender-antivirus-in-windows"></a><span data-ttu-id="bd8a5-104">Windows の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="bd8a5-104">Microsoft Defender Antivirus in Windows</span></span>

<span data-ttu-id="bd8a5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="bd8a5-105">**Applies to:**</span></span>

- [<span data-ttu-id="bd8a5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd8a5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bd8a5-107">Microsoft Defender ウイルス対策は、Microsoft Defender for Endpoint の次世代保護の主要コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-107">Microsoft Defender Antivirus is a major component of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bd8a5-108">この保護は、機械学習、ビッグデータ分析、脅威耐性に関する詳細な調査、Microsoft のクラウド インフラストラクチャを組み合わせて、組織内のデバイス (または、エンドポイント) を保護します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-108">This protection brings together machine learning, big-data analysis, in-depth threat resistance research, and the Microsoft cloud infrastructure to protect devices (or endpoints) in your organization.</span></span> <span data-ttu-id="bd8a5-109">Windows Defender ウイルス対策は Windows に組み込まれており、Microsoft Defender for Endpoint と連携して、デバイスとクラウドを保護します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-109">Microsoft Defender Antivirus is built into Windows, and it works with Microsoft Defender for Endpoint to provide protection on your device and in the cloud.</span></span> 

## <a name="compatibility-with-other-antivirus-products"></a><span data-ttu-id="bd8a5-110">他のウイルス対策製品との互換性</span><span class="sxs-lookup"><span data-stu-id="bd8a5-110">Compatibility with other antivirus products</span></span>

<span data-ttu-id="bd8a5-111">デバイスで Microsoft 以外のウイルス対策/マルウェア対策製品を使用している場合は、Microsoft 以外のウイルス対策ソリューションと一緒にパッシブ モードで Microsoft Defender ウイルス対策を実行できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-111">If you're using a non-Microsoft antivirus/antimalware product on your device, you might be able to run Microsoft Defender Antivirus in passive mode alongside the non-Microsoft antivirus solution.</span></span> <span data-ttu-id="bd8a5-112">使用するオペレーティング システムと、デバイスが Defender for Endpoint にオンボードされているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-112">It depends on the operating system used and whether your device is onboarded to Defender for Endpoint.</span></span> <span data-ttu-id="bd8a5-113">詳細については、「[Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-113">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a><span data-ttu-id="bd8a5-114">アクティブ モード、パッシブ モード、および無効モードの比較</span><span class="sxs-lookup"><span data-stu-id="bd8a5-114">Comparing active mode, passive mode, and disabled mode</span></span>

<span data-ttu-id="bd8a5-115">次の表は、Microsoft Defender ウイルス対策がアクティブ モード、パッシブ モード、または無効である場合に期待される内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-115">The following table describes what to expect when Microsoft Defender Antivirus is in active mode, passive mode, or disabled.</span></span>

| <span data-ttu-id="bd8a5-116">モード</span><span class="sxs-lookup"><span data-stu-id="bd8a5-116">Mode</span></span>  | <span data-ttu-id="bd8a5-117">動作</span><span class="sxs-lookup"><span data-stu-id="bd8a5-117">What happens</span></span>  |
|---------|---------|
| <span data-ttu-id="bd8a5-118">アクティブ モード</span><span class="sxs-lookup"><span data-stu-id="bd8a5-118">Active mode</span></span> | <span data-ttu-id="bd8a5-119">アクティブ モードでは、Microsoft Defender ウイルス対策はデバイス上の主要なウイルス対策アプリとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-119">In active mode, Microsoft Defender Antivirus is used as the primary antivirus app on the device.</span></span> <span data-ttu-id="bd8a5-120">ファイルがスキャンされ、脅威が修正され、検出された脅威が組織のセキュリティ レポートと Windows セキュリティ アプリに一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-120">Files are scanned, threats are remediated, and detected threats are listed in your organization's security reports and in your Windows Security app.</span></span> |
| <span data-ttu-id="bd8a5-121">パッシブ モード</span><span class="sxs-lookup"><span data-stu-id="bd8a5-121">Passive mode</span></span> | <span data-ttu-id="bd8a5-122">パッシブ モードでは、Microsoft Defender ウイルス対策はデバイス上の主要なウイルス対策アプリとして使用されません。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-122">In passive mode, Microsoft Defender Antivirus is not used as the primary antivirus app on the device.</span></span> <span data-ttu-id="bd8a5-123">ファイルがスキャンされ、検出された脅威が報告されますが、脅威は Microsoft Defender ウイルス対策によって修正されません。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-123">Files are scanned, and detected threats are reported, but threats are not remediated by Microsoft Defender Antivirus.</span></span>   |
| <span data-ttu-id="bd8a5-124">無効またはアンインストール済み</span><span class="sxs-lookup"><span data-stu-id="bd8a5-124">Disabled or uninstalled</span></span>  | <span data-ttu-id="bd8a5-125">無効にするかアンインストールすると、Microsoft Defender ウイルス対策は使用されません。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-125">When disabled or uninstalled, Microsoft Defender Antivirus is not used.</span></span> <span data-ttu-id="bd8a5-126">ファイルのスキャン、脅威の修復は行われません。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-126">Files are not scanned, and threats are not remediated.</span></span> <span data-ttu-id="bd8a5-127">一般に、Microsoft Defender ウイルス対策を無効にしたりアンインストールしたりすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-127">In general, we do not recommend disabling or uninstalling Microsoft Defender Antivirus.</span></span>  |

<span data-ttu-id="bd8a5-128">詳細については、「[Microsoft Defender ウイルス対策互換性](microsoft-defender-antivirus-compatibility.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-128">To learn more, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a><span data-ttu-id="bd8a5-129">デバイス上の Microsoft Defender ウイルス対策の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="bd8a5-129">Check the state of Microsoft Defender Antivirus on your device</span></span>

<span data-ttu-id="bd8a5-130">デバイス上の Microsoft Defender ウイルス対策の状態を確認する場合は、Windows セキュリティ アプリや Windows PowerShell などのいくつかの方法のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-130">If you want to check the state of Microsoft Defender Antivirus on your device, you can use one of several methods, such as the Windows Security app or Windows PowerShell.</span></span>

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="bd8a5-131">Windows セキュリティ アプリを使用して、Microsoft Defender ウイルス対策の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="bd8a5-131">Use the Windows Security app to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="bd8a5-132">Windows デバイスで、[スタート] メニューを選択し、`Security` の入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-132">On your Windows device, select the Start menu, and begin typing `Security`.</span></span> <span data-ttu-id="bd8a5-133">次に、結果で Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-133">Then open the Windows Security app in the results.</span></span>

2. <span data-ttu-id="bd8a5-134">**[ウイルスと脅威の防止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-134">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="bd8a5-135">**[ウイルスと脅威の防止設定]** で **[設定の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-135">Under **Virus & threat protection settings**, choose **Manage settings**.</span></span>

<span data-ttu-id="bd8a5-136">設定ページにウイルス対策/マルウェア対策ソリューションの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-136">You'll see the name of your antivirus/antimalware solution on the settings page.</span></span>

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a><span data-ttu-id="bd8a5-137">PowerShell を使用して Microsoft Defender ウイルス対策の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="bd8a5-137">Use PowerShell to check status of Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="bd8a5-138">[スタート] メニューを選択し、`PowerShell` の入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-138">Select the Start menu, and begin typing `PowerShell`.</span></span> <span data-ttu-id="bd8a5-139">次に、結果で Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-139">Then open Windows PowerShell in the results.</span></span>

2. <span data-ttu-id="bd8a5-140">種類 `Get-MpComputerStatus`。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-140">Type `Get-MpComputerStatus`.</span></span>

3. <span data-ttu-id="bd8a5-141">結果のリストで、**AMRunningMode** 行を確認します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-141">In the list of results, look at the **AMRunningMode** row.</span></span>

   - <span data-ttu-id="bd8a5-142">**通常** は、Microsoft Defender ウイルス対策がアクティブ モードで実行されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-142">**Normal** means Microsoft Defender Antivirus is running in active mode.</span></span>
   - <span data-ttu-id="bd8a5-143">**パッシブ モード** は、Microsoft Defender ウイルス対策が実行されていることを意味しますが、デバイス上の主要なウイルス対策/マルウェア対策製品ではありません。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-143">**Passive mode** means Microsoft Defender Antivirus running, but is not the primary antivirus/antimalware product on your device.</span></span>
   - <span data-ttu-id="bd8a5-144">**EDR ブロック モード** は、Microsoft Defender ウイルス対策が実行されており、「ブロック モードの EDR」と呼ばれる Microsoft Defender for Endpoint の機能が有効になっていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-144">**EDR Block Mode** means Microsoft Defender Antivirus is running and a capability in Microsoft Defender for Endpoint that is called "EDR in block mode" is enabled.</span></span> <span data-ttu-id="bd8a5-145">(「[ブロック モードのエンドポイントでの検出と対応 (EDR)](edr-in-block-mode.md)」を参照してください。)</span><span class="sxs-lookup"><span data-stu-id="bd8a5-145">(See [Endpoint detection and response (EDR) in block mode](edr-in-block-mode.md).)</span></span>
   - <span data-ttu-id="bd8a5-146">**SxS パッシブ モード** は、Microsoft Defender ウイルス対策が別のウイルス対策/マルウェア対策製品と一緒にパッシブ モードで実行されており、デバイスが Microsoft Defender for Endpoint にオンボードされていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-146">**SxS Passive Mode** means Microsoft Defender Antivirus is running in passive mode alongside another antivirus/antimalware product, and your device is not onboarded to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bd8a5-147">この場合、Microsoft Defender ウイルス対策には限定された定期的なスキャンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-147">In this case, limited periodic scanning is used for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="bd8a5-148">詳細については、「[Microsoft Defender ウイルス対策で限定された定期的なスキャンを使用する](limited-periodic-scanning-microsoft-defender-antivirus.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-148">To learn more, see [Use limited periodic scanning in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="bd8a5-149">Get-MpComputerStatus PowerShell コマンドレットの詳細については、リファレンス記事 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-149">To learn more about the Get-MpComputerStatus PowerShell cmdlet, see the reference article [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).</span></span>

## <a name="get-your-antivirusantimalware-platform-updates"></a><span data-ttu-id="bd8a5-150">ウイルス対策/マルウェア対策プラットフォームの更新プログラムを取得する</span><span class="sxs-lookup"><span data-stu-id="bd8a5-150">Get your antivirus/antimalware platform updates</span></span>

<span data-ttu-id="bd8a5-151">Microsoft Defender ウイルス対策、またはウイルス対策/マルウェア対策ソリューションを最新の状態に保つことが重要です。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-151">It's important to keep Microsoft Defender Antivirus, or any antivirus/antimalware solution, up to date.</span></span> <span data-ttu-id="bd8a5-152">Microsoft は定期的な更新プログラムをリリースして、デバイスが、新しいマルウェアや攻撃手法から保護する最新のテクノロジを備えていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-152">Microsoft releases regular updates to help ensure that your devices have the latest technology to protect against new malware and attack techniques.</span></span> <span data-ttu-id="bd8a5-153">詳細については、「[Microsoft Defender ウイルス対策の更新プログラムの管理とベースラインの適用](manage-updates-baselines-microsoft-defender-antivirus.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd8a5-153">To learn more, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span> 

## <a name="see-also"></a><span data-ttu-id="bd8a5-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="bd8a5-154">See also</span></span>

- [<span data-ttu-id="bd8a5-155">Windows Server 上の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="bd8a5-155">Microsoft Defender Antivirus on Windows Server</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="bd8a5-156">Microsoft Defender ウイルス対策の管理および構成</span><span class="sxs-lookup"><span data-stu-id="bd8a5-156">Microsoft Defender Antivirus management and configuration</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bd8a5-157">Microsoft Defender ウイルス対策を評価する</span><span class="sxs-lookup"><span data-stu-id="bd8a5-157">Evaluate Microsoft Defender Antivirus protection</span></span>](evaluate-microsoft-defender-antivirus.md)
