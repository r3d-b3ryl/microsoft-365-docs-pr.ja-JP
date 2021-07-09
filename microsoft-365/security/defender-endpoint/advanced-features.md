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
ms.openlocfilehash: 2448b95e5c5c5da25a916b659f6b49d04ba8f0c1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339576"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="ca49b-104">Defender for Endpoint で高度な機能を構成する</span><span class="sxs-lookup"><span data-stu-id="ca49b-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="ca49b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ca49b-105">**Applies to:**</span></span>
- [<span data-ttu-id="ca49b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ca49b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ca49b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca49b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="ca49b-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ca49b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ca49b-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ca49b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="ca49b-110">使用する Microsoft セキュリティ製品によっては、Defender for Endpoint を統合できる高度な機能がいくつか用意されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="ca49b-111">高度な機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="ca49b-111">Enable advanced features</span></span>

1. <span data-ttu-id="ca49b-112">ナビゲーション ウィンドウで、[基本設定]**セットアップの [高度な**  >  **機能] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ca49b-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="ca49b-113">構成する高度な機能を選択し、設定を [オン] と [オフ] **の間で切り** 替 **えます**。</span><span class="sxs-lookup"><span data-stu-id="ca49b-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="ca49b-114">[設定 **の保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca49b-114">Click **Save preferences**.</span></span>

<span data-ttu-id="ca49b-115">次の高度な機能を使用して、潜在的に悪意のあるファイルから保護され、セキュリティ調査中により良い洞察を得る。</span><span class="sxs-lookup"><span data-stu-id="ca49b-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="ca49b-116">自動調査</span><span class="sxs-lookup"><span data-stu-id="ca49b-116">Automated investigation</span></span>

<span data-ttu-id="ca49b-117">この機能を有効にし、サービスの自動調査および修復機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="ca49b-118">詳細については、「自動調査 [」を参照してください](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="ca49b-119">ライブ応答</span><span class="sxs-lookup"><span data-stu-id="ca49b-119">Live response</span></span>

<span data-ttu-id="ca49b-120">適切なアクセス許可を持つユーザーがデバイスでライブ応答セッションを開始できるよう、この機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ca49b-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="ca49b-121">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="ca49b-122">サーバーのライブ応答</span><span class="sxs-lookup"><span data-stu-id="ca49b-122">Live response for servers</span></span>
<span data-ttu-id="ca49b-123">この機能を有効にし、適切なアクセス許可を持つユーザーがサーバーでライブ応答セッションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="ca49b-124">役割の割り当ての詳細については、「役割の作成と [管理」を参照してください](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="ca49b-125">ライブ応答の署名されていないスクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="ca49b-125">Live response unsigned script execution</span></span>

<span data-ttu-id="ca49b-126">この機能を有効にすると、ライブ応答セッションで署名されていないスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="always-remediate-pua"></a><span data-ttu-id="ca49b-127">PUA を常に修復する</span><span class="sxs-lookup"><span data-stu-id="ca49b-127">Always remediate PUA</span></span>
<span data-ttu-id="ca49b-128">望ましくない可能性のあるアプリケーション (PUA) は、コンピューターの動作が遅くなる、予期しない広告を表示する、または最悪の場合は予期しないソフトウェアや望ましくない可能性のある他のソフトウェアをインストールするソフトウェアのカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="ca49b-128">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> 

<span data-ttu-id="ca49b-129">この機能を有効にし、PUA 保護がデバイスで構成されていない場合でも、不要な可能性のあるアプリケーション (PUA) がテナント内のすべてのデバイスで修復されます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-129">Turn on this feature so that potentially unwanted applications (PUA) are remediated on all devices in your tenant even if PUA protection is not configured on the devices.</span></span> <span data-ttu-id="ca49b-130">これにより、ユーザーがデバイスに不要なアプリケーションを誤ってインストールすることを防役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-130">This will help protect users from inadvertently installing unwanted applications on their device.</span></span> <span data-ttu-id="ca49b-131">オフにすると、修復はデバイスの構成に依存します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-131">When turned off, remediation is dependent on the device configuration.</span></span> 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a><span data-ttu-id="ca49b-132">スコープ付きデバイス グループ内への相関関係の制限</span><span class="sxs-lookup"><span data-stu-id="ca49b-132">Restrict correlation to within scoped device groups</span></span>
<span data-ttu-id="ca49b-133">この構成は、ローカルの SOC 操作でアラートの相関関係をアクセスできるデバイス グループにのみ制限する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-133">This configuration can be used for scenarios where local SOC operations would like to limit alert correlations only to device groups that they can access.</span></span> <span data-ttu-id="ca49b-134">この設定を有効にすると、デバイス グループをまたがったアラートで構成されるインシデントは、1 つのインシデントとは見なされません。</span><span class="sxs-lookup"><span data-stu-id="ca49b-134">By turning this setting on, an incident composed of alerts that cross device groups will no longer be considered a single incident.</span></span> <span data-ttu-id="ca49b-135">ローカル SOC は、関連するデバイス グループの 1 つへのアクセス権を持つため、インシデントに対してアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-135">The local SOC can then take action on the incident because they have access to one of the device groups involved.</span></span> <span data-ttu-id="ca49b-136">ただし、グローバル SOC では、1 つのインシデントではなく、デバイス グループ別に複数の異なるインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-136">However, global SOC will see several different incidents by device group instead of one incident.</span></span> <span data-ttu-id="ca49b-137">この設定を有効にしない場合は、組織全体のインシデントの相関関係の利点を上回る場合は、この設定を有効にすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="ca49b-137">We do not recommend turning this setting on unless doing so outweighs the benefits of incident correlation across the entire organization</span></span>
>[!NOTE]
><span data-ttu-id="ca49b-138">この設定を変更すると、将来のアラートの相関関係にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-138">Changing this setting impacts future alert correlations only.</span></span>

## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="ca49b-139">ブロック モードEDR有効にする</span><span class="sxs-lookup"><span data-stu-id="ca49b-139">Enable EDR in block mode</span></span>
<span data-ttu-id="ca49b-140">ブロック モードでのエンドポイントの検出と応答 (EDR) は、パッシブ モードで実行されている場合でも、悪意のあるMicrosoft Defender ウイルス対策からの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-140">Endpoint detection and response (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="ca49b-141">オンにすると、EDRモードでデバイスで検出された悪意のあるアーティファクトや動作がブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-141">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="ca49b-142">EDRモードでは、侵害後に検出された悪意のあるアーティファクトを修復するために、舞台裏で動作します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-142">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span>


## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="ca49b-143">Autoresolve 修復されたアラート</span><span class="sxs-lookup"><span data-stu-id="ca49b-143">Autoresolve remediated alerts</span></span>

<span data-ttu-id="ca49b-144">Windows 10 Version 1809 以降に作成されたテナントの場合、自動調査と修復機能は既定で構成され、自動分析結果の状態が "脅威が見つかりません" または "修復済み" であるアラートを解決します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-144">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="ca49b-145">アラートを自動解決したくない場合は、手動で機能をオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-145">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="ca49b-146">そのバージョンより前に作成されたテナントの場合は、[高度な機能] ページからこの機能を手動で [有効にする必要](https://securitycenter.windows.com/preferences2/integration) があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-146">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ca49b-147">自動解決アクションの結果は、デバイスで検出されたアクティブなアラートに基づくデバイス リスク レベルの計算に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-147">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="ca49b-148">セキュリティ運用アナリストが手動でアラートの状態を "進行中" または "解決済み" に設定した場合、自動解決機能は上書きされません。</span><span class="sxs-lookup"><span data-stu-id="ca49b-148">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="ca49b-149">ファイルを許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="ca49b-149">Allow or block file</span></span>

<span data-ttu-id="ca49b-150">ブロックは、組織が次の要件を満たしている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-150">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="ca49b-151">アクティブMicrosoft Defender ウイルス対策マルウェア対策ソリューションとして使用し、</span><span class="sxs-lookup"><span data-stu-id="ca49b-151">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="ca49b-152">クラウドベースの保護機能が有効になっている</span><span class="sxs-lookup"><span data-stu-id="ca49b-152">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="ca49b-153">この機能を使用すると、ネットワーク内の悪意のある可能性のあるファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-153">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="ca49b-154">ファイルをブロックすると、組織内のデバイスでファイルが読み取り、書き込み、または実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="ca49b-154">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="ca49b-155">ファイルを **許可またはブロックするには** 、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-155">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="ca49b-156">ナビゲーション ウィンドウで、[エンドポイントの全般 **詳細設定設定** ファイルを許可またはブロック  >    >    >    >  **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ca49b-156">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="ca49b-157">[オン] と [オフ]**の間で設定を\*\*\*\*切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="ca49b-157">Toggle the setting between **On** and **Off**.</span></span>

    ![ブロック ファイル機能の詳細設定のイメージ](images/atp-preferences-setup.png)

1. <span data-ttu-id="ca49b-159">ページ **の下部にある [基本** 設定の保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-159">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="ca49b-160">この機能を有効にした後、[](respond-file-alerts.md#allow-or-block-file)ファイルのプロファイルページの [インジケーターの追加] タブを使用してファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-160">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="ca49b-161">カスタム ネットワーク インジケーター</span><span class="sxs-lookup"><span data-stu-id="ca49b-161">Custom network indicators</span></span>

<span data-ttu-id="ca49b-162">この機能を有効にすることで、IP アドレス、ドメイン、または URL のインジケーターを作成し、カスタム インジケーター リストに基づいて許可またはブロックするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-162">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="ca49b-163">この機能を使用するには、デバイスがバージョン 1709 以降Windows 10実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-163">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="ca49b-164">また、ブロック モードでネットワーク保護を行い、マルウェア対策プラットフォームのバージョン 4.18.1906.3 以降は [KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca49b-164">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="ca49b-165">詳細については、「指標の管理 [」を参照してください](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-165">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ca49b-166">ネットワーク保護は、Defender for Endpoint データで選択した場所の外部にある可能性がある場所で要求を処理する評判サービスを活用します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-166">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="tamper-protection"></a><span data-ttu-id="ca49b-167">タンパープロテクション</span><span class="sxs-lookup"><span data-stu-id="ca49b-167">Tamper protection</span></span>
<span data-ttu-id="ca49b-168">一部の種類のサイバー攻撃では、悪いアクターがコンピューターでウイルス対策保護などのセキュリティ機能を無効にしようとします。</span><span class="sxs-lookup"><span data-stu-id="ca49b-168">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="ca49b-169">悪いアクターは、データに簡単にアクセスしたり、マルウェアをインストールしたり、データ、ID、デバイスを悪用したりするために、セキュリティ機能を無効にしています。</span><span class="sxs-lookup"><span data-stu-id="ca49b-169">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span>

<span data-ttu-id="ca49b-170">タンパープロテクションは基本的Microsoft Defender ウイルス対策ロックし、アプリやメソッドを通じてセキュリティ設定が変更されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="ca49b-170">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods.</span></span>

<span data-ttu-id="ca49b-171">この機能は、組織でクラウド ベースMicrosoft Defender ウイルス対策が有効になっている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-171">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="ca49b-172">詳細については、「クラウドで提供される保護を通じて、Microsoft Defender ウイルス対策テクノロジを使用[する」を参照してください](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-172">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="ca49b-173">セキュリティ ソリューションとその重要な機能に対する望ましくない変更を防止するために、改ざん防止を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="ca49b-173">Keep tamper protection turned on to prevent unwanted changes to your security solution and its essential features.</span></span>


## <a name="show-user-details"></a><span data-ttu-id="ca49b-174">ユーザーの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="ca49b-174">Show user details</span></span>

<span data-ttu-id="ca49b-175">この機能を有効にし、ユーザーの詳細がユーザーの詳細を表示Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="ca49b-175">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="ca49b-176">詳細には、ユーザー アカウント エンティティを調査する際のユーザーの画像、名前、タイトル、および部署情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-176">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="ca49b-177">ユーザー アカウント情報は、次のビューで確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-177">You can find user account information in the following views:</span></span>

- <span data-ttu-id="ca49b-178">セキュリティ運用ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="ca49b-178">Security operations dashboard</span></span>
- <span data-ttu-id="ca49b-179">アラート キュー</span><span class="sxs-lookup"><span data-stu-id="ca49b-179">Alert queue</span></span>
- <span data-ttu-id="ca49b-180">[デバイスの詳細] ページ</span><span class="sxs-lookup"><span data-stu-id="ca49b-180">Device details page</span></span>

<span data-ttu-id="ca49b-181">詳細については、「ユーザー アカウントの [調査」を参照してください](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-181">For more information, see [Investigate a user account](investigate-user.md).</span></span>


## <a name="skype-for-business-integration"></a><span data-ttu-id="ca49b-182">Skype for Business 統合</span><span class="sxs-lookup"><span data-stu-id="ca49b-182">Skype for Business integration</span></span>

<span data-ttu-id="ca49b-183">この統合をSkype for Businessすることで、ユーザーとのコミュニケーションをSkype for Business、電子メール、または電話を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-183">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="ca49b-184">これは、ユーザーと通信し、リスクを軽減する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ca49b-184">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="ca49b-185">デバイスがネットワークから分離されている場合は、Outlook および Skype 通信を有効にし、ネットワークから切断されている間にユーザーに通信できるポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-185">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="ca49b-186">この設定は、デバイスがSkypeモードOutlook通信に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-186">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="microsoft-defender-for-identity-integration"></a><span data-ttu-id="ca49b-187">Id 統合用 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ca49b-187">Microsoft Defender for Identity integration</span></span>

<span data-ttu-id="ca49b-188">Microsoft Defender for Identity との統合により、別の Microsoft Identity セキュリティ製品に直接ピボットできます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-188">The integration with Microsoft Defender for Identity allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="ca49b-189">Microsoft Defender for Identity は、侵害された疑いのあるアカウントと関連するリソースに関する追加の分析情報を使用して調査を強化します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-189">Microsoft Defender for Identity augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="ca49b-190">この機能を有効にすると、識別の観点からネットワーク全体をピボットすることで、デバイスベースの調査機能を強化できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-190">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="ca49b-191">この機能を有効にするには、適切なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca49b-191">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="ca49b-192">Office 365脅威インテリジェンス接続</span><span class="sxs-lookup"><span data-stu-id="ca49b-192">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="ca49b-193">この機能は、アクティブなユーザーまたは脅威インテリジェンス Office 365 E5がある場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-193">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="ca49b-194">詳細については、「E5 製品のOffice 365 Enterpriseを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca49b-194">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="ca49b-195">この機能を有効にした場合、microsoft Defender for Office 365 のデータを Microsoft 365 Defender に組み込み、Office 365 メールボックスと Windows デバイス全体で包括的なセキュリティ調査を行えます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-195">When you turn this feature on, you'll be able to incorporate data from Microsoft Defender for Office 365 into Microsoft 365 Defender to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="ca49b-196">この機能を有効にするには、適切なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ca49b-196">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="ca49b-197">脅威インテリジェンスでコンテキスト デバイスのOffice 365を受け取る場合は、[セキュリティ とコンプライアンス] ダッシュボードで Defender for Endpoint &する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-197">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="ca49b-198">詳細については、「脅威の調査 [と対応」を参照してください](/microsoft-365/security/office-365-security/office-365-ti)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-198">For more information, see [Threat investigation and response](/microsoft-365/security/office-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a><span data-ttu-id="ca49b-199">Microsoft 脅威エキスパート - ターゲット攻撃通知</span><span class="sxs-lookup"><span data-stu-id="ca49b-199">Microsoft Threat Experts - Targeted Attack Notifications</span></span>

<span data-ttu-id="ca49b-200">2 つの Microsoft Threat Expert コンポーネントの中で、標的型攻撃通知は一般提供です。</span><span class="sxs-lookup"><span data-stu-id="ca49b-200">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="ca49b-201">エキスパートオンデマンド機能はまだプレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="ca49b-201">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="ca49b-202">experts-on-demand 機能は、プレビューを申請し、アプリケーションが承認されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-202">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="ca49b-203">ターゲット攻撃通知は、Defender for Endpoint ポータルMicrosoft 脅威エキスパート、構成した場合は電子メールを介して、ターゲット攻撃通知を受信できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-203">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="ca49b-204">Defender for Endpoint Microsoft 脅威エキスパートの機能は、エンドポイントの E5 ライセンスで[Enterprise Mobility + Security。](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)</span><span class="sxs-lookup"><span data-stu-id="ca49b-204">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>
## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="ca49b-205">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ca49b-205">Microsoft Cloud App Security</span></span>

<span data-ttu-id="ca49b-206">この設定を有効にすると、Defender for Endpoint シグナルMicrosoft Cloud App Securityに転送され、クラウド アプリケーションの使用状況を詳細に確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-206">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="ca49b-207">転送されたデータは、ユーザーのデータと同じ場所にCloud App Securityされます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-207">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="ca49b-208">この機能は、E5 ライセンスを使用して[、Enterprise Mobility + Securityを実行](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)しているWindows 10 バージョン 1709 [(KB4493441](https://support.microsoft.com/help/4493441)の OS ビルド 16299.1085)、Windows 10 バージョン 1803 (OS ビルド 17134.704 [KB449364)、Windows 10 Version 1809](https://support.microsoft.com/help/4493464)(OS ビルド 17763.379 および[KB4489899)、](https://support.microsoft.com/help/4489899)または Windows 10 以降のバージョン。</span><span class="sxs-lookup"><span data-stu-id="ca49b-208">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="ca49b-209">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="ca49b-209">Microsoft Secure Score</span></span>

<span data-ttu-id="ca49b-210">Microsoft Defender for Endpoint シグナルをセキュリティ センターの Microsoft Secure Score に転送Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-210">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="ca49b-211">この機能を有効にすることで、Microsoft Secure Score でデバイスのセキュリティ状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-211">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="ca49b-212">転送されたデータは、Microsoft Secure Score データと同じ場所に保存および処理されます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-212">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="ca49b-213">Microsoft Defender for Identity ポータルから Microsoft Defender for Endpoint の統合を有効にする</span><span class="sxs-lookup"><span data-stu-id="ca49b-213">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="ca49b-214">Microsoft Defender for Identity でコンテキスト デバイスの統合を受け取る場合は、Microsoft Defender for Identity ポータルで機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-214">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="ca49b-215">グローバル管理者または [セキュリティ管理者の](https://portal.atp.azure.com/) 役割を持つ Microsoft Defender for Identity ポータルにログインします。</span><span class="sxs-lookup"><span data-stu-id="ca49b-215">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="ca49b-216">[インスタンス **の作成] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca49b-216">Click **Create your instance**.</span></span>

3. <span data-ttu-id="ca49b-217">[統合] 設定を [オン] **に切り替え、[** 保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ca49b-217">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="ca49b-218">両方のポータルの統合手順を完了すると、デバイスの詳細またはユーザーの詳細ページに関連するアラートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-218">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="web-content-filtering"></a><span data-ttu-id="ca49b-219">Web コンテンツ フィルタリング</span><span class="sxs-lookup"><span data-stu-id="ca49b-219">Web content filtering</span></span>
<span data-ttu-id="ca49b-220">望ましくないコンテンツを含む Web サイトへのアクセスをブロックし、すべてのドメインで Web アクティビティを追跡します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-220">Block access to websites containing unwanted content and track web activity across all domains.</span></span> <span data-ttu-id="ca49b-221">ブロックする Web コンテンツ カテゴリを指定するには、Web コンテンツ フィルター ポリシー [を作成します](https://security.microsoft.com/preferences2/web_content_filtering_policy)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-221">To specify the web content categories you want to block, create a [web content filtering policy](https://security.microsoft.com/preferences2/web_content_filtering_policy).</span></span> <span data-ttu-id="ca49b-222">Microsoft Defender for Endpoint セキュリティ ベースラインを展開する場合は、ブロック モードでネットワーク [保護を行います](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-222">Ensure you have network protection in block mode when deploying the [Microsoft Defender for Endpoint security baseline](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2).</span></span>


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="ca49b-223">Microsoft コンプライアンス センターとエンドポイント通知を共有する</span><span class="sxs-lookup"><span data-stu-id="ca49b-223">Share endpoint alerts with Microsoft Compliance Center</span></span>
<span data-ttu-id="ca49b-224">エンドポイント のセキュリティアラートとそのトリアージの状態を Microsoft コンプライアンス センターに転送し、警告を使用してインサイダーリスク管理ポリシーを強化し、内部リスクを害する前に修復することができます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-224">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="ca49b-225">転送されたデータは、ユーザーのデータと同じ場所にOffice 365されます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-225">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="ca49b-226">Insider リスク管理設定で [セキュリティ ポリシー](/microsoft-365/compliance/insider-risk-management-settings#indicators) 違反インジケーターを構成すると、Defender for Endpoint アラートが該当するユーザーのインサイダー リスク管理と共有されます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-226">After configuring the [Security policy violation indicators](/microsoft-365/compliance/insider-risk-management-settings#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>



## <a name="microsoft-intune-connection"></a><span data-ttu-id="ca49b-227">Microsoft Intune接続</span><span class="sxs-lookup"><span data-stu-id="ca49b-227">Microsoft Intune connection</span></span>

<span data-ttu-id="ca49b-228">Defender for Endpoint は、デバイス リスクベースの条件付[Microsoft Intune](/intune/what-is-intune)[アクセスを有効にするアプリケーションと統合できます](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-228">Defender for Endpoint can be integrated with [Microsoft Intune](/intune/what-is-intune) to [enable device risk-based conditional access](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="ca49b-229">この機能 [を有効に](configure-conditional-access.md)した場合、Defender for Endpoint デバイス情報を Intune と共有し、ポリシーの適用を強化できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-229">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca49b-230">この機能を使用するには、Intune と Defender for Endpoint の両方で統合を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-230">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="ca49b-231">特定の手順の詳細については、「Endpoint 用 [Defender で条件付きアクセスを構成する」を参照してください](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-231">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="ca49b-232">この機能は、次の場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-232">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="ca49b-233">E5 (または E5) Enterprise Mobility + Security E3およびWindowsライセンスMicrosoft 365 Enterpriseテナント</span><span class="sxs-lookup"><span data-stu-id="ca49b-233">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="ca49b-234">アクティブなMicrosoft Intune環境で、Intune が管理するデバイスWindows 10 Azure AD[参加しています](/azure/active-directory/devices/concept-azure-ad-join/)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-234">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](/azure/active-directory/devices/concept-azure-ad-join/).</span></span>


### <a name="conditional-access-policy"></a><span data-ttu-id="ca49b-235">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ca49b-235">Conditional Access policy</span></span>

<span data-ttu-id="ca49b-236">Intune 統合を有効にした場合、Intune は従来の条件付きアクセス (CA) ポリシーを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-236">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="ca49b-237">この従来の CA ポリシーは、Intune に状態レポートを設定する前提条件です。</span><span class="sxs-lookup"><span data-stu-id="ca49b-237">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="ca49b-238">削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-238">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="ca49b-239">Intune によって作成される従来の CA ポリシー[](/azure/active-directory/conditional-access/overview/)は、エンドポイントの構成に使用される最新の条件付きアクセス ポリシーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="ca49b-239">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>


## <a name="device-discovery"></a><span data-ttu-id="ca49b-240">デバイス検出</span><span class="sxs-lookup"><span data-stu-id="ca49b-240">Device discovery</span></span>
<span data-ttu-id="ca49b-241">追加のアプライアンスや面倒なプロセス変更を必要とせずに、企業ネットワークに接続されている管理されていないデバイスを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-241">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="ca49b-242">オンボード デバイスを使用すると、ネットワーク内の管理されていないデバイスを見つけて、脆弱性とリスクを評価できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-242">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="ca49b-243">詳細については、「デバイスの検出 [」を参照してください](device-discovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ca49b-243">For more information, see [Device discovery](device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ca49b-244">フィルターをいつでも適用して、デバイス インベントリ リストから管理されていないデバイスを除外できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-244">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="ca49b-245">また、API クエリのオンボーディング状態列を使用して、管理されていないデバイスをフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-245">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="ca49b-246">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="ca49b-246">Preview features</span></span>

<span data-ttu-id="ca49b-247">Defender for Endpoint プレビュー リリースの新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca49b-247">Learn about new features in the Defender for Endpoint preview release.</span></span> <span data-ttu-id="ca49b-248">プレビュー エクスペリエンスをオンにして、今後の機能を試してみてください。</span><span class="sxs-lookup"><span data-stu-id="ca49b-248">Try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="ca49b-249">今後の機能にアクセスできます。これは、機能が一般に利用可能になる前に全体的なエクスペリエンスを向上させるためにフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="ca49b-249">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>




## <a name="related-topics"></a><span data-ttu-id="ca49b-250">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca49b-250">Related topics</span></span>

- [<span data-ttu-id="ca49b-251">データ保持設定の更新</span><span class="sxs-lookup"><span data-stu-id="ca49b-251">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="ca49b-252">アラート通知を構成する</span><span class="sxs-lookup"><span data-stu-id="ca49b-252">Configure alert notifications</span></span>](configure-email-notifications.md)
