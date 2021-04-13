---
title: ブロックを一目で有効にしてマルウェアを数秒で検出する
description: 一目でブロックをオンにし、数秒でマルウェアを検出してブロックします。
keywords: スキャン, BAFS, マルウェア, 最初に見た, 一目, クラウド, ディフェンダー
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 837b7899368e69b274323125c97169bbe4f823b7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691564"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="0d7cd-104">一目でブロックをオンにする</span><span class="sxs-lookup"><span data-stu-id="0d7cd-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0d7cd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="0d7cd-105">**Applies to:**</span></span>

- [<span data-ttu-id="0d7cd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0d7cd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0d7cd-107">一目でブロックすると、数秒で新しいマルウェアを検出してブロックできます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="0d7cd-108">この保護は、特定の前提条件設定が有効になっている場合、既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="0d7cd-109">これらの設定には、クラウド配信の保護、指定されたサンプル送信タイムアウト (50 秒など)、およびファイルブロック レベルの高が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="0d7cd-110">ほとんどのエンタープライズ組織では、Microsoft Defender ウイルス対策の展開でこれらの設定が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="0d7cd-111">クラウドベースの [保護サービスが](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) ファイルを分析する間、ファイルの実行を妨げる時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="0d7cd-112">また、ファイル [がブロックされている場合に](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) ユーザーのデスクトップに表示されるメッセージをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="0d7cd-113">会社名、連絡先情報、メッセージ URL を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="0d7cd-114">Microsoft Defender for Endpoint のデモ web サイトに [アクセスして](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com 機能が動作し、動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="0d7cd-115">メカニズム</span><span class="sxs-lookup"><span data-stu-id="0d7cd-115">How it works</span></span>

<span data-ttu-id="0d7cd-116">Microsoft Defender Antivirus が疑わしいが検出されないファイルを検出すると、クラウド保護バックエンドに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="0d7cd-117">クラウド バックエンドは、ファイルのヒューリスティック、機械学習、および自動分析を適用して、ファイルが悪意のあるファイルであるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="0d7cd-118">Microsoft Defender Antivirus は、複数の検出および防止テクノロジを使用して、正確でインテリジェントでリアルタイムの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="0d7cd-119">詳細については、このブログを参照してください。 Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジ [について説明します](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="0d7cd-120">![Microsoft Defender AV エンジンの一覧](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="0d7cd-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="0d7cd-121">Windows 10 バージョン 1803 以降では、一目でブロックすると、移植できない実行可能ファイル (JS、VBS、マクロなど) と実行可能ファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="0d7cd-122">一目でブロックすると、インターネットからダウンロードされた実行可能ファイル、またはインターネット ゾーンから発生するポータブルでない実行可能ファイルに対してクラウド保護バックエンドのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="0d7cd-123">.exe ファイルのハッシュ値は、クラウド バックエンドを介してチェックされ、ファイルが以前に検出されていないファイルかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="0d7cd-124">クラウド バックエンドが判断できない場合、Microsoft Defender Antivirus はファイルをロックし、コピーをクラウドにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="0d7cd-125">クラウドは、ファイルが悪意のあるか安全かを判断するかどうかに応じて、ファイルを実行したり、すべての将来の遭遇でブロックしたりする前に、追加の分析を実行して決定に到達します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="0d7cd-126">多くの場合、このプロセスでは、新しいマルウェアの応答時間を数時間から数秒に短縮できます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="0d7cd-127">Microsoft Intune で一目でブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="0d7cd-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="0d7cd-128">Microsoft Intune は、Microsoft エンドポイント マネージャーの一部です。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="0d7cd-129">Microsoft Endpoint Manager 管理センター ( ) で、[ [https://endpoint.microsoft.com](https://endpoint.microsoft.com) デバイス構成 **プロファイル**  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="0d7cd-130">[デバイス制限] プロファイルの種類を使用 **してプロファイルを選択または** 作成します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="0d7cd-131">[デバイス制限 **プロファイルの** 構成設定] で **、[Microsoft Defender ウイルス** 対策] の下で次の設定を設定または確認します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="0d7cd-132">**クラウド配信の保護**: 有効</span><span class="sxs-lookup"><span data-stu-id="0d7cd-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="0d7cd-133">**ファイル ブロック レベル**: 高</span><span class="sxs-lookup"><span data-stu-id="0d7cd-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="0d7cd-134">**クラウドによるファイル スキャンの** 時間の延長 : 50</span><span class="sxs-lookup"><span data-stu-id="0d7cd-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="0d7cd-135">**サンプル提出の前にユーザーに確認** する : プロンプトを表示せずにすべてのデータを送信する</span><span class="sxs-lookup"><span data-stu-id="0d7cd-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune の構成](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="0d7cd-137">設定内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="0d7cd-138">ファイル ブロック レベルを High に設定 **すると** 、強力なレベルの検出が適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="0d7cd-139">万が一、ファイルブロックによって正当なファイルが誤検知された場合は、検疫済み [ファイルを復元できます](./restore-quarantined-files-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="0d7cd-140">Intune で Microsoft Defender ウイルス対策デバイスの制限を構成する方法の詳細については、「Configure device Restriction [settings in Microsoft Intune」を参照してください](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="0d7cd-141">Intune の Microsoft Defender ウイルス対策デバイスの制限の一覧については、「Intune の Windows 10 (以降) のデバイス制限 [」を参照してください](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="0d7cd-142">Microsoft Endpoint Manager で一目でブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="0d7cd-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="0d7cd-143">Microsoft Endpoint Configuration Manager を探している場合は、Microsoft エンドポイント マネージャーの一部です。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="0d7cd-144">Microsoft Endpoint Manager ( ) で [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、[エンドポイント セキュリティ **ウイルス対策] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="0d7cd-145">既存のポリシーを選択するか、Microsoft Defender ウイルス対策プロファイルの種類を使用して新 **しいポリシーを** 作成します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="0d7cd-146">次の構成設定を設定または確認します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="0d7cd-147">**クラウドによる保護を有効にする**: はい</span><span class="sxs-lookup"><span data-stu-id="0d7cd-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="0d7cd-148">**クラウドによって提供される保護レベル**: 高</span><span class="sxs-lookup"><span data-stu-id="0d7cd-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="0d7cd-149">**Defender Cloud Extended Timeout in Seconds**: 50</span><span class="sxs-lookup"><span data-stu-id="0d7cd-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="エンドポイント マネージャーで一目で確認する設定をブロックする":::

4. <span data-ttu-id="0d7cd-151">すべてのユーザー、すべてのデバイス、またはすべてのユーザーとデバイスなどのグループにMicrosoft Defender ウイルス対策プロファイル **を適用します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="0d7cd-152">グループ ポリシーで一目でブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="0d7cd-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="0d7cd-153">Intune または Microsoft エンドポイント マネージャーを使用して、一目でブロックを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="0d7cd-154">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="0d7cd-155">グループ ポリシー **管理エディターを使用して、[\*\*\*\*コンピューターの構成] [** 管理用テンプレート  >    >  **] Windows コンポーネント Microsoft** Defender ウイルス対策マップ  >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="0d7cd-156">[マップ] セクションで、[一目でブロックする] 機能を構成する **を** ダブルクリックし、[有効] に設定し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0d7cd-157">常に **プロンプト (0) に設定すると** 、デバイスの保護状態が低下します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="0d7cd-158">[送信 **しない] (2) に設定すると** 、一目でブロックが機能しません。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="0d7cd-159">[マップ] セクションで、[詳細な分析が必要な場合にファイル サンプルを送信する] をダブルクリックし、[有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="0d7cd-160">[詳細 **な分析が必要な場合にファイル サンプルを送信する] で、[** すべての **サンプルを送信**] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="0d7cd-161">設定を変更した場合は、ネットワーク全体にグループ ポリシー オブジェクトを再展開して、すべてのエンドポイントが確実にカバーされます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="0d7cd-162">個々のクライアントでブロックが一目で有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="0d7cd-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="0d7cd-163">Windows のセキュリティ設定を使用して、個々のクライアントで一目でブロックが有効になっているか確認できます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="0d7cd-164">クラウド配信の保護と自動サンプル送信の両方が有効になっている限り、一目で **ブロックが自動的** に有効になります。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="0d7cd-165">Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="0d7cd-166">[ **ウイルス対策&脅威保護]** を選択し、[ウイルスの検出] の [脅威&の設定] で **、[設定の管理**] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows セキュリティ アプリの [ウイルス&保護設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="0d7cd-168">クラウドによる **保護と自動** サンプル **送信の両方が** 有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="0d7cd-169">前提条件の設定がグループ ポリシーを使用して構成および展開されている場合、このセクションで説明する設定はグレー表示され、個々のエンドポイントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="0d7cd-170">グループ ポリシー オブジェクトを使用して行った変更は、Windows の設定で設定を更新する前に、最初に個々のエンドポイントに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="0d7cd-171">ブロックの一目での検証が機能している</span><span class="sxs-lookup"><span data-stu-id="0d7cd-171">Validate block at first sight is working</span></span>

<span data-ttu-id="0d7cd-172">機能が動作しているのを確認するには、「ネットワークとクラウド間の接続を検証する」 [のガイダンスに従います](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="0d7cd-173">一目でブロックをオフにする</span><span class="sxs-lookup"><span data-stu-id="0d7cd-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="0d7cd-174">ブロックを一目でオフにすると、デバイスとネットワークの保護状態が低下します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="0d7cd-175">実際にブロックを一目で保護せずに前提条件の設定を保持する場合は、一目でブロックを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="0d7cd-176">遅延の問題が発生している場合や、ネットワークに対する機能の影響をテストする場合は、一時的にブロックをオフにできます。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="0d7cd-177">ただし、一目でブロックを完全に無効にすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="0d7cd-178">Microsoft Endpoint Manager でブロックを一目でオフにする</span><span class="sxs-lookup"><span data-stu-id="0d7cd-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="0d7cd-179">Microsoft Endpoint Manager 管理センター ( ) に移動 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="0d7cd-180">[エンドポイント セキュリティ **ウイルス対策**  >  **] に** 移動し、Microsoft Defender ウイルス対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="0d7cd-181">[管理 **] で**、[プロパティ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="0d7cd-182">[構成設定 **] の横にある**[編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="0d7cd-183">次の設定の 1 つ以上を変更します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="0d7cd-184">[ **クラウド配信の保護を有効にする] を** **[いいえ] または [構成** されていません **] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="0d7cd-185">[ **クラウド配信の保護レベル] を [** 構成されていません **] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="0d7cd-186">[Defender **Cloud Extended Timeout in Seconds] ボックスをオフ** にします。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="0d7cd-187">設定を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="0d7cd-188">グループ ポリシーで一目でブロックをオフにする</span><span class="sxs-lookup"><span data-stu-id="0d7cd-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="0d7cd-189">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="0d7cd-190">グループ ポリシー **管理エディターを使用して、[** コンピューターの構成] **に移動し、[** 管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="0d7cd-191">Windows コンポーネントの Microsoft Defender ウイルス **対策**  >  マップを **通じてツリーを**  >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="0d7cd-192">[一目 **でブロックする] 機能をダブルクリックし、** オプションを [無効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d7cd-193">一目でブロックを無効にしても、前提条件のグループ ポリシーは無効または変更されない。</span><span class="sxs-lookup"><span data-stu-id="0d7cd-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d7cd-194">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d7cd-194">See also</span></span>

- [<span data-ttu-id="0d7cd-195">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="0d7cd-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="0d7cd-196">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="0d7cd-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)