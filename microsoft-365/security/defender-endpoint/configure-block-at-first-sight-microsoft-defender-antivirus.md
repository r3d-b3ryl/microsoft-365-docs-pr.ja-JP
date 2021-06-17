---
title: 事前ブロックを有効にして、マルウェアを数秒で検出する
description: 事前ブロック機能を有効にして、数秒以内にマルウェアを検出してブロックします。
keywords: スキャン、事前ブロック、マルウェア、事前、クラウド、ディフェンダー、アンチウイルス
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/15/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 3a5f766e21afcb29d3503345a49637061b5f0e38
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964702"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="e7cc4-104">事前ブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="e7cc4-104">Turn on block at first sight</span></span>

<span data-ttu-id="e7cc4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e7cc4-105">**Applies to:**</span></span>

- [<span data-ttu-id="e7cc4-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e7cc4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e7cc4-107">この記事では、"事前ブロック" と呼ばれるウイルス対策/マルウェア対策機能について説明し、組織で事前ブロックを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="e7cc4-108">この記事は、組織のセキュリティ設定を管理するエンタープライズ管理者および IT プロフェッショナルを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="e7cc4-109">エンタープライズ管理者や IT プロではないが、事前ブロックについて質問がある場合は、「[Not an enterprise admin or IT Pro? (エンタープライズ管理者またはITプロではありませんか?)](#not-an-enterprise-admin-or-it-pro)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="e7cc4-110">"事前ブロック" とは？</span><span class="sxs-lookup"><span data-stu-id="e7cc4-110">What is "block at first sight"?</span></span>

<span data-ttu-id="e7cc4-111">事前ブロックは、数秒以内に新しいマルウェアを検出してブロックするための方法を提供する次世代の保護機能です。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="e7cc4-112">特定のセキュリティ設定が有効になっている場合、事前ブロックが有効になります。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="e7cc4-113">これには、以下の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-113">These settings include:</span></span>

- <span data-ttu-id="e7cc4-114">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="e7cc4-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="e7cc4-115">指定されたサンプル送信タイムアウト (50 秒など) そして、</span><span class="sxs-lookup"><span data-stu-id="e7cc4-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="e7cc4-116">高のファイルブロックレベル。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="e7cc4-117">ほとんどの企業組織では、事前ブロックを有効にするために必要な設定は、Microsoft Defender ウイルス対策の展開で構成されています。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="e7cc4-118">メカニズム</span><span class="sxs-lookup"><span data-stu-id="e7cc4-118">How it works</span></span>

<span data-ttu-id="e7cc4-119">Microsoft Defender ウイルス対策 は、疑わしいが検出されていないファイルを検出すると、クラウド保護バックエンドにクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="e7cc4-120">クラウド バックエンドでは、ヒューリスティックな機械学習による自動化されたファイル分析を適用して、悪意のあるファイルか、脅威ではないファイルかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="e7cc4-121">Microsoft Defender ウイルス対策は、複数の検出および防止テクノロジを使用して、正確でインテリジェントなリアルタイムの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Microsoft Defender AV エンジンのリスト](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="e7cc4-123">詳細については、ブログ記事「[Microsoft Defender for Endpoint の次世代保護の中核となる高度なテクノロジについて」](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="e7cc4-124">事前ブロックについて知っておくべきいくつかのこと</span><span class="sxs-lookup"><span data-stu-id="e7cc4-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="e7cc4-125">Windows 10 バージョン 1803 以降では、事前ブロックを実行すると、移植性のない実行可能ファイル (JS、VBS、マクロなど) と実行可能ファイルをブロックすることがあります。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="e7cc4-126">事前ブロックでは、インターネットからダウンロードされた、またはインターネット ゾーンで発生した実行可能ファイルおよび非ポータブルの実行可能ファイルに対し、クラウド保護バックエンドのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="e7cc4-127">.exe ファイルのハッシュ値は、クラウド バックエンドを介してチェックされ、ファイルが以前に検出されなかったファイルであるかどうかが判断されます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="e7cc4-128">クラウド バックエンドで判断できない場合、Microsoft Defender ウイルス対策によってファイルがロックされ、ファイルのコピーがクラウドにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="e7cc4-129">クラウドでさらに分析が実行されて判断が下された後は、そのファイルが危険か脅威でないかの判断に応じて、それ以降そのファイルの実行がすべて許可されるか、すべてブロックされます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="e7cc4-130">多くの場合、このプロセスによって、従来数時間かかっていた新しいマルウェアへの対応時間が数秒に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="e7cc4-131">クラウドベースの保護サービスによってファイルを分析する間、[ファイルが実行されないように抑制する時間の長さを指定する](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="e7cc4-132">また、ファイルがブロックされたときに[ユーザーのデスクトップに表示されるメッセージをカスタマイズする](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="e7cc4-133">会社名、連絡先情報、メッセージの URL を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="e7cc4-134">Microsoft Intune で事前ブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="e7cc4-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="e7cc4-135">Microsoft Intune (現在は、Microsoft Endpoint Manager の一部)。.</span><span class="sxs-lookup"><span data-stu-id="e7cc4-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="e7cc4-136">Microsoft Endpoint Manager管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) で、**[デバイス]** > **[構成プロファイル]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="e7cc4-137">**[デバイス制限]** プロファイル タイプを使用してプロファイルを選択または作成します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="e7cc4-138">[デバイス制限プロファイル] の **[構成設定]** で、**Microsoft Defender ウイルス対策** の次の設定を設定または確認します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="e7cc4-139">**クラウドによる保護**: 有効</span><span class="sxs-lookup"><span data-stu-id="e7cc4-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="e7cc4-140">**ファイル ブロック レベル**: 高</span><span class="sxs-lookup"><span data-stu-id="e7cc4-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="e7cc4-141">**クラウドによるファイル スキャンの時間延長**: 50</span><span class="sxs-lookup"><span data-stu-id="e7cc4-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="e7cc4-142">**サンプルを送信する前にユーザーに確認メッセージを表示する**: 確認メッセージを表示せずにすべてのデータを送信する</span><span class="sxs-lookup"><span data-stu-id="e7cc4-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune 構成](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="e7cc4-144">設定内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="e7cc4-145">ファイルのブロック レベルを **[高]** に設定すると、強力な検出レベルが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="e7cc4-146">万一、ファイルのブロックによって正当なファイルが誤検出された場合、セキュリティ運用チームは[隔離されたファイルを復元](./restore-quarantined-files-microsoft-defender-antivirus.md)できます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="e7cc4-147">Intune での ≈ Defender ウイルス対策のデバイスの制限の構成について詳しくは、「[Microsoft Intune でデバイスの制限設定を構成する](/intune/device-restrictions-configure)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="e7cc4-148">Intune での Microsoft Defender ウイルス対策のデバイスの制限の一覧については、「[Intune を使用して機能を許可または制限するように Windows 10 (以降) のデバイスを設定する](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="e7cc4-149">Microsoft Endpoint Manager で事前ブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="e7cc4-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="e7cc4-150">Microsoft Endpoint Configuration Manager をお探しであれば、こちらは現在 Microsoft Endpoint Manager の一部になっています。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="e7cc4-151">Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) で、**[Endpoint security]** > **[Antivirus]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="e7cc4-152">既存のポリシーを選択するか、**Microsoft Defender ウイルス対策** のプロファイル タイプを使用して新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="e7cc4-153">次の構成設定を設定または確認します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="e7cc4-154">**クラウドによる保護を有効にする**: はい</span><span class="sxs-lookup"><span data-stu-id="e7cc4-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="e7cc4-155">**クラウドによる保護レベル**: 高</span><span class="sxs-lookup"><span data-stu-id="e7cc4-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="e7cc4-156">**Defender クラウドの延長タイムアウト (秒単位)**: 50</span><span class="sxs-lookup"><span data-stu-id="e7cc4-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="EndpointManagerでの事前ブロックの設定":::

4. <span data-ttu-id="e7cc4-158">Microsoft Defender ウイルス対策のプロファイルを、**[すべてのユーザー]**、**[すべてのデバイス]**、または **[すべてのユーザーとデバイス]** などのグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="e7cc4-159">グループポリシーで事前ブロックを有効にする</span><span class="sxs-lookup"><span data-stu-id="e7cc4-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="e7cc4-160">Intune または Microsoft Endpoint Manager を使用して、事前ブロックを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="e7cc4-161">グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="e7cc4-162">**[グループ ポリシー管理エディター]** を使用して、**[コンピューターの構成]** > **[管理用テンプレート]** > **[Windows コンポーネント]** > **[Microsoft Defender ウイルス対策** > **][MAPS]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="e7cc4-163">[MAPS] セクションで、**[事前ブロックを構成する] 機能** をダブルクリックし、**[有効]** に設定して、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e7cc4-164">**[常に確認する] (0)** に設定すると、デバイスの保護状態が低下します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="e7cc4-165">**[送信しない] (2)** に設定すると、事前ブロックが動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="e7cc4-166">[MAPS] セクションで、**[詳細な分析が必要な場合はファイルのサンプルを送信する]** をダブルクリックし、**[有効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="e7cc4-167">**[詳細な分析が必要な場合はファイルのサンプルを送信する]** で、**[すべてのサンプルを送信]** を選択し、**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="e7cc4-168">通常どおり、ネットワーク全体にグループ ポリシー オブジェクトを再展開します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="e7cc4-169">個別のクライアント デバイスで事前ブロックが有効であることを確認する</span><span class="sxs-lookup"><span data-stu-id="e7cc4-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="e7cc4-170">Windows セキュリティ アプリを使用して、個々のクライアント デバイスで事前ブロックが有効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="e7cc4-171">事前ブロックは、**[クラウドベースの保護]** と **[サンプルの自動送信]** の両方が有効になっている限り、自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="e7cc4-172">Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="e7cc4-173">**[ウイルスと脅威保護]** を選択し、**[ウイルスと脅威保護設定]** で **[設定の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows セキュリティ アプリの [ウイルスと脅威の防止の設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="e7cc4-175">**[クラウドベースの保護]** と **[サンプルの自動送信]** がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="e7cc4-176">前提条件の設定が構成され、グループ ポリシーを使って展開されている場合、このセクションで説明する設定は灰色表示され、個別のエンドポイントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="e7cc4-177">グループ ポリシーを使った変更は、Windows の設定で設定を更新する前に、最初に個別のエンドポイントに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="e7cc4-178">事前ブロックが機能していることを検証する</span><span class="sxs-lookup"><span data-stu-id="e7cc4-178">Validate block at first sight is working</span></span>

<span data-ttu-id="e7cc4-179">この機能が機能していることを検証するには、[事前ブロックのサンプル ファイル](https://demo.wd.microsoft.com/Page/BAFS)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="e7cc4-180">ファイルをダウンロードするには、セキュリティ管理者ロールまたはグローバル管理者ロールが割り当てられている Azure AD のアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="e7cc4-181">機能が機能していることを検証するには、「[ネットワークとクラウド間の接続を検証する](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)」のガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="e7cc4-182">事前ブロックを無効にする</span><span class="sxs-lookup"><span data-stu-id="e7cc4-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="e7cc4-183">事前ブロックを無効にすると、デバイスとネットワークの保護状態が低下します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="e7cc4-184">事前ブロック保護を使用しないで、実際に前提条件の設定を保持する場合は、事前ブロックを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="e7cc4-185">この機能がネットワークにどのように影響するかを確認するために、一時的に事前ブロックをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="e7cc4-186">ただし、事前ブロックを完全に無効にすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="e7cc4-187">Microsoft Endpoint Manager で事前ブロックを無効にする</span><span class="sxs-lookup"><span data-stu-id="e7cc4-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="e7cc4-188">Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動してサイン インします。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="e7cc4-189">**[エンドポイント セキュリティ]** > **[ウイルス対策]** に移動し、Microsoft Defender ウイルス対策ポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="e7cc4-190">[**管理**] で [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="e7cc4-191">**[構成の設定]** の横にある **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="e7cc4-192">次の設定の 1 つ以上を変更します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="e7cc4-193">**[クラウドで配信される保護を有効にする]** を **[いいえ]** または **[未構成]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="e7cc4-194">**[クラウド配信の保護レベル]** を **[未構成]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="e7cc4-195">**Defender クラウドの延長タイムアウト (秒単位)** のチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="e7cc4-196">設定を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="e7cc4-197">グループ ポリシーで事前ブロックを無効にする</span><span class="sxs-lookup"><span data-stu-id="e7cc4-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="e7cc4-198">グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="e7cc4-199">**[グループ ポリシー管理エディター]** を使用して、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="e7cc4-200">**[Windows コンポーネント]** > **[Microsoft Defender ウイルス対策]** > **[MAPS]** の順にツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="e7cc4-201">**['事前ブロック' 機能を構成する]** をダブルクリックして、オプションを **[無効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7cc4-202">事前ブロックを無効にしても、前提条件のグループ ポリシーが無効になったり変更されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="e7cc4-203">エンタープライズ管理者でも IT プロでもありませんか?</span><span class="sxs-lookup"><span data-stu-id="e7cc4-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="e7cc4-204">エンタープライズ管理者でも IT Pro でもないが、事前ブロックについて質問がある場合は、このセクションが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="e7cc4-205">事前ブロックするは、マルウェアを数秒以内に検出してブロックする脅威保護機能です。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="e7cc4-206">「事前ブロック」と呼ばれる特定の設定はありませんが、デバイスで特定の設定が構成されている場合、この機能は有効になります。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="e7cc4-207">自分のデバイスで事前ブロックをオンまたはオフに管理する方法</span><span class="sxs-lookup"><span data-stu-id="e7cc4-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="e7cc4-208">組織によって管理されていない個人用デバイスを使用している場合、事前ブロックを有効または無効にする方法を疑問に思うかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="e7cc4-209">Windows　セキュリティ　アプリを使用して、事前ブロックを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="e7cc4-210">Windows 10 コンピューターで、Windows セキュリティ アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="e7cc4-211">**[ウイルスと脅威の防止]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="e7cc4-212">**[ウイルスと脅威保護設定]** で **[設定の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="e7cc4-213">次のいずれかの手順を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="e7cc4-214">事前ブロックを有効にするには、**[クラウドベースの保護]** と **[サンプルの自動送信]** の両方がオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="e7cc4-215">事前ブロックを無効にするには、**[クラウドベースの保護]** と **[サンプルの自動送信]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="e7cc4-216">事前ブロックをオフにすると、デバイスの保護レベルが低下します。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="e7cc4-217">事前ブロックを完全に無効にすることはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e7cc4-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="e7cc4-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7cc4-218">See also</span></span>

- [<span data-ttu-id="e7cc4-219">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="e7cc4-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="e7cc4-220">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="e7cc4-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e7cc4-221">Windows セキュリティで保護を継続する</span><span class="sxs-lookup"><span data-stu-id="e7cc4-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
