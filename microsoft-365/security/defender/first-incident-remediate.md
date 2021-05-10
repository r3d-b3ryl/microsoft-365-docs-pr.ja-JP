---
title: 手順 2.  最初のインシデントを修復する
description: Defender で最初のインシデントを修復する方法をMicrosoft 365します。
keywords: インシデント、アラート、調査、相関関係、攻撃、コンピューター、デバイス、ユーザー、ID、メールボックス、電子メール、365、microsoft、m365、インシデント対応、サイバー攻撃
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ed597c55a646eb00d6e6d256c287b22c119f8148
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297346"
---
# <a name="step-2-remediate-your-first-incident"></a><span data-ttu-id="b9021-105">手順 2.</span><span class="sxs-lookup"><span data-stu-id="b9021-105">Step 2.</span></span> <span data-ttu-id="b9021-106">最初のインシデントを修復する</span><span class="sxs-lookup"><span data-stu-id="b9021-106">Remediate your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b9021-107">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b9021-107">**Applies to:**</span></span>
- <span data-ttu-id="b9021-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9021-108">Microsoft 365 Defender</span></span>

<span data-ttu-id="b9021-109">Microsoft 365Defender は、検出および分析機能を提供するだけでなく、マルウェアの格納と根絶も提供します。</span><span class="sxs-lookup"><span data-stu-id="b9021-109">Microsoft 365 Defender not only provides detection and analysis capabilities but also provides containment and eradication of malware.</span></span> <span data-ttu-id="b9021-110">Containment には、攻撃の影響を軽減する手順が含まれていますが、根絶によって、攻撃者のアクティビティのすべての痕跡がネットワークから削除されます。</span><span class="sxs-lookup"><span data-stu-id="b9021-110">Containment includes steps to reduce the impact of the attack while eradication ensures all traces of attacker activity are removed from the network.</span></span>  <span data-ttu-id="b9021-111">Microsoft 365Defender には、オペレーティング システムと攻撃の[](m365d-autoir.md)種類に応じて自動修復するように構成できる修復アクションがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="b9021-111">Microsoft 365 Defender offers several remediation actions which can be configured to [auto-remediate](m365d-autoir.md) depending on your operating system and the attack type.</span></span>

<span data-ttu-id="b9021-112">Microsoft 365Defender には、アナリストが手動で開始できる修復アクションがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="b9021-112">Microsoft 365 Defender offers several remediation actions that analysts can manually initiate.</span></span> <span data-ttu-id="b9021-113">アクションは、デバイス上のアクションとファイルのアクションという 2 つのカテゴリに分けられます。</span><span class="sxs-lookup"><span data-stu-id="b9021-113">Actions are separated into two categories, Actions on devices and Actions on files.</span></span> <span data-ttu-id="b9021-114">一部のアクションを使用して脅威を直ちに停止し、他のアクションはさらに法医学分析を支援します。</span><span class="sxs-lookup"><span data-stu-id="b9021-114">Some actions can be used to immediately stop the threat while other actions assist in further forensic analysis.</span></span>

## <a name="actions-on-devices"></a><span data-ttu-id="b9021-115">デバイスでのアクション</span><span class="sxs-lookup"><span data-stu-id="b9021-115">Actions on devices</span></span>

