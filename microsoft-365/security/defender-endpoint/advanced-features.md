---
title: Microsoft Defender for Endpoint の高度な機能を構成する
description: Microsoft Defender for Endpoint のブロック ファイルなどの高度な機能を有効にする。
keywords: 高度な機能、設定、ファイルのブロック、自動調査、自動解決、skype、id の microsoft Defender、Office 365、Azure 情報保護、intune
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
ms.openlocfilehash: ed6f6b42570a908a1f4a83d46ef5b2de0c558692
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199743"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="d9a05-104">Defender for Endpoint で高度な機能を構成する</span><span class="sxs-lookup"><span data-stu-id="d9a05-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="d9a05-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d9a05-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9a05-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9a05-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d9a05-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9a05-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="d9a05-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d9a05-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d9a05-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="d9a05-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="d9a05-110">使用する Microsoft セキュリティ製品によっては、Defender for Endpoint を統合できる高度な機能がいくつか用意されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="d9a05-111">高度な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="d9a05-111">Enable advanced features</span></span>

1. <span data-ttu-id="d9a05-112">ナビゲーション ウィンドウで、[基本設定]**セットアップの [高度な**  >  **機能] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9a05-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="d9a05-113">構成する高度な機能を選択し、設定を [オン] と [オフ] **の間で切り** 替 **えます**。</span><span class="sxs-lookup"><span data-stu-id="d9a05-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="d9a05-114">[設定 **の保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d9a05-114">Click **Save preferences**.</span></span>

<span data-ttu-id="d9a05-115">次の高度な機能を使用して、潜在的に悪意のあるファイルから保護され、セキュリティ調査中により良い洞察を得る。</span><span class="sxs-lookup"><span data-stu-id="d9a05-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="d9a05-116">自動調査</span><span class="sxs-lookup"><span data-stu-id="d9a05-116">Automated investigation</span></span>

<span data-ttu-id="d9a05-117">この機能を有効にし、サービスの自動調査および修復機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="d9a05-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="d9a05-118">詳細については、「自動調査 [」を参照してください](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="d9a05-119">ライブ応答</span><span class="sxs-lookup"><span data-stu-id="d9a05-119">Live response</span></span>

<span data-ttu-id="d9a05-120">適切なアクセス許可を持つユーザーがデバイスでライブ応答セッションを開始できるよう、この機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d9a05-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="d9a05-121">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="d9a05-122">サーバーのライブ応答</span><span class="sxs-lookup"><span data-stu-id="d9a05-122">Live response for servers</span></span>
<span data-ttu-id="d9a05-123">この機能を有効にし、適切なアクセス許可を持つユーザーがサーバーでライブ応答セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="d9a05-124">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="d9a05-125">ライブ応答の署名されていないスクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="d9a05-125">Live response unsigned script execution</span></span>

<span data-ttu-id="d9a05-126">この機能を有効にすると、ライブ応答セッションで署名されていないスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="d9a05-127">Autoresolve 修復されたアラート</span><span class="sxs-lookup"><span data-stu-id="d9a05-127">Autoresolve remediated alerts</span></span>

<span data-ttu-id="d9a05-128">Windows 10 バージョン 1809 以降に作成されたテナントの場合、自動分析結果の状態が "脅威が見つかりません" または "修復済み" であるアラートを解決するように、自動調査と修復機能が既定で構成されています。</span><span class="sxs-lookup"><span data-stu-id="d9a05-128">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="d9a05-129">アラートを自動解決したくない場合は、手動で機能をオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-129">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="d9a05-130">そのバージョンより前に作成されたテナントの場合は、[高度な機能] ページからこの機能を手動で [有効にする必要](https://securitycenter.windows.com/preferences2/integration) があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-130">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d9a05-131">自動解決アクションの結果は、デバイスで検出されたアクティブなアラートに基づくデバイス リスク レベルの計算に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-131">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="d9a05-132">セキュリティ運用アナリストが手動でアラートの状態を "進行中" または "解決済み" に設定した場合、自動解決機能は上書きされません。</span><span class="sxs-lookup"><span data-stu-id="d9a05-132">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="d9a05-133">ファイルを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="d9a05-133">Allow or block file</span></span>

