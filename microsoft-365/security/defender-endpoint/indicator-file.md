---
title: ファイルのインジケーターを作成する
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュのインジケーターを作成します。
keywords: ファイル、ハッシュ、管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199611"
---
# <a name="create-indicators-for-files"></a><span data-ttu-id="e747c-104">ファイルのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="e747c-104">Create indicators for files</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e747c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e747c-105">**Applies to:**</span></span>
- [<span data-ttu-id="e747c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e747c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e747c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e747c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="e747c-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="e747c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e747c-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="e747c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="e747c-110">悪意のある可能性のあるファイルやマルウェアの疑いを禁止することで、組織での攻撃の伝播をさらに防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="e747c-110">You can prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="e747c-111">悪意のある可能性のあるポータブル実行可能ファイル (PE) ファイルが分かっている場合は、そのファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="e747c-111">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="e747c-112">この操作によって、組織内のコンピューターで読み取り、書き込み、または実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="e747c-112">This operation will prevent it from being read, written, or executed on machines in your organization.</span></span>

<span data-ttu-id="e747c-113">ファイルのインジケーターを作成するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="e747c-113">There are two ways you can create indicators for files:</span></span>
- <span data-ttu-id="e747c-114">設定ページからインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="e747c-114">By creating an indicator through the settings page</span></span>
- <span data-ttu-id="e747c-115">ファイルの詳細ページからインジケーターの追加ボタンを使用してコンテキスト インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="e747c-115">By creating a contextual indicator using the add indicator button from the file details page</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="e747c-116">はじめに</span><span class="sxs-lookup"><span data-stu-id="e747c-116">Before you begin</span></span>
<span data-ttu-id="e747c-117">ファイルのインジケーターを作成する前に、次の前提条件を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e747c-117">It's important to understand the following prerequisites prior to creating indicators for files:</span></span>

- <span data-ttu-id="e747c-118">この機能は、組織でウイルス対策とクラウドベースWindows Defenderが有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e747c-118">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="e747c-119">詳細については、「クラウド提供の保護を通じて Microsoft Defender ウイルス対策で次世代テクノロジを使用する [」を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="e747c-119">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="e747c-120">マルウェア対策クライアントのバージョンは、4.18.1901.x 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e747c-120">The Antimalware client version must be 4.18.1901.x or later.</span></span>
- <span data-ttu-id="e747c-121">Windows 10 バージョン 1703 以降の Windows Server 2016 および 2019 のコンピューターでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e747c-121">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="e747c-122">ファイルのブロックを開始するには、まず [設定] で [ブロック] 機能または [許可 [**]** 機能を有効にする](advanced-features.md)必要があります。</span><span class="sxs-lookup"><span data-stu-id="e747c-122">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
- <span data-ttu-id="e747c-123">この機能は、疑わしいマルウェア (または悪意のある可能性のあるファイル) が Web からダウンロードされるのを防ぐために設計されています。</span><span class="sxs-lookup"><span data-stu-id="e747c-123">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="e747c-124">現在、.exe ファイルや _.dll_ ファイルを含むポータブル実行可能ファイル _(PE) ファイルがサポート_ されています。</span><span class="sxs-lookup"><span data-stu-id="e747c-124">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="e747c-125">対象範囲は時間の長い期間延長されます。</span><span class="sxs-lookup"><span data-stu-id="e747c-125">The coverage will be extended over time.</span></span>

<span data-ttu-id="e747c-126">ネットワーク共有からローカル デバイスに大きなファイルをコピーする場合、特に VPN 接続を使用してパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e747c-126">Performance can be affected if you are copying large files from a network share onto your local device, especially over a VPN connection.</span></span> 

> [!IMPORTANT]
> - <span data-ttu-id="e747c-127">許可またはブロックアクションの前にファイルの分類がデバイスのキャッシュに存在する場合は、ファイルに対して許可またはブロック関数を実行できません。</span><span class="sxs-lookup"><span data-stu-id="e747c-127">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action</span></span> 
> - <span data-ttu-id="e747c-128">信頼できる署名付きファイルは、異なる方法で処理されます。</span><span class="sxs-lookup"><span data-stu-id="e747c-128">Trusted signed files will be treated differently.</span></span> <span data-ttu-id="e747c-129">Defender for Endpoint は、悪意のあるファイルを処理するために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="e747c-129">Defender for Endpoint is optimized to handle malicious files.</span></span> <span data-ttu-id="e747c-130">信頼できる署名付きファイルをブロックしようとすると、パフォーマンスに影響を与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="e747c-130">Trying to block trusted signed files, in some cases, may have performance implications.</span></span>
> - <span data-ttu-id="e747c-131">通常、ファイル ブロックは数分以内に適用されますが、30 分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e747c-131">Typically, file blocks are enforced within a couple of minutes, but can take upwards of 30 minutes.</span></span>
> - <span data-ttu-id="e747c-132">ファイル インジケーター ポリシーが競合している場合は、より安全なポリシーの適用ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e747c-132">If there are conflicting file indicator policies, the enforcement policy of the more secure policy is applied.</span></span> <span data-ttu-id="e747c-133">たとえば、両方のハッシュの種類が同じファイルを定義している場合、SHA-256 ファイル ハッシュ インジケーター ポリシーが MD5 ファイル ハッシュ インジケーター ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e747c-133">For example, a SHA-256 file hash indicator policy takes precedence over an MD5 file hash indicator policy if both hash types define the same file.</span></span>

### <a name="create-an-indicator-for-files-from-the-settings-page"></a><span data-ttu-id="e747c-134">設定ページからファイルのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="e747c-134">Create an indicator for files from the settings page</span></span>

1. <span data-ttu-id="e747c-135">ナビゲーション ウィンドウで、[設定インジケーター]**を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e747c-135">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="e747c-136">[ファイル ハッシュ **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="e747c-136">Select the **File hash** tab.</span></span>

3. <span data-ttu-id="e747c-137">[インジケーター **の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e747c-137">Select **Add indicator**.</span></span>

4. <span data-ttu-id="e747c-138">次の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="e747c-138">Specify the following details:</span></span>
   - <span data-ttu-id="e747c-139">Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。</span><span class="sxs-lookup"><span data-stu-id="e747c-139">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="e747c-140">Action - 実行するアクションを指定し、説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e747c-140">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="e747c-141">Scope - コンピューター グループのスコープを定義します。</span><span class="sxs-lookup"><span data-stu-id="e747c-141">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="e747c-142">[概要] タブで詳細を確認し、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e747c-142">Review the details in the Summary tab, then click **Save**.</span></span>

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a><span data-ttu-id="e747c-143">ファイルの詳細ページからコンテキスト インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="e747c-143">Create a contextual indicator from the file details page</span></span>
<span data-ttu-id="e747c-144">ファイルに対して応答アクションを実行 [する場合のオプションの 1](respond-file-alerts.md) つは、ファイルのインジケーターを追加することです。</span><span class="sxs-lookup"><span data-stu-id="e747c-144">One of the options when taking [response actions on a file](respond-file-alerts.md) is adding an indicator for the file.</span></span> 

<span data-ttu-id="e747c-145">ファイルのインジケーター ハッシュを追加すると、組織内のコンピューターがファイルを実行しようとするたびに、アラートを発生してファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="e747c-145">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a machine in your organization attempts to run it.</span></span>

<span data-ttu-id="e747c-146">インジケーターによって自動的にブロックされたファイルは、ファイルのアクション センターには表示されませんが、アラートはアラート キューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e747c-146">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e747c-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="e747c-147">Related topics</span></span>
- [<span data-ttu-id="e747c-148">インジケーターの作成</span><span class="sxs-lookup"><span data-stu-id="e747c-148">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="e747c-149">IPs と URL/ドメインのインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="e747c-149">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="e747c-150">証明書に基づいてインジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="e747c-150">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="e747c-151">インジケーターの管理</span><span class="sxs-lookup"><span data-stu-id="e747c-151">Manage indicators</span></span>](indicator-manage.md)