- <span data-ttu-id="b9021-116">**デバイスを分離** する - このアクティビティは、マルウェアの拡散を最小限に抑え、悪意のあるアクターが攻撃を続けることなく分析を継続するために、すべてのネットワーク トラフィック (インターネットと内部) を直ちにブロックします。</span><span class="sxs-lookup"><span data-stu-id="b9021-116">**Isolate the device** - This activity immediately blocks all network traffic (internet and internal) to minimize the spread of malware and allow analysts to continue analysis without a malicious actor being able to continue an attack.</span></span> <span data-ttu-id="b9021-117">許可される唯一の接続は、Microsoft Defender for Identity サービス クラウドへの接続なので、Microsoft Defender for Identity は引き続きデバイスを監視できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-117">The only connection allowed is to the Microsoft Defender for Identity service cloud so Microsoft Defender for Identity can continue to monitor the device.</span></span> 
- <span data-ttu-id="b9021-118">**アプリの実行を** 制限する - アプリケーションの実行を制限するために、Microsoft が発行した証明書によって署名されている場合にのみファイルを実行できるコード整合性ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b9021-118">**Restrict app execution** - To restrict an application from running, a code integrity policy is applied that only allows files to run if they are signed by a Microsoft-issued certificate.</span></span> <span data-ttu-id="b9021-119">この制限方法は、攻撃者が侵害されたデバイスを制御し、さらに悪意のあるアクティビティを実行するのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9021-119">This method of restriction can help prevent an attacker from controlling compromised devices and performing further malicious activities.</span></span>
- <span data-ttu-id="b9021-120">**[ウイルス対策スキャン** の実行] - Defender ウイルスMicrosoft Defender ウイルス対策がアクティブなウイルス対策ソリューションかどうかに関Microsoft Defender ウイルス対策、他のウイルス対策ソリューションと一緒にスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-120">**Run Antivirus scan** - A Microsoft Defender Antivirus scan can run alongside other antivirus solutions, whether Defender Antivirus is the active antivirus solution or not.</span></span> <span data-ttu-id="b9021-121">別のウイルス対策ベンダー製品がプライマリ エンドポイント保護ソリューションである場合は、パッシブ モードで Defender ウイルス対策を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-121">If another antivirus vendor product is the primary endpoint protection solution, you can run Defender Antivirus in Passive mode.</span></span>
- <span data-ttu-id="b9021-122">**自動調査を開始する** - デバイスで新しい汎用自動調査を開始できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-122">**Initiate automated investigation** - You can start a new general purpose automated investigation on the device.</span></span> <span data-ttu-id="b9021-123">調査の実行中、デバイスから生成された他のアラートは、その調査が完了するまで、継続的な自動調査に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b9021-123">While an investigation is running, any other alert generated from the device will be added to an ongoing automated investigation until that investigation is completed.</span></span> <span data-ttu-id="b9021-124">さらに、他のデバイスで同じ脅威が見られる場合は、それらのデバイスが調査に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b9021-124">In addition, if the same threat is seen on other devices, those devices are added to the investigation.</span></span>
- <span data-ttu-id="b9021-125">**ライブ応答の開始** - ライブ応答は、リモート シェル接続を使用してデバイスに瞬時にアクセスできる機能です。</span><span class="sxs-lookup"><span data-stu-id="b9021-125">**Initiate live response** - Live response is a capability that gives you instantaneous access to a device by using a remote shell connection.</span></span> <span data-ttu-id="b9021-126">これにより、詳細な調査作業を行い、迅速に特定された脅威をリアルタイムに含める即時対応アクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-126">This gives you the ability to do in-depth investigative work and take immediate response actions to promptly contain identified threats in real time.</span></span> <span data-ttu-id="b9021-127">ライブ応答は、法医学データの収集、スクリプトの実行、分析のための疑わしいエンティティの送信、脅威の修復、および新たな脅威の予防的な捜しを可能にすることで、調査を強化するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="b9021-127">Live response is designed to enhance investigations by enabling you to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span>
- <span data-ttu-id="b9021-128">**調査パッケージの収集** - 調査または対応プロセスの一環として、デバイスから調査パッケージを収集できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-128">**Collect investigation package** - As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="b9021-129">調査パッケージを収集することで、デバイスの現在の状態を特定し、攻撃者が使用するツールと手法をさらに理解できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-129">By collecting the investigation package, you can identify the current state of the device and further understand the tools and techniques used by the attacker.</span></span> 
- <span data-ttu-id="b9021-130">**脅威の専門家** に相談する (デバイスとファイルの両方のアクションで利用可能) - 既に侵害されている可能性のあるデバイスやデバイスに関する詳細な分析情報については、Microsoft の脅威専門家に問い合うことができます。</span><span class="sxs-lookup"><span data-stu-id="b9021-130">**Consult a threat expert** (available in both Actions on devices and files) - You can consult a Microsoft threat expert for more insights regarding potentially compromised devices or devices that are already compromised.</span></span> <span data-ttu-id="b9021-131">Microsoft の脅威の専門家は、迅速かつ正確な対応のために、Microsoft Defender セキュリティ センター内から直接関与できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-131">Microsoft threat experts can be engaged directly from within the Microsoft Defender Security Center for a timely and accurate response.</span></span> 

