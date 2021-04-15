---
title: Microsoft Defender ウイルス対策が更新プログラムを受信する方法と場所を管理する
description: Microsoft Defender ウイルス対策が保護更新プログラムを受け取る方法のフォールバック順序を管理します。
keywords: 更新プログラム、セキュリティ 基準、保護、フォールバック順序、ADL、MMPC、UNC、ファイル パス、共有、WSUS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9b1c9bc8c86c5b348e3c4d2a51e0bfafaf3e7174
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765469"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a><span data-ttu-id="95cd3-104">Microsoft Defender ウイルス対策の更新プログラムのソースを管理する</span><span class="sxs-lookup"><span data-stu-id="95cd3-104">Manage the sources for Microsoft Defender Antivirus protection updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="95cd3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="95cd3-105">**Applies to:**</span></span>

- [<span data-ttu-id="95cd3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="95cd3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

<span data-ttu-id="95cd3-107">ウイルス対策保護を最新の状態に保つことは重要です。</span><span class="sxs-lookup"><span data-stu-id="95cd3-107">Keeping your antivirus protection up to date is critical.</span></span> <span data-ttu-id="95cd3-108">Microsoft Defender ウイルス対策の保護更新プログラムを管理するには、次の 2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-108">There are two components to managing protection updates for Microsoft Defender Antivirus:</span></span> 
- <span data-ttu-id="95cd3-109">*更新* プログラムのダウンロード先。そして</span><span class="sxs-lookup"><span data-stu-id="95cd3-109">*Where* the updates are downloaded from; and</span></span> 
- <span data-ttu-id="95cd3-110">*更新* プログラムをダウンロードして適用する場合。</span><span class="sxs-lookup"><span data-stu-id="95cd3-110">*When* updates are downloaded and applied.</span></span> 

<span data-ttu-id="95cd3-111">この記事では、更新プログラムをダウンロードする場所を指定する方法について説明します (これはフォールバック順序とも呼ばれています)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-111">This article describes how to specify from where updates should be downloaded (this is also known as the fallback order).</span></span> <span data-ttu-id="95cd3-112">更新 [プログラムの動作の](manage-updates-baselines-microsoft-defender-antivirus.md) 概要、および更新プログラムの他の側面 (更新プログラムのスケジュール設定など) を構成する方法については、「Microsoft Defender ウイルス対策更新プログラムの管理と基準計画の適用」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cd3-112">See [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md) topic for an overview on how updates work, and how to configure other aspects of updates (such as scheduling updates).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95cd3-113">Microsoft Defender ウイルス対策セキュリティ インテリジェンスの更新プログラムは、Windows Update を通じて配信され、2019 年 10 月 21 日月曜日から開始され、すべてのセキュリティ インテリジェンス更新プログラムは SHA-2 専用に署名されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-113">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update and starting Monday, October 21, 2019, all security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="95cd3-114">セキュリティ インテリジェンスを更新するには、SHA-2 をサポートするためにデバイスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-114">Your devices must be updated to support SHA-2 in order to update your security intelligence.</span></span> <span data-ttu-id="95cd3-115">詳細については [、「2019 SHA-2 Code Signing Support requirement for Windows および WSUS」を参照してください](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-115">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>  


<a id="fallback-order"></a>

## <a name="fallback-order"></a><span data-ttu-id="95cd3-116">フォールバック順序</span><span class="sxs-lookup"><span data-stu-id="95cd3-116">Fallback order</span></span>

<span data-ttu-id="95cd3-117">通常、プライマリ ソースから更新プログラムを個別にダウンロードし、その後、ネットワーク構成に基づいて優先度の高い順に他のソースをダウンロードするエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-117">Typically, you configure endpoints to individually download updates from a primary source followed by other sources in order of priority, based on your network configuration.</span></span> <span data-ttu-id="95cd3-118">更新プログラムは、指定した順序でソースから取得されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-118">Updates are obtained from sources in the order you specify.</span></span> <span data-ttu-id="95cd3-119">ソースが使用できない場合は、リスト内の次のソースがすぐに使用されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-119">If a source is not available, the next source in the list is used immediately.</span></span>

<span data-ttu-id="95cd3-120">更新プログラムが発行されると、更新プログラムのサイズを最小限に抑えるためのロジックが適用されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-120">When updates are published, some logic is applied to minimize the size of the update.</span></span> <span data-ttu-id="95cd3-121">ほとんどの場合、最新の更新プログラムと、デバイスに現在インストールされている更新プログラム (デルタと呼ばれます) の違いだけがダウンロードされて適用されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-121">In most cases, only the differences between the latest update and the update that is currently installed (this is referred to as the delta) on the device is downloaded and applied.</span></span> <span data-ttu-id="95cd3-122">ただし、デルタのサイズは、次の 2 つの主な要因に依存します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-122">However, the size of the delta depends on two main factors:</span></span>
- <span data-ttu-id="95cd3-123">デバイスの最後の更新プログラムの年齢。そして</span><span class="sxs-lookup"><span data-stu-id="95cd3-123">The age of the last update on the device; and</span></span> 
- <span data-ttu-id="95cd3-124">更新プログラムのダウンロードと適用に使用されるソース。</span><span class="sxs-lookup"><span data-stu-id="95cd3-124">The source used to download and apply updates.</span></span> 

<span data-ttu-id="95cd3-125">エンドポイントの更新プログラムが古いほど、ダウンロードは大きくなります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-125">The older the updates on an endpoint, the larger the download will be.</span></span> <span data-ttu-id="95cd3-126">ただし、ダウンロード頻度も考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-126">However, you must also consider download frequency as well.</span></span> <span data-ttu-id="95cd3-127">更新スケジュールが頻繁に行われると、ネットワーク使用量が増加しますが、スケジュールが低いほどダウンロードあたりのファイル サイズが大きくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-127">A more frequent update schedule can result in more network usage, whereas a less-frequent schedule can result in larger file sizes per download.</span></span> 

<span data-ttu-id="95cd3-128">エンドポイントが更新プログラムを取得する場所を指定できる場所は 5 種類です。</span><span class="sxs-lookup"><span data-stu-id="95cd3-128">There are five locations where you can specify where an endpoint should obtain updates:</span></span> 

- [<span data-ttu-id="95cd3-129">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="95cd3-129">Microsoft Update</span></span>](https://support.microsoft.com/help/12373/windows-update-faq)
- [<span data-ttu-id="95cd3-130">Windows Server Update Service</span><span class="sxs-lookup"><span data-stu-id="95cd3-130">Windows Server Update Service</span></span>](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [<span data-ttu-id="95cd3-131">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="95cd3-131">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/core/servers/manage/updates)
- [<span data-ttu-id="95cd3-132">ネットワーク ファイル共有</span><span class="sxs-lookup"><span data-stu-id="95cd3-132">Network file share</span></span>](#unc-share)
- <span data-ttu-id="95cd3-133">[Microsoft Defender ウイルス対策および他](https://www.microsoft.com/en-us/wdsi/defenderupdates) の Microsoft マルウェア対策のセキュリティ インテリジェンス更新プログラム (ポリシーとレジストリには、マイクロソフト マルウェア プロテクション センター (MMPC) セキュリティ インテリジェンス (以前の名前) としてリストされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-133">[Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) (Your policy and registry might have this listed as Microsoft Malware Protection Center (MMPC) security intelligence, its former name.)</span></span>

<span data-ttu-id="95cd3-134">Microsoft Update では、最高レベルの保護を確保するために、迅速なリリースが可能になります。つまり、頻繁にダウンロードする頻度が少なめになります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-134">To ensure the best level of protection, Microsoft Update allows for rapid releases, which means smaller downloads on a frequent basis.</span></span> <span data-ttu-id="95cd3-135">Windows Server Update Service、Microsoft Endpoint Configuration Manager、Microsoft セキュリティ インテリジェンス更新プログラムのソースは、更新プログラムの頻度が低い。</span><span class="sxs-lookup"><span data-stu-id="95cd3-135">The Windows Server Update Service, Microsoft Endpoint Configuration Manager, and Microsoft security intelligence updates sources deliver less frequent updates.</span></span> <span data-ttu-id="95cd3-136">したがって、デルタを大きくすると、ダウンロードが大きくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-136">Thus, the delta can be larger, resulting in larger downloads.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="95cd3-137">Windows Server Update Service または Microsoft Update の後に Microsoft [Security](https://www.microsoft.com/security/portal/definitions/adl.aspx) インテリジェンス ページの更新プログラムをフォールバック ソースとして設定した場合、更新プログラムは、現在の更新プログラムが古いと見なされた場合にのみ、セキュリティ インテリジェンス更新プログラムからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-137">If you have set [Microsoft Security intelligence page](https://www.microsoft.com/security/portal/definitions/adl.aspx) updates as a fallback source after Windows Server Update Service or Microsoft Update, updates are only downloaded from security intelligence updates when the current update is considered out-of-date.</span></span> <span data-ttu-id="95cd3-138">(既定では、Windows Server Update Service または Microsoft Update サービスから更新プログラムを適用できない日が 7 日間連続しています)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-138">(By default, this is seven consecutive days of not being able to apply updates from the Windows Server Update Service or Microsoft Update services).</span></span>
> <span data-ttu-id="95cd3-139">ただし、保護が古いとして報告される日数を [設定できます](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-139">You can, however, [set the number of days before protection is reported as out-of-date](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span><p>
> <span data-ttu-id="95cd3-140">2019 年 10 月 21 日月曜日から、セキュリティ インテリジェンス更新プログラムは SHA-2 専用に署名されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-140">Starting Monday, October 21, 2019, security intelligence updates will be SHA-2 signed exclusively.</span></span> <span data-ttu-id="95cd3-141">最新のセキュリティ インテリジェンス更新プログラムを取得するには、SHA-2 をサポートするためにデバイスを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-141">Devices must be updated to support SHA-2 in order to get the latest security intelligence updates.</span></span> <span data-ttu-id="95cd3-142">詳細については [、「2019 SHA-2 Code Signing Support requirement for Windows および WSUS」を参照してください](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-142">To learn more, see [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span>

<span data-ttu-id="95cd3-143">各ソースには、次の表で説明するように、更新プログラムを発行する頻度に加えて、ネットワークの構成方法に依存する一般的なシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-143">Each source has typical scenarios that depend on how your network is configured, in addition to how often they publish updates, as described in the following table:</span></span>

|<span data-ttu-id="95cd3-144">場所</span><span class="sxs-lookup"><span data-stu-id="95cd3-144">Location</span></span> | <span data-ttu-id="95cd3-145">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="95cd3-145">Sample scenario</span></span> |
|---|---|
|<span data-ttu-id="95cd3-146">Windows Server Update Service</span><span class="sxs-lookup"><span data-stu-id="95cd3-146">Windows Server Update Service</span></span> | <span data-ttu-id="95cd3-147">Windows Server Update Service を使用して、ネットワークの更新プログラムを管理しています。</span><span class="sxs-lookup"><span data-stu-id="95cd3-147">You are using Windows Server Update Service to manage updates for your network.</span></span>|
|<span data-ttu-id="95cd3-148">Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="95cd3-148">Microsoft Update</span></span> | <span data-ttu-id="95cd3-149">エンドポイントを Microsoft Update に直接接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-149">You want your endpoints to connect directly to Microsoft Update.</span></span> <span data-ttu-id="95cd3-150">これは、エンタープライズ ネットワークに不定期に接続するエンドポイントや、更新プログラムを管理するために Windows Server Update Service を使用しない場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-150">This can be useful for endpoints that irregularly connect to your enterprise network, or if you do not use Windows Server Update Service to manage your updates.</span></span>|
|<span data-ttu-id="95cd3-151">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="95cd3-151">File share</span></span> | <span data-ttu-id="95cd3-152">インターネットに接続されていないデバイス (VM など) があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-152">You have non-Internet-connected devices (such as VMs).</span></span> <span data-ttu-id="95cd3-153">インターネットに接続された VM ホストを使用して、更新プログラムをネットワーク共有にダウンロードし、そこから VM が更新プログラムを取得できます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-153">You can use your Internet-connected VM host to download the updates to a network share, from which the VMs can obtain the updates.</span></span> <span data-ttu-id="95cd3-154">仮想デスクトップ [インフラストラクチャ (VDI)](deployment-vdi-microsoft-defender-antivirus.md) 環境でファイル共有を使用する方法については、VDI 展開ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cd3-154">See the [VDI deployment guide](deployment-vdi-microsoft-defender-antivirus.md) for how file shares can be used in virtual desktop infrastructure (VDI) environments.</span></span>|
|<span data-ttu-id="95cd3-155">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="95cd3-155">Microsoft Endpoint Manager</span></span> | <span data-ttu-id="95cd3-156">Microsoft Endpoint Manager を使用してエンドポイントを更新しています。</span><span class="sxs-lookup"><span data-stu-id="95cd3-156">You are using Microsoft Endpoint Manager to update your endpoints.</span></span>|
|<span data-ttu-id="95cd3-157">Microsoft Defender ウイルス対策と他の Microsoft マルウェア対策 (以前は MMPC と呼ばば) のセキュリティ インテリジェンス更新プログラム</span><span class="sxs-lookup"><span data-stu-id="95cd3-157">Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware (formerly referred to as MMPC)</span></span> |<span data-ttu-id="95cd3-158">[SHA-2 をサポートするためにデバイスが更新されていないことを確認します](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-158">[Make sure your devices are updated to support SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).</span></span> <span data-ttu-id="95cd3-159">Microsoft Defender ウイルス対策セキュリティ インテリジェンスの更新プログラムは Windows Update を通じて配信され、2019 年 10 月 21 日月曜日からセキュリティ インテリジェンス更新プログラムは SHA-2 によって排他的に署名されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-159">Microsoft Defender Antivirus Security intelligence updates are delivered through Windows Update, and starting Monday October 21, 2019 security intelligence updates will be SHA-2 signed exclusively.</span></span> <br/><span data-ttu-id="95cd3-160">最近の感染による最新の保護更新プログラムをダウンロードするか、VDI 展開用の強力な基本イメージを準備 [するのに役立ちます](deployment-vdi-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-160">Download the latest protection updates because of a recent infection or to help provision a strong, base image for [VDI deployment](deployment-vdi-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="95cd3-161">このオプションは通常、プライマリ ソースではなく、最終的なフォールバック ソースとしてのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-161">This option should generally be used only as a final fallback source, and not the primary source.</span></span> <span data-ttu-id="95cd3-162">指定した日数、Windows Server Update Service または Microsoft Update から更新プログラムをダウンロードできない場合にのみ [使用されます](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-162">It will only be used if updates cannot be downloaded from Windows Server Update Service or Microsoft Update for [a specified number of days](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date).</span></span>|

<span data-ttu-id="95cd3-163">グループ ポリシー、Microsoft Endpoint Configuration Manager、PowerShell コマンドレット、WMI で更新ソースを使用する順序を管理できます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-163">You can manage the order in which update sources are used with Group Policy, Microsoft Endpoint Configuration Manager, PowerShell cmdlets, and WMI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95cd3-164">Windows Server Update Service をダウンロード場所として設定する場合は、場所の指定に使用する管理ツールに関係なく、更新プログラムを承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-164">If you set Windows Server Update Service as a download location, you must approve the updates, regardless of the management tool you use to specify the location.</span></span> <span data-ttu-id="95cd3-165">Windows Server Update Service を使用して自動承認ルールを設定できます。これは、更新プログラムが少なくとも 1 日に 1 回届く場合に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-165">You can set up an automatic approval rule with Windows Server Update Service, which might be useful as updates arrive at least once a day.</span></span> <span data-ttu-id="95cd3-166">詳細については、「スタンドアロン [Windows Server Update Service でのエンドポイント保護更新プログラムの同期」を参照してください](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-166">To learn more, see [synchronize endpoint protection updates in standalone Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

<span data-ttu-id="95cd3-167">この記事の手順では、最初に注文を設定する方法と、注文を有効にしている場合は [ファイル共有] オプションを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-167">The procedures in this article first describe how to set the order, and then how to set up the **File share** option if you have enabled it.</span></span>

## <a name="use-group-policy-to-manage-the-update-location"></a><span data-ttu-id="95cd3-168">グループ ポリシーを使用して更新場所を管理する</span><span class="sxs-lookup"><span data-stu-id="95cd3-168">Use Group Policy to manage the update location</span></span>

1. <span data-ttu-id="95cd3-169">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="95cd3-169">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="95cd3-170">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="95cd3-170">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="95cd3-171">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95cd3-171">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="95cd3-172">署名の更新プログラムを使用して **ツリー> Windows Defender > Windows コンポーネントに展開し、** 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-172">Expand the tree to **Windows components > Windows Defender > Signature updates** and configure the following settings:</span></span>

   1.  <span data-ttu-id="95cd3-173">[セキュリティ インテリジェンス **更新プログラム** をダウンロードするためのソースの順序を定義する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="95cd3-173">Double-click the **Define the order of sources for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   2.  <span data-ttu-id="95cd3-174">次のスクリーンショットに示すように、1 つのパイプで区切られたソースの順序 `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` を入力します。たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95cd3-174">Enter the order of sources, separated by a single pipe, for example: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC`, as shown in the following screenshot.</span></span>

   ![ソースの順序を示すグループ ポリシー設定のスクリーンショット](images/defender/wdav-order-update-sources.png)

   3. <span data-ttu-id="95cd3-176">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95cd3-176">Click **OK**.</span></span> <span data-ttu-id="95cd3-177">これにより、保護更新プログラムのソースの順序が設定されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-177">This will set the order of protection update sources.</span></span>

   4. <span data-ttu-id="95cd3-178">[セキュリティ インテリジェンス更新プログラムをダウンロード **するための** ファイル共有の定義] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="95cd3-178">Double-click the **Define file shares for downloading security intelligence updates** setting and set the option to **Enabled**.</span></span>

   5. <span data-ttu-id="95cd3-179">ファイル共有ソースを入力します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-179">Enter the file share source.</span></span> <span data-ttu-id="95cd3-180">複数のソースがある場合は、使用する順序で各ソースを 1 つのパイプで区切って入力します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-180">If you have multiple sources, enter each source in the order they should be used, separated by a single pipe.</span></span> <span data-ttu-id="95cd3-181">パス [を示す標準の UNC](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) 表記を使用します。たとえば、次のようになります `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` 。</span><span class="sxs-lookup"><span data-stu-id="95cd3-181">Use [standard UNC notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) for denoting the path, for example: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name`.</span></span>  <span data-ttu-id="95cd3-182">パスを入力しない場合、VM が更新プログラムをダウンロードすると、このソースはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-182">If you do not enter any paths, then this source will be skipped when the VM downloads updates.</span></span>

   6. <span data-ttu-id="95cd3-183">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95cd3-183">Click **OK**.</span></span> <span data-ttu-id="95cd3-184">これにより、ソースが参照される場合のファイル共有の順序が [ソースの順序の定義 **... グループ** ポリシー設定で設定されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-184">This will set the order of file shares when that source is referenced in the **Define the order of sources...** group policy setting.</span></span>

> [!NOTE]
> <span data-ttu-id="95cd3-185">Windows 10 バージョン 1703 から 1809 まで、ポリシー パスは Windows コンポーネント **> Microsoft Defender** Antivirus > Signature Updates for Windows 10 バージョン 1903 の場合、ポリシー パスは Windows コンポーネント > Microsoft Defender Antivirus >**セキュリティ** インテリジェンス更新プログラムです。</span><span class="sxs-lookup"><span data-stu-id="95cd3-185">For Windows 10, versions 1703 up to and including 1809, the policy path is **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903, the policy path is **Windows Components > Microsoft Defender Antivirus > Security Intelligence Updates**</span></span>

## <a name="use-configuration-manager-to-manage-the-update-location"></a><span data-ttu-id="95cd3-186">Configuration Manager を使用して更新場所を管理する</span><span class="sxs-lookup"><span data-stu-id="95cd3-186">Use Configuration Manager to manage the update location</span></span>

<span data-ttu-id="95cd3-187">Microsoft Endpoint Manager (現在のブランチ) の構成の詳細については、「Configure Security Intelligence Updates for Endpoint [Protection」](/configmgr/protect/deploy-use/endpoint-definition-updates) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cd3-187">See [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a><span data-ttu-id="95cd3-188">PowerShell コマンドレットを使用して更新場所を管理する</span><span class="sxs-lookup"><span data-stu-id="95cd3-188">Use PowerShell cmdlets to manage the update location</span></span>

<span data-ttu-id="95cd3-189">更新順序を設定するには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-189">Use the following PowerShell cmdlets to set the update order.</span></span>

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
<span data-ttu-id="95cd3-190">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cd3-190">See the following articles for more information:</span></span>
- [<span data-ttu-id="95cd3-191">Set-MpPreference -SignatureFallbackOrder</span><span class="sxs-lookup"><span data-stu-id="95cd3-191">Set-MpPreference -SignatureFallbackOrder</span></span>](/powershell/module/defender/set-mppreference)
- [<span data-ttu-id="95cd3-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span><span class="sxs-lookup"><span data-stu-id="95cd3-192">Set-MpPreference -SignatureDefinitionUpdateFileSharesSource</span></span>](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [<span data-ttu-id="95cd3-193">PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する</span><span class="sxs-lookup"><span data-stu-id="95cd3-193">Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95cd3-194">Defender コマンドレット</span><span class="sxs-lookup"><span data-stu-id="95cd3-194">Defender cmdlets</span></span>](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a><span data-ttu-id="95cd3-195">Windows 管理命令 (WMI) を使用して更新場所を管理する</span><span class="sxs-lookup"><span data-stu-id="95cd3-195">Use Windows Management Instruction (WMI) to manage the update location</span></span>

<span data-ttu-id="95cd3-196">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-196">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

<span data-ttu-id="95cd3-197">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cd3-197">See the following articles for more information:</span></span>
- [<span data-ttu-id="95cd3-198">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="95cd3-198">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a><span data-ttu-id="95cd3-199">モバイル デバイス管理 (MDM) を使用して更新場所を管理する</span><span class="sxs-lookup"><span data-stu-id="95cd3-199">Use Mobile Device Management (MDM) to manage the update location</span></span>

<span data-ttu-id="95cd3-200">MDM [の構成の詳細については、「Policy CSP - Defender/SignatureUpdateFallbackOrder」](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95cd3-200">See [Policy CSP - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) for details on configuring MDM.</span></span>

## <a name="what-if-were-using-a-third-party-vendor"></a><span data-ttu-id="95cd3-201">サードパーティベンダーを使用している場合は、</span><span class="sxs-lookup"><span data-stu-id="95cd3-201">What if we're using a third-party vendor?</span></span>

<span data-ttu-id="95cd3-202">この記事では、Microsoft Defender ウイルス対策の更新プログラムを構成および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-202">This article describes how to configure and manage updates for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="95cd3-203">ただし、サード パーティベンダーは、これらのタスクを実行するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-203">However, third-party vendors can be used to perform these tasks.</span></span> 

<span data-ttu-id="95cd3-204">たとえば、Contoso 社が、Microsoft Defender Antivirus を含むセキュリティ ソリューションを管理するために Fabrikam を採用したとします。</span><span class="sxs-lookup"><span data-stu-id="95cd3-204">For example, suppose that Contoso has hired Fabrikam to manage their security solution, which includes Microsoft Defender Antivirus.</span></span> <span data-ttu-id="95cd3-205">Fabrikam は通常 [、Windows 管理イン](./use-wmi-microsoft-defender-antivirus.md)ストルメンテーション [、PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレット、 [または Windows](./command-line-arguments-microsoft-defender-antivirus.md) コマンド ラインを使用してパッチと更新プログラムを展開します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-205">Fabrikam typically uses [Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md), [PowerShell cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md), or [Windows command-line](./command-line-arguments-microsoft-defender-antivirus.md) to deploy patches and updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="95cd3-206">Microsoft は、Microsoft Defender ウイルス対策を管理するためのサード パーティ製ソリューションをテストしない。</span><span class="sxs-lookup"><span data-stu-id="95cd3-206">Microsoft does not test third-party solutions for managing Microsoft Defender Antivirus.</span></span>

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a><span data-ttu-id="95cd3-207">セキュリティ インテリジェンス更新プログラムの UNC 共有を作成する</span><span class="sxs-lookup"><span data-stu-id="95cd3-207">Create a UNC share for security intelligence updates</span></span>

<span data-ttu-id="95cd3-208">スケジュールされたタスクを使用して MMPC サイトからセキュリティ インテリジェンス更新プログラムをダウンロードするネットワーク ファイル共有 (UNC/マップドライブ) を設定します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-208">Set up a network file share (UNC/mapped drive) to download security intelligence updates from the MMPC site by using a scheduled task.</span></span>

1. <span data-ttu-id="95cd3-209">共有をプロビジョニングして更新プログラムをダウンロードするシステムで、スクリプトを保存するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-209">On the system on which you want to provision the share and download the updates, create a folder to which you will save the script.</span></span>
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. <span data-ttu-id="95cd3-210">署名の更新を保存するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-210">Create the folder to which you will save the signature updates.</span></span>
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. <span data-ttu-id="95cd3-211">PowerShell スクリプトをダウンロードするには、次[の www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4。](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)</span><span class="sxs-lookup"><span data-stu-id="95cd3-211">Download the PowerShell script from [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).</span></span>

4. <span data-ttu-id="95cd3-212">[手動 **ダウンロード] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95cd3-212">Click **Manual Download**.</span></span>

5. <span data-ttu-id="95cd3-213">[生 **の nupkg ファイルをダウンロードする] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="95cd3-213">Click **Download the raw nupkg file**.</span></span>

6. <span data-ttu-id="95cd3-214">ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-214">Extract the file.</span></span>

7. <span data-ttu-id="95cd3-215">ファイルをコピーSignatureDownloadCustomTask.ps1作成したフォルダー C:\Tool\PS-Scripts\ にコピーします。</span><span class="sxs-lookup"><span data-stu-id="95cd3-215">Copy the file SignatureDownloadCustomTask.ps1 to the folder you previously created, C:\Tool\PS-Scripts\ .</span></span>

8. <span data-ttu-id="95cd3-216">コマンド ラインを使用して、スケジュールされたタスクを設定します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-216">Use the command line to set up the scheduled task.</span></span>
    > [!NOTE]
    > <span data-ttu-id="95cd3-217">更新プログラムには、完全とデルタの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-217">There are two types of updates: full and delta.</span></span>
   - <span data-ttu-id="95cd3-218">x64 デルタの場合:</span><span class="sxs-lookup"><span data-stu-id="95cd3-218">For x64 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - <span data-ttu-id="95cd3-219">x64 フルの場合:</span><span class="sxs-lookup"><span data-stu-id="95cd3-219">For x64 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - <span data-ttu-id="95cd3-220">x86 デルタの場合:</span><span class="sxs-lookup"><span data-stu-id="95cd3-220">For x86 delta:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - <span data-ttu-id="95cd3-221">x86 フルの場合:</span><span class="sxs-lookup"><span data-stu-id="95cd3-221">For x86 full:</span></span>

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

    > [!NOTE]
    > <span data-ttu-id="95cd3-222">スケジュールされたタスクが作成されると、[タスク スケジューラ] の [Microsoft\Windows\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="95cd3-222">When the scheduled tasks are created, you can find these in the Task Scheduler under Microsoft\Windows\Windows Defender</span></span>
9. <span data-ttu-id="95cd3-223">各タスクを手動で実行し、次のフォルダーにデータ (mpam-d.exe、mpam-fe.exe、および nis_full.exe) が含まれています (別の場所を選択している可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-223">Run each task manually and verify that you have data (mpam-d.exe, mpam-fe.exe, and nis_full.exe) in the following folders (you might have chosen different locations):</span></span>

   - <span data-ttu-id="95cd3-224">C:\Temp\TempSigs\x86</span><span class="sxs-lookup"><span data-stu-id="95cd3-224">C:\Temp\TempSigs\x86</span></span>
   - <span data-ttu-id="95cd3-225">C:\Temp\TempSigs\x64</span><span class="sxs-lookup"><span data-stu-id="95cd3-225">C:\Temp\TempSigs\x64</span></span>

   <span data-ttu-id="95cd3-226">スケジュールされたタスクが失敗した場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-226">If the scheduled task fails, run the following commands:</span></span>

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86″
    ```
    > [!NOTE]
    > <span data-ttu-id="95cd3-227">問題は、実行ポリシーが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="95cd3-227">Issues could also be due to execution policy.</span></span>
    
10. <span data-ttu-id="95cd3-228">C:\Temp\TempSigs をポイントする共有を作成します (例: \\ server\updates)。</span><span class="sxs-lookup"><span data-stu-id="95cd3-228">Create a share pointing to C:\Temp\TempSigs (e.g. \\server\updates).</span></span>
    > [!NOTE]
    > <span data-ttu-id="95cd3-229">少なくとも、認証されたユーザーには "読み取り" アクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="95cd3-229">At a minimum, authenticated users must have “Read” access.</span></span>
11. <span data-ttu-id="95cd3-230">ポリシー内の共有場所を共有に設定します。</span><span class="sxs-lookup"><span data-stu-id="95cd3-230">Set the share location in the policy to the share.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95cd3-231">パスに x64 (または x86) フォルダーを追加しない。</span><span class="sxs-lookup"><span data-stu-id="95cd3-231">Do not add the x64 (or x86) folder in the path.</span></span> <span data-ttu-id="95cd3-232">このプロセスmpcmdrun.exe自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="95cd3-232">The mpcmdrun.exe process adds it automatically.</span></span>

## <a name="related-articles"></a><span data-ttu-id="95cd3-233">関連記事</span><span class="sxs-lookup"><span data-stu-id="95cd3-233">Related articles</span></span>

- [<span data-ttu-id="95cd3-234">Microsoft Defender ウイルス対策の展開</span><span class="sxs-lookup"><span data-stu-id="95cd3-234">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95cd3-235">Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する</span><span class="sxs-lookup"><span data-stu-id="95cd3-235">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95cd3-236">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="95cd3-236">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95cd3-237">イベントベースの強制的な更新の管理</span><span class="sxs-lookup"><span data-stu-id="95cd3-237">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95cd3-238">モバイル デバイスと VM の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="95cd3-238">Manage updates for mobile devices and VMs</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="95cd3-239">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="95cd3-239">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)