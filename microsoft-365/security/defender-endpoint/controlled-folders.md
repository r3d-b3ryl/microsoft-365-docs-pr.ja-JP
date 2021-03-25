---
title: フォルダー アクセス制御によるファイルの暗号化から重要なフォルダーをランサムウェアから保護する
description: 既定のフォルダー内のファイルは、悪意のあるアプリによって変更されるから保護できます。 ランサムウェアによるファイルの暗号化を防止します。
keywords: フォルダー アクセスの制御, Windows 10, Windows Defender, ランサムウェア, 保護, ファイル, フォルダー
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: ae50d53fbc9bf01d4cd16b939461eecc9ec1a568
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165179"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a><span data-ttu-id="64335-105">フォルダー アクセスを制御して重要なフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="64335-105">Protect important folders with controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64335-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="64335-106">**Applies to:**</span></span>
- [<span data-ttu-id="64335-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="64335-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64335-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64335-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="64335-109">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="64335-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64335-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="64335-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a><span data-ttu-id="64335-111">フォルダー アクセスの制御とは</span><span class="sxs-lookup"><span data-stu-id="64335-111">What is controlled folder access?</span></span>

<span data-ttu-id="64335-112">フォルダー アクセスの制御により、ランサムウェアなどの悪意のあるアプリや脅威から貴重なデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="64335-112">Controlled folder access helps protect your valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="64335-113">フォルダー アクセスの制御により、既知の信頼できるアプリの一覧に対してアプリをチェックすることで、データを保護します。</span><span class="sxs-lookup"><span data-stu-id="64335-113">Controlled folder access protects your data by checking apps against a list of known, trusted apps.</span></span> <span data-ttu-id="64335-114">Windows Server 2019 および Windows 10 クライアントでサポートされている場合、管理フォルダー アクセスは、Windows セキュリティ アプリ、Microsoft Endpoint Configuration Manager、または Intune (管理対象デバイスの場合) を使用して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="64335-114">Supported on Windows Server 2019 and Windows 10 clients, controlled folder access can be turned on using the Windows Security App, Microsoft Endpoint Configuration Manager, or Intune (for managed devices).</span></span> 

> [!NOTE]
> <span data-ttu-id="64335-115">スクリプト エンジンは信頼されていないので、制御された保護されたフォルダーへのアクセスを許可することはできません。</span><span class="sxs-lookup"><span data-stu-id="64335-115">Scripting engines are not trusted and you cannot allow them access to controlled protected folders.</span></span>  <span data-ttu-id="64335-116">たとえば、PowerShell は、証明書とファイルインジケーターで許可されている場合でも、フォルダー アクセスの制御 [によって信頼されません](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)。</span><span class="sxs-lookup"><span data-stu-id="64335-116">For example, PowerShell is not trusted by controlled folder access, even if you allow with [certificate and file indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span> 

<span data-ttu-id="64335-117">フォルダー アクセスの制御は [、Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md)で最適に機能します。これにより、通常のアラート調査シナリオの一環として、フォルダー アクセスの制御イベントとブロックに関する詳細なレポート [が提供されます](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="64335-117">Controlled folder access works best with [Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md), which gives you detailed reporting into controlled folder access events and blocks as part of the usual [alert investigation scenarios](investigate-alerts.md).</span></span>

> [!TIP]
> <span data-ttu-id="64335-118">フォルダー アクセスブロックの制御は、アラート キューにアラートを [生成しない](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="64335-118">Controlled folder access blocks don't generate alerts in the [Alerts queue](alerts-queue.md).</span></span> <span data-ttu-id="64335-119">ただし、高度な検索を使用している間、またはカスタム検出ルール[](investigate-machines.md)を使用して、デバイス[](advanced-hunting-overview.md)タイムライン ビューでフォルダー アクセス ブロックの制御に関する情報[を表示できます](custom-detection-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="64335-119">However, you can view information about controlled folder access blocks in the [device timeline view](investigate-machines.md), while using [advanced hunting](advanced-hunting-overview.md), or with [custom detection rules](custom-detection-rules.md).</span></span>

## <a name="how-does-controlled-folder-access-work"></a><span data-ttu-id="64335-120">フォルダー アクセスの制御方法</span><span class="sxs-lookup"><span data-stu-id="64335-120">How does controlled folder access work?</span></span>

<span data-ttu-id="64335-121">フォルダー アクセスの制御は、信頼できるアプリが保護されたフォルダーにアクセスできるようにすることでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="64335-121">Controlled folder access works by only allowing trusted apps to access protected folders.</span></span> <span data-ttu-id="64335-122">保護されたフォルダーは、フォルダー アクセスの制御が構成されている場合に指定されます。</span><span class="sxs-lookup"><span data-stu-id="64335-122">Protected folders are specified when controlled folder access is configured.</span></span> <span data-ttu-id="64335-123">通常、一般的に使用されるフォルダー (ドキュメント、画像、ダウンロードなど) は、管理フォルダーの一覧に含まれます。</span><span class="sxs-lookup"><span data-stu-id="64335-123">Typically, commonly used folders, such as those used for documents, pictures, downloads, and so on, are included in the list of controlled folders.</span></span> 

<span data-ttu-id="64335-124">フォルダー アクセスの制御は、信頼できるアプリの一覧で機能します。</span><span class="sxs-lookup"><span data-stu-id="64335-124">Controlled folder access works with a list of trusted apps.</span></span> <span data-ttu-id="64335-125">信頼できるソフトウェアの一覧に含まれるアプリは、期待通り動作します。</span><span class="sxs-lookup"><span data-stu-id="64335-125">Apps that are included in the list of trusted software work as expected.</span></span> <span data-ttu-id="64335-126">リストに含まれていないアプリは、保護されたフォルダー内のファイルに変更を加えません。</span><span class="sxs-lookup"><span data-stu-id="64335-126">Apps that are not included in the list are prevented from making any changes to files inside protected folders.</span></span> 

<span data-ttu-id="64335-127">アプリは、その普及率と評判に基づいてリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="64335-127">Apps are added to the list based upon their prevalence and reputation.</span></span> <span data-ttu-id="64335-128">組織全体で非常に普及しているアプリで、悪意のあると見なされる動作を一度も表示したことがないアプリは、信頼できると見なされます。</span><span class="sxs-lookup"><span data-stu-id="64335-128">Apps that are highly prevalent throughout your organization and that have never displayed any behavior deemed malicious are considered trustworthy.</span></span> <span data-ttu-id="64335-129">これらのアプリは自動的にリストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="64335-129">Those apps are added to the list automatically.</span></span>

<span data-ttu-id="64335-130">アプリは、Configuration Manager または Intune を使用して、信頼できるリストに手動で追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="64335-130">Apps can also be added manually to the trusted list by using Configuration Manager or Intune.</span></span> <span data-ttu-id="64335-131">アプリのファイル インジケーター [の追加](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) などの追加アクションは、セキュリティ センター コンソールから実行できます。</span><span class="sxs-lookup"><span data-stu-id="64335-131">Additional actions, such as [adding a file indicator](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) for an app, can be performed from the Security Center Console.</span></span>

## <a name="why-controlled-folder-access-is-important"></a><span data-ttu-id="64335-132">フォルダー アクセスの制御が重要な理由</span><span class="sxs-lookup"><span data-stu-id="64335-132">Why controlled folder access is important</span></span>

<span data-ttu-id="64335-133">フォルダー アクセスの制御は、ドキュメントや情報をランサムウェアから保護する場合に特に役立 [ちます](https://www.microsoft.com/wdsi/threats/ransomware)。</span><span class="sxs-lookup"><span data-stu-id="64335-133">Controlled folder access is especially useful in helping to protect your documents and information from [ransomware](https://www.microsoft.com/wdsi/threats/ransomware).</span></span> <span data-ttu-id="64335-134">ランサムウェア攻撃では、ファイルが暗号化され、人質に保持される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64335-134">In a ransomware attack, your files can get encrypted and held hostage.</span></span> <span data-ttu-id="64335-135">フォルダー アクセスを制御すると、アプリが保護されたフォルダー内のファイルに変更を加えたコンピューターに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="64335-135">With controlled folder access in place, a notification appears on the computer where an app attempted to make changes to a file in a protected folder.</span></span> <span data-ttu-id="64335-136">通知は [、会社の詳細](customize-attack-surface-reduction.md#customize-the-notification) と連絡先情報でカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="64335-136">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span> <span data-ttu-id="64335-137">また、ルールを個別に有効にして、機能が監視する手法をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="64335-137">You can also enable the rules individually to customize what techniques the feature monitors.</span></span>

<span data-ttu-id="64335-138">保護 [されたフォルダーには、](#review-controlled-folder-access-events-in-windows-event-viewer) 一般的なシステム フォルダー (ブート セクターを含む) が含まれます。さらにフォルダー [を追加できます](customize-controlled-folders.md#protect-additional-folders)。</span><span class="sxs-lookup"><span data-stu-id="64335-138">The [protected folders](#review-controlled-folder-access-events-in-windows-event-viewer) include common system folders (including boot sectors), and you can [add more folders](customize-controlled-folders.md#protect-additional-folders).</span></span> <span data-ttu-id="64335-139">アプリが [保護されたフォルダー](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) へのアクセス権を与えるのを許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="64335-139">You can also [allow apps](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) to give them access to the protected folders.</span></span>

<span data-ttu-id="64335-140">監査モードを [使用して](audit-windows-defender.md) 、フォルダー アクセスが有効になっている場合に組織に与える影響を評価できます。</span><span class="sxs-lookup"><span data-stu-id="64335-140">You can use [audit mode](audit-windows-defender.md) to evaluate how controlled folder access would impact your organization if it were enabled.</span></span> <span data-ttu-id="64335-141">また、テスト グラウンド web サイト [Windows Defenderサイト](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com 機能が動作し、動作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="64335-141">You can also visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the feature is working and see how it works.</span></span>

<span data-ttu-id="64335-142">フォルダー アクセスの制御は、次のバージョンの Windows でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="64335-142">Controlled folder access is supported on the following versions of Windows:</span></span>
- <span data-ttu-id="64335-143">[Windows 10 バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降</span><span class="sxs-lookup"><span data-stu-id="64335-143">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) and later</span></span>
- [<span data-ttu-id="64335-144">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="64335-144">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a><span data-ttu-id="64335-145">Windows システム フォルダーは既定で保護されています</span><span class="sxs-lookup"><span data-stu-id="64335-145">Windows system folders are protected by default</span></span>

<span data-ttu-id="64335-146">Windows システム フォルダーは、他のいくつかのフォルダーと共に、既定で保護されます。</span><span class="sxs-lookup"><span data-stu-id="64335-146">Windows system folders are protected by default, along with several other folders:</span></span> 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> <span data-ttu-id="64335-147">追加のフォルダーを保護として構成できますが、既定で保護されている Windows システム フォルダーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="64335-147">You can configure additional folders as protected, but you cannot remove the Windows system folders that are protected by default.</span></span>

## <a name="requirements-for-controlled-folder-access"></a><span data-ttu-id="64335-148">フォルダー アクセスの制御の要件</span><span class="sxs-lookup"><span data-stu-id="64335-148">Requirements for controlled folder access</span></span>

<span data-ttu-id="64335-149">フォルダー アクセスの制御には [、Microsoft Defender ウイルス対策のリアルタイム保護を有効にする必要があります](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="64335-149">Controlled folder access requires enabling [Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="64335-150">Microsoft Defender セキュリティ センターでフォルダー アクセスの制御イベントを確認する</span><span class="sxs-lookup"><span data-stu-id="64335-150">Review controlled folder access events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="64335-151">Defender for Endpoint は、アラート調査シナリオの一環として、イベントとブロックに関する詳細 [なレポートを提供します](investigate-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="64335-151">Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="64335-152">高度な検索を使用して、Microsoft Defender for Endpoint データ [を照会できます](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="64335-152">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="64335-153">監査モード[を使用している](audit-windows-defender.md)場合は、高度な検索[](advanced-hunting-overview.md)を使用して、フォルダー アクセスの制御設定が有効になっている場合に環境に与える影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="64335-153">If you're using [audit mode](audit-windows-defender.md), you can use [advanced hunting](advanced-hunting-overview.md) to see how controlled folder access settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="64335-154">クエリ例:</span><span class="sxs-lookup"><span data-stu-id="64335-154">Example query:</span></span>

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a><span data-ttu-id="64335-155">Windows イベント ビューアーでフォルダー アクセスの制御イベントを確認する</span><span class="sxs-lookup"><span data-stu-id="64335-155">Review controlled folder access events in Windows Event Viewer</span></span>

<span data-ttu-id="64335-156">Windows イベント ログを確認して、コントロールされたフォルダー アクセス ブロック (または監査) アプリで作成されるイベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="64335-156">You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:</span></span>

1. <span data-ttu-id="64335-157">評価パッケージ [をダウンロードし](https://aka.ms/mp7z2w) 、デバイス上 *cfa-events.xmlアクセスしやすい* 場所にファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="64335-157">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="64335-158">[ **スタート] メニューに** 「イベント ビューアー」と入力して、Windows イベント ビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="64335-158">Type **Event viewer** in the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="64335-159">左側のパネルの [アクション] **で、[** カスタム ビュー **のインポート... を選択します**。</span><span class="sxs-lookup"><span data-stu-id="64335-159">On the left panel, under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="64335-160">抽出した場所に *移動cfa-events.xml選択* します。</span><span class="sxs-lookup"><span data-stu-id="64335-160">Navigate to where you extracted *cfa-events.xml* and select it.</span></span> <span data-ttu-id="64335-161">または [、XML を直接コピーします](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="64335-161">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="64335-162">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64335-162">Select **OK**.</span></span>

<span data-ttu-id="64335-163">次の表に、フォルダー アクセスの制御に関連するイベントを示します。</span><span class="sxs-lookup"><span data-stu-id="64335-163">The following table shows events related to controlled folder access:</span></span>

|<span data-ttu-id="64335-164">イベント ID</span><span class="sxs-lookup"><span data-stu-id="64335-164">Event ID</span></span> | <span data-ttu-id="64335-165">説明</span><span class="sxs-lookup"><span data-stu-id="64335-165">Description</span></span> |
|:---|:---|
|<span data-ttu-id="64335-166">5007</span><span class="sxs-lookup"><span data-stu-id="64335-166">5007</span></span> | <span data-ttu-id="64335-167">設定が変更された場合のイベント</span><span class="sxs-lookup"><span data-stu-id="64335-167">Event when settings are changed</span></span> |
|<span data-ttu-id="64335-168">1124</span><span class="sxs-lookup"><span data-stu-id="64335-168">1124</span></span> | <span data-ttu-id="64335-169">監査されたフォルダー アクセス イベント</span><span class="sxs-lookup"><span data-stu-id="64335-169">Audited controlled folder access event</span></span> | 
|<span data-ttu-id="64335-170">1123</span><span class="sxs-lookup"><span data-stu-id="64335-170">1123</span></span> | <span data-ttu-id="64335-171">ブロックされたフォルダー アクセス イベント</span><span class="sxs-lookup"><span data-stu-id="64335-171">Blocked controlled folder access event</span></span> |

## <a name="view-or-change-the-list-of-protected-folders"></a><span data-ttu-id="64335-172">保護されたフォルダーの一覧を表示または変更する</span><span class="sxs-lookup"><span data-stu-id="64335-172">View or change the list of protected folders</span></span>

<span data-ttu-id="64335-173">Windows セキュリティ アプリを使用して、フォルダー アクセスの制御によって保護されているフォルダーの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="64335-173">You can use the Windows Security app to view the list of folders that are protected by controlled folder access.</span></span> 

1. <span data-ttu-id="64335-174">Windows 10 デバイスで、Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="64335-174">On your Windows 10 device, open the Windows Security app.</span></span>
2. <span data-ttu-id="64335-175">[ **ウイルス対策&を選択します**。</span><span class="sxs-lookup"><span data-stu-id="64335-175">Select **Virus & threat protection**.</span></span>
3. <span data-ttu-id="64335-176">[ **ランサムウェア保護] で、[** ランサムウェア **保護の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="64335-176">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>
4. <span data-ttu-id="64335-177">フォルダー アクセスの制御がオフになっている場合は、有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64335-177">If controlled folder access is turned off, you'll need to turn it on.</span></span> <span data-ttu-id="64335-178">保護 **されたフォルダーを選択します**。</span><span class="sxs-lookup"><span data-stu-id="64335-178">Select **protected folders**.</span></span>
5. <span data-ttu-id="64335-179">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="64335-179">Do one of the following steps:</span></span>
   - <span data-ttu-id="64335-180">フォルダーを追加するには、[+ 保護 **されたフォルダーの追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="64335-180">To add a folder, select **+ Add a protected folder**.</span></span>
   - <span data-ttu-id="64335-181">フォルダーを削除するには、フォルダーを選択し、[削除] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="64335-181">To remove a folder, select it, and then select **Remove**.</span></span> 

> [!NOTE]
> <span data-ttu-id="64335-182">[Windows システム フォルダーは](#windows-system-folders-are-protected-by-default) 既定で保護され、一覧から削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="64335-182">[Windows system folders](#windows-system-folders-are-protected-by-default) are protected by default, and you cannot remove them from the list.</span></span>

## <a name="see-also"></a><span data-ttu-id="64335-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="64335-183">See also</span></span>

- [<span data-ttu-id="64335-184">フォルダー アクセスの制御を評価する</span><span class="sxs-lookup"><span data-stu-id="64335-184">Evaluate controlled folder access</span></span>](evaluate-controlled-folder-access.md)
- [<span data-ttu-id="64335-185">フォルダー アクセスの制御をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="64335-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
- [<span data-ttu-id="64335-186">より多くのフォルダーを保護する</span><span class="sxs-lookup"><span data-stu-id="64335-186">Protect more folders</span></span>](customize-controlled-folders.md#protect-additional-folders)