## <a name="actions-on-files"></a><span data-ttu-id="b9021-132">ファイルに対するアクション</span><span class="sxs-lookup"><span data-stu-id="b9021-132">Actions on files</span></span>

- <span data-ttu-id="b9021-133">**ファイルの停止と** 検疫 - このアクションには、実行中のプロセスの停止、ファイルの検疫、レジストリ キーなどの永続的なデータの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9021-133">**Stop and quarantine file** - This action includes stopping running processes, quarantining files, and deleting persistent data, such as any registry keys.</span></span> <span data-ttu-id="b9021-134">このアクションは、過去 30 日間Windows 10バージョン 1703 以降のデバイスで有効になります。</span><span class="sxs-lookup"><span data-stu-id="b9021-134">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span> 
- <span data-ttu-id="b9021-135">**ファイルをブロックまたは許可** するインジケーターを追加する - 悪意のある可能性のあるファイルやマルウェアの疑いを禁止することで、組織内の攻撃の伝播を防止します。</span><span class="sxs-lookup"><span data-stu-id="b9021-135">**Add indicators to block or allow file** - Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="b9021-136">この操作により、ファイルが組織内のデバイスで読み取り、書き込み、または実行されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="b9021-136">This operation will prevent the file from being read, written, or executed on devices in your organization.</span></span>
- <span data-ttu-id="b9021-137">**ファイルをダウンロードまたは収集** する – このアクションを使用すると、アナリストは、組織による詳細な分析のために、.zipで保護されたファイルをアーカイブ ファイルにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b9021-137">**Download or collect file** – This action allows analysts to download a file in a password protected .zip archive file for further analysis by the organization.</span></span>
- <span data-ttu-id="b9021-138">**深い分析** – このアクションは、セキュリティで保護された完全にインストルメント化されたクラウド環境でファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="b9021-138">**Deep analysis** – This action executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="b9021-139">詳細な分析結果は、ファイルのアクティビティ、観察された動作、およびドロップされたファイル、レジストリの変更、IP アドレスとの通信など、関連する成果物を示します。</span><span class="sxs-lookup"><span data-stu-id="b9021-139">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IP addresses.</span></span> 