<span data-ttu-id="d9a05-134">ブロックは、組織が次の要件を満たしている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-134">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="d9a05-135">アクティブなマルウェア対策ソリューションとして Microsoft Defender ウイルス対策を使用し、</span><span class="sxs-lookup"><span data-stu-id="d9a05-135">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="d9a05-136">クラウドベースの保護機能が有効になっている</span><span class="sxs-lookup"><span data-stu-id="d9a05-136">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="d9a05-137">この機能を使用すると、ネットワーク内の悪意のある可能性のあるファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-137">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="d9a05-138">ファイルをブロックすると、組織内のデバイスでファイルが読み取り、書き込み、または実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="d9a05-138">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="d9a05-139">ファイルを **許可またはブロックするには** 、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d9a05-139">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="d9a05-140">ナビゲーション ウィンドウで、[設定の詳細設定]**機能**  >  **[ファイルの**  >  **許可またはブロック] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d9a05-140">In the navigation pane, select **Settings** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="d9a05-141">[オン] と [オフ]**の間で設定を\*\*\*\*切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="d9a05-141">Toggle the setting between **On** and **Off**.</span></span>

    ![ブロック ファイル機能の詳細設定のイメージ](images/atp-preferences-setup.png)

1. <span data-ttu-id="d9a05-143">ページ **の下部にある [基本** 設定の保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9a05-143">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="d9a05-144">この機能を有効にした後、[](respond-file-alerts.md#allow-or-block-file)ファイルのプロファイルページの [インジケーターの追加] タブを使用してファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-144">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="d9a05-145">カスタム ネットワーク インジケーター</span><span class="sxs-lookup"><span data-stu-id="d9a05-145">Custom network indicators</span></span>

<span data-ttu-id="d9a05-146">この機能を有効にすることで、IP アドレス、ドメイン、または URL のインジケーターを作成し、カスタム インジケーター リストに基づいて許可またはブロックするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-146">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="d9a05-147">この機能を使用するには、デバイスで Windows 10 バージョン 1709 以降を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-147">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="d9a05-148">また、ブロック モードでネットワーク保護を行い、マルウェア対策プラットフォームのバージョン 4.18.1906.3 以降は [KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a05-148">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="d9a05-149">詳細については、「指標の管理 [」を参照してください](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-149">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d9a05-150">ネットワーク保護は、Defender for Endpoint データで選択した場所の外部にある可能性がある場所で要求を処理する評判サービスを活用します。</span><span class="sxs-lookup"><span data-stu-id="d9a05-150">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="show-user-details"></a><span data-ttu-id="d9a05-151">ユーザーの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="d9a05-151">Show user details</span></span>

<span data-ttu-id="d9a05-152">この機能を有効にし、Azure Active Directory に格納されているユーザーの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-152">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="d9a05-153">詳細には、ユーザー アカウント エンティティを調査する際のユーザーの画像、名前、タイトル、および部署情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-153">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="d9a05-154">ユーザー アカウント情報は、次のビューで確認できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-154">You can find user account information in the following views:</span></span>

- <span data-ttu-id="d9a05-155">セキュリティ運用ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="d9a05-155">Security operations dashboard</span></span>
- <span data-ttu-id="d9a05-156">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="d9a05-156">Alert queue</span></span>
- <span data-ttu-id="d9a05-157">[デバイスの詳細] ページ</span><span class="sxs-lookup"><span data-stu-id="d9a05-157">Device details page</span></span>

<span data-ttu-id="d9a05-158">詳細については、「ユーザー アカウントの [調査」を参照してください](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-158">For more information, see [Investigate a user account](investigate-user.md).</span></span>

## <a name="skype-for-business-integration"></a><span data-ttu-id="d9a05-159">Skype for Business 統合</span><span class="sxs-lookup"><span data-stu-id="d9a05-159">Skype for Business integration</span></span>

<span data-ttu-id="d9a05-160">Skype for Business 統合を有効にすると、Skype for Business、電子メール、または電話を使用してユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-160">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="d9a05-161">これは、ユーザーと通信し、リスクを軽減する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="d9a05-161">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a05-162">デバイスがネットワークから分離されている場合、ユーザーがネットワークから切断されている間にユーザーに通信できる Outlook と Skype の通信を有効にできるポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-162">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="d9a05-163">この設定は、デバイスが分離モードの場合に Skype と Outlook の通信に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-163">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="azure-advanced-threat-protection-integration"></a><span data-ttu-id="d9a05-164">Azure Advanced Threat Protection の統合</span><span class="sxs-lookup"><span data-stu-id="d9a05-164">Azure Advanced Threat Protection integration</span></span>

<span data-ttu-id="d9a05-165">Azure Advanced Threat Protection との統合により、別の Microsoft Identity セキュリティ製品に直接ピボットできます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-165">The integration with Azure Advanced Threat Protection allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="d9a05-166">Azure Advanced Threat Protection は、侵害された疑いのあるアカウントと関連リソースに関する追加の分析情報を使用して調査を強化します。</span><span class="sxs-lookup"><span data-stu-id="d9a05-166">Azure Advanced Threat Protection augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="d9a05-167">この機能を有効にすると、識別の観点からネットワーク全体をピボットすることで、デバイスベースの調査機能を強化できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-167">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a05-168">この機能を有効にするには、適切なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d9a05-168">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="d9a05-169">Office 365 脅威インテリジェンス接続</span><span class="sxs-lookup"><span data-stu-id="d9a05-169">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="d9a05-170">この機能は、アクティブな 365 E5 Office脅威インテリジェンス アドオンがある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-170">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="d9a05-171">詳細については、「365 Enterprise E5 Office」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a05-171">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="d9a05-172">この機能を有効にした場合、Office 365 Advanced Threat Protection のデータを Microsoft Defender セキュリティ センターに組み込み、Office 365 メールボックスと Windows デバイス全体で包括的なセキュリティ調査を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-172">When you turn this feature on, you'll be able to incorporate data from Office 365 Advanced Threat Protection into Microsoft Defender Security Center to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a05-173">この機能を有効にするには、適切なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="d9a05-173">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="d9a05-174">Office 365 脅威インテリジェンスでコンテキスト デバイスの統合を受け取る場合は、[セキュリティ とコンプライアンス] ダッシュボードで Defender for Endpoint &する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-174">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="d9a05-175">詳細については、「脅威の調査 [と対応」を参照してください](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-175">For more information, see [Threat investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts"></a><span data-ttu-id="d9a05-176">Microsoft 脅威エキスパート</span><span class="sxs-lookup"><span data-stu-id="d9a05-176">Microsoft Threat Experts</span></span>

<span data-ttu-id="d9a05-177">2 つの Microsoft Threat Expert コンポーネントの中で、標的型攻撃通知は一般提供です。</span><span class="sxs-lookup"><span data-stu-id="d9a05-177">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="d9a05-178">エキスパートオンデマンド機能はまだプレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="d9a05-178">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="d9a05-179">experts-on-demand 機能は、プレビューを申請し、アプリケーションが承認されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-179">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="d9a05-180">Microsoft Threat Experts から、Defender for Endpoint ポータルのアラート ダッシュボードを介して、および構成した場合は電子メールを介して標的型攻撃通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-180">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a05-181">Defender for Endpoint の Microsoft Threat Experts 機能は、エンタープライズ モビリティ + セキュリティの E5 ライセンス [で利用できます](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-181">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="d9a05-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d9a05-182">Microsoft Cloud App Security</span></span>

<span data-ttu-id="d9a05-183">この設定を有効にすると、Defender for Endpoint シグナルが Microsoft Cloud App Security に転送され、クラウド アプリケーションの使用状況を詳細に可視化できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-183">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="d9a05-184">転送されたデータは、Cloud App Security データと同じ場所に格納され、処理されます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-184">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a05-185">この機能は、Windows 10 バージョン[](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)1709 (OS ビルド 16299.1085 および[KB4493441)](https://support.microsoft.com/help/4493441)、Windows 10 を実行しているデバイスの E5 ライセンスで利用できます。 バージョン 1803 [(KB4493464](https://support.microsoft.com/help/4493464)の OS ビルド 17134.704)、Windows 10 バージョン 1809 (OS ビルド 17763.379 および[KB4489899)](https://support.microsoft.com/help/4489899)以降の Windows 10 バージョン。</span><span class="sxs-lookup"><span data-stu-id="d9a05-185">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="azure-information-protection"></a><span data-ttu-id="d9a05-186">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="d9a05-186">Azure Information Protection</span></span>

<span data-ttu-id="d9a05-187">この設定を有効にすると、信号を Azure Information Protection に転送できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-187">Turning on this setting allows signals to be forwarded to Azure Information Protection.</span></span> <span data-ttu-id="d9a05-188">これにより、データ所有者と管理者は、オンボードデバイス上の保護されたデータとデバイスリスク評価を可視化できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-188">It gives data owners and administrators visibility into protected data on onboarded devices and device risk ratings.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="d9a05-189">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="d9a05-189">Microsoft Secure Score</span></span>

<span data-ttu-id="d9a05-190">Microsoft Defender for Endpoint シグナルを Microsoft 365 セキュリティ センターの Microsoft Secure Score に転送します。</span><span class="sxs-lookup"><span data-stu-id="d9a05-190">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="d9a05-191">この機能を有効にすることで、Microsoft Secure Score でデバイスのセキュリティ状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-191">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="d9a05-192">転送されたデータは、Microsoft Secure Score データと同じ場所に保存および処理されます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-192">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="d9a05-193">Microsoft Defender for Identity ポータルから Microsoft Defender for Endpoint の統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="d9a05-193">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="d9a05-194">Microsoft Defender for Identity でコンテキスト デバイスの統合を受け取る場合は、Microsoft Defender for Identity ポータルで機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-194">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="d9a05-195">グローバル管理者または [セキュリティ管理者の](https://portal.atp.azure.com/) 役割を持つ Microsoft Defender for Identity ポータルにログインします。</span><span class="sxs-lookup"><span data-stu-id="d9a05-195">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="d9a05-196">[インスタンス **の作成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d9a05-196">Click **Create your instance**.</span></span>

3. <span data-ttu-id="d9a05-197">[統合] 設定を [オン] **に切り替え、[** 保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d9a05-197">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="d9a05-198">両方のポータルの統合手順を完了すると、デバイスの詳細またはユーザーの詳細ページに関連するアラートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-198">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="microsoft-intune-connection"></a><span data-ttu-id="d9a05-199">Microsoft Intune 接続</span><span class="sxs-lookup"><span data-stu-id="d9a05-199">Microsoft Intune connection</span></span>

<span data-ttu-id="d9a05-200">エンドポイントの Defender を [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) と統合して、デバイスリスクベースの条件付きアクセス [を有効にできます](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-200">Defender for Endpoint can be integrated with [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) to [enable device risk-based conditional access](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="d9a05-201">この機能 [を有効に](configure-conditional-access.md)した場合、Defender for Endpoint デバイス情報を Intune と共有し、ポリシーの適用を強化できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-201">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9a05-202">この機能を使用するには、Intune と Defender for Endpoint の両方で統合を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-202">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="d9a05-203">特定の手順の詳細については、「Endpoint 用 [Defender で条件付きアクセスを構成する」を参照してください](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-203">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="d9a05-204">この機能は、次の場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-204">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="d9a05-205">エンタープライズ モビリティ + セキュリティ E3、および Windows E5 (または Microsoft 365 Enterprise E5) のライセンステナント</span><span class="sxs-lookup"><span data-stu-id="d9a05-205">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="d9a05-206">アクティブな Microsoft Intune 環境で、Intune で管理される Windows 10 デバイス Azure AD [参加しています](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)。</span><span class="sxs-lookup"><span data-stu-id="d9a05-206">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).</span></span>

### <a name="conditional-access-policy"></a><span data-ttu-id="d9a05-207">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="d9a05-207">Conditional Access policy</span></span>

<span data-ttu-id="d9a05-208">Intune 統合を有効にした場合、Intune は従来の条件付きアクセス (CA) ポリシーを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="d9a05-208">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="d9a05-209">この従来の CA ポリシーは、Intune に状態レポートを設定する前提条件です。</span><span class="sxs-lookup"><span data-stu-id="d9a05-209">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="d9a05-210">削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-210">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="d9a05-211">Intune によって作成される従来の CA ポリシー[](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)は、エンドポイントの構成に使用される最新の条件付きアクセス ポリシーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="d9a05-211">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>

## <a name="preview-features"></a><span data-ttu-id="d9a05-212">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="d9a05-212">Preview features</span></span>

<span data-ttu-id="d9a05-213">Defender for Endpoint プレビュー リリースの新機能について説明し、プレビュー エクスペリエンスをオンにして、今後の機能を最初に試してみてください。</span><span class="sxs-lookup"><span data-stu-id="d9a05-213">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="d9a05-214">今後の機能にアクセスできます。これは、機能が一般に利用可能になる前に全体的なエクスペリエンスを向上させるためにフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-214">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="d9a05-215">Microsoft コンプライアンス センターとエンドポイント通知を共有する</span><span class="sxs-lookup"><span data-stu-id="d9a05-215">Share endpoint alerts with Microsoft Compliance Center</span></span>

<span data-ttu-id="d9a05-216">エンドポイント のセキュリティアラートとそのトリアージの状態を Microsoft コンプライアンス センターに転送し、警告を使用してインサイダーリスク管理ポリシーを強化し、内部リスクを害する前に修復することができます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-216">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="d9a05-217">転送されたデータは、365 データと同じ場所Office保存されます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-217">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="d9a05-218">Insider リスク管理設定で [セキュリティ ポリシー](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) 違反インジケーターを構成すると、Defender for Endpoint アラートが該当するユーザーのインサイダー リスク管理と共有されます。</span><span class="sxs-lookup"><span data-stu-id="d9a05-218">After configuring the [Security policy violation indicators](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9a05-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9a05-219">Related topics</span></span>

- [<span data-ttu-id="d9a05-220">データ保持設定の更新</span><span class="sxs-lookup"><span data-stu-id="d9a05-220">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="d9a05-221">アラート通知の構成</span><span class="sxs-lookup"><span data-stu-id="d9a05-221">Configure alert notifications</span></span>](configure-email-notifications.md)