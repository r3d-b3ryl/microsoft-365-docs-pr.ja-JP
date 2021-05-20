---
title: Microsoft Defender ウイルス対策でクラウドで提供される保護を有効にする
description: クラウドで提供される保護を有効にして、高速かつ高度な保護機能を利用できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、クラウド、一目でブロック
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572059"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="c550f-104">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="c550f-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c550f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c550f-105">**Applies to:**</span></span>

- [<span data-ttu-id="c550f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c550f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="c550f-107">Microsoft Defender ウイルス対策 クラウド サービスは、ネットワークとエンドポイントに最新の保護を提供するためのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="c550f-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="c550f-108">クラウド サービスと呼ばれますが、クラウドに保存されているファイルを保護するだけではありません。むしろ、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="c550f-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="c550f-109">Microsoft Defender ウイルス対策は、複数の検出および防止技術を使用して、正確でリアルタイムでインテリジェントな保護を実現します。</span><span class="sxs-lookup"><span data-stu-id="c550f-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="c550f-110">[エンドポイントの次世代保護のためのマイクロソフトディフェンダーの中核にある高度な技術を知る](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="c550f-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="c550f-111">クラウドで提供される保護Microsoft Defender ウイルス対策オンまたはオフにするには、次の複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="c550f-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="c550f-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c550f-112">Microsoft Intune</span></span>
- <span data-ttu-id="c550f-113">Microsoft エンドポイント マネージャー</span><span class="sxs-lookup"><span data-stu-id="c550f-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="c550f-114">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="c550f-114">Group Policy</span></span>
- <span data-ttu-id="c550f-115">コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="c550f-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="c550f-116">Windows セキュリティ アプリを使用して、個々のクライアントでオンまたはオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c550f-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="c550f-117">クラウド[で提供される保護の概要については、「Microsoft クラウド配信](cloud-protection-microsoft-defender-antivirus.md)保護を使用する」Microsoft Defender ウイルス対策参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="c550f-118">エンドポイントがクラウドで提供される保護サービスに確実に接続できるようにするための、ネットワーク接続の要件の詳細については、「 [ネットワーク接続の構成と検証](configure-network-connections-microsoft-defender-antivirus.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c550f-119">Windows 10では、このトピックで説明する **基本** レポートオプションと **詳細** レポート オプションの違いはありません。</span><span class="sxs-lookup"><span data-stu-id="c550f-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="c550f-120">これは従来の区別であり、どちらかの設定を選択すると、クラウドで提供される保護のレベルが同じになります。</span><span class="sxs-lookup"><span data-stu-id="c550f-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="c550f-121">共有される情報の種類や量に違いはありません。</span><span class="sxs-lookup"><span data-stu-id="c550f-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="c550f-122">収集内容の詳細については、 [Microsoft のプライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=521839)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c550f-123">Intune を使用してクラウドで提供される保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="c550f-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="c550f-124">Microsoft エンドポイント マネージャー管理センター ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) に移動してログインします。</span><span class="sxs-lookup"><span data-stu-id="c550f-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="c550f-125">ホーム **ウィンドウで** 、[ **デバイス構成> プロファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="c550f-126">構成する **デバイス制限プロファイルの** 種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="c550f-127">新しい **デバイス制限** プロファイル タイプを作成する必要がある場合は [、Microsoft Intuneでデバイス制限設定を構成するを](/intune/device-restrictions-configure)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="c550f-128">[**プロパティ**  >  **構成設定:**  >  **編集] Microsoft Defender ウイルス対策** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="c550f-129">クラウド配信保護スイッチ **で** 、[ **有効**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="c550f-130">[ **サンプル送信前にユーザーに確認** する] ドロップダウンで、[ **すべてのデータを自動的に送信する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="c550f-131">Intune デバイス プロファイルの作成方法と構成方法など、Intune デバイス プロファイルの詳細については、「[デバイス プロファイルのMicrosoft Intuneとは」](/intune/device-profiles)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c550f-132">Microsoft エンドポイント マネージャーを使用してクラウドで提供される保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="c550f-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="c550f-133">Microsoft エンドポイント マネージャー管理センター ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) に移動してログインします。</span><span class="sxs-lookup"><span data-stu-id="c550f-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="c550f-134">**[エンドポイント セキュリティ**  >  **アンチウイルス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="c550f-135">ウイルス対策プロファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-135">Select an antivirus profile.</span></span> <span data-ttu-id="c550f-136">(まだプロファイルがない場合、または新しいプロファイルを作成する場合は[、「Microsoft Intuneでデバイス制限の設定を構成](/intune/device-restrictions-configure)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="c550f-137">[ **プロパティ ] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-137">Select **Properties**.</span></span> <span data-ttu-id="c550f-138">次に、[ **構成の設定**] の横にある [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c550f-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="c550f-139">[ **クラウド保護**] を展開し、[ **クラウドで提供される保護レベル]** の一覧で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="c550f-140">**高**: 検出の強力なレベルを適用します。</span><span class="sxs-lookup"><span data-stu-id="c550f-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="c550f-141">**高プラス**: **High** レベルを使用し、追加の保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。</span><span class="sxs-lookup"><span data-stu-id="c550f-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="c550f-142">**ゼロ許容範囲**: 不明な実行可能ファイルをすべてブロックします。</span><span class="sxs-lookup"><span data-stu-id="c550f-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="c550f-143">[ **レビュー + 保存**] を選択し、[ 保存 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="c550f-144">Microsoft Endpoint Configuration Managerの構成の詳細については、「[マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c550f-145">グループ ポリシーを使用してクラウドで配信される保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="c550f-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="c550f-146">グループ ポリシー管理デバイスで、[グループ [ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))] を開き、構成するグループ ポリシー オブジェクトを右クリックして [ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c550f-147">グループ **ポリシー管理エディタ** で、[コンピュータの **構成]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="c550f-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c550f-148">[ **管理用テンプレート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="c550f-149">ツリーを展開して **コンポーネントをマップ> Microsoft Defender ウイルス対策 > Windows**</span><span class="sxs-lookup"><span data-stu-id="c550f-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="c550f-150">[ **マイクロソフトマップに参加**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c550f-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="c550f-151">オプションがオンになっていることを確認し、基本 **MAPS** または **高度なマップ** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c550f-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="c550f-152">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-152">Select **OK**.</span></span>

6. <span data-ttu-id="c550f-153">**[詳細な分析が必要な場合は、ファイル サンプルを送信** する] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c550f-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="c550f-154">最初のオプションが **[有効]** に設定され、他のオプションがどちらかに設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c550f-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="c550f-155">**安全なサンプルを送信** する (1)</span><span class="sxs-lookup"><span data-stu-id="c550f-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="c550f-156">**すべてのサンプルを送信** する (3)</span><span class="sxs-lookup"><span data-stu-id="c550f-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="c550f-157">[ **安全なサンプルを送信** する (1)] オプションは、ほとんどのサンプルが自動的に送信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c550f-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="c550f-158">個人情報が含まれている可能性のあるファイルは、引き続きプロンプトを表示し、追加の確認が必要です。</span><span class="sxs-lookup"><span data-stu-id="c550f-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="c550f-159">オプションを **常にプロンプト** (0) に設定すると、デバイスの保護状態が低下します。</span><span class="sxs-lookup"><span data-stu-id="c550f-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="c550f-160">**[送信しない**] (2) に設定すると、エンドポイントの Microsoft Defender の [[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md)] 機能が機能しません。</span><span class="sxs-lookup"><span data-stu-id="c550f-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="c550f-161">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c550f-162">PowerShell コマンドレットを使用してクラウドで提供される保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="c550f-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="c550f-163">次のコマンドレットは、クラウドで提供される保護を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c550f-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="c550f-164">Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については[、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策および](use-powershell-cmdlets-microsoft-defender-antivirus.md) [Defender コマンドレット](/powershell/module/defender/)を構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="c550f-165">[ポリシー CSP - ディフェンダー](/windows/client-management/mdm/policy-csp-defender) には、特に [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)に関する詳細情報もあります。</span><span class="sxs-lookup"><span data-stu-id="c550f-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="c550f-166">また **、-SubmitSamplesConsent** を `SendSafeSamples` (既定の設定 `NeverSend` )、または に設定することもできます `AlwaysPrompt` 。</span><span class="sxs-lookup"><span data-stu-id="c550f-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="c550f-167">この `SendSafeSamples` 設定は、ほとんどのサンプルが自動的に送信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c550f-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="c550f-168">個人情報が含まれている可能性のあるファイルは、引き続きプロンプトを表示し、追加の確認が必要です。</span><span class="sxs-lookup"><span data-stu-id="c550f-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="c550f-169">**設定 -SubmitSamples同意** デバイス `NeverSend` `AlwaysPrompt` の保護レベルを下げるか、または下げます。</span><span class="sxs-lookup"><span data-stu-id="c550f-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="c550f-170">さらに、 `NeverSend` エンドポイントの Microsoft Defender の [最初のサイトでブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md) 機能が機能しないことを意味するように設定します。</span><span class="sxs-lookup"><span data-stu-id="c550f-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="c550f-171">Windows管理命令 (WMI) を使用してクラウドで提供される保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="c550f-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="c550f-172">次のプロパティ [に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference)クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c550f-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="c550f-173">許可されるパラメーターの詳細については[、「WMIv2 API のWindows Defender」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c550f-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="c550f-174">Windows セキュリティ アプリを使用して、個々のクライアントでクラウド配信保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="c550f-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="c550f-175">[Microsoft MAPS グループ ポリシー **のレポート用にローカル設定の上書きを構成** する] 設定が **[無効]** に設定されている場合、Windows 設定の **クラウドベースの保護** 設定はグレー表示され、使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c550f-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="c550f-176">グループ ポリシーを使った変更は、Windows の設定で設定を更新する前に、最初に個別のエンドポイントに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c550f-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="c550f-177">タスクバーで盾アイコンを選択するか、または **[Defender]** のスタートメニューを検索して、Windows セキュリティアプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="c550f-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="c550f-178">**[ウイルス&脅威対策**] タイル (または左側のメニュー バーの盾アイコン) を選択し、[**ウイルス&脅威対策設定**] ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c550f-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Windows セキュリティ アプリの [ウイルスと脅威の防止の設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="c550f-180">**クラウドベースの保護** と **自動サンプル提出** が **On** に切り替わったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c550f-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="c550f-181">自動サンプル送信がグループ ポリシーで構成されている場合、設定はグレー表示され、使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="c550f-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c550f-182">関連記事</span><span class="sxs-lookup"><span data-stu-id="c550f-182">Related articles</span></span>

- [<span data-ttu-id="c550f-183">クラウド ブロックのタイムアウト期間の構成</span><span class="sxs-lookup"><span data-stu-id="c550f-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c550f-184">一目でブロックを構成する</span><span class="sxs-lookup"><span data-stu-id="c550f-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c550f-185">PowerShell コマンドレットを使った Microsoft Defender ウイルス対策の管理</span><span class="sxs-lookup"><span data-stu-id="c550f-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="c550f-186">[Microsoft Intune用Windows Endpoint Protectionを使用してPCを保護する](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="c550f-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="c550f-187">Defender コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c550f-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="c550f-188">マイクロソフトクラウド配信の保護をMicrosoft Defender ウイルス対策で使用する</span><span class="sxs-lookup"><span data-stu-id="c550f-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c550f-189">マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス</span><span class="sxs-lookup"><span data-stu-id="c550f-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="c550f-190">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="c550f-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