<span data-ttu-id="b9021-140">「インシデントの検出、 [トリ](first-incident-analyze.md#analyze-your-first-incident)アージ、分析」の例を続けて、アナリストは次のアクションでこのインシデントを修復できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-140">Continuing the example in [Detect, triage, and analyze incidents](first-incident-analyze.md#analyze-your-first-incident), an analyst can remediate this incident with these actions:</span></span>

1. <span data-ttu-id="b9021-141">ユーザー アカウントのパスワードをすぐにリセットする</span><span class="sxs-lookup"><span data-stu-id="b9021-141">Immediately reset the user account password</span></span>
2. <span data-ttu-id="b9021-142">詳細な分析が完了するまでMicrosoft 365 Defender でデバイスを分離する</span><span class="sxs-lookup"><span data-stu-id="b9021-142">Isolate the device in Microsoft 365 Defender until deep analysis is complete</span></span>
3. <span data-ttu-id="b9021-143">悪意のあるファイルがウイルスから検疫されたSharePoint</span><span class="sxs-lookup"><span data-stu-id="b9021-143">Ensure the malicious file was quarantined from SharePoint</span></span>
4. <span data-ttu-id="b9021-144">マルウェアの影響を受けたエンドポイントを確認する</span><span class="sxs-lookup"><span data-stu-id="b9021-144">Check which endpoints were affected by malware</span></span>
5. <span data-ttu-id="b9021-145">システムの再構築</span><span class="sxs-lookup"><span data-stu-id="b9021-145">Rebuild systems</span></span>
6. <span data-ttu-id="b9021-146">他のユーザーに対Microsoft Cloud App Security同様のアラートを確認する</span><span class="sxs-lookup"><span data-stu-id="b9021-146">Check for similar Microsoft Cloud App Security alerts for other users</span></span>
7. <span data-ttu-id="b9021-147">Tor IP アドレスをブロックする Microsoft Defender for Endpoint でカスタム インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="b9021-147">Create a custom indicator in Microsoft Defender for Endpoint to block a Tor IP address</span></span>
8. <span data-ttu-id="b9021-148">次の図に示Microsoft Cloud App Securityのような、この種類のアラートのガバナンス アクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b9021-148">Create a governance action in Microsoft Cloud App Security for this type of alert such as those shown in the following image:</span></span>

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="ポータルでのガバナンス アクションMicrosoft Cloud App Security例"::: 
 
<span data-ttu-id="b9021-150">修復アクションの大部分は、Defender で適用および追跡Microsoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-150">Most of the remediation actions can be applied and tracked in Microsoft 365 Defender.</span></span> 

## <a name="using-playbooks"></a><span data-ttu-id="b9021-151">プレイブックの使用</span><span class="sxs-lookup"><span data-stu-id="b9021-151">Using Playbooks</span></span>

<span data-ttu-id="b9021-152">さらに、プレイブックを使用して自動修復を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9021-152">In addition, automated remediation can be created using playbooks.</span></span> <span data-ttu-id="b9021-153">現在、Microsoft には、[次のシナリオ](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks)GitHubプレイブックを提供する Playbook テンプレートがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="b9021-153">Currently, Microsoft has [Playbook templates on GitHub](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) that provide playbooks for the following scenarios:</span></span>

- <span data-ttu-id="b9021-154">ユーザー検証を要求した後、機密性の高いファイル共有を削除する</span><span class="sxs-lookup"><span data-stu-id="b9021-154">Remove sensitive file sharing after requesting user validation</span></span>
- <span data-ttu-id="b9021-155">まれな国の自動トリアージアラート</span><span class="sxs-lookup"><span data-stu-id="b9021-155">Auto-triage infrequent country alerts</span></span>
- <span data-ttu-id="b9021-156">アカウントを無効にする前にマネージャーアクションを要求する</span><span class="sxs-lookup"><span data-stu-id="b9021-156">Request for manager action before disabling an account</span></span>
- <span data-ttu-id="b9021-157">悪意のある受信トレイ ルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="b9021-157">Disable malicious inbox rules</span></span>

<span data-ttu-id="b9021-158">Playbooks は、Power Automateを使用して、特定の条件がトリガーされた後に特定のアクティビティを自動化するためのカスタムのロボット プロセスオートメーション フローを作成します。</span><span class="sxs-lookup"><span data-stu-id="b9021-158">Playbooks use Power Automate to create custom robotic process automation flows to automate certain activities once specific criteria have been triggered.</span></span> <span data-ttu-id="b9021-159">組織は、既存のテンプレートまたはゼロからプレイブックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b9021-159">Organizations can create playbooks either from existing templates or from scratch.</span></span> 

<span data-ttu-id="b9021-160">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b9021-160">Here's an example.</span></span>
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="カスタムのロボット プロセスPower Automateフローの例"::: 
 
<span data-ttu-id="b9021-162">また、インシデント後のレビュー中に[](first-incident-post.md)プレイブックを作成して、インシデントからの修復アクションを作成して、迅速な修復アクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b9021-162">Playbooks can also be created during [post-incident review](first-incident-post.md) to create remediation actions from incidents for faster remediation actions.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b9021-163">次の手順</span><span class="sxs-lookup"><span data-stu-id="b9021-163">Next step</span></span>

<span data-ttu-id="b9021-164">[![手順 3: インシデントのインシデント後レビューを実行する方法について学習する](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)</span><span class="sxs-lookup"><span data-stu-id="b9021-164">[![Step 3: Learn how to perform a post-incident review of an incident](../../media/first-incident-overview/first-incident-path-step3.png)](first-incident-post.md)</span></span>

<span data-ttu-id="b9021-165">インシデントのインシデント [後レビューを実行する方法について学習します](first-incident-post.md)。</span><span class="sxs-lookup"><span data-stu-id="b9021-165">Learn how to [perform a post-incident review of an incident](first-incident-post.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b9021-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9021-166">See also</span></span>

- [<span data-ttu-id="b9021-167">インシデントの概要</span><span class="sxs-lookup"><span data-stu-id="b9021-167">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b9021-168">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="b9021-168">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b9021-169">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="b9021-169">Manage incidents</span></span>](manage-incidents.md)
