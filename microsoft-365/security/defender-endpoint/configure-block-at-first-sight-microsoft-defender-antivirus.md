---
title: ブロックを一目で有効にしてマルウェアを数秒で検出する
description: 一目でブロックをオンにし、数秒でマルウェアを検出してブロックします。
keywords: スキャン、一目でブロックする、マルウェア、一目で見る、クラウド、ディフェンダー、ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079205"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="ada3e-104">事前ブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="ada3e-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ada3e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ada3e-105">**Applies to:**</span></span>

- [<span data-ttu-id="ada3e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ada3e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ada3e-107">この記事では、「一目でブロックする」と呼ばれるウイルス対策/マルウェア対策機能について説明し、組織で一目でブロックを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="ada3e-108">この記事は、組織のセキュリティ設定を管理するエンタープライズ管理者と IT 管理者向けです。</span><span class="sxs-lookup"><span data-stu-id="ada3e-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="ada3e-109">enteprise 管理者または IT Pro ではないが、一目でブロックに関する質問がある場合は、「Not an enterprise admin or [IT Pro?](#not-an-enterprise-admin-or-it-pro)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ada3e-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="ada3e-110">"一目でブロック" とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="ada3e-110">What is "block at first sight"?</span></span>

<span data-ttu-id="ada3e-111">一目でブロックする機能は、新しいマルウェアを検出し、数秒でブロックする次世代保護の脅威保護機能です。</span><span class="sxs-lookup"><span data-stu-id="ada3e-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="ada3e-112">特定のセキュリティ設定が有効になっている場合、一目でブロックが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ada3e-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="ada3e-113">これらの設定には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-113">These settings include:</span></span>

- <span data-ttu-id="ada3e-114">クラウドによる保護。</span><span class="sxs-lookup"><span data-stu-id="ada3e-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="ada3e-115">指定したサンプル送信タイムアウト (50 秒など)。そして</span><span class="sxs-lookup"><span data-stu-id="ada3e-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="ada3e-116">ファイルブロックレベルが高い。</span><span class="sxs-lookup"><span data-stu-id="ada3e-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="ada3e-117">ほとんどの企業組織では、ブロックを一目で有効にするために必要な設定は、Microsoft Defender Antivirus 展開で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="ada3e-118">しくみ</span><span class="sxs-lookup"><span data-stu-id="ada3e-118">How it works</span></span>

<span data-ttu-id="ada3e-119">Microsoft Defender Antivirus が疑わしいが検出されないファイルを検出すると、クラウド保護バックエンドに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="ada3e-120">クラウド バックエンドは、ファイルのヒューリスティック、機械学習、および自動分析を適用して、ファイルが悪意のあるファイルであるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="ada3e-121">Microsoft Defender Antivirus は、複数の検出および防止テクノロジを使用して、正確でインテリジェントでリアルタイムの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Microsoft Defender AV エンジンの一覧](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="ada3e-123">詳細については、このブログを参照してください。 Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジ [について説明します](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="ada3e-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="ada3e-124">一目でブロックについて知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ada3e-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="ada3e-125">Windows 10 バージョン 1803 以降では、一目でブロックすると、移植できない実行可能ファイル (JS、VBS、マクロなど) と実行可能ファイルをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="ada3e-126">一目でブロックすると、インターネットからダウンロードされた実行可能ファイル、またはインターネット ゾーンから発生するポータブルでない実行可能ファイルに対してクラウド保護バックエンドのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="ada3e-127">.exe ファイルのハッシュ値は、クラウド バックエンドを介してチェックされ、ファイルが以前に検出されていないファイルかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="ada3e-128">クラウド バックエンドが判断できない場合、Microsoft Defender Antivirus はファイルをロックし、コピーをクラウドにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="ada3e-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="ada3e-129">クラウドは、ファイルが悪意のあると判断したかどうかに応じて、ファイルを実行したり、すべての将来の遭遇でブロックしたりする前に、より多くの分析を実行して決定に到達します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="ada3e-130">多くの場合、このプロセスでは、新しいマルウェアの応答時間を数時間から数秒に短縮できます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="ada3e-131">クラウドベースの [保護サービスが](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) ファイルを分析する間、ファイルの実行を妨げる時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="ada3e-132">また、ファイル [がブロックされている場合に](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) ユーザーのデスクトップに表示されるメッセージをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="ada3e-133">会社名、連絡先情報、メッセージ URL を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="ada3e-134">Microsoft Intune で一目でブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="ada3e-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="ada3e-135">Microsoft Intune は、Microsoft エンドポイント マネージャーの一部です。</span><span class="sxs-lookup"><span data-stu-id="ada3e-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="ada3e-136">Microsoft Endpoint Manager 管理センター ( ) で、[ [https://endpoint.microsoft.com](https://endpoint.microsoft.com) デバイス構成 **プロファイル**  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="ada3e-137">[デバイス制限] プロファイルの種類を使用 **してプロファイルを選択または** 作成します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="ada3e-138">[デバイス制限 **プロファイルの** 構成設定] で **、[Microsoft Defender ウイルス** 対策] の下で次の設定を設定または確認します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="ada3e-139">**クラウド配信の保護**: 有効</span><span class="sxs-lookup"><span data-stu-id="ada3e-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="ada3e-140">**ファイル ブロック レベル**: 高</span><span class="sxs-lookup"><span data-stu-id="ada3e-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="ada3e-141">**クラウドによるファイル スキャンの** 時間の延長 : 50</span><span class="sxs-lookup"><span data-stu-id="ada3e-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="ada3e-142">**サンプル提出の前にユーザーに確認** する : プロンプトを表示せずにすべてのデータを送信する</span><span class="sxs-lookup"><span data-stu-id="ada3e-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune の構成](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="ada3e-144">設定内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="ada3e-145">ファイル ブロック レベルを High に設定 **すると** 、強力なレベルの検出が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="ada3e-146">万が一、ファイルブロックによって正当なファイルが誤検知された場合、セキュリティ運用チームは検疫済みファイル [を復元できます](./restore-quarantined-files-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ada3e-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="ada3e-147">Intune で Microsoft Defender ウイルス対策デバイスの制限を構成する方法の詳細については、「Configure device Restriction [settings in Microsoft Intune」を参照してください](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="ada3e-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="ada3e-148">Intune の Microsoft Defender ウイルス対策デバイスの制限の一覧については、「Intune の Windows 10 (以降) のデバイス制限 [」を参照してください](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="ada3e-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="ada3e-149">Microsoft Endpoint Manager で一目でブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="ada3e-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="ada3e-150">Microsoft Endpoint Configuration Manager を探している場合は、Microsoft エンドポイント マネージャーの一部です。</span><span class="sxs-lookup"><span data-stu-id="ada3e-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="ada3e-151">Microsoft Endpoint Manager ( ) で [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、[エンドポイント セキュリティ **ウイルス対策] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="ada3e-152">既存のポリシーを選択するか、Microsoft Defender ウイルス対策プロファイルの種類を使用して新 **しいポリシーを** 作成します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="ada3e-153">次の構成設定を設定または確認します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="ada3e-154">**クラウドによる保護を有効にする**: はい</span><span class="sxs-lookup"><span data-stu-id="ada3e-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="ada3e-155">**クラウドによって提供される保護レベル**: 高</span><span class="sxs-lookup"><span data-stu-id="ada3e-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="ada3e-156">**Defender Cloud Extended Timeout in Seconds**: 50</span><span class="sxs-lookup"><span data-stu-id="ada3e-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="エンドポイント マネージャーで一目で確認する設定をブロックする":::

4. <span data-ttu-id="ada3e-158">すべてのユーザー、すべてのデバイス、またはすべてのユーザーとデバイスなどのグループにMicrosoft Defender ウイルス対策プロファイル **を適用します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="ada3e-159">グループ ポリシーで一目でブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="ada3e-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="ada3e-160">Intune または Microsoft エンドポイント マネージャーを使用して、一目でブロックを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ada3e-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="ada3e-161">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="ada3e-162">グループ ポリシー **管理エディターを使用して、[\*\*\*\*コンピューターの構成] [** 管理用テンプレート  >    >  **] Windows コンポーネント Microsoft** Defender ウイルス対策マップ  >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="ada3e-163">[マップ] セクションで、[一目でブロックする] 機能を構成する **を** ダブルクリックし、[有効] に設定し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ada3e-164">常に **プロンプト (0) に設定すると** 、デバイスの保護状態が低下します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="ada3e-165">[送信 **しない] (2) に設定すると** 、一目でブロックが機能しません。</span><span class="sxs-lookup"><span data-stu-id="ada3e-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="ada3e-166">[マップ] セクションで、[詳細な分析が必要な場合にファイル サンプルを送信する] をダブルクリックし、[有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="ada3e-167">[詳細 **な分析が必要な場合にファイル サンプルを送信する] で、[** すべての **サンプルを送信** する] を選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="ada3e-168">グループ ポリシー オブジェクトを、通常と同じ方法でネットワーク全体に再展開します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="ada3e-169">個々のクライアント デバイスでブロックが一目で有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="ada3e-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="ada3e-170">Windows セキュリティ アプリを使用して、個々のクライアント デバイスでブロックが一目で有効になっているか確認できます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="ada3e-171">クラウド配信の保護と自動サンプル送信の両方が有効になっている限り、一目で **ブロックが自動的** に有効になります。</span><span class="sxs-lookup"><span data-stu-id="ada3e-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="ada3e-172">Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="ada3e-173">[ **ウイルス対策&脅威保護]** を選択し、[ウイルスの検出] の [脅威&の設定] で **、[設定の管理**] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows セキュリティ アプリの [ウイルス&保護設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="ada3e-175">クラウドによる **保護と自動** サンプル **送信の両方が** 有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="ada3e-176">前提条件の設定がグループ ポリシーを使用して構成および展開されている場合、このセクションで説明する設定はグレー表示され、個々のエンドポイントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="ada3e-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="ada3e-177">グループ ポリシー オブジェクトを使用して行った変更は、Windows の設定で設定を更新する前に、最初に個々のエンドポイントに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ada3e-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="ada3e-178">ブロックの一目での検証が機能している</span><span class="sxs-lookup"><span data-stu-id="ada3e-178">Validate block at first sight is working</span></span>

<span data-ttu-id="ada3e-179">機能が動作しているのを確認するには、「ネットワークとクラウド間の接続を検証する」 [のガイダンスに従います](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)。</span><span class="sxs-lookup"><span data-stu-id="ada3e-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="ada3e-180">一目でブロックをオフにする</span><span class="sxs-lookup"><span data-stu-id="ada3e-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="ada3e-181">ブロックを一目でオフにすると、デバイスとネットワークの保護状態が低下します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="ada3e-182">実際にブロックを一目で保護せずに前提条件の設定を保持する場合は、一目でブロックを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="ada3e-183">一時的にブロックをオフにし、この機能がネットワークに与える影響を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="ada3e-184">ただし、一目でブロックを完全に無効にすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="ada3e-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="ada3e-185">Microsoft Endpoint Manager でブロックを一目でオフにする</span><span class="sxs-lookup"><span data-stu-id="ada3e-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="ada3e-186">Microsoft Endpoint Manager 管理センター ( ) に移動 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="ada3e-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="ada3e-187">[エンドポイント セキュリティ **ウイルス対策**  >  **] に** 移動し、Microsoft Defender ウイルス対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="ada3e-188">[管理 **] で**、[プロパティ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="ada3e-189">[構成設定 **] の横にある**[編集] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="ada3e-190">次の設定の 1 つ以上を変更します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="ada3e-191">[ **クラウド配信の保護を有効にする] を** **[いいえ] または [構成** されていません **] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="ada3e-192">[ **クラウド配信の保護レベル] を [** 構成されていません **] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="ada3e-193">[Defender Cloud **Extended Timeout in seconds] のチェック ボックスをオフにします**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="ada3e-194">設定を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="ada3e-195">グループ ポリシーで一目でブロックをオフにする</span><span class="sxs-lookup"><span data-stu-id="ada3e-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="ada3e-196">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="ada3e-197">グループ ポリシー管理 **エディターを使用して、[** コンピューターの構成] **に移動し、[** 管理 **用テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="ada3e-198">Windows コンポーネントの Microsoft Defender ウイルス **対策**  >  マップを **通じてツリーを**  >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="ada3e-199">[一目 **でブロックする] 機能をダブルクリックし、** オプションを [無効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ada3e-200">一目でブロックを無効にしても、前提条件のグループ ポリシーは無効または変更されない。</span><span class="sxs-lookup"><span data-stu-id="ada3e-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="ada3e-201">エンタープライズ管理者または IT プロではありませんか?</span><span class="sxs-lookup"><span data-stu-id="ada3e-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="ada3e-202">エンタープライズ管理者または IT プロではないが、ブロックに関する質問がある場合は、このセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ada3e-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="ada3e-203">一目でブロックする機能は、数秒でマルウェアを検出してブロックする脅威保護機能です。</span><span class="sxs-lookup"><span data-stu-id="ada3e-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="ada3e-204">[一目でブロックする] という特定の設定は指定されていませんが、デバイスで特定の設定が構成されている場合、この機能は有効になります。</span><span class="sxs-lookup"><span data-stu-id="ada3e-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="ada3e-205">自分のデバイスで一目でブロックを管理する方法</span><span class="sxs-lookup"><span data-stu-id="ada3e-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="ada3e-206">組織によって管理されていない個人用デバイスがある場合は、一目でブロックをオンまたはオフにする方法について疑問に思う場合があります。</span><span class="sxs-lookup"><span data-stu-id="ada3e-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="ada3e-207">Windows セキュリティ アプリを使用して、一目でブロックを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="ada3e-208">Windows 10 コンピューターで、Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="ada3e-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="ada3e-209">[ **ウイルス対策&を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="ada3e-210">[ **ウイルス対策&の設定] で、[** 設定の管理 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="ada3e-211">次のいずれかの手順を選択します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="ada3e-212">一目でブロックを有効にするには、クラウド配信の保護と自動サンプル送信の **両方** が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ada3e-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="ada3e-213">一目でブロックを無効にするには、[クラウド配信の保護] または [自動サンプル **送信\*\*\*\*] をオフにします**。</span><span class="sxs-lookup"><span data-stu-id="ada3e-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="ada3e-214">ブロックを一目でオフにすると、デバイスの保護レベルが下がります。</span><span class="sxs-lookup"><span data-stu-id="ada3e-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="ada3e-215">一目でブロックを完全に無効にすることをお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="ada3e-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="ada3e-216">関連項目</span><span class="sxs-lookup"><span data-stu-id="ada3e-216">See also</span></span>

- [<span data-ttu-id="ada3e-217">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="ada3e-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="ada3e-218">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="ada3e-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ada3e-219">Windows セキュリティで保護された環境を保つ</span><span class="sxs-lookup"><span data-stu-id="ada3e-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)